![](media/file0.png)

1.  [Title Page](text/title_page.xhtml)
2.  [Cover](text/cover.xhtml)
3.  [Table of Contents](#nav.xhtml_toc)

# Chapter 1: Introduction - Code Unification

**Based on:** JBCT v2.1.0 | **Pragmatica Lite Core:** 0.9.9

## What You’ll Learn

*   Why code unification matters in the AI era
*   The problems JBCT solves
*   The five evaluation criteria for design decisions
*   Foundational concepts: side effects, composition, monads

**Prerequisites:** Mid-/senior Java developers comfortable with Java 21+ features (records, sealed interfaces, pattern matching), lambdas, generics, and basic functional patterns.

* * *

## Code in a New Era

Software development is changing faster than ever. AI-powered code generation tools have moved from experimental novelty to daily workflow staple in just a few years. We now write code alongside - and increasingly with - intelligent assistants that can generate entire functions, refactor modules, and suggest architectural patterns. This shift creates new challenges that traditional coding practices weren’t designed to handle.

Historically, code has carried a heavy burden of personal style. Every developer brings preferences about naming, structure, error handling, and abstraction. Teams spend countless hours in code review debating subjective choices. Style guides help, but they can’t capture the deeper structural decisions that make code readable or maintainable. When AI generates code, it inherits these same inconsistencies - we just don’t know whose preferences it’s channeling or why it made particular choices.

This creates a context problem. When you read AI-generated code, you’re reverse-engineering decisions made by a model trained on millions of examples with conflicting styles. When AI reads your code to suggest changes, it must infer your intentions from structure that may not clearly express them. The cognitive overhead compounds: developers burn mental cycles translating between their mental model, the code’s structure, and what the AI “thinks” the code means.

Meanwhile, technical debt accumulates silently. Small deviations from good structure - a validation check here, an exception there, a bit of mixed abstraction levels - seem harmless in isolation. But they compound. Refactoring becomes risky. Testing becomes difficult. The codebase becomes a collection of special cases rather than a coherent system.

> Traditional approaches don’t provide clear, mechanical rules for when to refactor or how to structure new code, so these decisions remain subjective and inconsistent.

* * *

## The JBCT Approach

**Java Backend Coding Technology (JBCT)** proposes a different approach: **reduce the space of valid choices until there’s essentially one good way to do most things**. Not through rigid frameworks or heavy ceremony, but through a small set of rules that make structure predictable, refactoring mechanical, and business logic clearly separated from technical concerns.

The benefits compound:

**Unified structure** means humans can read AI-generated code without guessing about hidden assumptions, and AI can read human code without inferring structure from context. A use case looks the same whether you wrote it, your colleague wrote it, or an AI assistant generated it. The structure carries the intent.

**Minimal technical debt** emerges naturally because refactoring rules are built into the methodology. When a function grows beyond one clear responsibility, the rules tell you exactly how to split it. When a component gets reused, there’s one obvious place to move it. Debt doesn’t accumulate because prevention is cheaper than cleanup.

**Close business modeling** happens when you’re not fighting technical noise. Value objects enforce domain invariants at construction time. Use cases read like business processes because each step does one thing. Errors are domain concepts, not stack traces. Product owners can read the code structure and recognize their requirements.

**Requirement discovery** becomes systematic. When you structure code as validation → steps → composition, gaps become obvious. Missing validation rules surface when you define value objects. Unclear business logic reveals itself when you can’t name a step clearly. Edge cases emerge when you model errors as explicit types.

**Business logic as a readable language** happens when patterns become vocabulary. The four return types, parse-don’t-validate, and the fixed pattern catalog form a consistent way to express domain concepts in code. Anyone who understands the domain can pick up a new codebase virtually instantly.

**Deterministic code generation** becomes possible when the mapping from requirements to code is mechanical. Given a use case specification - inputs, outputs, validation rules, steps - there’s essentially one correct structure. Different developers (or AI assistants) should produce nearly identical implementations.

> **A Broader Movement:** JBCT is not alone in pursuing compile-time guarantees and type-driven design. Similar philosophies appear in database design (7NF type-first approaches), distributed systems, and functional programming communities. The common thread: shift errors from runtime to compile-time, make invalid states unrepresentable, and reduce cognitive load through explicit contracts.

* * *

## The Five Evaluation Criteria

Before diving into patterns, understand how we evaluate every decision in JBCT. Traditional “best practices” rely on subjective “readability” - but what does that mean? JBCT uses five objective criteria:

1.  **Mental Overhead** - “Don’t forget to…” and “Keep in mind…” items you must track. Lower is better.

2.  **Business/Technical Ratio** - Domain concepts vs framework/infrastructure noise. Higher domain visibility is better.

3.  **Design Impact** - Does an approach enforce good patterns or allow bad ones? Improves consistency or breaks it?

4.  **Reliability** - Does the compiler catch mistakes, or must you remember? Type safety eliminates bug classes.

5.  **Complexity** - Number of elements, connections, and hidden coupling. Fewer moving parts are better.

These aren’t preferences - they’re measurable. When we say “don’t use business exceptions,” we prove it: - **Mental Overhead**: Checked exceptions pollute signatures; unchecked are invisible (+2 for Result) - **Reliability**: Exceptions bypass type checker; Result makes failures explicit (+1 for Result) - **Complexity**: Exception hierarchies create coupling (+1 for Result)

### Example: Applying the Criteria

**Question:** Should we use `@Transactional` annotation or explicit transaction management in use cases?

**Analysis using the five criteria:**

1.  **Mental Overhead:**
    *   `@Transactional`: Invisible behavior - must remember that methods run in transactions, requires understanding proxy mechanics
    *   Explicit: Transaction boundaries are visible in code
    *   **Score: +2 for explicit**
2.  **Business/Technical Ratio:**
    *   Both approaches are technical infrastructure
    *   **Score: 0** (neutral)
3.  **Design Impact:**
    *   `@Transactional`: Couples business logic to Spring framework
    *   Explicit: Business logic stays framework-agnostic
    *   **Score: +2 for explicit**
4.  **Reliability:**
    *   `@Transactional`: Fails silently in some cases (private methods, self-invocation)
    *   Explicit: Compiler errors if you forget transaction handling
    *   **Score: +1 for explicit**
5.  **Complexity:**
    *   `@Transactional`: Hidden control flow
    *   Explicit: Control flow is visible
    *   **Score: +1 for explicit**

**Verdict: Use explicit transaction management (Aspect pattern)** - Total: +6 points for explicit

This is how every decision in JBCT is made—not based on opinion, but on measurable impact across five dimensions.

* * *

## Foundational Concepts

### What Are Side Effects?

A **side effect** is anything a function does beyond computing and returning a value:

*   Writing to a database
*   Making an HTTP call
*   Writing to a file
*   Printing to console
*   Modifying a global variable
*   Throwing an exception

**Pure function** (no side effects):

```
[](#cb1-1)public int add(int a, int b) {
[](#cb1-2)    return a + b;  // Only computes and returns
[](#cb1-3)}
```

**Impure function** (has side effects):

```
[](#cb2-1)public void saveUser(User user) {
[](#cb2-2)    database.save(user);  // Side effect: modifies external state
[](#cb2-3)    logger.info("User saved");  // Side effect: writes to log
[](#cb2-4)}
```

Why care? **Pure functions are predictable**: same inputs always produce same output. They’re easy to test (no mocking needed) and safe to run anywhere, anytime.

**Impure functions are necessary** - your app must interact with the world - but they’re **unpredictable**: network might fail, disk might be full, database might be down.

JBCT’s approach: **push side effects to the edges**. Keep business logic pure. Isolate impure operations in adapter leaves. This makes your core logic easy to test and reason about.

### What Is Composition?

**Composition** means building complex operations by combining simpler ones.

Traditional imperative style:

```
[](#cb3-1)public String processUser(String email) {
[](#cb3-2)    String trimmed = email.trim();
[](#cb3-3)    String lowercase = trimmed.toLowerCase();
[](#cb3-4)    String validated = validate(lowercase);
[](#cb3-5)    String saved = save(validated);
[](#cb3-6)    return saved;
[](#cb3-7)}
```

Functional composition:

```
[](#cb4-1)public Result<String> processUser(String email) {
[](#cb4-2)    return Result.success(email)
[](#cb4-3)                 .map(String::trim)
[](#cb4-4)                 .map(String::toLowerCase)
[](#cb4-5)                 .flatMap(this::validate)
[](#cb4-6)                 .flatMap(this::save);
[](#cb4-7)}
```

The second version **chains** operations. Each step takes the output of the previous step as input. The data flows through a pipeline.

Why this matters: composition lets you **build complex logic from simple pieces** without intermediate variables or explicit error checking at each step. The structure itself handles error propagation.

### What Are Monads (Smart Wrappers)?

In JBCT, we use types that wrap values and control how operations are applied to them.

> **Note:** In functional programming, these are called *monads*. This book uses both terms - “Smart Wrapper” for intuition, “monad” for precision.

**A monad controls when and if your operations run.**

#### The Key Insight: Inversion of Control

Traditional code: **you** decide when to do something. Monad code: **the monad** decides when to do something.

Think: “Do this operation, **if/when the value is available**.”

```
[](#cb5-1)// Traditional: YOU check, YOU decide
[](#cb5-2)String result;
[](#cb5-3)if (email != null) {
[](#cb5-4)    String trimmed = email.trim();
[](#cb5-5)    if (isValid(trimmed)) {
[](#cb5-6)        result = save(trimmed);
[](#cb5-7)        if (result == null) {
[](#cb5-8)            // Error: save failed
[](#cb5-9)        }
[](#cb5-10)    } else {
[](#cb5-11)        // Error: invalid
[](#cb5-12)    }
[](#cb5-13)} else {
[](#cb5-14)    // Error: null input
[](#cb5-15)}
[](#cb5-16)
[](#cb5-17)// Monad: WRAPPER checks, WRAPPER decides
[](#cb5-18)Result<String> result = Result.success(email)
[](#cb5-19)                              .map(String::trim)
[](#cb5-20)                              .flatMap(this::validate)
[](#cb5-21)                              .flatMap(this::save);
```

You’re saying: “Here’s what to do with the value… **if** you have one and **when** you’re ready.”

The monad decides: - **Option**: “I’ll apply your operation **if** the value is present” - **Result**: “I’ll apply your operation **if** there’s no error so far” - **Promise**: “I’ll apply your operation **when** the async result arrives”

Each monad has: - **map**: “Transform the value, if/when available” - **flatMap**: “Chain another operation, if/when the current one succeeds”

### Pragmatic, Not Pure

JBCT uses *pragmatic* monads. Monad laws are not required. Purity is not a goal. **Predictability is.**

We borrow functional patterns because they make code more predictable and composable, not because we’re pursuing theoretical purity. Side effects happen. I/O is necessary. The goal is to make side effects *explicit* and *isolated*, not to eliminate them.

If you’re coming from Haskell or Scala, adjust your expectations: this is practical Java, not academic FP.

### Immutability

All input data passed to operations must be treated as immutable and read-only. This isn’t about dogmatic functional purity - it’s about maintaining safety guarantees that make concurrent code predictable.

**What MUST be immutable:** - Data passed between parallel operations (Fork-Join pattern) - Input parameters to any operation - Response types returned from use cases - Value objects used as map keys or in collections

**What CAN be mutable (thread-confined):** - Local state within single operation (accumulators, builders) - Working objects within adapter boundaries - State confined to sequential patterns

**Key principle:** Mutability is safe when state is **thread-confined** (accessed by single thread). Parallel patterns require immutable inputs because no isolation exists.

* * *

## Who Should Use JBCT?

**You should use this if:** - You’re building backend services (REST APIs, microservices, batch processors) - You want code that’s easy for new team members to understand - You’re working with AI coding assistants and want generated code to match your structure - You value testability and want to minimize mocking - You’re tired of architectural debates and want mechanical rules

**This might not fit if:** - You’re building UI applications (different concerns, different patterns) - You need extreme performance optimization (some abstraction overhead) - Your team is heavily invested in a conflicting architecture - You prefer object-oriented design with mutable state

* * *

## Key Takeaways

1.  **JBCT unifies code** - Making code predictable across teams and AI collaboration
2.  **Five criteria** guide all decisions - Mental overhead, business/technical ratio, design impact, reliability, complexity
3.  **Side effects at edges** - Keep business logic pure, isolate I/O in adapters
4.  **Composition over imperative** - Chain operations, let structure handle errors
5.  **Monads invert control** - You describe transformations, the monad handles execution

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 1.1: Return Type Selection - Exercise 1.2: Option vs Result

* * *

## What’s Next

[Chapter 2](ch02-four-return-types.md) introduces the four return types that form the foundation of everything else: `T`, `Option<T>`, `Result<T>`, and `Promise<T>`. You’ll learn when to use each one, how they compose, and why these four types are all you need.

# Chapter 2: The Four Return Types

## What You’ll Learn

*   Why exactly four return types are sufficient
*   When to use each type: T, Option, Result, Promise
*   How to convert between types
*   Why Java’s standard library isn’t enough

* * *

## Overview

Every function in JBCT returns exactly one of four types. Not “usually” or “preferably”—exactly one, always. This isn’t an arbitrary restriction; it’s intentional compression of complexity into type signatures.

**Why by criteria:** - **Mental Overhead**: Hidden error channels (exceptions), hidden optionality (null), hidden asynchrony (blocking I/O) force remembering behavior not in signatures. Explicit types eliminate this (+3). - **Reliability**: Compiler verifies error handling, null safety, and async boundaries when encoded in types (+3). - **Complexity**: Four types cover all scenarios - no guessing about combinations (+2).

* * *

## T - Synchronous, Cannot Fail, Always Present

Use this when the operation is pure computation with no possibility of failure or missing data. Mathematical calculations, transformations of valid data, simple getters. If you can’t think of a way this function could fail or return nothing, it returns `T`.

```
[](#cb6-1)public record FullName(String value) {
[](#cb6-2)    public String initials() {  // returns String (T)
[](#cb6-3)        return value.chars()
[](#cb6-4)                    .filter(Character::isUpperCase)
[](#cb6-5)                    .collect(StringBuilder::new,
[](#cb6-6)                             StringBuilder::appendCodePoint,
[](#cb6-7)                             StringBuilder::append)
[](#cb6-8)                    .toString();
[](#cb6-9)    }
[](#cb6-10)}
```

The signature `String initials()` tells you: this always succeeds, always returns a value, completes immediately.

**Return `T` when:** - Pure computation (e.g., `calculateTotal`, `formatCurrency`) - Transformation of already-valid data (e.g., `toUpperCase`, `extractId`) - Getters for required fields (e.g., `user.email()`, `order.total()`)

* * *

## `Option<T>` - Synchronous, Cannot Fail, May Be Missing

Use this when absence is a valid outcome but failure isn’t possible. Lookups that might not find anything, optional configuration, nullable database columns when null is semantically meaningful. The key: missing data is normal business behavior, not an error.

```
[](#cb7-1)public interface PreferenceRepository {
[](#cb7-2)    Option<Theme> findThemePreference(UserId id);  // might not be set
[](#cb7-3)}
```

The signature `Option<Theme>` tells you: this always succeeds, but the value might be absent. The caller must handle both cases.

**Return `Option<T>` when:** - Lookup might not find anything (e.g., `findByUsername`) - Field is genuinely optional in the domain (e.g., `user.middleName()`) - “Not found” is a normal outcome, not an error

* * *

## `Result<T>` - Synchronous, Can Fail, Business/Validation Errors

Use this when an operation might fail for business or validation reasons. Parsing input, enforcing invariants, business rules that can be violated. Failures are represented as typed `Cause` objects, not exceptions.

> **Note:** `Cause` represents domain failures or error reasons. Think of it as “FailureReason” or “DomainError”—the typed representation of why a business operation failed.

```
[](#cb8-1)public record Email(String value) {
[](#cb8-2)    private static final Pattern EMAIL_PATTERN =
[](#cb8-3)        Pattern.compile("^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$");
[](#cb8-4)    private static final Fn1<Cause, String> INVALID_EMAIL =
[](#cb8-5)        Causes.forOneValue("Invalid email format: %s");
[](#cb8-6)
[](#cb8-7)    public static Result<Email> email(String raw) {
[](#cb8-8)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb8-9)                     .map(String::trim)
[](#cb8-10)                     .filter(INVALID_EMAIL, EMAIL_PATTERN.asMatchPredicate())
[](#cb8-11)                     .map(Email::new);
[](#cb8-12)    }
[](#cb8-13)}
```

The signature `Result<Email>` tells you: this might fail (invalid format), completes immediately, failure is typed.

**Return `Result<T>` when:** - Validating input (e.g., `Email.email(raw)`) - Enforcing business rules (e.g., `checkInvariant`) - Parsing or constructing domain objects (e.g., `OrderId.orderId(raw)`)

> **Why Result: Error Handling Philosophy**
> 
> Error handling logic belongs where business context exists to make decisions. Sometimes that’s close to where the error occurred; sometimes the error propagates unchanged because only the caller has enough context to decide.
> 
> Different mechanisms have distinct trade-offs:
> 
> | Mechanism | Transparency | Ergonomics | Reliability |
> | --- | --- | --- | --- |
> | **Checked exceptions** | ✅ Explicit | ❌ Verbose, coupling | ✅ Compiler-enforced |
> | **Unchecked exceptions** | ❌ Hidden | ⚠️ Mental overhead | ❌ Silent failures |
> | **Errors as values** (Go) | ✅ Visible | ❌ Manual propagation | ❌ Easy to ignore |
> | **Functional (Result)** | ✅ In type | ✅ Monadic composition | ✅ Compiler-enforced |
> 
> `Result<T>` combines the best: explicit in signature, ergonomic via `map`/`flatMap`, compiler-verified handling.

* * *

## `Promise<T>` - Asynchronous, Can Fail

Use this for any I/O operation, external service call, or computation that might block. `Promise<T>` is semantically equivalent to `Result<T>` but asynchronous - failures are carried in the Promise itself, not nested inside it.

```
[](#cb9-1)public interface AccountRepository {
[](#cb9-2)    Promise<Account> findById(AccountId id);  // async lookup, can fail
[](#cb9-3)}
```

The signature `Promise<Account>` tells you: this completes later (async), might fail (network, database), failure is carried in the Promise.

> **Promise as Async Result**
> 
> Think of `Promise<T>` as the asynchronous counterpart to `Result<T>`. Both represent operations that can succeed or fail with typed errors. The only difference is timing: `Result<T>` completes immediately, `Promise<T>` completes later. The same `map`/`flatMap` patterns work identically; converting is trivial (`result.async()` lifts to Promise, `promise.await()` blocks to Result). When you understand `Result<T>`, you understand `Promise<T>`.

**Promise Resolution and Thread Safety:**

Promise resolution is **thread-safe** and happens **exactly once**:

*   Multiple threads can attempt resolution - only the first succeeds
*   Resolution serves as synchronization point
*   Transformations execute after resolution
*   Side effects execute independently

```
[](#cb10-1)var promise = Promise.<User>promise();
[](#cb10-2)
[](#cb10-3)// Multiple threads racing to resolve - only first wins
[](#cb10-4)executor.submit(() -> promise.succeed(user1));  // First to resolve
[](#cb10-5)executor.submit(() -> promise.succeed(user2));  // Ignored
[](#cb10-6)
[](#cb10-7)// All transformations see the same result (user1)
[](#cb10-8)promise.map(this::processUser)
[](#cb10-9)       .flatMap(this::saveToDatabase)
[](#cb10-10)       .onSuccess(this::logSuccess);
```

**Return `Promise<T>` when:** - Any I/O operation (database, HTTP, file system) - External service calls - Operations that might block or take time

* * *

## Why Exactly Four?

These four types form a complete basis for composition. You can lift “up” when needed (`Option` to `Result` to `Promise`), but you never nest the same concern twice.

Each type represents one orthogonal concern: - **Synchronous vs. asynchronous**: now vs. later - **Can fail vs cannot fail**: error channel present or absent - **Value vs optional value**: presence guaranteed or not

**Decision table:**

| Sync? | Can Fail? | May Be Absent? | Return Type |
| --- | --- | --- | --- |
| Yes | No | No | `T` |
| Yes | No | Yes | `Option<T>` |
| Yes | Yes | No | `Result<T>` |
| Async | Yes | No | `Promise<T>` |

* * *

## Return Type Matrix

### Allowed Return Types

| Type | Use Case |
| --- | --- |
| `T` | Synchronous, cannot fail, always present |
| `Option<T>` | Synchronous, cannot fail, might be absent |
| `Result<T>` | Synchronous, can fail |
| `Promise<T>` | Asynchronous, can fail |
| `Result<Option<T>>` | Optional value that can fail validation |
| `Promise<Option<T>>` | Async lookup that might not find anything |

### Discouraged

| Type | Why Discouraged |
| --- | --- |
| `Optional<T>` | Use `Option<T>` for consistency |
| `CompletableFuture<T>` | Use `Promise<T>` for consistent error handling |
| Framework-specific types (`Mono<T>`, `ResponseEntity<T>`) | Keep business logic framework-agnostic |

### Forbidden (Double-Monad Nesting)

| Type | Why Forbidden |
| --- | --- |
| `Promise<Result<T>>` | `Promise` already carries failures - double error channel |
| `Result<Result<T>>` | Nested failures create unwrapping ceremony |
| `Option<Option<T>>` | Nested optionality is meaningless |
| `Promise<Option<Result<T>>>` | Triple nesting - architectural smell |

**Rule:** Each monadic concern (optionality, failure, asynchrony) appears at most once in a return type.

* * *

## Why Not Java’s Built-in Types?

**“Can’t I just use `Optional`, `CompletableFuture`, and exceptions?”**

You could, but you’d hit these problems:

| Java Approach | Problem | JBCT Solution |
| --- | --- | --- |
| `return null` | Hidden optionality → NPE at runtime | `Option<T>` explicit in type |
| `Optional<T>` | Can’t represent failures | `Result<T>` for typed errors |
| `try-catch` | Invisible control flow | `Result<T>` - errors as values |
| `CompletableFuture<T>` | Complex error handling | `Promise<T>` consistent patterns |

**Key differences:** - **Explicit in types**: Signature tells you failure modes, no hidden exceptions - **Consistent composition**: `map`/`flatMap` work the same across all types - **No nesting**: One concern per type level - **Better inference**: AI can generate correct error handling from types alone

* * *

## Type Conversions

### Lifting: Moving Between Types

You can lift a “lower” type into a “higher” one:

```
[](#cb11-1)// T → Option/Result/Promise
[](#cb11-2)Option.option(value)
[](#cb11-3)Result.success(value)
[](#cb11-4)Promise.success(value)
[](#cb11-5)
[](#cb11-6)// Option → Result/Promise
[](#cb11-7)option.toResult(cause)
[](#cb11-8)option.async(cause)
[](#cb11-9)
[](#cb11-10)// Result → Promise
[](#cb11-11)result.async()
```

Example:

```
[](#cb12-1)public Promise<Response> execute(Request request) {
[](#cb12-2)    return ValidRequest.validRequest(request)
[](#cb12-3)                       .async()  // Result → Promise
[](#cb12-4)                       .flatMap(step1::apply)
[](#cb12-5)                       .flatMap(step2::apply);
[](#cb12-6)}
```

### Forbidden Nesting: `Promise<Result<T>>`

**`Promise<Result<T>>` is forbidden.** `Promise<T>` already carries failures - nesting `Result` inside creates two error channels.

**Wrong:**

```
[](#cb13-1)Promise<Result<User>> loadUser(UserId id) { /* ... */ }
[](#cb13-2)
[](#cb13-3)// Caller must unwrap twice - absurd ceremony
[](#cb13-4)loadUser(id)
[](#cb13-5)    .flatMap(resultUser -> resultUser.fold(
[](#cb13-6)        Cause::promise,
[](#cb13-7)        user -> Promise.success(user)
[](#cb13-8)    ));
```

**Right:**

```
[](#cb14-1)Promise<User> loadUser(UserId id) { /* ... */ }
[](#cb14-2)
[](#cb14-3)// Caller just chains
[](#cb14-4)return loadUser(id).flatMap(nextStep);
```

### Allowed Nesting: `Result<Option<T>>`

`Result<Option<T>>` is permitted sparingly for “optional value that can fail validation.”

```
[](#cb15-1)Result<Option<ReferralCode>> refCode = ReferralCode.referralCode(input);
[](#cb15-2)// Success(None) = not provided, valid
[](#cb15-3)// Success(Some(code)) = provided and valid
[](#cb15-4)// Failure(cause) = provided but invalid
```

Use `Verify.ensureOption()` (Pragmatica Lite 0.9.0+) to implement this pattern:

```
[](#cb16-1)public static Result<Option<ReferralCode>> referralCode(String raw) {
[](#cb16-2)    return Verify.ensureOption(
[](#cb16-3)        Option.option(raw).map(String::trim).filter(s -> !s.isEmpty()),
[](#cb16-4)        PATTERN.asMatchPredicate(),
[](#cb16-5)        INVALID_FORMAT
[](#cb16-6)    ).map(opt -> opt.map(ReferralCode::new));
[](#cb16-7)}
```

* * *

## API Quick Reference

### Type Conversions

```
[](#cb17-1)// Option conversions
[](#cb17-2)option.toResult(cause)      // Option → Result
[](#cb17-3)option.async(cause)         // Option → Promise
[](#cb17-4)option.toOptional()         // Option → Java Optional
[](#cb17-5)
[](#cb17-6)// Result conversions
[](#cb17-7)result.async()              // Result → Promise
[](#cb17-8)result.option()             // Result → Option (loses error)
[](#cb17-9)
[](#cb17-10)// Promise conversions
[](#cb17-11)promise.await()             // Promise → Result (blocks)
[](#cb17-12)promise.await(timeout)      // Promise → Result (with timeout)
[](#cb17-13)
[](#cb17-14)// Cause conversions (preferred)
[](#cb17-15)cause.result()              // Cause → Result failure
[](#cb17-16)cause.promise()             // Cause → Promise failure
```

### Creating Instances

```
[](#cb18-1)// Option
[](#cb18-2)Option.some(value)
[](#cb18-3)Option.none()
[](#cb18-4)Option.option(nullable)     // null → none
[](#cb18-5)
[](#cb18-6)// Result
[](#cb18-7)Result.success(value)
[](#cb18-8)cause.result()              // Preferred for failure
[](#cb18-9)
[](#cb18-10)// Promise
[](#cb18-11)Promise.success(value)
[](#cb18-12)cause.promise()             // Preferred for failure
[](#cb18-13)Promise.promise()           // Unresolved
```

* * *

## Key Takeaways

1.  **Four types cover all cases** - T, Option, Result, Promise
2.  **Signatures tell everything** - failure modes, optionality, synchrony
3.  **Lift up, never nest** - Convert to higher types, never `Promise<Result<T>>`
4.  **Consistent composition** - Same map/flatMap across all types
5.  **Use Cause methods** - Prefer `cause.result()` over `Result.failure(cause)`

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 1.3: Type Lifting - Exercise 1.4: Cause Creation - Exercise 1.5: Pragmatica Lite Operations

* * *

## What’s Next

[Chapter 3](ch03-pragmatica-lite-essentials.md) covers Pragmatica Lite Core - the library that provides these four types. You’ll learn the API in depth and see common usage patterns.

# Chapter 3: Pragmatica Lite Essentials

This chapter introduces Pragmatica Lite Core—the library that provides the foundational types for JBCT. You’ll learn why the library exists, its design philosophy, and how to use its core features effectively.

* * *

## Why a Custom Library?

Java provides `Optional` and `CompletableFuture`. Why not use them?

### Problems with Java’s Built-in Types

| Type | Problem |
| --- | --- |
| `Optional` | No error channel - you know something is missing but not why |
| `Optional` | Not designed for validation - orElseThrow loses context |
| `CompletableFuture` | Exceptions as control flow - checked exceptions don’t compose |
| `CompletableFuture` | Verbose API - thenApply, thenCompose, exceptionally chains |
| `null` | Billion-dollar mistake - no type safety, NPE at runtime |

### What JBCT Needs

1.  **Four distinct return types** - Each with clear semantics
2.  **Composable error handling** - Errors as values, not exceptions
3.  **Consistent API** - Same method names across all types
4.  **Type-safe transformations** - Lift between types without losing information

Pragmatica Lite Core provides exactly this.

* * *

## Installation

**Maven (preferred):**

```
[](#cb19-1)<dependency>
[](#cb19-2)   <groupId>org.pragmatica-lite</groupId>
[](#cb19-3)   <artifactId>core</artifactId>
[](#cb19-4)   <version>0.9.9</version>
[](#cb19-5)</dependency>
```

**Gradle:**

```
[](#cb20-1)implementation 'org.pragmatica-lite:core:0.9.9'
```

* * *

## The Four Core Types

### `Option<T>` - Value May Be Absent

```
[](#cb21-1)import org.pragmatica.lang.Option;
[](#cb21-2)
[](#cb21-3)Option<User> user = Option.some(new User("Alice"));
[](#cb21-4)Option<User> nobody = Option.none();
[](#cb21-5)Option<User> fromNullable = Option.option(possiblyNullValue);
```

**Use when:** Value might not exist, but absence is not an error.

**Examples:** Cache lookup, optional configuration, search result.

### `Result<T>` - Operation May Fail

```
[](#cb22-1)import org.pragmatica.lang.Result;
[](#cb22-2)import org.pragmatica.lang.Cause;
[](#cb22-3)
[](#cb22-4)Result<Email> valid = Result.success(new Email("user@example.com"));
[](#cb22-5)Result<Email> invalid = INVALID_EMAIL.result();  // Preferred: fluent style
[](#cb22-6)
[](#cb22-7)// Also works (but verbose)
[](#cb22-8)Result<Email> invalid2 = Causes.cause("Invalid format").result();
```

**Use when:** Synchronous operation that can fail with typed error.

**Examples:** Validation, parsing, business rule checks.

### `Promise<T>` - Async Operation May Fail

```
[](#cb23-1)import org.pragmatica.lang.Promise;
[](#cb23-2)
[](#cb23-3)Promise<User> fetching = Promise.promise();  // Unresolved
[](#cb23-4)Promise<User> ready = Promise.success(user);  // Already resolved
[](#cb23-5)Promise<User> failed = USER_NOT_FOUND.promise();  // Preferred: fluent style
```

**Use when:** Asynchronous operation (I/O, external service).

**Examples:** Database query, HTTP call, file read.

### Cause - Typed Error

```
[](#cb24-1)import org.pragmatica.lang.Cause;
[](#cb24-2)import org.pragmatica.lang.utils.Causes;
[](#cb24-3)
[](#cb24-4)// Simple cause
[](#cb24-5)Cause simple = Causes.cause("Something went wrong");
[](#cb24-6)
[](#cb24-7)// Cause with context
[](#cb24-8)Fn1<Cause, String> INVALID_EMAIL = Causes.forOneValue("Invalid email: %s");
[](#cb24-9)Cause withContext = INVALID_EMAIL.apply("not-an-email");
[](#cb24-10)
[](#cb24-11)// Cause from exception
[](#cb24-12)Cause fromException = Causes.fromThrowable(exception);
```

**Use when:** Representing failure reason in Result or Promise.

* * *

## Design Philosophy

### Consistent Method Names

All types share the same vocabulary where applicable:

| Method | Option | Result | Promise |
| --- | --- | --- | --- |
| Transform value | `map()` | `map()` | `map()` |
| Chain operations | `flatMap()` | `flatMap()` | `flatMap()` |
| Filter with condition | - | `filter()` | `filter()` |
| Provide fallback | `or()` | `or()` | `or()` |
| Handle success | `onPresent()` | `onSuccess()` | `onSuccess()` |
| Handle failure | `onEmpty()` | `onFailure()` | `onFailure()` |

### Prefer Cause Methods Over Factory Methods

```
[](#cb25-1)// DO: Use Cause methods
[](#cb25-2)Cause error = VALIDATION_FAILED;
[](#cb25-3)return error.result();   // Result<T>
[](#cb25-4)return error.promise();  // Promise<T>
[](#cb25-5)
[](#cb25-6)// DON'T: Use factory methods with Cause
[](#cb25-7)return Result.failure(error);   // Works but verbose
[](#cb25-8)return Promise.failure(error);  // Works but verbose
```

### Lift to Higher Types, Not Lower

```
[](#cb26-1)// Lifting UP is safe
[](#cb26-2)Option<T> option = ...;
[](#cb26-3)Result<T> result = option.toResult(CAUSE_IF_EMPTY);
[](#cb26-4)Promise<T> promise = result.async();
[](#cb26-5)
[](#cb26-6)// Going DOWN loses information
[](#cb26-7)Result<T> result = ...;
[](#cb26-8)Option<T> option = result.option();  // Loses error info!
```

* * *

## Type Transformations

### Option Conversions

```
[](#cb27-1)Option<User> option = findUser(id);
[](#cb27-2)
[](#cb27-3)// Option -> Result (provide cause for empty case)
[](#cb27-4)Result<User> result = option.toResult(USER_NOT_FOUND);
[](#cb27-5)
[](#cb27-6)// Option -> Promise (provide cause for empty case)
[](#cb27-7)Promise<User> promise = option.async(USER_NOT_FOUND);
[](#cb27-8)
[](#cb27-9)// Option -> Java Optional (interop only)
[](#cb27-10)Optional<User> javaOptional = option.toOptional();
```

### Result Conversions

```
[](#cb28-1)Result<User> result = validateUser(input);
[](#cb28-2)
[](#cb28-3)// Result -> Promise (lift to async context)
[](#cb28-4)Promise<User> promise = result.async();
[](#cb28-5)
[](#cb28-6)// Result -> Option (loses error - use sparingly)
[](#cb28-7)Option<User> option = result.option();
```

### Promise Conversions

```
[](#cb29-1)Promise<User> promise = fetchUser(id);
[](#cb29-2)
[](#cb29-3)// Promise -> Result (blocks current thread)
[](#cb29-4)Result<User> result = promise.await();
[](#cb29-5)
[](#cb29-6)// Promise -> Result with timeout
[](#cb29-7)Result<User> result = promise.await(TimeSpan.timeSpan(5).seconds());
```

* * *

## Common Operations

### map - Transform Success Value

```
[](#cb30-1)Result<String> raw = Result.success("  USER@EXAMPLE.COM  ");
[](#cb30-2)
[](#cb30-3)Result<String> normalized = raw
[](#cb30-4)    .map(String::trim)
[](#cb30-5)    .map(String::toLowerCase);
[](#cb30-6)// Result.success("user@example.com")
```

### flatMap - Chain Dependent Operations

```
[](#cb31-1)Result<Email> email = Email.email(rawEmail);
[](#cb31-2)Result<Password> password = Password.password(rawPassword);
[](#cb31-3)
[](#cb31-4)// Wrong: Nested Result
[](#cb31-5)Result<Result<ValidRequest>> nested = email.map(e ->
[](#cb31-6)    password.map(p -> new ValidRequest(e, p))
[](#cb31-7));
[](#cb31-8)
[](#cb31-9)// Correct: Flat chain
[](#cb31-10)Result<ValidRequest> flat = email.flatMap(e ->
[](#cb31-11)    password.map(p -> new ValidRequest(e, p))
[](#cb31-12));
```

### filter - Validate with Predicate

```
[](#cb32-1)Result<Integer> age = Result.success(25);
[](#cb32-2)
[](#cb32-3)Result<Integer> adult = age.filter(
[](#cb32-4)    Causes.cause("Must be 18 or older"),
[](#cb32-5)    a -> a >= 18
[](#cb32-6));
```

### recover - Handle Specific Failures

```
[](#cb33-1)Promise<Config> config = loadFromDatabase()
[](#cb33-2)    .recover(cause -> switch (cause) {
[](#cb33-3)        case DatabaseError _ -> loadFromFile();
[](#cb33-4)        case FileError _ -> Promise.success(Config.defaults());
[](#cb33-5)        default -> cause.promise();
[](#cb33-6)    });
```

### or / orElse - Provide Fallback

```
[](#cb34-1)// or: Fallback value
[](#cb34-2)String name = option.or("Anonymous");
[](#cb34-3)
[](#cb34-4)// orElse: Fallback wrapped value
[](#cb34-5)Option<User> user = cache.find(id).orElse(database.find(id));
```

* * *

## Aggregation

### Result.all - Validate Multiple Fields

```
[](#cb35-1)Result<ValidRequest> request = Result.all(
[](#cb35-2)    Email.email(raw.email()),
[](#cb35-3)    Password.password(raw.password()),
[](#cb35-4)    Name.name(raw.name())
[](#cb35-5)).map(ValidRequest::new);
```

**Behavior:** Accumulates ALL failures into CompositeCause. Does not short-circuit.

### Promise.all - Parallel Execution

```
[](#cb36-1)Promise<Dashboard> dashboard = Promise.all(
[](#cb36-2)    fetchProfile(userId),
[](#cb36-3)    fetchOrders(userId),
[](#cb36-4)    fetchPreferences(userId)
[](#cb36-5)).map(Dashboard::new);
```

**Behavior:** Executes in parallel, fails fast on first failure.

### Result.allOf / Promise.allOf - Collection Aggregation

```
[](#cb37-1)// Validate list of emails
[](#cb37-2)Result<List<Email>> emails = Result.allOf(
[](#cb37-3)    rawEmails.stream().map(Email::email).toList()
[](#cb37-4));
[](#cb37-5)
[](#cb37-6)// Fetch multiple users in parallel
[](#cb37-7)Promise<List<Result<User>>> users = Promise.allOf(
[](#cb37-8)    userIds.stream().map(this::fetchUser).toList()
[](#cb37-9));
```

### any - First Success Wins

```
[](#cb38-1)Promise<Config> config = Promise.any(
[](#cb38-2)    loadFromPrimarySource(),
[](#cb38-3)    loadFromSecondarySource(),
[](#cb38-4)    loadFromFallback()
[](#cb38-5));
```

* * *

## Exception Handling with lift

### Basic lift - Wrap Throwing Code

```
[](#cb39-1)// Wrap supplier that may throw
[](#cb39-2)Result<Integer> parsed = Result.lift(() -> Integer.parseInt(raw));
[](#cb39-3)
[](#cb39-4)// With custom error mapping
[](#cb39-5)Result<Integer> parsed = Result.lift(
[](#cb39-6)    ParseError::new,
[](#cb39-7)    () -> Integer.parseInt(raw)
[](#cb39-8));
```

### lift with Parameters

```
[](#cb40-1)// Single parameter
[](#cb40-2)Result<Hash> hashed = Result.lift1(
[](#cb40-3)    HashError::new,
[](#cb40-4)    encoder::encode,
[](#cb40-5)    password.value()
[](#cb40-6));
[](#cb40-7)
[](#cb40-8)// Two parameters
[](#cb40-9)Result<Token> token = Result.lift2(
[](#cb40-10)    TokenError::new,
[](#cb40-11)    tokenService::generate,
[](#cb40-12)    userId,
[](#cb40-13)    expiry
[](#cb40-14));
```

### Promise.lift - Async Exception Wrapping

```
[](#cb41-1)Promise<User> user = Promise.lift(
[](#cb41-2)    DatabaseError::new,
[](#cb41-3)    () -> jdbcTemplate.queryForObject(sql, mapper, id)
[](#cb41-4));
```

* * *

## Validation Utilities

### Verify.Is Predicates

```
[](#cb42-1)import org.pragmatica.lang.utils.Verify;
[](#cb42-2)
[](#cb42-3)// String checks
[](#cb42-4)Verify.ensure(value, Verify.Is::notNull)
[](#cb42-5)Verify.ensure(value, Verify.Is::notBlank)
[](#cb42-6)Verify.ensure(value, Verify.Is::notEmpty)
[](#cb42-7)
[](#cb42-8)// Length checks
[](#cb42-9)Verify.ensure(password, Verify.Is::lenBetween, 8, 128)
[](#cb42-10)
[](#cb42-11)// Pattern matching
[](#cb42-12)Verify.ensure(email, Verify.Is::matches, EMAIL_PATTERN)
[](#cb42-13)
[](#cb42-14)// Numeric checks
[](#cb42-15)Verify.ensure(age, Verify.Is::positive)
[](#cb42-16)Verify.ensure(age, Verify.Is::between, 0, 150)
[](#cb42-17)Verify.ensure(quantity, Verify.Is::lessThanOrEqualTo, 100)
```

### Combining Validations

```
[](#cb43-1)public static Result<Password> password(String raw) {
[](#cb43-2)    return Verify.ensure(raw, Verify.Is::notNull)
[](#cb43-3)        .filter(TOO_SHORT, s -> Verify.Is.lenBetween(s, 8, 128))
[](#cb43-4)        .filter(NO_DIGIT, DIGIT_PATTERN.asMatchPredicate())
[](#cb43-5)        .filter(NO_UPPER, UPPER_PATTERN.asMatchPredicate())
[](#cb43-6)        .map(Password::new);
[](#cb43-7)}
```

### Parse Utilities - JDK Wrappers

```
[](#cb44-1)import org.pragmatica.lang.parse.*;
[](#cb44-2)
[](#cb44-3)// Instead of Result.lift(() -> Integer.parseInt(raw))
[](#cb44-4)Result<Integer> number = Number.parseInt(raw);
[](#cb44-5)Result<Long> bigNumber = Number.parseLong(raw);
[](#cb44-6)Result<BigDecimal> decimal = Number.parseBigDecimal(raw);
[](#cb44-7)
[](#cb44-8)// Date/time parsing
[](#cb44-9)Result<LocalDate> date = DateTime.parseLocalDate(raw);
[](#cb44-10)Result<Instant> instant = DateTime.parseInstant(raw);
[](#cb44-11)
[](#cb44-12)// Network types
[](#cb44-13)Result<UUID> uuid = Network.parseUUID(raw);
[](#cb44-14)Result<URI> uri = Network.parseURI(raw);
```

* * *

## Callback Methods

### Success/Failure Handlers

```
[](#cb45-1)result
[](#cb45-2)    .onSuccess(user -> log.info("Found user: {}", user.id()))
[](#cb45-3)    .onFailure(cause -> log.warn("User not found: {}", cause.message()));
[](#cb45-4)
[](#cb45-5)promise
[](#cb45-6)    .onSuccess(data -> cache.put(key, data))
[](#cb45-7)    .onFailure(cause -> metrics.incrementFailure());
```

### Result Handler (Both Cases)

```
[](#cb46-1)promise.onResult(result -> {
[](#cb46-2)    if (result.isSuccess()) {
[](#cb46-3)        metrics.recordSuccess();
[](#cb46-4)    } else {
[](#cb46-5)        metrics.recordFailure();
[](#cb46-6)    }
[](#cb46-7)});
```

### fold - Transform Both Cases

```
[](#cb47-1)// Result -> ResponseEntity
[](#cb47-2)ResponseEntity<?> response = result.fold(
[](#cb47-3)    cause -> toErrorResponse(cause),    // Failure case first
[](#cb47-4)    data -> ResponseEntity.ok(data)     // Success case second
[](#cb47-5));
```

* * *

## Unit Type

For operations that succeed but produce no value:

```
[](#cb48-1)// Use Unit, never Void
[](#cb48-2)Result<Unit> validated = checkBusinessRule(input);
[](#cb48-3)Promise<Unit> sent = sendNotification(user);
[](#cb48-4)
[](#cb48-5)// Create success with no value
[](#cb48-6)Result<Unit> ok = Result.unitResult();
[](#cb48-7)
[](#cb48-8)// Convert any result to Unit
[](#cb48-9)Promise<Unit> ignored = fetchData().mapToUnit();
```

* * *

## Thread Safety

### Promise Resolution

Promises have exactly-once resolution semantics:

```
[](#cb49-1)Promise<User> promise = Promise.promise();
[](#cb49-2)
[](#cb49-3)// Only first resolution wins
[](#cb49-4)promise.succeed(user1);  // This resolves the promise
[](#cb49-5)promise.succeed(user2);  // Ignored
[](#cb49-6)promise.fail(cause);     // Ignored
```

### Transformation Thread Safety

Transformations are thread-safe but execution order depends on resolution:

```
[](#cb50-1)Promise<User> promise = fetchUser(id);
[](#cb50-2)
[](#cb50-3)// These may execute on different threads
[](#cb50-4)promise
[](#cb50-5)    .map(this::enrichUser)      // Executes after resolution
[](#cb50-6)    .onSuccess(this::cacheUser) // Executes after map
[](#cb50-7)    .onFailure(this::logError); // Executes if failed
```

* * *

## Quick Reference

### Creating Instances

```
[](#cb51-1)// Option
[](#cb51-2)Option.some(value)           // Present
[](#cb51-3)Option.none()                // Empty
[](#cb51-4)Option.option(nullable)      // null -> none, value -> some
[](#cb51-5)
[](#cb51-6)// Result
[](#cb51-7)Result.success(value)        // Success
[](#cb51-8)cause.result()               // Failure (preferred)
[](#cb51-9)Result.unitResult()          // Success with Unit
[](#cb51-10)
[](#cb51-11)// Promise
[](#cb51-12)Promise.success(value)       // Resolved success
[](#cb51-13)cause.promise()              // Resolved failure (preferred)
[](#cb51-14)Promise.promise()            // Unresolved
```

### Type Lifting

```
[](#cb52-1)option.toResult(cause)       // Option -> Result
[](#cb52-2)option.async(cause)          // Option -> Promise
[](#cb52-3)result.async()               // Result -> Promise
[](#cb52-4)promise.await()              // Promise -> Result (blocks)
```

### Common Transformations

```
[](#cb53-1).map(fn)                     // Transform value
[](#cb53-2).flatMap(fn)                 // Chain monadic operation
[](#cb53-3).filter(cause, predicate)    // Validate with predicate
[](#cb53-4).recover(fn)                 // Handle failure
[](#cb53-5).or(fallback)                // Provide default value
[](#cb53-6).mapToUnit()                 // Discard value, keep success/failure
```

* * *

## Exercises

1.  **Parse a date range:** Create a `DateRange` value object with `from` and `to` fields. Use `DateTime.parseLocalDate()` and validate that `from` is before `to`.

2.  **Combine validations:** Write a `Username` value object that must be 3-20 characters, alphanumeric only, and not on a blocklist. Chain the validations.

3.  **Handle nullable external API:** You receive a `Map<String, Object>` from a JSON parser. Write a method that safely extracts an optional `email` field and validates it.

4.  **Lift JDBC code:** Wrap a `jdbcTemplate.query()` call in `Promise.lift()` with appropriate error mapping.

* * *

## Summary

Pragmatica Lite Core provides:

*   **Four types with clear semantics** - Option, Result, Promise, Cause
*   **Consistent API** - Same method names across types
*   **Composable error handling** - Errors as values, not exceptions
*   **Type-safe transformations** - Lift between types without losing information
*   **Validation utilities** - Verify.Is predicates, parse wrappers
*   **Thread-safe promises** - Exactly-once resolution, safe transformations

The library is intentionally minimal. It provides the building blocks for JBCT without imposing architectural decisions. Your business logic remains framework-independent.

* * *

## What’s Next

With the foundation in place, we move to the core principles: - **Chapter 4:** Parse, Don’t Validate - Making invalid states unrepresentable - **Chapter 5:** Error Handling & Composition - Typed errors and recovery patterns

# Chapter 4: Parse, Don’t Validate

## What You’ll Learn

*   Why validation should be inseparable from construction
*   How to use factory methods with `Result<T>` returns
*   Cross-field validation techniques
*   Real-world validation scenarios
*   How to adopt this incrementally in existing codebases

**Prerequisites:** [Chapter 2: The Four Return Types](ch02-four-return-types.md)

* * *

## The Principle

Most Java code validates data after construction. You create an object with raw values, then call a `validate()` method that might throw exceptions or return error lists. This approach is backwards.

**The principle:** Make invalid states unrepresentable. If construction succeeds, the object is valid by definition. Validation is parsing - converting untyped or weakly-typed input into strongly typed domain objects that enforce invariants at the type level.

**Why by criteria:** - **Mental Overhead**: No “remember to validate” - type system guarantees validity (+2) - **Reliability**: Compiler enforces that invalid objects cannot be constructed (+3) - **Design Impact**: Business invariants concentrated in factories, not scattered (+2) - **Complexity**: Single validation point per type eliminates redundant checks (+1)

* * *

## The Traditional (Wrong) Approach

```
[](#cb54-1)// DON'T: Validation separated from construction
[](#cb54-2)public class Email {
[](#cb54-3)    private final String value;
[](#cb54-4)
[](#cb54-5)    public Email(String value) {
[](#cb54-6)        this.value = value;  // accepts anything
[](#cb54-7)    }
[](#cb54-8)
[](#cb54-9)    public boolean isValid() {  // Caller must remember to check
[](#cb54-10)        return value != null && value.matches("^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$");
[](#cb54-11)    }
[](#cb54-12)}
[](#cb54-13)
[](#cb54-14)// Client code must validate manually:
[](#cb54-15)Email email = new Email(input);
[](#cb54-16)if (!email.isValid()) {
[](#cb54-17)    throw new ValidationException("Invalid email");
[](#cb54-18)}
```

**Problems:** - You can construct invalid `Email` objects - Validation is a separate step that callers might forget - The `isValid()` method returns a boolean, discarding information about what’s wrong - You can’t distinguish “null” from “malformed” from “too long”

* * *

## The Parse-Don’t-Validate Approach

```
[](#cb55-1)// DO: Validation IS construction
[](#cb55-2)public record Email(String value) {
[](#cb55-3)    private static final Pattern EMAIL_PATTERN =
[](#cb55-4)        Pattern.compile("^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$");
[](#cb55-5)    private static final Fn1<Cause, String> INVALID_EMAIL =
[](#cb55-6)        Causes.forOneValue("Invalid email format: %s");
[](#cb55-7)
[](#cb55-8)    public static Result<Email> email(String raw) {
[](#cb55-9)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb55-10)                     .map(String::trim)
[](#cb55-11)                     .filter(INVALID_EMAIL, EMAIL_PATTERN.asMatchPredicate())
[](#cb55-12)                     .map(Email::new);
[](#cb55-13)    }
[](#cb55-14)}
[](#cb55-15)
[](#cb55-16)// Client code gets the Result:
[](#cb55-17)Result<Email> result = Email.email(input);
[](#cb55-18)// If this is a Success, the Email is valid. Guaranteed.
```

The constructor is private (or package-private). The only way to get an `Email` is through the static factory `email()`, which returns `Result<Email>`. If you have an `Email` instance, it’s valid - no separate check needed.

> **Note:** As of current Java versions, records do not support declaring the canonical constructor as private. Rely on team discipline and code review to ensure value objects are only constructed through their factory methods. Direct `new Email(...)` calls stand out immediately and are easy to catch.

* * *

## Naming Conventions

**Factory naming**: Factories are always named after their type, lowercase-first (camelCase):

```
[](#cb56-1)Email.email(raw)
[](#cb56-2)Password.password(raw)
[](#cb56-3)AccountId.accountId(raw)
```

This creates a natural, readable call site that’s grep-friendly and allows static imports.

**Validated input naming**: Use the `Valid` prefix for types representing validated inputs:

```
[](#cb57-1)// DO: Use Valid prefix
[](#cb57-2)record ValidRequest(Email email, Password password) { ... }
[](#cb57-3)record ValidUser(Email email, HashedPassword hashed) { ... }
[](#cb57-4)
[](#cb57-5)// DON'T: Use Validated prefix (too verbose)
[](#cb57-6)record ValidatedRequest(...)
```

* * *

## Optional Fields with Validation

What if a field is optional but must be valid when present? Use `Result<Option<T>>` with `Verify.ensureOption()`:

```
[](#cb58-1)public record ReferralCode(String value) {
[](#cb58-2)    private static final Pattern PATTERN = Pattern.compile("^[A-Z0-9]{6}$");
[](#cb58-3)    private static final Cause INVALID_FORMAT = Causes.cause("Invalid referral code format");
[](#cb58-4)
[](#cb58-5)    public static Result<Option<ReferralCode>> referralCode(String raw) {
[](#cb58-6)        return Verify.ensureOption(
[](#cb58-7)            Option.option(raw).map(String::trim).filter(s -> !s.isEmpty()),
[](#cb58-8)            PATTERN.asMatchPredicate(),
[](#cb58-9)            INVALID_FORMAT
[](#cb58-10)        ).map(opt -> opt.map(ReferralCode::new));
[](#cb58-11)    }
[](#cb58-12)}
```

The `Verify.ensureOption()` method (Pragmatica Lite 0.9.0+) handles this pattern elegantly: - If the `Option` is empty, succeeds with `Option.none()` - no validation needed - If present and valid, succeeds with `Option.some(value)` - If present and invalid, fails with the provided cause

**Caller semantics:** - `Failure(cause)`: Invalid input (provided but doesn’t match pattern) - `Success(None)`: No value provided (valid state) - `Success(Some(code))`: Valid code provided

* * *

## Normalization in Factories

Factories can normalize input as part of parsing:

```
[](#cb59-1)public static Result<Email> email(String raw) {
[](#cb59-2)    return Verify.ensure(raw, Verify.Is::notNull)
[](#cb59-3)                 .map(String::trim)           // Remove whitespace
[](#cb59-4)                 .map(String::toLowerCase)    // Lowercase for comparison
[](#cb59-5)                 .filter(INVALID_EMAIL, EMAIL_PATTERN.asMatchPredicate())
[](#cb59-6)                 .map(Email::new);
[](#cb59-7)}
```

Now all `Email` instances are trimmed and lowercased. Domain logic never worries about case or whitespace.

* * *

## Where Validation Belongs

**Clear rule for validation placement:**

| Validation Type | Where | Example |
| --- | --- | --- |
| **Single-field invariants** | Value object factory | Email format, password strength, ID format |
| **Cross-field invariants** | ValidRequest factory | Password doesn’t contain email, date range valid |
| **External state invariants** | Use case step | Email uniqueness (DB), credit check (external service) |

**Rationale:** - Value objects enforce invariants that depend only on the field’s own value - ValidRequest enforces invariants that require multiple fields but no external state - Use cases handle invariants that require external lookups (database, services)

```
[](#cb60-1)// Value object: single-field invariant
[](#cb60-2)public record Email(String value) {
[](#cb60-3)    public static Result<Email> email(String raw) { /* format check only */ }
[](#cb60-4)}
[](#cb60-5)
[](#cb60-6)// ValidRequest: cross-field invariant
[](#cb60-7)public record ValidRegistration(Email email, Password password) {
[](#cb60-8)    public static Result<ValidRegistration> validRegistration(Email email, Password pwd) {
[](#cb60-9)        // Check password doesn't contain email local part
[](#cb60-10)    }
[](#cb60-11)}
[](#cb60-12)
[](#cb60-13)// Use case step: external state invariant
[](#cb60-14)interface CheckEmailUnique {
[](#cb60-15)    Promise<Email> apply(Email email);  // DB lookup
[](#cb60-16)}
```

* * *

## Cross-Field Validation with Result.all()

Use `Result.all()` to validate independent fields, then add cross-field rules:

**Example: Password must not contain email local part**

```
[](#cb61-1)record ValidRegistration(Email email, Password password) {
[](#cb61-2)    private static final Cause PASSWORD_CONTAINS_EMAIL =
[](#cb61-3)        Causes.cause("Password cannot contain email local part");
[](#cb61-4)
[](#cb61-5)    static Result<ValidRegistration> validRegistration(String emailRaw,
[](#cb61-6)                                                       String passwordRaw) {
[](#cb61-7)        return Result.all(Email.email(emailRaw),
[](#cb61-8)                         Password.password(passwordRaw))
[](#cb61-9)                     .flatMap(ValidRegistration::checkPasswordNotContainsEmail);
[](#cb61-10)    }
[](#cb61-11)
[](#cb61-12)    private static Result<ValidRegistration> checkPasswordNotContainsEmail(
[](#cb61-13)            Email email, Password pwd) {
[](#cb61-14)        String localPart = email.value().split("@")[0];
[](#cb61-15)        return pwd.value().contains(localPart)
[](#cb61-16)            ? PASSWORD_CONTAINS_EMAIL.result()
[](#cb61-17)            : Result.success(new ValidRegistration(email, pwd));
[](#cb61-18)    }
[](#cb61-19)}
```

**Pattern:** 1\. Validate individual fields with `Result.all()` → accumulates per-field errors 2\. Use `.flatMap()` to add cross-field validation → fail-fast on cross-field rules 3\. Extract cross-field logic to named methods 4\. Only construct if all validation passes

* * *

## Real-World Validation Scenarios

### Date Range Validation

```
[](#cb62-1)public record DateRange(LocalDate start, LocalDate end) {
[](#cb62-2)    private static final Fn1<Cause, LocalDate> END_BEFORE_START =
[](#cb62-3)        date -> Causes.cause("End date must be after start date: " + date);
[](#cb62-4)
[](#cb62-5)    public static Result<DateRange> dateRange(LocalDate start, LocalDate end) {
[](#cb62-6)        return Verify.ensure(start, Verify.Is::notNull)
[](#cb62-7)                     .flatMap(_ -> Verify.ensure(end, Verify.Is::notNull))
[](#cb62-8)                     .flatMap(_ -> Verify.ensure(end, isAfter(start), END_BEFORE_START))
[](#cb62-9)                     .map(_ -> new DateRange(start, end));
[](#cb62-10)    }
[](#cb62-11)
[](#cb62-12)    private static Predicate<LocalDate> isAfter(LocalDate start) {
[](#cb62-13)        return end -> end.isAfter(start);
[](#cb62-14)    }
[](#cb62-15)}
```

### Business Rule Validation

```
[](#cb63-1)public record ValidOrder(OrderId id, Money total, List<LineItem> items) {
[](#cb63-2)    private static final Fn1<Cause, Money> TOTAL_MISMATCH =
[](#cb63-3)        Causes.forOneValue("Order total does not match line items. Expected: %s");
[](#cb63-4)
[](#cb63-5)    public static Result<ValidOrder> validOrder(OrderId id,
[](#cb63-6)                                                Money total,
[](#cb63-7)                                                List<LineItem> items) {
[](#cb63-8)        return total.equals(calculateTotal(items))
[](#cb63-9)            ? Result.success(new ValidOrder(id, total, items))
[](#cb63-10)            : TOTAL_MISMATCH.apply(calculateTotal(items)).result();
[](#cb63-11)    }
[](#cb63-12)
[](#cb63-13)    private static Money calculateTotal(List<LineItem> items) {
[](#cb63-14)        return items.stream()
[](#cb63-15)                    .map(LineItem::subtotal)
[](#cb63-16)                    .reduce(Money.ZERO, Money::add);
[](#cb63-17)    }
[](#cb63-18)}
```

### Collecting Multiple Errors

```
[](#cb64-1)public record ValidRegistration(Email email, Password password, Age age) {
[](#cb64-2)    public static Result<ValidRegistration> validate(String emailRaw,
[](#cb64-3)                                                     String passwordRaw,
[](#cb64-4)                                                     String ageRaw) {
[](#cb64-5)        return Result.all(Email.email(emailRaw),
[](#cb64-6)                         Password.password(passwordRaw),
[](#cb64-7)                         Age.age(ageRaw))
[](#cb64-8)                     .map(ValidRegistration::new);
[](#cb64-9)        // If any field fails, Result.all() accumulates ALL errors
[](#cb64-10)        // User sees "Invalid email AND password too short AND age out of range"
[](#cb64-11)    }
[](#cb64-12)}
```

* * *

## Pragmatica Lite Validation Utilities

**Verify.Is Predicates:**

```
[](#cb65-1)// Instead of custom lambdas:
[](#cb65-2).flatMap(s -> s.length() >= 8 ? Result.success(s) : Result.failure(...))
[](#cb65-3)
[](#cb65-4)// Use filter with standard predicates:
[](#cb65-5).filter(TOO_SHORT, s -> Verify.Is.lenBetween(s, 8, 128))
```

Common predicates: `notNull`, `notBlank`, `lenBetween`, `matches`, `positive`, `nonNegative`, `between`, `greaterThan`, `lessThan`, `contains`.

**Parse Subpackage:**

```
[](#cb66-1)import org.pragmatica.lang.parse.Number;
[](#cb66-2)import org.pragmatica.lang.parse.DateTime;
[](#cb66-3)import org.pragmatica.lang.parse.Network;
[](#cb66-4)
[](#cb66-5)Number.parseInt(raw)              // Result<Integer>
[](#cb66-6)DateTime.parseLocalDate(raw)      // Result<LocalDate>
[](#cb66-7)Network.parseUUID(raw)            // Result<UUID>
```

**Example:**

```
[](#cb67-1)public record Age(int value) {
[](#cb67-2)    public static Result<Age> age(String raw) {
[](#cb67-3)        return Number.parseInt(raw)
[](#cb67-4)                     .filter(Causes.cause("Age 0-150"),
[](#cb67-5)                             v -> Verify.Is.between(v, 0, 150))
[](#cb67-6)                     .map(Age::new);
[](#cb67-7)    }
[](#cb67-8)}
```

* * *

## Adopting Incrementally

**Don’t refactor everything at once.** Adopt incrementally at boundaries.

**1\. New features first** - Use parse-don’t-validate for all new code

**2\. Keep existing validation at controller boundaries:**

```
[](#cb68-1)// BEFORE: Spring controller with @Valid
[](#cb68-2)@PostMapping("/register")
[](#cb68-3)public ResponseEntity<?> register(@Valid @RequestBody RegistrationRequest dto) {
[](#cb68-4)    var request = new RegisterUser.Request(dto.email(), dto.password());
[](#cb68-5)    return registerUser.execute(request)
[](#cb68-6)                       .fold(this::errorResponse, this::successResponse);
[](#cb68-7)}
[](#cb68-8)
[](#cb68-9)// AFTER: Fully migrated
[](#cb68-10)@PostMapping("/register")
[](#cb68-11)public ResponseEntity<?> register(@RequestBody RegisterUser.Request raw) {
[](#cb68-12)    return registerUser.execute(raw)
[](#cb68-13)        .fold(this::errorResponse, this::successResponse);
[](#cb68-14)}
```

**3\. Gradually move validation from services to value objects:** - Find a service method with manual validation - Extract that validation into a value object factory - Update callers to use the value object - Repeat

* * *

## Key Takeaways

1.  **Validation IS construction** - If an instance exists, it’s valid
2.  **Factory methods return `Result<T>`** - Success means valid object
3.  **`Result.all()` accumulates errors** - Show all problems at once
4.  **Normalization in factories** - Trim, lowercase, etc. happen once
5.  **`Result<Option<T>>`** - For optional values that must validate when present
6.  **Adopt incrementally** - Start at boundaries, work inward

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 2.1: PhoneNumber value object - Exercise 2.2: DateRange aggregate validation - Exercise 2.3: Error accumulation vs short-circuit

* * *

## What’s Next

[Chapter 5](ch05-error-handling.md) covers error handling - how to define typed errors, compose them, and handle failures cleanly without exceptions.

# Chapter 5: Error Handling & Composition

## What You’ll Learn

*   Why business logic never throws exceptions
*   How to define typed error hierarchies with Cause
*   Error accumulation vs fail-fast semantics
*   Monadic composition rules

**Prerequisites:** [Chapter 4: Parse, Don’t Validate](ch04-parse-dont-validate.md)

* * *

## No Business Exceptions

Business failures are not exceptional—they’re expected outcomes of business rules. An invalid email isn’t an exception; it’s a normal case of bad input. An account being locked isn’t an exception; it’s a business state.

**The rule:** Business logic never throws exceptions for business failures. All failures flow through `Result` or `Promise` as typed `Cause` objects.

* * *

## Why Result: Error Handling Philosophy

Error handling logic belongs where business context exists to make decisions. Sometimes that’s close to where the error occurred; sometimes the error propagates unchanged because only the caller has enough context to decide. This fundamental truth doesn’t depend on the error mechanism—it’s about where knowledge lives.

Different languages use different mechanisms for error propagation, each with distinct trade-offs in **transparency** (is failure visible?), **ergonomics** (is it pleasant to use?), and **reliability** (does the compiler help?):

| Mechanism | Transparency | Ergonomics | Reliability |
| --- | --- | --- | --- |
| **Checked exceptions** | ✅ Explicit in signature | ❌ Verbose, tight coupling | ✅ Compiler-enforced |
| **Unchecked exceptions** | ❌ Hidden in implementation | ⚠️ Acceptable, but mental overhead | ❌ Silent failures |
| **Errors as values** (Go) | ✅ Return value visible | ❌ Manual `if err != nil` everywhere | ❌ Easy to ignore |
| **Functional (Result/Either)** | ✅ Type signature | ✅ Monadic composition | ✅ Compiler-enforced |

**Checked exceptions** couple caller and callee tightly—changes in lower-level methods cascade upward, forcing signature changes throughout the call stack.

**Unchecked exceptions** eliminate coupling but hide failure modes. Every method call requires reading implementation to discover what might throw. The mental overhead is constant; the bugs are intermittent.

**Errors as values** (Go-style) make failure visible but require manual propagation at every step. Complex scenarios with multiple error sources or interleaved resource management become error-prone boilerplate.

**Functional style** (`Result<T>`) combines the best properties: failure is explicit in the type signature (transparent), monadic composition eliminates manual propagation (ergonomic), and the compiler ensures every failure is either handled or propagated (reliable). The “do this if value is available” semantics of `map`/`flatMap` means error handling code only appears where decisions are made—not at every intermediate step.

Being absolutely clear about failure possibility isn’t pedantry—it’s the foundation of maintainable code.

* * *

## The Traditional (Wrong) Approach

```
[](#cb69-1)// DON'T: Exceptions for business logic
[](#cb69-2)public User loginUser(String email, String password) throws
[](#cb69-3)        InvalidEmailException,
[](#cb69-4)        InvalidPasswordException,
[](#cb69-5)        AccountLockedException,
[](#cb69-6)        CredentialMismatchException {
[](#cb69-7)
[](#cb69-8)    if (!isValidEmail(email)) {
[](#cb69-9)        throw new InvalidEmailException(email);
[](#cb69-10)    }
[](#cb69-11)    // ... more checks throwing exceptions
[](#cb69-12)}
```

**Problems:** - Checked exceptions pollute signatures - Unchecked exceptions are invisible - Exception hierarchies create coupling - Stack traces are expensive for business failures - Testing requires catching exceptions

* * *

## The Result-Based Approach

```
[](#cb70-1)// DO: Failures as typed values
[](#cb70-2)public Result<User> loginUser(String emailRaw, String passwordRaw) {
[](#cb70-3)    return Result.all(Email.email(emailRaw),
[](#cb70-4)                     Password.password(passwordRaw))
[](#cb70-5)                 .flatMap(this::validateAndCheckStatus);
[](#cb70-6)}
[](#cb70-7)
[](#cb70-8)private Result<User> validateAndCheckStatus(Email email, Password password) {
[](#cb70-9)    return checkCredentials(email, password)
[](#cb70-10)            .flatMap(this::checkAccountStatus);
[](#cb70-11)}
[](#cb70-12)
[](#cb70-13)private Result<User> checkAccountStatus(User user) {
[](#cb70-14)    return user.isLocked()
[](#cb70-15)            ? new LoginError.AccountLocked(user.id()).result()
[](#cb70-16)            : Result.success(user);
[](#cb70-17)}
```

* * *

## Defining Typed Errors

Every failure is a `Cause`. Define error types as sealed interfaces:

```
[](#cb71-1)public sealed interface LoginError extends Cause {
[](#cb71-2)    record AccountLocked(UserId userId) implements LoginError {
[](#cb71-3)        @Override
[](#cb71-4)        public String message() {
[](#cb71-5)            return "Account is locked: " + userId;
[](#cb71-6)        }
[](#cb71-7)    }
[](#cb71-8)
[](#cb71-9)    enum InvalidCredentials implements LoginError {
[](#cb71-10)        INSTANCE;
[](#cb71-11)
[](#cb71-12)        @Override
[](#cb71-13)        public String message() {
[](#cb71-14)            return "Invalid email or password";
[](#cb71-15)        }
[](#cb71-16)    }
[](#cb71-17)}
```

**Benefits:** - Exhaustive switch expressions - Compiler checks all cases handled - Clear documentation of failure modes

* * *

## Error Accumulation with Result.all()

`Result.all()` collects validation failures into a `CompositeCause`:

```
[](#cb72-1)// If both fail:
[](#cb72-2)Result.all(Email.email("not-an-email"),
[](#cb72-3)           Password.password("weak"))
[](#cb72-4)      .flatMap(this::processLogin);
[](#cb72-5)
[](#cb72-6)// Returns: CompositeCause([
[](#cb72-7)//   "Invalid email format: not-an-email",
[](#cb72-8)//   "Password must be at least 8 characters"
[](#cb72-9)// ])
```

Users see all errors at once, not fix-and-retry repeatedly.

* * *

## Programming Errors vs Business Errors

### Business Errors → Result/Promise with Typed Cause

**Business errors** are expected outcomes of business rules:

| Error Type | Example | Representation |
| --- | --- | --- |
| Validation failure | Invalid email format | `Result<T>` with `ValidationError` |
| Business rule violation | Insufficient funds | `Result<T>` with `InsufficientFunds` |
| Not found | User doesn’t exist | `Result<T>` with `NotFound` or `Option.none()` |
| External service failure | Payment declined | `Promise<T>` with `PaymentError` |

**Rule:** If a user action can trigger it, it’s a business error—represent with `Result` or `Promise`.

### Programming Errors → Exceptions (Fail Fast)

**Programming errors** indicate bugs that should never reach production:

| Error Type | Example | Handling |
| --- | --- | --- |
| Null invariant violation | Null passed to non-null parameter | `IllegalArgumentException` |
| Impossible state | Switch case that should never happen | `IllegalStateException` |
| Configuration error | Missing required config at startup | Fail fast, don’t start |

**Rule:** Exceptions for programming errors only when there’s no meaningful recovery and the application should terminate or restart.

### Adapter Boundaries → Map to Domain Types

**Adapter code** catches external exceptions and maps to domain types:

```
[](#cb73-1)// Adapter: map null → Option, exception → Cause
[](#cb73-2)public Promise<Option<User>> findById(UserId id) {
[](#cb73-3)    return Promise.lift(
[](#cb73-4)        RepositoryError.DatabaseFailure::new,  // Exception → Cause
[](#cb73-5)        () -> Option.option(jdbcTemplate.queryForObject(...))  // null → Option
[](#cb73-6)    );
[](#cb73-7)}
```

**Rule:** No external exception or null crosses adapter boundaries—map immediately.

* * *

## Adapter Exceptions: The Boundary

Foreign code throws exceptions. **Adapters** catch and convert them:

```
[](#cb74-1)class JpaUserRepository implements UserRepository {
[](#cb74-2)    public Promise<Option<User>> findByEmail(Email email) {
[](#cb74-3)        return Promise.lift(
[](#cb74-4)            RepositoryError.DatabaseFailure::new,  // Convert exception → Cause
[](#cb74-5)            () -> {
[](#cb74-6)                // JDBC/JPA code that might throw
[](#cb74-7)                return Option.option(result);
[](#cb74-8)            });
[](#cb74-9)    }
[](#cb74-10)}
```

Business logic never sees foreign exceptions - only domain errors.

* * *

## Monadic Composition Rules

### map vs flatMap

```
[](#cb75-1)// map: Transform success value (T → U)
[](#cb75-2)result.map(String::toUpperCase)
[](#cb75-3)
[](#cb75-4)// flatMap: Chain operations (T → Result<U>)
[](#cb75-5)result.flatMap(this::validate)
```

Use `flatMap` when the transformation itself can fail.

### Lifting Between Types

```
[](#cb76-1)// Option → Result
[](#cb76-2)option.toResult(cause)
[](#cb76-3)
[](#cb76-4)// Result → Promise
[](#cb76-5)result.async()
[](#cb76-6)
[](#cb76-7)// Full chain
[](#cb76-8)return ValidRequest.validRequest(request)
[](#cb76-9)           .async()              // Result → Promise
[](#cb76-10)           .flatMap(step1)       // Promise chains
[](#cb76-11)           .flatMap(step2);
```

### Forbidden: `Promise<Result<T>>`

`Promise<T>` already carries failures. Never nest:

```
[](#cb77-1)// WRONG
[](#cb77-2)Promise<Result<User>> loadUser(UserId id)
[](#cb77-3)
[](#cb77-4)// RIGHT
[](#cb77-5)Promise<User> loadUser(UserId id)
```

### Allowed: `Result<Option<T>>`

For optional values that must validate when present:

```
[](#cb78-1)Result<Option<ReferralCode>> refCode = ReferralCode.referralCode(input);
[](#cb78-2)// Success(None) = not provided
[](#cb78-3)// Success(Some(code)) = valid code
[](#cb78-4)// Failure(cause) = invalid code
```

Use `Verify.ensureOption()` (Pragmatica Lite 0.9.0+) to implement this pattern:

```
[](#cb79-1)public static Result<Option<ReferralCode>> referralCode(String raw) {
[](#cb79-2)    return Verify.ensureOption(
[](#cb79-3)        Option.option(raw).map(String::trim).filter(s -> !s.isEmpty()),
[](#cb79-4)        PATTERN.asMatchPredicate(),
[](#cb79-5)        INVALID_FORMAT
[](#cb79-6)    ).map(opt -> opt.map(ReferralCode::new));
[](#cb79-7)}
```

* * *

## Testing Errors

```
[](#cb80-1)// Test failure
[](#cb80-2)@Test
[](#cb80-3)void email_rejectsInvalidFormat() {
[](#cb80-4)    Email.email("not-an-email")
[](#cb80-5)         .onSuccess(Assertions::fail);  // Fail if unexpectedly succeeds
[](#cb80-6)}
[](#cb80-7)
[](#cb80-8)// Test success
[](#cb80-9)@Test
[](#cb80-10)void email_acceptsValidFormat() {
[](#cb80-11)    Email.email("user@example.com")
[](#cb80-12)        .onFailure(Assertions::fail)
[](#cb80-13)        .onSuccess(email -> assertEquals("user@example.com", email.value()));
[](#cb80-14)}
[](#cb80-15)
[](#cb80-16)// Test async
[](#cb80-17)@Test
[](#cb80-18)void execute_succeeds() {
[](#cb80-19)    useCase.execute(request)
[](#cb80-20)           .await()
[](#cb80-21)           .onFailure(Assertions::fail)
[](#cb80-22)           .onSuccess(response -> assertEquals("expected", response.value()));
[](#cb80-23)}
```

* * *

## Key Takeaways

1.  **No business exceptions** - Errors are values, not thrown
2.  **Sealed interfaces** - Define exhaustive error types
3.  **Result.all()** - Accumulates all failures, not just first
4.  **Adapters convert** - Exceptions → Cause at boundaries
5.  **Never nest** - `Promise<Result<T>>` is forbidden
6.  **Test functionally** - Use `onSuccess`/`onFailure` assertions

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 2.3: Error accumulation vs short-circuit - Exercise 2.5: Recovery patterns

* * *

## What’s Next

[Chapter 6](ch06-null-policy-recovery.md) covers null policy - when null is acceptable and how to recover from errors with fallback values.

# Chapter 6: Null Policy & Error Recovery

## What You’ll Learn

*   When null is acceptable (and when it isn’t)
*   How to handle null at adapter boundaries
*   Error recovery patterns with fallback values
*   Graceful degradation strategies

**Prerequisites:** [Chapter 5: Error Handling & Composition](ch05-error-handling.md)

* * *

## Null Policy

> **The One Rule:** No null crosses domain boundaries. Incoming null is mapped to `Option.none()`; outbound domain null is forbidden.

In traditional Java, `null` has two meanings: “value not found” and “error occurred.” This ambiguity forces defensive null checks throughout your codebase. JBCT eliminates this confusion with a simple rule: **business logic never returns null**.

### Never Return Null

**Core Rule**: JBCT code NEVER returns null. Use `Option<T>` for optional values.

Traditional Java uses null for semantically different cases - “value not found” and “error occurred.” This creates hidden failure modes:

```
[](#cb81-1)// DON'T: Traditional Java with null
[](#cb81-2)public User findUser(UserId id) {
[](#cb81-3)    return repository.findById(id.value());  // May return null - but why?
[](#cb81-4)}
[](#cb81-5)
[](#cb81-6)// Caller must defend:
[](#cb81-7)User user = findUser(id);
[](#cb81-8)if (user == null) {  // Not found? Error? Database down? Unknown!
[](#cb81-9)    // What happened? We don't know.
[](#cb81-10)}
```

The caller has no idea whether null means “user doesn’t exist” or “database connection failed.” This ambiguity spreads defensive null checks everywhere.

**JBCT eliminates this**:

```
[](#cb82-1)// DO: Using Option
[](#cb82-2)public Option<User> findUser(UserId id) {
[](#cb82-3)    return Option.option(repository.findById(id.value()));
[](#cb82-4)}
[](#cb82-5)
[](#cb82-6)// Caller gets explicit semantics:
[](#cb82-7)findUser(id)
[](#cb82-8)    .onPresent(user -> process(user))
[](#cb82-9)    .onEmpty(() -> handleNotFound());
```

Now the type signature tells us exactly what’s happening: the user might not be present, but the operation itself cannot fail. If the operation can fail (database error), use `Result<Option<User>>` or `Promise<Option<User>>`.

* * *

## When Null IS Acceptable

Null appears only at **adapter boundaries** when interfacing with external code that uses null:

### 1\. Wrapping External APIs

When calling external libraries that may return null, wrap immediately at the adapter boundary:

```
[](#cb83-1)// Adapter layer - wrap nullable external API
[](#cb83-2)public Option<User> findUser(UserId id) {
[](#cb83-3)    User user = repository.findById(id.value());  // External API may return null
[](#cb83-4)    return Option.option(user);  // Wrap immediately: null -> none(), value -> some(value)
[](#cb83-5)}
```

**Spring Data JPA example:**

```
[](#cb84-1)public Option<User> findByEmail(Email email) {
[](#cb84-2)    return Option.option(userRepository.findByEmail(email.value()));  // JPA returns null if not found
[](#cb84-3)}
```

**JDBC ResultSet example:**

```
[](#cb85-1)public Promise<Option<User>> loadUser(UserId id) {
[](#cb85-2)    return Promise.lift(RepositoryError.DatabaseFailure::new,
[](#cb85-3)                        () -> {
[](#cb85-4)                            ResultSet rs = executeQuery(id);
[](#cb85-5)                            User user = rs.next() ? mapUser(rs) : null;  // null if not found
[](#cb85-6)                            return Option.option(user);  // Wrap before returning
[](#cb85-7)                        });
[](#cb85-8)}
```

**Pattern**: `Option.option(nullable)` immediately converts external null to `Option.none()`.

### 2\. Writing to Nullable Database Columns

When persisting to databases with nullable columns, convert `Option<T>` to null for the column:

```
[](#cb86-1)// Adapter layer - JOOQ insert with optional field
[](#cb86-2)public Promise<Unit> saveUser(User user) {
[](#cb86-3)    return Promise.lift(
[](#cb86-4)            RepositoryError.DatabaseFailure::new,
[](#cb86-5)            () -> {
[](#cb86-6)                dsl.insertInto(USERS)
[](#cb86-7)                   .set(USERS.ID, user.id().value())
[](#cb86-8)                   .set(USERS.EMAIL, user.email().value())
[](#cb86-9)                   .set(USERS.REFERRAL_CODE,
[](#cb86-10)                        user.refCode().map(ReferralCode::value).orElse(null))  // Option -> nullable column
[](#cb86-11)                   .execute();
[](#cb86-12)                return Unit.unit();
[](#cb86-13)            });
[](#cb86-14)}
```

**JDBC PreparedStatement example:**

```
[](#cb87-1)PreparedStatement stmt = connection.prepareStatement(
[](#cb87-2)    "INSERT INTO users (id, email, referral_code) VALUES (?, ?, ?)");
[](#cb87-3)stmt.setString(1, user.id().value());
[](#cb87-4)stmt.setString(2, user.email().value());
[](#cb87-5)stmt.setString(3, user.refCode().map(ReferralCode::value).orElse(null));  // Option -> null
```

**Pattern**: `.orElse(null)` ONLY when mapping `Option<T>` to nullable database column.

### 3\. Testing Validation

Use null in test inputs to verify that validation correctly rejects null:

```
[](#cb88-1)@Test
[](#cb88-2)void email_fails_forNull() {
[](#cb88-3)    Email.email(null)  // Test null input
[](#cb88-4)         .onSuccess(Assertions::fail);
[](#cb88-5)}
[](#cb88-6)
[](#cb88-7)@Test
[](#cb88-8)void validRequest_fails_whenFieldNull() {
[](#cb88-9)    var request = new Request("valid@example.com", null);  // Test null password
[](#cb88-10)    ValidRequest.validRequest(request)
[](#cb88-11)                .onSuccess(Assertions::fail);
[](#cb88-12)}
```

**Pattern**: Use null in test inputs to verify validation behavior.

* * *

## When Null is NOT Acceptable

### Never Pass Null Between JBCT Components

Business logic components communicate using domain types, never null:

```
[](#cb89-1)// DON'T: Defensive null checking in business logic
[](#cb89-2)public Result<Order> processOrder(User user, Cart cart) {
[](#cb89-3)    if (user == null || cart == null) {  // Don't do this
[](#cb89-4)        return OrderError.InvalidInput.INSTANCE.result();
[](#cb89-5)    }
[](#cb89-6)    // ...
[](#cb89-7)}
[](#cb89-8)
[](#cb89-9)// DO: Parameters guaranteed non-null by convention
[](#cb89-10)public Result<Order> processOrder(User user, Cart cart) {
[](#cb89-11)    // If cart might be absent, parameter should be Option<Cart>
[](#cb89-12)    // If user might be absent, operation shouldn't be called
[](#cb89-13)    // ...
[](#cb89-14)}
[](#cb89-15)
[](#cb89-16)// DO: Explicit optionality when needed
[](#cb89-17)public Result<Order> processOrder(User user, Option<Cart> cart) {
[](#cb89-18)    return cart.toResult(OrderError.EmptyCart.INSTANCE)
[](#cb89-19)               .flatMap(c -> validateAndProcess(user, c));
[](#cb89-20)}
```

**Rule**: If a value might be absent, use `Option<T>` parameter, never null.

### Never Use Null for “Unknown” vs “Absent”

Null conflates two meanings: “value not set” and “value unknown/error”. Use types to distinguish:

```
[](#cb90-1)// DON'T: Null means "unknown"
[](#cb90-2)public String getUserTheme(UserId id) {
[](#cb90-3)    Theme theme = findTheme(id);
[](#cb90-4)    return theme != null ? theme.name() : null;  // What does null mean?
[](#cb90-5)}
[](#cb90-6)
[](#cb90-7)// DO: Option distinguishes "not set" from "error"
[](#cb90-8)public Option<Theme> getUserTheme(UserId id) {
[](#cb90-9)    return findTheme(id);  // none() = not set, some(theme) = set
[](#cb90-10)}
[](#cb90-11)
[](#cb90-12)// DO: Result distinguishes "not found" from "error"
[](#cb90-13)public Result<Theme> getRequiredTheme(UserId id) {
[](#cb90-14)    return findTheme(id)
[](#cb90-15)        .toResult(ThemeError.NotFound.INSTANCE);
[](#cb90-16)}
```

### Never Return Null from Business Logic

Business logic always uses typed returns:

```
[](#cb91-1)// DON'T: Returning null from business logic
[](#cb91-2)public User enrichUser(User user) {
[](#cb91-3)    Profile profile = loadProfile(user.id());
[](#cb91-4)    if (profile == null) {
[](#cb91-5)        return null;  // Don't return null!
[](#cb91-6)    }
[](#cb91-7)    return user.withProfile(profile);
[](#cb91-8)}
[](#cb91-9)
[](#cb91-10)// DO: Using Option
[](#cb91-11)public Option<User> enrichUser(User user) {
[](#cb91-12)    return loadProfile(user.id())  // Returns Option<Profile>
[](#cb91-13)        .map(profile -> user.withProfile(profile));
[](#cb91-14)}
[](#cb91-15)
[](#cb91-16)// DO: Using Result if enrichment can fail
[](#cb91-17)public Result<User> enrichUser(User user) {
[](#cb91-18)    return loadProfile(user.id())
[](#cb91-19)        .toResult(ProfileError.NotFound.INSTANCE)
[](#cb91-20)        .map(profile -> user.withProfile(profile));
[](#cb91-21)}
```

* * *

## Null Policy Summary

| Context | Null Usage | Correct Approach |
| --- | --- | --- |
| Return values from JBCT code | Never | Use `Option<T>` |
| Parameters between JBCT components | Never | Use `Option<T>` or required types |
| Wrapping external API returns | Allowed | `Option.option(nullable)` immediately |
| Writing to nullable DB columns | Allowed | `.orElse(null)` at write boundary |
| Test inputs for validation | Allowed | Test null rejection |
| “Unknown” or “absent” semantics | Never | Use `Option<T>` or `Result<T>` |

**Core Principle**: Null exists only at system boundaries (adapters). Inside JBCT code, absence is represented by `Option.none()`, never null.

**Why This Matters**: - **Mental Overhead**: No defensive null checks in business logic - **Reliability**: Compiler enforces null handling at boundaries - **Complexity**: Clear semantics - `Option.none()` vs null confusion eliminated

* * *

## Error Recovery Patterns

So far we’ve focused on error **handling** - how to represent and propagate failures through `Result` and `Promise`. But real systems need **recovery** - providing fallback values, retrying operations, or gracefully degrading when errors occur.

### Providing Fallback Values

When an operation fails, you can substitute a default value using `.or()`:

```
[](#cb92-1)// Provide a literal fallback value
[](#cb92-2)public Theme getUserTheme(UserId userId) {
[](#cb92-3)    return loadTheme(userId)  // Returns Option<Theme>
[](#cb92-4)        .or(Theme.DEFAULT);   // Use DEFAULT if none
[](#cb92-5)}
[](#cb92-6)
[](#cb92-7)// Lazy evaluation with supplier
[](#cb92-8)public Config getConfig(String key) {
[](#cb92-9)    return loadFromCache(key)  // Returns Option<Config>
[](#cb92-10)        .or(() -> loadFromDefaults(key))  // Only evaluated if cache miss
[](#cb92-11)        .or(Config.EMPTY);  // Final fallback
[](#cb92-12)}
```

The `.or()` method works with `Option`, `Result`, and `Promise`:

```
[](#cb93-1)// Option<T> - provide value if empty
[](#cb93-2)option.or(defaultValue)
[](#cb93-3)option.or(() -> computeDefault())
[](#cb93-4)
[](#cb93-5)// Result<T> - provide value if failure
[](#cb93-6)result.or(defaultValue)
[](#cb93-7)result.or(() -> computeDefault())
[](#cb93-8)
[](#cb93-9)// Promise<T> - provide value if failure (async)
[](#cb93-10)promise.or(defaultValue)
[](#cb93-11)promise.or(() -> computeDefault())
```

### Fallback to Alternative Operations

Use `.orElse()` when you want to try an alternative operation that returns the same monadic type:

```
[](#cb94-1)// Try cache, then database, then in-memory
[](#cb94-2)public Promise<User> findUser(UserId id) {
[](#cb94-3)    return cacheRepository.find(id)      // Promise<User>
[](#cb94-4)                          .orElse(databaseRepository.find(id))  // Try DB if cache fails
[](#cb94-5)                          .orElse(Promise.success(User.GUEST)); // Final fallback
[](#cb94-6)}
[](#cb94-7)
[](#cb94-8)// Result version
[](#cb94-9)public Result<Config> loadConfig(String key) {
[](#cb94-10)    return loadFromFile(key)      // Result<Config>
[](#cb94-11)        .orElse(loadFromEnv(key))  // Try environment if file fails
[](#cb94-12)        .orElse(Result.success(Config.DEFAULT));
[](#cb94-13)}
```

**The difference**: - `.or(value)` - substitute a plain value - `.orElse(M<T>)` - substitute with another `Result`/`Promise`/`Option`

### Recovering from Specific Failures

Use `.recover()` when you want to transform failures into successes based on the error:

```
[](#cb95-1)public Result<User> findUserOrGuest(UserId id) {
[](#cb95-2)    return userRepository.find(id)
[](#cb95-3)        .recover(this::recoverUserErrors);
[](#cb95-4)}
[](#cb95-5)
[](#cb95-6)private User recoverUserErrors(Cause cause) {
[](#cb95-7)    return switch (cause) {
[](#cb95-8)        case UserError.NotFound ignored -> User.GUEST;
[](#cb95-9)        case UserError.DatabaseError ignored -> User.OFFLINE;
[](#cb95-10)        default -> throw new IllegalStateException("Unexpected error: " + cause);
[](#cb95-11)    };
[](#cb95-12)}
```

**Promise version with async recovery:**

```
[](#cb96-1)public Promise<Order> processOrder(OrderRequest request) {
[](#cb96-2)    return paymentService.charge(request)
[](#cb96-3)        .recover(this::recoverPaymentErrors);
[](#cb96-4)}
[](#cb96-5)
[](#cb96-6)private Promise<Order> recoverPaymentErrors(Cause cause) {
[](#cb96-7)    return switch (cause) {
[](#cb96-8)        case PaymentError.InsufficientFunds ignored ->
[](#cb96-9)            splitPaymentService.process(request);  // Async alternative
[](#cb96-10)        case PaymentError.TemporaryFailure ignored ->
[](#cb96-11)            Promise.success(request).flatMap(paymentService::charge);  // Retry once
[](#cb96-12)        default -> cause.promise();  // Can't recover
[](#cb96-13)    };
[](#cb96-14)}
```

* * *

## Graceful Degradation Pattern

Combine recovery with feature detection:

```
[](#cb97-1)public Promise<Dashboard> loadDashboard(UserId userId) {
[](#cb97-2)    return Promise.all(loadUserProfile(userId),
[](#cb97-3)                       loadRecentOrders(userId).or(List.of()),
[](#cb97-4)                       loadRecommendations(userId).or(List.of()))
[](#cb97-5)                  .map(Dashboard::new);
[](#cb97-6)}
```

Here, profile is **required** (must succeed), but orders and recommendations gracefully degrade to empty lists if unavailable. The dashboard still loads with reduced functionality.

### Real-World Example: Configuration with Fallbacks

```
[](#cb98-1)public interface LoadConfig {
[](#cb98-2)    record Config(String apiUrl, int timeout, boolean retryEnabled) {}
[](#cb98-3)
[](#cb98-4)    Promise<Config> load();
[](#cb98-5)
[](#cb98-6)    static LoadConfig loadConfig(LoadFromFile loadFile,
[](#cb98-7)                                 LoadFromEnv loadEnv) {
[](#cb98-8)        return () -> loadFile.apply()
[](#cb98-9)                             .orElse(loadEnv.apply())
[](#cb98-10)                             .or(() -> new Config("https://api.default.com", 30, true));
[](#cb98-11)    }
[](#cb98-12)}
```

This tries file configuration, falls back to environment variables, and finally uses hardcoded defaults. Each layer adds resiliency.

* * *

## Recovery Patterns Summary

| Pattern | Method | Use When |
| --- | --- | --- |
| Default value | `.or(value)` | Fixed fallback available |
| Lazy default | `.or(() -> compute())` | Fallback is expensive to create |
| Alternative operation | `.orElse(M<T>)` | Try another source/service |
| Conditional recovery | `.recover(cause -> ...)` | Transform specific errors to success |
| Graceful degradation | `.or(emptyValue)` | Feature optional, show partial data |

### When NOT to Recover

Don’t use recovery to hide genuine errors:

```
[](#cb99-1)// DON'T: Swallowing errors silently
[](#cb99-2)loadCriticalData(id)
[](#cb99-3)    .or(Data.EMPTY)  // User never knows load failed!
[](#cb99-4)
[](#cb99-5)// DO: Let critical errors propagate
[](#cb99-6)loadCriticalData(id)  // Caller handles the error
```

Recovery is for **expected** failures where degradation makes sense (cache miss, optional feature unavailable). Critical errors should propagate so callers can handle them appropriately.

**Why This Matters**: - **Reliability**: Systems stay operational despite partial failures - **User Experience**: Graceful degradation better than total failure - **Complexity**: Clear recovery strategy, no hidden try-catch blocks

* * *

## Key Takeaways

1.  **Null only at boundaries** - Adapters wrap external nulls in `Option`
2.  **Option.option(nullable)** - Immediate conversion at entry point
3.  **Never return null** - Use `Option<T>` for optional values
4.  **.or() for defaults** - Provide fallback values
5.  **.orElse() for alternatives** - Try another operation
6.  **.recover() for conditional** - Transform specific failures to success

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 2.5: Recovery patterns - Exercise 5.2: Graceful degradation scenarios

* * *

## What’s Next

[Chapter 7](ch07-basic-patterns.md) introduces the basic structural patterns - Leaf, Condition, and Iteration - that handle 80% of your daily coding needs.

# Chapter 7: Basic Patterns & Structure

## What You’ll Learn

*   When to extract functions (mechanical rules, not judgment calls)
*   How to keep code at a single level of abstraction
*   The three basic patterns: Leaf, Condition, Iteration
*   Zone-based naming conventions

**Prerequisites:** [Chapter 6: Null Policy & Error Recovery](ch06-null-policy-recovery.md)

* * *

## Single Pattern Per Function

Every function implements exactly one pattern from a fixed catalog: Leaf, Sequencer, Fork-Join, Condition, or Iteration. (Aspects are the exception—they decorate other patterns.)

**Why?** Cognitive load. When reading a function, you should recognize its shape immediately. If it’s a Sequencer, you know it chains dependent steps linearly. If it’s Fork-Join, you know it runs independent operations and combines results. Mixing patterns within a function creates mixed abstraction levels and forces readers to hold multiple mental models simultaneously.

This rule has a mechanical benefit: it makes refactoring deterministic. When a function grows beyond one pattern, you extract the second pattern into its own function. There’s no subjective judgment about “is this too complex?” - if you’re doing two patterns, split it.

**Why by criteria:** - **Mental Overhead**: One pattern per function means immediate recognition - no mental model switching (+2) - **Complexity**: Mechanical refactoring rule eliminates subjective debates about “too complex” (+2) - **Design Impact**: Forces proper abstraction layers - no mixing orchestration with computation (+2)

### The Pain of Mixed Patterns

Before showing violations, understand the **concrete problems** that mixing patterns causes:

**Testing becomes brittle:**

```
[](#cb100-1)// Mixed pattern function
[](#cb100-2)public Result<Report> generateReport(ReportRequest request) {
[](#cb100-3)    // Validates, fetches in parallel, computes, formats - all in one
[](#cb100-4)}
[](#cb100-5)
[](#cb100-6)// To test, you need:
[](#cb100-7)// 1\. Valid request setup
[](#cb100-8)// 2\. Mock for fetchUserData
[](#cb100-9)// 3\. Mock for fetchSalesData
[](#cb100-10)// 4\. Verify computeMetrics logic
[](#cb100-11)// 5\. Verify formatReport logic
[](#cb100-12)// Can't test parts independently - it's all or nothing
```

**Debugging is unclear:**

```
[](#cb101-1)// Stack trace points to generateReport() line 45
[](#cb101-2)// But which step failed? Validation? Fork-Join fetch? Compute? Format?
[](#cb101-3)// You can't tell without stepping through the whole function
```

**Reuse is impossible:**

```
[](#cb102-1)// Another use case needs the same Fork-Join fetch logic
[](#cb102-2)// But it's buried inside generateReport()
[](#cb102-3)// Can't reuse it - have to copy-paste or refactor
```

**With single pattern per function:** - Each function is independently testable - Patterns are reusable across use cases - Failures are localized (stack trace says “fetchReportData failed”) - Structure is predictable and scannable

### Example Violation

```
[](#cb103-1)// DON'T: Mixing Sequencer and Fork-Join
[](#cb103-2)public Result<Report> generateReport(ReportRequest request) {
[](#cb103-3)    return ValidRequest.validRequest(request)
[](#cb103-4)                       .flatMap(valid -> {
[](#cb103-5)                           // Sequencer starts here
[](#cb103-6)                           var userData = fetchUserData(valid.userId());
[](#cb103-7)                           var salesData = fetchSalesData(valid.dateRange());
[](#cb103-8)
[](#cb103-9)                           // Wait, now we're doing Fork-Join?
[](#cb103-10)                           return Result.all(userData, salesData)
[](#cb103-11)                                        .flatMap((user, sales) -> computeMetrics(user, sales))
[](#cb103-12)                                        .flatMap(this::formatReport);  // Back to Sequencer
[](#cb103-13)                       });
[](#cb103-14)}
```

This function starts as a Sequencer (validate -> fetch -> compute -> format), but `fetchUserData` and `fetchSalesData` are independent, so we suddenly do a Fork-Join in the middle. Mixed abstraction levels. Hard to test. Unclear at a glance what the function does.

### Corrected

```
[](#cb104-1)// DO: One pattern per function
[](#cb104-2)public Result<Report> generateReport(ReportRequest request) {
[](#cb104-3)    return ValidRequest.validRequest(request)
[](#cb104-4)                       .flatMap(this::fetchReportData)
[](#cb104-5)                       .flatMap(this::computeMetrics)
[](#cb104-6)                       .flatMap(this::formatReport);
[](#cb104-7)}
[](#cb104-8)
[](#cb104-9)private Result<ReportData> fetchReportData(ValidRequest request) {
[](#cb104-10)    // This function is a Fork-Join
[](#cb104-11)    return Result.all(fetchUserData(request.userId()),
[](#cb104-12)                      fetchSalesData(request.dateRange()))
[](#cb104-13)                 .map(ReportData::new);
[](#cb104-14)}
```

Now `generateReport` is a pure Sequencer (validate -> fetch -> compute -> format), and `fetchReportData` is a pure Fork-Join. Each function has one clear job.

### Mechanical Refactoring

If you’re writing a Sequencer and realize step 3 needs to do a Fork-Join internally, extract step 3 into its own function that implements Fork-Join. The original Sequencer stays clean.

**Rule of thumb**: One pattern per function. If you see two patterns, extract one.

* * *

## Single Level of Abstraction

**The rule:** No complex logic inside lambdas. Lambdas passed to `map`, `flatMap`, and similar combinators may contain only: - Method references (e.g., `Email::new`, `this::processUser`) - Single method calls with parameter forwarding (e.g., `param -> someMethod(outerParam, param)`)

**Why?** Lambdas are composition points, not implementation locations. When you bury logic inside a lambda, you hide abstraction levels and make the code harder to read, test, and reuse. Extract complex logic to named functions - the name documents intent, the function becomes testable in isolation, and the composition chain stays flat and readable.

**Why by criteria:** - **Mental Overhead**: Flat composition chains scan linearly - no descending into nested logic (+2) - **Business/Technical Ratio**: Named functions document intent; anonymous lambdas hide it (+2) - **Complexity**: Each function testable in isolation; buried lambda logic requires testing through container (+2)

### Anti-Pattern

```
[](#cb105-1)// DON'T: Complex logic inside lambda
[](#cb105-2)return fetchUser(userId)
[](#cb105-3)    .flatMap(user -> {
[](#cb105-4)        if (user.isActive() && user.hasPermission("admin")) {
[](#cb105-5)            return loadAdminDashboard(user)
[](#cb105-6)                .map(dashboard -> {
[](#cb105-7)                    var summary = new Summary(
[](#cb105-8)                        dashboard.metrics(),
[](#cb105-9)                        dashboard.alerts().stream()
[](#cb105-10)                            .filter(Alert::isUrgent)
[](#cb105-11)                            .toList()
[](#cb105-12)                    );
[](#cb105-13)                    return new Response(user, summary);
[](#cb105-14)                });
[](#cb105-15)        } else {
[](#cb105-16)            return AccessError.InsufficientPermissions.INSTANCE.promise();
[](#cb105-17)        }
[](#cb105-18)    });
```

This lambda contains: conditional logic, nested map, stream processing, object construction. Mixed abstraction levels. Hard to test. Hard to read.

### Correct Approach

```
[](#cb106-1)// DO: Extract to named functions
[](#cb106-2)return fetchUser(userId)
[](#cb106-3)    .flatMap(this::checkAdminAccess)
[](#cb106-4)    .flatMap(this::loadAdminDashboard)
[](#cb106-5)    .map(this::buildResponse);
[](#cb106-6)
[](#cb106-7)private Promise<User> checkAdminAccess(User user) {
[](#cb106-8)    return isActiveAdministrator(user)
[](#cb106-9)            ? Promise.success(user)
[](#cb106-10)            : AccessError.InsufficientPermissions.INSTANCE.promise();
[](#cb106-11)}
[](#cb106-12)
[](#cb106-13)private boolean isActiveAdministrator(User user) {
[](#cb106-14)    return user.isActive() && user.hasPermission("admin");
[](#cb106-15)}
[](#cb106-16)
[](#cb106-17)private Response buildResponse(Dashboard dashboard) {
[](#cb106-18)    var urgentAlerts = filterUrgentAlerts(dashboard.alerts());
[](#cb106-19)    var summary = new Summary(dashboard.metrics(), urgentAlerts);
[](#cb106-20)    return new Response(dashboard.user(), summary);
[](#cb106-21)}
[](#cb106-22)
[](#cb106-23)private List<Alert> filterUrgentAlerts(List<Alert> alerts) {
[](#cb106-24)    return alerts.stream()
[](#cb106-25)                 .filter(Alert::isUrgent)
[](#cb106-26)                 .toList();
[](#cb106-27)}
```

Now the top-level chain reads linearly: fetch -> check access -> load dashboard -> build response. Each step is named, testable, and at a single abstraction level.

### Allowed in Lambdas

**Method references:**

```
[](#cb107-1).map(Email::new)
[](#cb107-2).flatMap(this::saveUser)
[](#cb107-3).map(User::id)
```

**Single method call with parameter forwarding:**

```
[](#cb108-1).flatMap(user -> checkPermissions(requiredRole, user))
[](#cb108-2).map(order -> calculateTotal(taxRate, order))
```

### Forbidden in Lambdas

*   Conditionals (`if`, ternary, `switch`)
*   Try-catch blocks
*   Multi-statement blocks
*   Object construction beyond simple factory calls

**No ternaries** (they are the Condition pattern):

```
[](#cb109-1)// DON'T: Ternary in lambda
[](#cb109-2).flatMap(user -> user.isPremium()
[](#cb109-3)    ? applyPremiumDiscount(user)
[](#cb109-4)    : applyStandardDiscount(user))
[](#cb109-5)
[](#cb109-6)// DO: Extract to named function
[](#cb109-7).flatMap(this::applyApplicableDiscount)
[](#cb109-8)
[](#cb109-9)private Result<Discount> applyApplicableDiscount(User user) {
[](#cb109-10)    return user.isPremium()
[](#cb109-11)        ? applyPremiumDiscount(user)
[](#cb109-12)        : applyStandardDiscount(user);
[](#cb109-13)}
```

* * *

## The Three-Zone Framework

Maintaining “single level of abstraction” becomes mechanical when you think of your codebase in three distinct zones, each with its own vocabulary:

**Zone 1 (Use Case Level)** - High-level business goals: - `RegisterUser.execute()`, `ProcessOrder.execute()`, `LoadDashboard.execute()` - One Zone 1 function per use case - the entry point

**Zone 2 (Orchestration Level)** - Coordinating steps that break down the goal: - Step interfaces in Sequencer/Fork-Join patterns - Verbs: `validate`, `process`, `handle`, `transform`, `apply`, `check`, `load`, `save`, `manage`, `configure`, `initialize` - Examples: `ValidateInput.apply()`, `ProcessPayment.apply()`, `HandleNotification.apply()`

**Zone 3 (Implementation Level)** - Concrete technical operations: - Business and adapter leaves - Verbs: `get`, `set`, `fetch`, `parse`, `calculate`, `convert`, `hash`, `format`, `encode`, `decode`, `extract`, `split`, `join`, `log`, `send`, `receive`, `read`, `write`, `add`, `remove` - Examples: `hashPassword()`, `parseJson()`, `fetchFromDatabase()`, `calculateTax()`

**The key insight:** Functions at each zone should only call functions from the same zone or one level down. Zone 2 functions call other Zone 2 steps or Zone 3 leaves. Zone 3 leaves perform atomic operations. This creates natural layering.

**Example - Maintaining zone consistency:**

```
[](#cb110-1)// GOOD - All steps at Zone 2 (orchestration level)
[](#cb110-2)public Promise<Response> execute(Request request) {
[](#cb110-3)    return ValidRequest.validRequest(request)              // Zone 2: validate
[](#cb110-4)                       .async()
[](#cb110-5)                       .flatMap(this::processCredentials)  // Zone 2: process
[](#cb110-6)                       .flatMap(this::saveUser)            // Zone 2: save
[](#cb110-7)                       .flatMap(this::sendConfirmation);   // Zone 2: send
[](#cb110-8)}
[](#cb110-9)
[](#cb110-10)// BAD - Mixing Zone 2 and Zone 3 in same chain
[](#cb110-11)public Promise<Response> execute(Request request) {
[](#cb110-12)    return ValidRequest.validRequest(request)              // Zone 2
[](#cb110-13)                       .async()
[](#cb110-14)                       .flatMap(this::hashPassword)        // Zone 3 - too specific!
[](#cb110-15)                       .flatMap(this::saveUser)            // Zone 2
[](#cb110-16)                       .flatMap(this::fetchConfirmToken);  // Zone 3 - too specific!
[](#cb110-17)}
```

In the bad example, `hashPassword` and `fetchConfirmToken` are Zone 3 operations (concrete technical details). They should be wrapped in Zone 2 steps like `processCredentials` and `sendConfirmation`.

### The Stepdown Rule Test

A simple way to verify your abstraction levels: read your code aloud by adding “to” before each function. It should sound like a natural narrative:

```
[](#cb111-1)// Reading this aloud:
[](#cb111-2)// "To execute, we validate the request,
[](#cb111-3)//  then we process payment,
[](#cb111-4)//  then we send confirmation."
[](#cb111-5)return ValidRequest.validRequest(request)
[](#cb111-6)                   .async()
[](#cb111-7)                   .flatMap(this::processPayment)
[](#cb111-8)                   .flatMap(this::sendConfirmation);
```

If adding “to” makes it sound awkward or overly detailed (“to hash password, then to save to database, then to fetch from cache”), you’re mixing abstraction levels.

* * *

## Pattern: Leaf

**Definition:** A **Leaf** (an atomic operation with no substeps) is the smallest unit of processing - a function that does one thing and has no internal steps. It’s either a business leaf (pure computation) or an adapter leaf (I/O or side effects).

**Rationale (by criteria):** - **Mental Overhead**: Atomic operations have no internal steps to track - immediate comprehension (+2) - **Business/Technical Ratio**: Business leaves are pure domain logic; adapter leaves isolate technical concerns (+2) - **Complexity**: Single responsibility per leaf - no hidden interactions (+2) - **Reliability**: Pure business leaves are deterministic and easily testable (+1)

### Business Leaves

Business leaves are pure functions that transform data or enforce business rules:

```
[](#cb112-1)// Simple calculation leaf
[](#cb112-2)public static Price calculateDiscount(Price original, Percentage rate) {
[](#cb112-3)    return original.multiply(rate);
[](#cb112-4)}
[](#cb112-5)
[](#cb112-6)// Domain rule enforcement leaf
[](#cb112-7)public static Result<Unit> checkInventory(Product product, Quantity requested) {
[](#cb112-8)    return product.availableQuantity().isGreaterThanOrEqual(requested)
[](#cb112-9)        ? Result.unitResult()
[](#cb112-10)        : InsufficientInventory.cause(product.id(), requested);
[](#cb112-11)}
[](#cb112-12)
[](#cb112-13)// Data transformation leaf
[](#cb112-14)public static OrderSummary toSummary(Order order) {
[](#cb112-15)    return new OrderSummary(order.id(),
[](#cb112-16)                            order.totalAmount(),
[](#cb112-17)                            order.items().size());
[](#cb112-18)}
```

If there’s no I/O and no side effects, it’s a business leaf. Keep each leaf focused on one transformation or one business rule.

### Adapter Leaves

Adapter leaves integrate with external systems: databases, HTTP clients, message queues, file systems. They map foreign errors to domain Causes.

```
[](#cb113-1)public interface UserRepository {
[](#cb113-2)    Promise<Option<User>> findByEmail(Email email);
[](#cb113-3)}
[](#cb113-4)
[](#cb113-5)// Adapter leaf implementation
[](#cb113-6)class PostgresUserRepository implements UserRepository {
[](#cb113-7)    private final DataSource dataSource;
[](#cb113-8)
[](#cb113-9)    public Promise<Option<User>> findByEmail(Email email) {
[](#cb113-10)        return Promise.lift(RepositoryError.DatabaseFailure::new,
[](#cb113-11)                            () -> {
[](#cb113-12)                                try (var conn = dataSource.getConnection();
[](#cb113-13)                                     var stmt = conn.prepareStatement(
[](#cb113-14)                                         "SELECT * FROM users WHERE email = ?")) {
[](#cb113-15)
[](#cb113-16)                                    stmt.setString(1, email.value());
[](#cb113-17)                                    var rs = stmt.executeQuery();
[](#cb113-18)
[](#cb113-19)                                    return rs.next() ? mapUser(rs) : null;
[](#cb113-20)                                }
[](#cb113-21)                            }).map(Option::option);
[](#cb113-22)    }
[](#cb113-23)
[](#cb113-24)    private User mapUser(ResultSet rs) throws SQLException {
[](#cb113-25)        return new User(/* ... */);
[](#cb113-26)    }
[](#cb113-27)}
```

The adapter catches `SQLException` and wraps it in `RepositoryError.DatabaseFailure`, a domain `Cause`. Callers never see `SQLException`.

### Thread Safety

Leaf operations are **thread-safe through confinement** - each invocation operates independently with its own local state. Mutable local variables (accumulators, builders, working objects) are safe within a leaf because they never escape the function scope. Input parameters must be treated as read-only.

### Placement Rules

**If a leaf is only used by one caller**, keep it nearby (same file, same package).

**If it’s reused**, move it immediately to the nearest `shared` package. Don’t defer - tech debt accumulates when shared code stays in wrong locations.

* * *

## Pattern: Condition

**Definition:** Condition represents branching logic based on data. The key: express conditions as values, not control-flow side effects. Keep branches at the same abstraction level.

**Rationale (by criteria):** - **Mental Overhead**: Conditions as expressions - evaluates to single value, not control flow scatter (+2) - **Business/Technical Ratio**: Branch logic mirrors domain rules, not imperative jumps (+2) - **Complexity**: Same abstraction level per branch - prevents tangled logic (+2) - **Reliability**: Type-checked branches ensure all cases return compatible types (+2)

### Simple Conditional

```
[](#cb114-1)// DO: Condition as expression returning the monad
[](#cb114-2)Result<Discount> calculateDiscount(Order order) {
[](#cb114-3)    return order.isPremiumUser()
[](#cb114-4)        ? premiumDiscount(order)      // returns Result<Discount>
[](#cb114-5)        : standardDiscount(order);    // returns Result<Discount>
[](#cb114-6)}
```

Both branches return the same type (`Result<Discount>`), so the ternary is just choosing which function to call. No mixed abstractions.

### Pattern Matching

Using Java’s switch expressions:

```
[](#cb115-1)Result<ShippingCost> calculateShipping(Order order, ShippingMethod method) {
[](#cb115-2)    return switch (method) {
[](#cb115-3)        case STANDARD -> standardShipping(order);
[](#cb115-4)        case EXPRESS -> expressShipping(order);
[](#cb115-5)        case OVERNIGHT -> overnightShipping(order);
[](#cb115-6)    };
[](#cb115-7)}
```

Each case returns `Result<ShippingCost>`. The switch expression evaluates to a single result.

### Nested Conditions

Avoid deep nesting by extracting subdecisions into named functions:

```
[](#cb116-1)// DON'T: Nested ternaries
[](#cb116-2)return user.isPremium()
[](#cb116-3)    ? (order.total().greaterThan(THRESHOLD)
[](#cb116-4)        ? largeOrderPremiumDiscount(order)
[](#cb116-5)        : smallOrderPremiumDiscount(order))
[](#cb116-6)    : (order.total().greaterThan(THRESHOLD)
[](#cb116-7)        ? largeOrderStandardDiscount(order)
[](#cb116-8)        : smallOrderStandardDiscount(order));
```

Extract:

```
[](#cb117-1)// DO: Extract nested logic
[](#cb117-2)Result<Discount> calculateDiscount(User user, Order order) {
[](#cb117-3)    return user.isPremium()
[](#cb117-4)        ? premiumDiscount(order)
[](#cb117-5)        : standardDiscount(order);
[](#cb117-6)}
[](#cb117-7)
[](#cb117-8)private Result<Discount> premiumDiscount(Order order) {
[](#cb117-9)    return order.total().greaterThan(THRESHOLD)
[](#cb117-10)        ? largeOrderPremiumDiscount(order)
[](#cb117-11)        : smallOrderPremiumDiscount(order);
[](#cb117-12)}
[](#cb117-13)
[](#cb117-14)private Result<Discount> standardDiscount(Order order) {
[](#cb117-15)    return order.total().greaterThan(THRESHOLD)
[](#cb117-16)        ? largeOrderStandardDiscount(order)
[](#cb117-17)        : smallOrderStandardDiscount(order);
[](#cb117-18)}
```

Now each function has one level of branching. Much clearer.

### Condition with Monads

Use `filter` for cleaner composition when applicable:

```
[](#cb118-1)// DON'T: Ternary in lambda
[](#cb118-2)return fetchUser(userId)
[](#cb118-3)    .flatMap(user -> user.isActive()
[](#cb118-4)        ? processActiveUser(user)
[](#cb118-5)        : UserError.InactiveAccount.INSTANCE.result());
[](#cb118-6)
[](#cb118-7)// DO: Using filter (preferred)
[](#cb118-8)return fetchUser(userId)
[](#cb118-9)    .filter(User::isActive, UserError.InactiveAccount.INSTANCE)
[](#cb118-10)    .flatMap(this::processActiveUser);
```

* * *

## Pattern: Iteration

**Definition:** Iteration processes collections, streams, or recursive structures. Prefer functional combinators over explicit loops. Keep transformations pure.

**Rationale (by criteria):** - **Mental Overhead**: Declarative combinators state intent; imperative loops require tracing (+2) - **Business/Technical Ratio**: map/filter express business logic; loops are iteration mechanics (+2) - **Complexity**: Functional composition eliminates index management and loop state (+2) - **Reliability**: Pure transformations have no side effects - deterministic and testable (+2)

### Mapping Collections

```
[](#cb119-1)// Transforming a list of raw inputs to domain objects
[](#cb119-2)Result<List<Email>> parseEmails(List<String> rawEmails) {
[](#cb119-3)    return Result.allOf(rawEmails.stream()
[](#cb119-4)                                 .map(Email::email)
[](#cb119-5)                                 .toList());
[](#cb119-6)}
```

`Result.allOf` aggregates a `List<Result<Email>>` into `Result<List<Email>>`. If any email is invalid, you get a `CompositeCause` with all failures.

### Filtering and Transforming

```
[](#cb120-1)List<ActiveUser> activeUsers(List<User> users) {
[](#cb120-2)    return users.stream()
[](#cb120-3)                .filter(User::isActive)
[](#cb120-4)                .map(this::toActiveUser)
[](#cb120-5)                .toList();
[](#cb120-6)}
[](#cb120-7)
[](#cb120-8)private ActiveUser toActiveUser(User user) {
[](#cb120-9)    return new ActiveUser(user.id(), user.email());
[](#cb120-10)}
```

Pure transformation, no side effects, returns `List<ActiveUser>` (type `T`, not `Result`, because this can’t fail).

### Async Iteration

When processing collections with async operations, decide between sequential and parallel:

**Sequential:**

```
[](#cb121-1)// Process orders one at a time
[](#cb121-2)Promise<List<Receipt>> processOrders(List<Order> orders) {
[](#cb121-3)    Promise<List<Receipt>> result = Promise.success(List.of());
[](#cb121-4)
[](#cb121-5)    for (Order order : orders) {
[](#cb121-6)        result = result.flatMap2(this::appendReceipt, order);
[](#cb121-7)    }
[](#cb121-8)
[](#cb121-9)    return result;
[](#cb121-10)}
[](#cb121-11)
[](#cb121-12)private Promise<List<Receipt>> appendReceipt(List<Receipt> receipts, Order order) {
[](#cb121-13)    return processOrder(order)
[](#cb121-14)               .map(receipt -> appendToList(receipts, receipt));
[](#cb121-15)}
```

**Parallel (when orders are independent):**

```
[](#cb122-1)// Process orders in parallel
[](#cb122-2)Promise<List<Receipt>> processOrders(List<Order> orders) {
[](#cb122-3)    return Promise.allOf(orders.stream()
[](#cb122-4)                               .map(this::processOrder)
[](#cb122-5)                               .toList());
[](#cb122-6)}
```

Use parallel when operations are independent.

### Common Mistakes

**DON’T mix side effects into stream operations:**

```
[](#cb123-1)// DON'T: Side effect in the map
[](#cb123-2)users.stream()
[](#cb123-3)    .map(user -> {
[](#cb123-4)        logger.info("Processing user: {}", user.id());  // Side effect!
[](#cb123-5)        return processUser(user);
[](#cb123-6)    })
[](#cb123-7)    .toList();
```

**DON’T use imperative loops when combinators exist:**

```
[](#cb124-1)// DON'T: Imperative accumulation
[](#cb124-2)List<Result<Email>> results = new ArrayList<>();
[](#cb124-3)for (String raw : rawEmails) {
[](#cb124-4)    results.add(Email.email(raw));
[](#cb124-5)}
[](#cb124-6)
[](#cb124-7)// DO: Declarative collection
[](#cb124-8)Result<List<Email>> emails = Result.allOf(
[](#cb124-9)    rawEmails.stream().map(Email::email).toList()
[](#cb124-10));
```

* * *

## Naming Conventions

Consistent naming reduces cognitive load and makes code self-documenting.

### Factory Method Naming

Factories are always named after their type, lowercase-first (camelCase):

```
[](#cb125-1)Email.email("user@example.com")
[](#cb125-2)Password.password("Secret123")
[](#cb125-3)AccountId.accountId("ACC-001")
[](#cb125-4)UserId.userId(raw)
```

This pattern is grep-friendly: searching for `Email.email` finds all email construction sites.

### Validated Input Naming

Use the `Valid` prefix (not `Validated`) for types representing validated inputs:

```
[](#cb126-1)// DO: Use Valid prefix
[](#cb126-2)record ValidRequest(Email email, Password password) {
[](#cb126-3)    static Result<ValidRequest> validRequest(Request raw) { ... }
[](#cb126-4)}
[](#cb126-5)
[](#cb126-6)// DON'T: Use Validated prefix (too verbose)
[](#cb126-7)record ValidatedRequest(...)
```

### Zone-Based Naming Vocabulary

**Zone 2 Verbs (Step Interfaces - Orchestration):**

| Verb | When to Use | Example |
| --- | --- | --- |
| `validate` | Checking rules/constraints | `ValidateInput` |
| `process` | Transforming or interpreting data | `ProcessPayment` |
| `handle` | Coordinating reactions to events | `HandleRefund` |
| `load` | Retrieving data for use | `LoadUserProfile` |
| `save` | Persisting changes | `SaveOrder` |
| `check` | Verifying conditions | `CheckInventory` |

**Zone 3 Verbs (Leaves - Implementation):**

| Verb | Typical Use | Example |
| --- | --- | --- |
| `get` | Retrieve a value | `getTimestamp()` |
| `fetch` | Pull from external source | `fetchWeatherData()` |
| `parse` | Break down structured input | `parseJson()` |
| `calculate` | Perform computation | `calculateTax()` |
| `hash` | Cryptographic transformation | `hashPassword()` |
| `format` | Build structured output | `formatDate()` |
| `send` | Transmit over network | `sendEmail()` |

### Test Naming

Follow the pattern: `methodName_outcome_condition`

```
[](#cb127-1)void validRequest_succeeds_forValidInput()
[](#cb127-2)void validRequest_fails_forInvalidEmail()
[](#cb127-3)void execute_succeeds_forValidInput()
[](#cb127-4)void execute_fails_whenEmailAlreadyExists()
```

* * *

## Key Takeaways

1.  **Single Pattern Per Function** - One pattern per function, extract if you see two
2.  **Single Level of Abstraction** - No complex logic in lambdas, only method references or simple forwarding
3.  **Leaf** - Atomic unit: pure computation (business) or I/O (adapter)
4.  **Condition** - Branching as values, same type from all branches
5.  **Iteration** - Functional combinators over collections, pure transformations
6.  **Zone-based naming** - Use appropriate verbs for each abstraction level

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 3.1: Pattern identification - Exercise 3.2: Leaf extraction - Exercise 3.4: Zone-based naming

* * *

## What’s Next

[Chapter 8](ch08-advanced-patterns.md) covers advanced patterns - Sequencer, Fork-Join, and Aspects - that compose these basic patterns into sophisticated workflows.

# Chapter 8: Advanced Patterns

## What You’ll Learn

*   **Sequencer**: The workhorse pattern for chaining dependent steps
*   **Fork-Join**: Parallel composition for independent operations
*   **Aspects**: Adding cross-cutting concerns without mixing responsibilities

**Prerequisites:** [Chapter 7: Basic Patterns & Structure](ch07-basic-patterns.md)

* * *

## Pattern: Sequencer

**Definition:** A Sequencer chains dependent steps linearly using `map` and `flatMap`. Each step’s output feeds the next step’s input. This is the primary pattern for use case implementation.

**Rationale (by criteria):** - **Mental Overhead**: Linear flow, 2-5 steps fits short-term memory capacity - predictable structure (+3) - **Business/Technical Ratio**: Steps mirror business process language - reads like requirements (+3) - **Complexity**: Fail-fast semantics, each step isolated and testable (+2) - **Design Impact**: Forces proper step decomposition, prevents monolithic functions (+2)

### The 2-5 Rule

A Sequencer should have 2 to 5 steps. Fewer than 2, and it’s probably just a Leaf. More than 5, and it needs decomposition—extract sub-sequencers or group steps.

> The rule is intended to limit local complexity. It is derived from the average size of short-term memory - 7 +/- 2 elements.

**Domain requirements take precedence:** Some functions inherently require more steps because the domain demands it. Value object factories may need multiple validation and normalization steps to ensure invariants. Fork-Join patterns may need to aggregate 6+ independent results because that’s what the domain requires. Don’t artificially fit domain logic into numeric rules. The 2-5 guideline helps you recognize when to consider refactoring, but domain semantics always win.

### Sync Example

```
[](#cb128-1)public interface ProcessOrder {
[](#cb128-2)    record Request(String orderId, String paymentToken) {}
[](#cb128-3)    record Response(OrderConfirmation confirmation) {}
[](#cb128-4)
[](#cb128-5)    Result<Response> execute(Request request);
[](#cb128-6)
[](#cb128-7)    interface ValidateInput {
[](#cb128-8)        Result<ValidRequest> apply(Request raw);
[](#cb128-9)    }
[](#cb128-10)    interface ReserveInventory {
[](#cb128-11)        Result<Reservation> apply(ValidRequest req);
[](#cb128-12)    }
[](#cb128-13)    interface ProcessPayment {
[](#cb128-14)        Result<Payment> apply(Reservation reservation);
[](#cb128-15)    }
[](#cb128-16)    interface ConfirmOrder {
[](#cb128-17)        Result<Response> apply(Payment payment);
[](#cb128-18)    }
[](#cb128-19)
[](#cb128-20)    static ProcessOrder processOrder(ValidateInput validate,
[](#cb128-21)                                     ReserveInventory reserve,
[](#cb128-22)                                     ProcessPayment processPayment,
[](#cb128-23)                                     ConfirmOrder confirm) {
[](#cb128-24)        return request -> validate.apply(request)                 // Step 1
[](#cb128-25)                                  .flatMap(reserve::apply)        // Step 2
[](#cb128-26)                                  .flatMap(processPayment::apply) // Step 3
[](#cb128-27)                                  .flatMap(confirm::apply);       // Step 4
[](#cb128-28)    }
[](#cb128-29)}
```

Four steps, each a single-method interface. The `execute()` body reads top-to-bottom: validate -> reserve -> process payment -> confirm. Each step returns `Result<T>`, so we chain with `flatMap`. If any step fails, the chain short-circuits and returns the failure.

### Async Example

Same structure, different types:

```
[](#cb129-1)public Promise<Response> execute(Request request) {
[](#cb129-2)    return ValidateInput.validate(request)              // returns Result<ValidInput>
[](#cb129-3)                        .async()                        // lift to Promise<ValidInput>
[](#cb129-4)                        .flatMap(reserve::apply)        // returns Promise<Reservation>
[](#cb129-5)                        .flatMap(processPayment::apply) // returns Promise<Payment>
[](#cb129-6)                        .flatMap(confirm::apply);       // returns Promise<Response>
[](#cb129-7)}
```

Validation is synchronous (returns `Result`), so we lift it to `Promise` using `.async()`. The rest of the chain is async.

### When to Extract Sub-Sequencers

If a step grows complex internally, extract it to its own interface with a nested structure. Suppose `processPayment` actually needs to: authorize card -> capture funds -> record transaction. That’s three dependent steps - a Sequencer. Extract:

```
[](#cb130-1)// Original step interface
[](#cb130-2)interface ProcessPayment {
[](#cb130-3)    Promise<Payment> apply(Reservation reservation);
[](#cb130-4)}
[](#cb130-5)
[](#cb130-6)// Implementation delegates to a sub-sequencer
[](#cb130-7)interface CreditCardPaymentProcessor extends ProcessPayment {
[](#cb130-8)    interface AuthorizeCard {
[](#cb130-9)        Promise<Reservation> apply(Reservation reservation);
[](#cb130-10)    }
[](#cb130-11)    interface CaptureFunds {
[](#cb130-12)        Promise<Reservation> apply(Reservation reservation);
[](#cb130-13)    }
[](#cb130-14)    interface RecordTransaction {
[](#cb130-15)        Promise<Payment> apply(Reservation reservation);
[](#cb130-16)    }
[](#cb130-17)
[](#cb130-18)    static CreditCardPaymentProcessor creditCardPaymentProcessor(
[](#cb130-19)            AuthorizeCard authorizeCard,
[](#cb130-20)            CaptureFunds captureFunds,
[](#cb130-21)            RecordTransaction recordTransaction) {
[](#cb130-22)        return (reservation) -> authorizeCard.apply(reservation)
[](#cb130-23)                                             .flatMap(captureFunds::apply)
[](#cb130-24)                                             .flatMap(recordTransaction::apply);
[](#cb130-25)    }
[](#cb130-26)}
```

Now `CreditCardPaymentProcessor` is itself a Sequencer with three steps. The top-level use case remains a clean 4-step chain.

### Thread Safety

Sequencer pattern is **thread-safe through sequential execution** - steps execute one after another, never in parallel. Each step is isolated and thread-confined. Mutable local state within individual steps is safe because steps don’t overlap. Data passed between steps must be immutable.

### Common Mistakes

**DON’T nest logic inside flatMap:**

```
[](#cb131-1)// DON'T: Business logic buried in lambda
[](#cb131-2)return validate.apply(request)
[](#cb131-3)    .flatMap(valid -> {
[](#cb131-4)        if (valid.isPremiumUser()) {
[](#cb131-5)            return applyDiscount(valid)
[](#cb131-6)                .flatMap(reserve::apply);
[](#cb131-7)        } else {
[](#cb131-8)            return reserve.apply(valid);
[](#cb131-9)        }
[](#cb131-10)    })
[](#cb131-11)    .flatMap(processPayment::apply);
```

Extract:

```
[](#cb132-1)// DO: Extract to named function
[](#cb132-2)return validate.apply(request)
[](#cb132-3)               .flatMap(this::applyDiscountIfEligible)
[](#cb132-4)               .flatMap(reserve::apply)
[](#cb132-5)               .flatMap(processPayment::apply);
[](#cb132-6)
[](#cb132-7)private Result<ValidRequest> applyDiscountIfEligible(ValidRequest request) {
[](#cb132-8)    return request.isPremiumUser()
[](#cb132-9)        ? applyDiscount(request)
[](#cb132-10)        : Result.success(request);
[](#cb132-11)}
```

**DON’T mix Fork-Join inside a Sequencer without extraction:**

```
[](#cb133-1)// DON'T: Suddenly doing Fork-Join mid-sequence
[](#cb133-2)return validate.apply(request)
[](#cb133-3)    .flatMap(valid -> {
[](#cb133-4)        var userPromise = fetchUser(valid.userId());
[](#cb133-5)        var productPromise = fetchProduct(valid.productId());
[](#cb133-6)        return Promise.all(userPromise, productPromise)
[](#cb133-7)            .flatMap((user, product) -> reserve.apply(user, product));
[](#cb133-8)    })
[](#cb133-9)    .flatMap(processPayment::apply);
```

Extract:

```
[](#cb134-1)// DO: Extract Fork-Join to its own step
[](#cb134-2)return validate.apply(request)
[](#cb134-3)               .flatMap(this::fetchUserAndProduct)  // Fork-Join inside
[](#cb134-4)               .flatMap(reserve::apply)
[](#cb134-5)               .flatMap(processPayment::apply);
[](#cb134-6)
[](#cb134-7)private Promise<ReservationInput> fetchUserAndProduct(ValidRequest request) {
[](#cb134-8)    return Promise.all(fetchUser(request.userId()),
[](#cb134-9)                       fetchProduct(request.productId()))
[](#cb134-10)                  .map(ReservationInput::new);
[](#cb134-11)}
```

* * *

## Pattern: Fork-Join

**Definition:** Fork-Join (also known as Fan-Out-Fan-In) executes independent operations concurrently and combines their results. Use it when you have parallel work with no dependencies between branches.

**Rationale (by criteria):** - **Mental Overhead**: Parallel execution explicit in structure - no hidden concurrency (+2) - **Complexity**: Independence constraint acts as design validator - forces proper data organization (+3) - **Reliability**: Type system prevents dependent operations from being parallelized (+2) - **Design Impact**: Reveals coupling issues - dependencies surface as compile errors (+3)

### Two Primary Flavors

**1\. Result.all(…) - Synchronous aggregation:**

Not concurrent, just collects multiple Results:

```
[](#cb135-1)// Validating multiple independent fields
[](#cb135-2)Result<ValidRequest> validated = Result.all(Email.email(raw.email()),
[](#cb135-3)                                            Password.password(raw.password()),
[](#cb135-4)                                            AccountId.accountId(raw.accountId()))
[](#cb135-5)                                       .flatMap(ValidRequest::new);
```

If all succeed, you get a tuple of values to pass to the combiner. If any fail, you get a `CompositeCause` containing all failures (not just the first).

**2\. Promise.all(…) - Parallel async execution:**

```
[](#cb136-1)// Running independent I/O operations in parallel
[](#cb136-2)Promise<Dashboard> buildDashboard(UserId userId) {
[](#cb136-3)    return Promise.all(userService.fetchProfile(userId),
[](#cb136-4)                       orderService.fetchRecentOrders(userId),
[](#cb136-5)                       notificationService.fetchUnread(userId))
[](#cb136-6)                  .map(this::createDashboard);
[](#cb136-7)}
[](#cb136-8)
[](#cb136-9)private Dashboard createDashboard(Profile profile,
[](#cb136-10)                                  List<Order> orders,
[](#cb136-11)                                  List<Notification> notifications) {
[](#cb136-12)    return new Dashboard(profile, orders, notifications);
[](#cb136-13)}
```

All three fetches run concurrently. The Promise completes when all inputs complete successfully or fails immediately if any input fails.

### Special Fork-Join Cases

**1. `Promise.allOf(Collection<Promise<T>>)` - Resilient collection:**

```
[](#cb137-1)// Fetching data from dynamic number of sources
[](#cb137-2)Promise<Report> generateSystemReport(List<ServiceId> services) {
[](#cb137-3)    var healthChecks = services.stream()
[](#cb137-4)                               .map(healthCheckService::check)
[](#cb137-5)                               .toList();
[](#cb137-6)
[](#cb137-7)    return Promise.allOf(healthChecks)
[](#cb137-8)                  .map(this::createReport);
[](#cb137-9)}
[](#cb137-10)
[](#cb137-11)private Report createReport(List<Result<HealthStatus>> results) {
[](#cb137-12)    var successes = results.stream()
[](#cb137-13)                           .filter(Result::isSuccess)
[](#cb137-14)                           .map(Result::value)
[](#cb137-15)                           .toList();
[](#cb137-16)    var failures = results.stream()
[](#cb137-17)                          .filter(Result::isFailure)
[](#cb137-18)                          .map(Result::cause)
[](#cb137-19)                          .toList();
[](#cb137-20)    return new Report(successes, failures);
[](#cb137-21)}
```

Returns `Promise<List<Result<T>>>` - unlike `Promise.all()` which fails fast, `allOf()` waits for all promises to complete and collects both successes and failures.

**2\. `Promise.any(Promise<T>...)` - First-success wins:**

```
[](#cb138-1)// Racing multiple data sources
[](#cb138-2)Promise<ExchangeRate> fetchRate(Currency from, Currency to) {
[](#cb138-3)    return Promise.any(primaryRateProvider.getRate(from, to),
[](#cb138-4)                       secondaryRateProvider.getRate(from, to),
[](#cb138-5)                       fallbackRateProvider.getRate(from, to));
[](#cb138-6)}
```

Returns the first successfully completed Promise, canceling remaining operations.

### Independence and Thread Safety

Fork-Join has a crucial constraint: **all branches must be truly independent with immutable inputs**.

> **Caution:** Type-level independence is not the same as infrastructure-level independence. Operations that appear independent at the code level may conflict at the infrastructure level: - **Database locks:** Two queries may deadlock on shared rows - **Rate limits:** Parallel API calls may exhaust quotas - **Connection pools:** Parallel operations may compete for connections - **Transactions:** Operations in the same transaction may have ordering requirements
> 
> Validate infrastructure constraints, not just type signatures.

**Design Independence** - When you try to write a Fork-Join and discover hidden dependencies, it reveals design issues: - Data redundancy: If branch A needs data from branch B, maybe that data should be provided upfront - Incorrect data organization: Dependencies signal that data is split across sources when it should be colocated - Missing abstraction: Hidden dependencies may indicate a missing concept

**Thread Safety** - Parallel execution requires immutable inputs: - All input data MUST be immutable - no shared mutable state between parallel branches - Local mutable state is safe - thread-confined accumulators, builders within each branch are fine - Results must be immutable - data returned from branches will be combined

Example design issue:

```
[](#cb139-1)// DON'T: Logical dependency
[](#cb139-2)Promise.all(fetchUserProfile(userId),      // Returns User
[](#cb139-3)            fetchUserPreferences(userId))  // Needs User.timezone from profile!
```

Example thread safety violation:

```
[](#cb140-1)// DON'T: Shared mutable state
[](#cb140-2)private final DiscountContext context = new DiscountContext();  // Mutable
[](#cb140-3)
[](#cb140-4)Promise<Result> calculate() {
[](#cb140-5)    return Promise.all(applyBogo(cart, context),       // DATA RACE
[](#cb140-6)                       applyPercentOff(cart, context))  // Both mutate context
[](#cb140-7)                  .map(this::merge);
[](#cb140-8)}
[](#cb140-9)
[](#cb140-10)// DO: Immutable inputs
[](#cb140-11)Promise<Result> calculate(Cart cart) {
[](#cb140-12)    return Promise.all(applyBogo(cart),        // Immutable cart
[](#cb140-13)                       applyPercentOff(cart))  // Immutable cart
[](#cb140-14)                  .map(this::mergeDiscounts);
[](#cb140-15)}
```

### Common Mistakes

**DON’T use Fork-Join when there are hidden dependencies:**

```
[](#cb141-1)// DON'T: These aren't actually independent
[](#cb141-2)Promise.all(allocateInventory(orderId),   // Might lock inventory
[](#cb141-3)            chargePayment(paymentToken))  // Should only charge if inventory succeeds
```

If inventory allocation fails, we’ve already charged the customer. Use a Sequencer.

**DON’T ignore errors in Fork-Join branches:**

```
[](#cb142-1)// DON'T: Silently swallowing failures
[](#cb142-2)Promise.all(fetchPrimary(id).recover(err -> Option.none()),  // Hides failure
[](#cb142-3)            fetchSecondary(id).recover(err -> Option.none()))
```

Model the “best-effort” case explicitly with proper types.

* * *

## Pattern: Aspects (Decorators)

**Definition:** Aspects are higher-order functions that wrap steps or use cases to add cross-cutting concerns - retry, timeout, logging, metrics - without changing business semantics.

**Rationale (by criteria):** - **Mental Overhead**: Cross-cutting concerns separated from business logic - clear responsibilities (+3) - **Business/Technical Ratio**: Business logic stays pure; technical concerns isolated in decorators (+3) - **Complexity**: Composable aspects via higher-order functions - no framework magic (+2) - **Design Impact**: Business logic independent of retry/metrics/logging - testable separately (+3)

### Placement

**Local concerns:** Wrap individual steps when the aspect applies to just that step. Example: retry only on external API calls.

**Cross-cutting concerns:** Wrap the entire `execute()` method. Example: metrics for the whole use case.

### Example: Retry Aspect on a Step

```
[](#cb143-1)public interface FetchUserProfile {
[](#cb143-2)    Promise<Profile> apply(UserId userId);
[](#cb143-3)}
[](#cb143-4)
[](#cb143-5)// Step implementation
[](#cb143-6)class UserServiceClient implements FetchUserProfile {
[](#cb143-7)    public Promise<Profile> apply(UserId userId) {
[](#cb143-8)        return httpClient.get("/users/" + userId.value())
[](#cb143-9)                         .map(this::parseProfile);
[](#cb143-10)    }
[](#cb143-11)}
[](#cb143-12)
[](#cb143-13)// Applying a retry aspect at construction:
[](#cb143-14)static ProcessUserData processUserData(..., UserServiceClient userServiceClient, ...) {
[](#cb143-15)    var retryPolicy = RetryPolicy.builder()
[](#cb143-16)                                 .maxAttempts(3)
[](#cb143-17)                                 .backoff(exponential(100, 2.0))
[](#cb143-18)                                 .build();
[](#cb143-19)
[](#cb143-20)    return new processUserData(validateInput,
[](#cb143-21)                               withRetry(retryPolicy, userServiceClient),  // Decorated
[](#cb143-22)                               processData);
[](#cb143-23)}
```

### Example: Metrics Aspect on Use Case

```
[](#cb144-1)public interface LoginUser {
[](#cb144-2)    Promise<LoginResponse> execute(LoginRequest request);
[](#cb144-3)
[](#cb144-4)    static LoginUser loginUser(...) {
[](#cb144-5)        var rawUseCase = new loginUser(...);
[](#cb144-6)        var metricsPolicy = MetricsPolicy.metricsPolicy("user_login");
[](#cb144-7)        return withMetrics(metricsPolicy, rawUseCase);
[](#cb144-8)    }
[](#cb144-9)}
```

### Composing Multiple Aspects

Order matters. Typical ordering (outermost to innermost): 1. Metrics/Logging (outermost - observe everything) 2\. Timeout (global deadline) 3\. CircuitBreaker (fail-fast if system is degraded) 4\. Retry (per-attempt) 5\. RateLimit (throttle requests) 6\. Business logic (innermost)

```
[](#cb145-1)var decoratedStep = withMetrics(metricsPolicy,
[](#cb145-2)    withTimeout(timeoutPolicy,
[](#cb145-3)        withCircuitBreaker(breakerPolicy,
[](#cb145-4)            withRetry(retryPolicy, rawStep))));
```

### Operational Semantics

**Timeout Behavior:** - **Logical timeout:** Promise resolves with `TimeoutError` after deadline - **Actual cancellation:** The underlying operation may continue running - **Rule:** Timeout doesn’t guarantee resource cleanup—idempotent operations are safer

```
[](#cb146-1)// Timeout resolves promise but underlying HTTP call may complete
[](#cb146-2)promise.timeout(TimeSpan.seconds(5))  // Returns TimeoutError after 5s
[](#cb146-3)       .onFailure(this::logTimeout);   // Operation may still finish
```

**Retry Semantics:** - **Idempotency required:** Retried operations must be safe to repeat - **State changes:** Non-idempotent operations (money transfers, order creation) need idempotency keys - **Backoff:** Exponential backoff prevents thundering herd

```
[](#cb147-1)// Safe: idempotent read
[](#cb147-2)withRetry(policy, () -> fetchUser(id))
[](#cb147-3)
[](#cb147-4)// Unsafe without idempotency key: creates duplicate
[](#cb147-5)withRetry(policy, () -> createOrder(request))  // DON'T
[](#cb147-6)
[](#cb147-7)// Safe: idempotent write with key
[](#cb147-8)withRetry(policy, () -> createOrder(request, idempotencyKey))  // DO
```

**Composition Order Semantics:**

| Order | Meaning |
| --- | --- |
| Metrics → Timeout → Retry → Operation | Metrics count total time; timeout applies to all retries |
| Timeout → Metrics → Retry → Operation | Timeout per attempt; metrics count each retry |
| Retry → Timeout → Operation | Each attempt has own timeout |

**Rule:** Define composition order based on what you want to observe and control. Document your choice.

### Testing Aspects

Test aspects in isolation with synthetic steps. Use case tests remain aspect-agnostic:

```
[](#cb148-1)// Aspect test (isolated)
[](#cb148-2)@Test
[](#cb148-3)void retryAspect_retriesOnFailure() {
[](#cb148-4)    var failingStep = new FlakyStep(2);  // Fail times
[](#cb148-5)    var retryPolicy = RetryPolicy.maxAttempts(3);
[](#cb148-6)    var decorated = withRetry(retryPolicy, failingStep);
[](#cb148-7)
[](#cb148-8)    var result = decorated.apply(input).await();
[](#cb148-9)
[](#cb148-10)    assertTrue(result.isSuccess());
[](#cb148-11)    assertEquals(3, failingStep.invocationCount());
[](#cb148-12)}
[](#cb148-13)
[](#cb148-14)// Use case test (aspect-agnostic)
[](#cb148-15)@Test
[](#cb148-16)void loginUser_success() {
[](#cb148-17)    var useCase = LoginUser.loginUser(mockValidate, mockCheckCreds, mockGenerateToken);
[](#cb148-18)
[](#cb148-19)    var result = useCase.execute(validRequest).await();
[](#cb148-20)
[](#cb148-21)    assertTrue(result.isSuccess());
[](#cb148-22)    // No assertions about retries, timeouts, etc.
[](#cb148-23)}
```

### Common Mistakes

**DON’T mix aspect logic into business logic:**

```
[](#cb149-1)// DON'T: Retry logic inside the step
[](#cb149-2)Promise<Profile> fetchProfile(UserId id) {
[](#cb149-3)    return retryWithBackoff(() -> httpClient.get("/users/" + id.value()))
[](#cb149-4)            .map(this::parseProfile);
[](#cb149-5)}
```

Extract to an aspect decorator.

**DO keep aspects composable and reusable:**

```
[](#cb150-1)static <I, O> Fn1<I, Promise<O>> withTimeout(TimeSpan timeout, Fn1<I, Promise<O>> step) {
[](#cb150-2)    return input -> step.apply(input).timeout(timeout);
[](#cb150-3)}
[](#cb150-4)
[](#cb150-5)static <I, O> Fn1<I, Promise<O>> withRetry(RetryPolicy policy, Fn1<I, Promise<O>> step) {
[](#cb150-6)    return input -> retryLogic(policy, () -> step.apply(input));
[](#cb150-7)}
```

### Logging Philosophy

**Principle:** Logging belongs only at **leaves** and **external boundaries**. Composition code has zero logging.

**Rationale:** - Leaves perform real work - they’re the only places where operations can fail or produce observable effects - Boundaries are where we interact with external systems - the points of uncertainty - Everything else is composition - deterministic routing of values through the system

**Implementation:** Wrap leaf implementations in a logging aspect at construction:

```
[](#cb151-1)public interface UserRepository {
[](#cb151-2)    Promise<User> findById(UserId id);
[](#cb151-3)
[](#cb151-4)    static UserRepository create(DataSource ds, Logger log) {
[](#cb151-5)        var impl = new UserRepositoryImpl(ds);
[](#cb151-6)        return withLogging(log, "UserRepository", impl);
[](#cb151-7)    }
[](#cb151-8)}
[](#cb151-9)
[](#cb151-10)public static UserRepository withLogging(Logger log, String name, UserRepository impl) {
[](#cb151-11)    return id -> {
[](#cb151-12)        var correlationId = CorrelationContext.current();
[](#cb151-13)        log.debug("[{}] {}.findById input: {}", correlationId, name, id);
[](#cb151-14)
[](#cb151-15)        return impl.findById(id)
[](#cb151-16)                   .onSuccess(user -> log.debug("[{}] {}.findById success", correlationId, name))
[](#cb151-17)                   .onFailure(cause -> log.warn("[{}] {}.findById failure: {}", correlationId, name, cause.message()));
[](#cb151-18)    };
[](#cb151-19)}
```

**What gets logged:** - Input parameters (sanitized for sensitive data) - Outcome (success or failure cause) - Correlation ID for request tracing

**Anti-pattern - scattered logging in composition:**

```
[](#cb152-1)// DON'T: Logging in composition code
[](#cb152-2)return validateInput(request)
[](#cb152-3)    .onSuccess(v -> log.info("Validated"))  // Noise
[](#cb152-4)    .flatMap(this::fetchUser)
[](#cb152-5)    .onSuccess(u -> log.info("Fetched user"))  // Noise
[](#cb152-6)    .flatMap(this::processOrder);
[](#cb152-7)
[](#cb152-8)// DO: Wrap leaves at construction
[](#cb152-9)static ProcessOrder processOrder(UserRepository users, Logger log) {
[](#cb152-10)    return new ProcessOrderImpl(withLogging(log, "users", users));
[](#cb152-11)}
```

* * *

## Key Takeaways

1.  **Sequencer** - Chain dependent steps (2-5 rule), fail-fast semantics
2.  **Fork-Join** - Parallel independent operations, strict immutability requirement
3.  **Aspects** - Cross-cutting concerns as decorators, tested separately
4.  **Logging Philosophy** - Logging only at leaves and boundaries, composition is transparent
5.  **Independence validation** - Prevents Fork-Join mistakes; use Sequencer if unsure
6.  **Pattern composition** - Sequencers call Fork-Joins, Aspects wrap both

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 3.3: Pattern composition - Exercise 3.5: Aspect implementation

* * *

## What’s Next

[Chapter 9](ch09-thread-safety.md) provides a comprehensive thread safety quick reference, consolidating all the thread safety rules across JBCT patterns.

# Chapter 9: Thread Safety

## What You’ll Learn

*   Core thread safety principles in JBCT
*   Pattern-by-pattern safety guarantees
*   Promise resolution semantics
*   Common mistakes and how to avoid them

**Prerequisites:** [Chapter 8: Advanced Patterns](ch08-advanced-patterns.md)

* * *

## Core Rules

**Two principles ensure thread safety:**

1.  **Immutable at boundaries**: All data passed between functions (parameters, return values) must be immutable
2.  **Thread confinement**: Mutable state is allowed within a single-threaded execution path (sequential patterns)

These rules mean you can use mutable local variables in sequential code, but any data shared across threads must be immutable.

* * *

## Pattern-by-Pattern Safety Guarantees

### Leaf (Sequential)

Thread-safe through sequential execution:

```
[](#cb153-1)// SAFE: Mutable local state OK
[](#cb153-2)public Result<Order> calculateTotal(Cart cart) {
[](#cb153-3)    var total = 0.0;  // Mutable local variable
[](#cb153-4)    for (Item item : cart.items()) {
[](#cb153-5)        total += item.price();  // Sequential mutation
[](#cb153-6)    }
[](#cb153-7)    return Result.success(new Order(cart, total));
[](#cb153-8)}
```

*   Mutable local state confined to single thread
*   Input (`cart`) is read-only
*   Output (`Order`) is immutable

### Sequencer (Sequential)

Thread-safe, mutable local state OK:

```
[](#cb154-1)// SAFE: Each step runs sequentially
[](#cb154-2)return ValidRequest.validRequest(request)
[](#cb154-3)                   .async()
[](#cb154-4)                   .flatMap(checkEmail::apply)    // Runs first
[](#cb154-5)                   .flatMap(hashPassword::apply)  // Runs second
[](#cb154-6)                   .flatMap(saveUser::apply);     // Runs third
```

*   Steps execute in order, never concurrently
*   Each step can use mutable local state
*   Promise resolution is a synchronization point

### Fork-Join (Parallel)

Requires strict immutability:

```
[](#cb155-1)// SAFE: Immutable cart passed to both operations
[](#cb155-2)Promise.all(applyBogo(cart),          // cart is immutable
[](#cb155-3)            applyPercentOff(cart))    // cart is immutable
[](#cb155-4)       .map(this::mergeDiscounts);
[](#cb155-5)
[](#cb155-6)// UNSAFE: Shared mutable context creates data race
[](#cb155-7)private final DiscountContext context = new DiscountContext();  // Mutable!
[](#cb155-8)Promise.all(applyBogo(cart, context),     // Both access context
[](#cb155-9)            applyPercentOff(cart, context))  // DATA RACE
[](#cb155-10)       .map(this::merge);
```

*   All parallel operations receive immutable inputs
*   No shared mutable state between parallel operations
*   Results merged after all complete

### Condition (Sequential)

Thread-safe, no shared mutable state:

```
[](#cb156-1)// SAFE: Only one branch executes
[](#cb156-2)return user.isPremium()
[](#cb156-3)    ? processPremium(user)
[](#cb156-4)    : processBasic(user);
```

*   Branches never execute concurrently
*   Each branch can use mutable local state

### Iteration (Sequential)

Thread-safe through sequential processing:

```
[](#cb157-1)// SAFE: Stream processes sequentially
[](#cb157-2)var results = items.stream()
[](#cb157-3)                   .map(Item::validate)  // Sequential
[](#cb157-4)                   .toList();
```

*   Stream operations sequential by default
*   Parallel streams require immutable inputs (use with caution)

### Aspects (Inherits)

Safety depends on wrapped operation:

```
[](#cb158-1)// SAFE: Aspect preserves underlying safety
[](#cb158-2)var retried = withRetry(retryPolicy, sequentialStep);  // Still sequential
[](#cb158-3)var retried = withRetry(retryPolicy, forkJoinStep);    // Still parallel
```

*   Decorators don’t change concurrency model
*   Retry/timeout/metrics don’t introduce shared state

* * *

## Promise Resolution Thread Safety

Promise resolution has exactly-once semantics with built-in synchronization:

```
[](#cb159-1)Promise<User> promise = Promise.promise();
[](#cb159-2)
[](#cb159-3)// Thread 1
[](#cb159-4)promise.resolve(Result.success(user));
[](#cb159-5)
[](#cb159-6)// Thread 2
[](#cb159-7)promise.resolve(Result.success(anotherUser));  // Ignored - already resolved
```

*   First `resolve()` wins, subsequent calls ignored
*   `flatMap`/`map` chains wait for resolution before executing
*   Resolution acts as synchronization point for sequential chains

* * *

## Common Mistakes

### Mistake 1: Shared Mutable State in Fork-Join

```
[](#cb160-1)// WRONG: Mutable list shared across parallel operations
[](#cb160-2)private final List<String> errors = new ArrayList<>();
[](#cb160-3)
[](#cb160-4)Promise.all(validateEmail(request).onFailure(e -> errors.add(e.message())),     // DATA RACE
[](#cb160-5)            validatePassword(request).onFailure(e -> errors.add(e.message())))  // DATA RACE
[](#cb160-6)       .map(this::process);
```

**Fix:** Use immutable results and combine after:

```
[](#cb161-1)// CORRECT: Each operation returns its own result
[](#cb161-2)Promise.all(validateEmail(request),
[](#cb161-3)            validatePassword(request))
[](#cb161-4)       .map((emailResult, passwordResult) -> combineResults(emailResult, passwordResult));
```

### Mistake 2: Assuming Sequential Execution in Promise.all

```
[](#cb162-1)// WRONG: Assuming order
[](#cb162-2)Promise.all(incrementCounter(), incrementCounter())  // May execute concurrently!
```

Promise.all runs operations in parallel. If order matters, use Sequencer.

### Mistake 3: Mutating Input Parameters

```
[](#cb163-1)// WRONG: Mutating shared input
[](#cb163-2)private Promise<Discount> applyDiscount(Cart cart) {
[](#cb163-3)    cart.setSubtotal(cart.subtotal().subtract(discount));  // DATA RACE
[](#cb163-4)    return Promise.success(new Discount(discount));
[](#cb163-5)}
[](#cb163-6)
[](#cb163-7)// CORRECT: Create new instances
[](#cb163-8)private Promise<Discount> applyDiscount(Cart cart) {
[](#cb163-9)    var discountAmount = calculateDiscountFor(cart);
[](#cb163-10)    return Promise.success(new Discount(cart, discountAmount));  // Returns new data
[](#cb163-11)}
```

* * *

## Independence Validation Checklist

Use this checklist to verify parallel operations are truly independent:

If any checkbox fails, use Sequencer instead of Fork-Join.

* * *

## When to Use Mutable State

**Allowed:** - Local variables in sequential patterns (Leaf, Sequencer, Condition, Iteration) - Builders constructing immutable objects - Accumulators in sequential loops

**Forbidden:** - Shared across parallel operations (Fork-Join) - Passed between use case steps - Returned from functions (return immutable copy instead)

* * *

## Testing for Thread Safety

Mutable test fixtures are acceptable - tests execute sequentially:

```
[](#cb164-1)// SAFE: Test-scoped mutable state
[](#cb164-2)@Test
[](#cb164-3)void execute_succeeds_forValidInput() {
[](#cb164-4)    List<String> callLog = new ArrayList<>();  // Mutable, but test-scoped
[](#cb164-5)
[](#cb164-6)    CheckEmail checkEmail = req -> {
[](#cb164-7)        callLog.add("email");  // Sequential execution
[](#cb164-8)        return Promise.success(req);
[](#cb164-9)    };
[](#cb164-10)
[](#cb164-11)    useCase.execute(request)
[](#cb164-12)           .await()
[](#cb164-13)           .onSuccess(response -> assertEquals(List.of("email"), callLog));
[](#cb164-14)}
```

Tests are sequential, so mutable fixtures don’t create races.

* * *

## Quick Reference Table

| Pattern | Execution | Local Mutable State | Input Requirements |
| --- | --- | --- | --- |
| Leaf | Sequential | Safe | Read-only |
| Sequencer | Sequential | Safe | Immutable between steps |
| Fork-Join | Parallel | Safe (confined) | Strictly immutable |
| Condition | Sequential | Safe | Read-only |
| Iteration | Sequential | Safe | Read-only |
| Aspects | Inherits | Inherits | Inherits |

* * *

## Key Takeaways

1.  **Immutable at boundaries** - Parameters and return values always immutable
2.  **Thread confinement** - Mutable local state safe in sequential patterns
3.  **Fork-Join strictness** - All inputs must be immutable, no shared state
4.  **Promise resolution** - Exactly-once, acts as synchronization point
5.  **Independence validation** - Use checklist before parallelizing
6.  **When in doubt** - Use Sequencer; premature parallelization causes subtle bugs

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 3.6: Identifying thread safety issues - Exercise 3.7: Converting unsafe code to safe patterns

* * *

## What’s Next

[Chapter 10](ch10-testing-philosophy.md) introduces the testing philosophy - evolutionary testing and integration-first approaches that work naturally with JBCT patterns.

# Chapter 10: Testing Philosophy

## What You’ll Learn

*   Why integration-first testing aligns with functional composition
*   The evolutionary process: stub everything -> implement incrementally -> production-ready
*   How to handle complex test inputs with builders and factories
*   When you still need unit tests

**Prerequisites:** [Chapter 9: Thread Safety](ch09-thread-safety.md)

* * *

## The Problem with Traditional Testing

### Traditional Approach: Component-Focused

Most Java testing follows this pattern:

```
[](#cb165-1)// Separate tests for each component
[](#cb165-2)class ValidateInputTest {
[](#cb165-3)    @Test void emailValidation() { /* ... */ }
[](#cb165-4)    @Test void passwordValidation() { /* ... */ }
[](#cb165-5)    // 10 tests
[](#cb165-6)}
[](#cb165-7)
[](#cb165-8)class CheckCredentialsTest {
[](#cb165-9)    @Test void validCredentials() { /* ... */ }
[](#cb165-10)    @Test void invalidCredentials() { /* ... */ }
[](#cb165-11)    // 5 tests
[](#cb165-12)}
[](#cb165-13)
[](#cb165-14)class CheckAccountStatusTest {
[](#cb165-15)    @Test void activeAccount() { /* ... */ }
[](#cb165-16)    @Test void inactiveAccount() { /* ... */ }
[](#cb165-17)    // 3 tests
[](#cb165-18)}
[](#cb165-19)
[](#cb165-20)class GenerateTokenTest {
[](#cb165-21)    @Test void tokenGeneration() { /* ... */ }
[](#cb165-22)    // 4 tests
[](#cb165-23)}
[](#cb165-24)
[](#cb165-25)// Total: 22 tests, never testing them TOGETHER
```

**Problems:** 1\. **Doesn’t test composition** - Steps work individually but fail when chained 2. **Doesn’t test error propagation** - How do failures bubble through the chain? 3\. **Doesn’t test actual behavior** - Tests verify components, not use cases 4\. **Brittle** - Interface changes break all tests, even when behavior unchanged 5. **False confidence** - All tests pass, production fails because integration untested

### What We Actually Want to Test

When a user calls `UserLogin.execute(request)`, we care about:

*   **Does the request get validated correctly?**
*   **Do all steps execute in order?**
*   **Does each step failure propagate correctly?**
*   **Do branch conditions work as expected?**
*   **Does the complete behavior match requirements?**

These are **integration questions**, not unit questions.

* * *

## Philosophy: Integration-First Testing

### The Core Principle

**Test assembled use cases, not isolated components.**

Your use case is a composition of steps. Test the composition. Stub only at adapter boundaries (database, HTTP, external services). Test all business logic together.

**Why by criteria:** - **Mental Overhead**: One test suite per use case, not per component (+2). Test names directly map to scenarios. - **Business/Technical Ratio**: Tests read like behavior specifications, not technical assertions (+3). - **Reliability**: Tests verify actual end-to-end behavior, not isolated fragments (+3). - **Complexity**: Fewer test contexts, clearer boundaries (business vs adapters) (+2).

### The Three Testing Layers

**1\. Value Objects: Unit Tests (100% coverage)**

Value objects are pure, isolated, and enforce invariants. Test them comprehensively:

```
[](#cb166-1)class EmailTest {
[](#cb166-2)    @ParameterizedTest
[](#cb166-3)    @ValueSource(strings = {"bad", "no@domain", "@missing", "CAPS@TEST.COM"})
[](#cb166-4)    void email_rejectsInvalidFormat(String raw) {
[](#cb166-5)        Email.email(raw).onSuccess(Assertions::fail);
[](#cb166-6)    }
[](#cb166-7)
[](#cb166-8)    @Test
[](#cb166-9)    void email_normalizesToLowercase() {
[](#cb166-10)        Email.email("USER@EXAMPLE.COM")
[](#cb166-11)             .onSuccess(email -> assertEquals("user@example.com", email.value()));
[](#cb166-12)    }
[](#cb166-13)}
```

**Why unit test here?** Value objects have zero dependencies. They’re pure functions. Unit testing is natural.

**2\. Business Leaves: Unit Tests if Complex**

Simple business leaves (single calculation, simple transformation) don’t need isolated tests - they’re covered by use case integration tests.

Complex business leaves (rich algorithms, many branches) deserve unit tests:

```
[](#cb167-1)class PricingEngineTest {
[](#cb167-2)    @Test void volumeDiscount_appliesAtThreshold() { /* ... */ }
[](#cb167-3)    @Test void combinedDiscounts_stackCorrectly() { /* ... */ }
[](#cb167-4)    @Test void edgeCases_handleGracefully() { /* ... */ }
[](#cb167-5)}
```

**Guideline:** If a leaf has 3+ conditional branches or complex logic, write unit tests.

**3\. Use Cases: Integration Tests (Test Vectors)**

The heart of your testing: test complete use case behavior with all steps assembled, only adapters stubbed.

```
[](#cb168-1)class UserLoginTest {
[](#cb168-2)    CheckCredentials mockCredentials;
[](#cb168-3)    CheckAccountStatus mockStatus;
[](#cb168-4)    GenerateToken mockToken;
[](#cb168-5)    UserLogin useCase;
[](#cb168-6)
[](#cb168-7)    @BeforeEach
[](#cb168-8)    void setup() {
[](#cb168-9)        mockCredentials = vr -> Result.success(new Credentials("user-1"));
[](#cb168-10)        mockStatus = c -> Result.success(new Account(c.userId(), true));
[](#cb168-11)        mockToken = acc -> Result.success(new Response("token-" + acc.userId()));
[](#cb168-12)        useCase = UserLogin.userLogin(mockCredentials, mockStatus, mockToken);
[](#cb168-13)    }
[](#cb168-14)
[](#cb168-15)    @Test
[](#cb168-16)    void execute_succeeds_forValidInput() {
[](#cb168-17)        var request = new Request("john@example.com", "Valid123", null);
[](#cb168-18)
[](#cb168-19)        useCase.execute(request)
[](#cb168-20)               .onFailure(Assertions::fail)
[](#cb168-21)               .onSuccess(response -> assertEquals("token-user-1", response.token()));
[](#cb168-22)    }
[](#cb168-23)}
```

This tests **real behavior**: validation -> credentials -> status -> token, with error propagation.

* * *

## The Evolutionary Testing Process

### Overview

Instead of writing tests after implementation, evolve them **alongside** implementation:

```
Phase 1: Stub Everything
    |
Phase 2: Implement & Test Validation
    |
Phase 3-N: Implement Steps Incrementally
    |
Final: Production-Ready
```

At each phase, **all tests remain green**. You’re not breaking and fixing - you’re growing.

### Phase 1: Stub Everything

**Goal:** Establish test structure before implementing anything.

**Step 1:** Create use case interface with factory returning stub implementation:

```
[](#cb170-1)public interface UserLogin {
[](#cb170-2)    record Request(String email, String password, String referral) {}
[](#cb170-3)    record Response(String token) {}
[](#cb170-4)
[](#cb170-5)    Result<Response> execute(Request request);
[](#cb170-6)
[](#cb170-7)    static UserLogin userLogin() {
[](#cb170-8)        return request -> Result.success(new Response("stub-token"));
[](#cb170-9)    }
[](#cb170-10)}
```

**Step 2:** Write initial tests:

```
[](#cb171-1)class UserLoginTest {
[](#cb171-2)    @Test
[](#cb171-3)    void execute_succeeds_forValidInput() {
[](#cb171-4)        var useCase = UserLogin.userLogin();
[](#cb171-5)        var request = new Request("john@example.com", "Valid123", null);
[](#cb171-6)
[](#cb171-7)        useCase.execute(request)
[](#cb171-8)               .onSuccess(response -> assertEquals("stub-token", response.token()));
[](#cb171-9)    }
[](#cb171-10)}
```

### Phase 2: Implement Validation

**Step 1:** Add validated request with validation logic:

```
[](#cb172-1)record ValidRequest(Email email, Password password, Option<ReferralCode> referral) {
[](#cb172-2)    static Result<ValidRequest> validRequest(Request raw) {
[](#cb172-3)        return Result.all(Email.email(raw.email()),
[](#cb172-4)                          Password.password(raw.password()),
[](#cb172-5)                          ReferralCode.referralCode(raw.referral()))
[](#cb172-6)                     .map(ValidRequest::new);
[](#cb172-7)    }
[](#cb172-8)}
```

**Step 2:** Update factory to use validation:

```
[](#cb173-1)static UserLogin userLogin() {
[](#cb173-2)    return request -> ValidRequest.validRequest(request)
[](#cb173-3)                                  .map(_ -> new Response("stub-token"));
[](#cb173-4)}
```

**Step 3:** Add validation test vectors:

```
[](#cb174-1)@Test
[](#cb174-2)void execute_fails_forInvalidEmail() {
[](#cb174-3)    var useCase = UserLogin.userLogin();
[](#cb174-4)    var request = new Request("bad-email", "Valid123", null);
[](#cb174-5)
[](#cb174-6)    useCase.execute(request)
[](#cb174-7)           .onSuccess(Assertions::fail);
[](#cb174-8)}
[](#cb174-9)
[](#cb174-10)@Test
[](#cb174-11)void execute_aggregatesMultipleErrors() {
[](#cb174-12)    var useCase = UserLogin.userLogin();
[](#cb174-13)    var request = new Request("bad", "weak", "invalid-ref");
[](#cb174-14)
[](#cb174-15)    useCase.execute(request)
[](#cb174-16)           .onSuccess(Assertions::fail)
[](#cb174-17)           .onFailure(cause -> assertInstanceOf(Causes.CompositeCause.class, cause));
[](#cb174-18)}
```

### Phase 3-N: Continue Expanding

Repeat for each remaining step: - Add step interface - Update factory to accept dependency - Update existing test stubs - Add step failure scenarios

* * *

## Handling Complex Input Objects

### Test Data Builders

**Fluent API for constructing test data:**

```
[](#cb175-1)public class TestData {
[](#cb175-2)    public static RequestBuilder request() {
[](#cb175-3)        return new RequestBuilder();
[](#cb175-4)    }
[](#cb175-5)
[](#cb175-6)    public static class RequestBuilder {
[](#cb175-7)        private String email = "default@example.com";
[](#cb175-8)        private String password = "DefaultValid123";
[](#cb175-9)        private String referral = null;
[](#cb175-10)
[](#cb175-11)        public RequestBuilder withEmail(String email) {
[](#cb175-12)            this.email = email;
[](#cb175-13)            return this;
[](#cb175-14)        }
[](#cb175-15)
[](#cb175-16)        public RequestBuilder withPassword(String password) {
[](#cb175-17)            this.password = password;
[](#cb175-18)            return this;
[](#cb175-19)        }
[](#cb175-20)
[](#cb175-21)        public Request build() {
[](#cb175-22)            return new Request(email, password, referral);
[](#cb175-23)        }
[](#cb175-24)    }
[](#cb175-25)}
```

**Usage:**

```
[](#cb176-1)var request = TestData.request().build();
[](#cb176-2)var invalidEmail = TestData.request().withEmail("bad").build();
```

### Canonical Test Vectors

**Pre-defined test data constants:**

```
[](#cb177-1)public interface TestVectors {
[](#cb177-2)    Request VALID = new Request("user@example.com", "Valid123", null);
[](#cb177-3)    Request INVALID_EMAIL = new Request("bad", "Valid123", null);
[](#cb177-4)    Request WEAK_PASSWORD = new Request("user@example.com", "weak", null);
[](#cb177-5)    Request MULTIPLE_ERRORS = new Request("bad", "weak", "invalid");
[](#cb177-6)}
```

### Which Approach to Use?

*   **Canonical Vectors:** Simple use cases, few fields, limited variations
*   **Factory Methods:** Medium complexity, systematic field variations
*   **Builders:** Complex objects, many optional fields, many combinations

* * *

## Key Takeaways

1.  **Test composition, not components** - Use case is what matters
2.  **Stub only adapters** - Database, HTTP, external services
3.  **Evolve tests with implementation** - Always green, never break-and-fix
4.  **Three layers** - Value objects (unit), complex leaves (unit), use cases (integration)
5.  **Use test data utilities** - Builders, vectors, factories reduce boilerplate

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 4.1: Building test data builders - Exercise 4.2: Evolutionary testing walkthrough

* * *

## What’s Next

[Chapter 11](ch11-testing-practice.md) covers testing in practice - organizing large test suites, the complete RegisterUser example, and migrating from traditional unit testing.

# Chapter 11: Testing in Practice

## What You’ll Learn

*   How to organize large test counts without drowning in complexity
*   What to test where (value objects, leaves, use cases, adapters)
*   Complete worked example: RegisterUser from stub to production
*   How to migrate from traditional unit testing

**Prerequisites:** [Chapter 10: Testing Philosophy](ch10-testing-philosophy.md)

* * *

## Managing Large Test Counts

### The “Problem”

Comprehensive testing generates many tests:

```
UserLoginTest: 35 tests
RegisterUserTest: 42 tests
UpdateProfileTest: 28 tests
```

**This is not a problem - it’s honest complexity.** 35 tests = 35 real scenarios.

But we need organization to stay sane.

### Strategy 1: Nested Test Classes

**Group tests by scenario type:**

```
[](#cb179-1)class UserLoginTest {
[](#cb179-2)    private UserLogin useCase;
[](#cb179-3)    private CheckCredentials stubCreds;
[](#cb179-4)    private CheckAccountStatus stubStatus;
[](#cb179-5)    private GenerateToken stubToken;
[](#cb179-6)
[](#cb179-7)    @BeforeEach
[](#cb179-8)    void setup() {
[](#cb179-9)        stubCreds = vr -> Result.success(new Credentials("user-1"));
[](#cb179-10)        stubStatus = c -> Result.success(new Account(c.userId(), true));
[](#cb179-11)        stubToken = acc -> Result.success(new Response("token-" + acc.userId()));
[](#cb179-12)        useCase = UserLogin.userLogin(stubCreds, stubStatus, stubToken);
[](#cb179-13)    }
[](#cb179-14)
[](#cb179-15)    @Nested class HappyPath {
[](#cb179-16)        @Test void execute_succeeds_forValidInput() { /* ... */ }
[](#cb179-17)        @Test void execute_succeeds_withOptionalReferral() { /* ... */ }
[](#cb179-18)    }
[](#cb179-19)
[](#cb179-20)    @Nested class ValidationFailures {
[](#cb179-21)        @Test void execute_fails_forInvalidEmail() { /* ... */ }
[](#cb179-22)        @Test void execute_fails_forWeakPassword() { /* ... */ }
[](#cb179-23)        @Test void execute_aggregatesMultipleErrors() { /* ... */ }
[](#cb179-24)    }
[](#cb179-25)
[](#cb179-26)    @Nested class StepFailures {
[](#cb179-27)        @Test void execute_fails_whenCredentialsInvalid() { /* ... */ }
[](#cb179-28)        @Test void execute_fails_whenAccountInactive() { /* ... */ }
[](#cb179-29)        @Test void execute_fails_whenTokenGenerationFails() { /* ... */ }
[](#cb179-30)    }
[](#cb179-31)
[](#cb179-32)    @Nested class EdgeCases {
[](#cb179-33)        @Test void execute_handlesNullReferral() { /* ... */ }
[](#cb179-34)        @Test void execute_handlesEmptyStrings() { /* ... */ }
[](#cb179-35)    }
[](#cb179-36)}
```

**Benefits:** - IDE collapses nested classes - scan at high level - Clear categorization - find tests by scenario type - Shared setup per category - Test report groups meaningfully

### Strategy 2: Parameterized Tests

**Collapse similar tests into data-driven variants:**

```
[](#cb180-1)@ParameterizedTest
[](#cb180-2)@ValueSource(strings = {"bad", "no@domain", "@missing", "user@", "CAPS@TEST.COM"})
[](#cb180-3)void execute_fails_forInvalidEmail(String invalidEmail) {
[](#cb180-4)    var request = TestData.request().withEmail(invalidEmail).build();
[](#cb180-5)
[](#cb180-6)    useCase.execute(request)
[](#cb180-7)           .onSuccess(Assertions::fail);
[](#cb180-8)}
[](#cb180-9)
[](#cb180-10)@ParameterizedTest
[](#cb180-11)@CsvSource({
[](#cb180-12)    "weak, TooShort",
[](#cb180-13)    "alllowercase, NoUppercase",
[](#cb180-14)    "ALLUPPERCASE, NoLowercase"
[](#cb180-15)})
[](#cb180-16)void execute_fails_forWeakPassword(String password, String expectedReason) {
[](#cb180-17)    var request = TestData.request().withPassword(password).build();
[](#cb180-18)
[](#cb180-19)    useCase.execute(request)
[](#cb180-20)           .onSuccess(Assertions::fail)
[](#cb180-21)           .onFailure(cause -> assertTrue(cause.message().contains(expectedReason)));
[](#cb180-22)}
```

**Reduces:** 5 individual tests -> 1 parameterized test with 5 values.

### Strategy 3: Test Organization in Files

**Large use cases -> multiple test files:**

```
usecase/
|-- userlogin/
    |-- UserLogin.java (implementation)
    |-- UserLoginValidationTest.java (validation scenarios)
    |-- UserLoginFlowTest.java (happy path + step failures)
    |-- UserLoginEdgeCasesTest.java (edge cases)
```

**Guideline:** Keep individual test files under 500 lines.

* * *

## What to Test Where

### Coverage Criteria by Component Type

**1\. Value Objects: 100% Coverage (Unit Tests)**

```
[](#cb182-1)class EmailTest {
[](#cb182-2)    @Test void email_accepts_validFormat() { }
[](#cb182-3)    @Test void email_rejects_missingAt() { }
[](#cb182-4)    @Test void email_rejects_missingDomain() { }
[](#cb182-5)    @Test void email_normalizesToLowercase() { }
[](#cb182-6)    @Test void email_trimsWhitespace() { }
[](#cb182-7)}
```

**Why 100%?** Value objects are pure, isolated, easy to test. No excuse for gaps.

**2\. Business Leaves: 100% if Complex, Skip if Trivial (Unit Tests)**

**Complex leaf (write unit tests):**

```
[](#cb183-1)class PricingEngine {
[](#cb183-2)    Result<Price> calculatePrice(Order order) {
[](#cb183-3)        // 50 lines, 8 branches, complex discounting logic
[](#cb183-4)    }
[](#cb183-5)}
[](#cb183-6)// Deserves dedicated PricingEngineTest with 20+ tests
```

**Trivial leaf (covered by integration):**

```
[](#cb184-1)static Price applyTax(Price base) {
[](#cb184-2)    return new Price(base.amount().multiply(TAX_RATE));
[](#cb184-3)}
[](#cb184-4)// No dedicated test - covered when use case tested
```

**Guideline:** If leaf has 3+ branches or 20+ lines, write unit tests.

**3\. Use Cases: 90%+ Coverage (Integration Test Vectors)**

```
[](#cb185-1)class RegisterUserTest {
[](#cb185-2)    // Happy path
[](#cb185-3)    @Test void execute_succeeds_forValidInput() { }
[](#cb185-4)
[](#cb185-5)    // Validation failures
[](#cb185-6)    @Test void execute_fails_forInvalidEmail() { }
[](#cb185-7)    @Test void execute_fails_forWeakPassword() { }
[](#cb185-8)
[](#cb185-9)    // Step failures
[](#cb185-10)    @Test void execute_fails_whenEmailAlreadyExists() { }
[](#cb185-11)    @Test void execute_fails_whenPasswordHashingFails() { }
[](#cb185-12)
[](#cb185-13)    // Branch conditions
[](#cb185-14)    @Test void execute_sendsWelcomeEmail_forNewUser() { }
[](#cb185-15)}
```

**Why 90%+?** Use cases are the behavior. Incomplete coverage = incomplete understanding.

**4\. Adapters: Success + Error Modes (Contract Tests)**

```
[](#cb186-1)class JooqUserRepositoryTest {
[](#cb186-2)    @Test void findById_succeeds_whenUserExists() { }
[](#cb186-3)    @Test void findById_returnsEmpty_whenUserNotFound() { }
[](#cb186-4)    @Test void findById_wrapsException_whenDatabaseFails() { }
[](#cb186-5)}
```

**In use case tests:** Stub adapters. Don’t test database interaction 30 times.

* * *

## The Testing Pyramid

```
 /\
            /  \
           /____\ E2E Tests (few)
          /      \ - Through REST layer
         /        \ - Real database (Testcontainers)
        /__________\ Integration Tests (many)
       /            \ - Use case test vectors
      /              \ - All business logic assembled
     /                \ - Only adapters stubbed
    /__________________\ Unit Tests (some)
   /                    \ - Value objects (all)
  /                      \ - Complex business leaves
 /                        \ - Adapter contracts
/--------------------------\
```

**This is inverted from traditional pyramid** - we have MORE integration tests than unit tests.

**Why?** Because our business logic is composition. Testing fragments misses the point.

* * *

## Complete Worked Example: RegisterUser

### Phase 1: Stub Everything

```
[](#cb188-1)public interface RegisterUser {
[](#cb188-2)    record Request(String email, String password) {}
[](#cb188-3)    record Response(String userId) {}
[](#cb188-4)
[](#cb188-5)    Promise<Response> execute(Request request);
[](#cb188-6)
[](#cb188-7)    static RegisterUser registerUser() {
[](#cb188-8)        return request -> Promise.success(new Response("stub-user-id"));
[](#cb188-9)    }
[](#cb188-10)}
```

**Test:**

```
[](#cb189-1)@Test
[](#cb189-2)void execute_succeeds_forValidInput() {
[](#cb189-3)    var useCase = RegisterUser.registerUser();
[](#cb189-4)    var request = new Request("john@example.com", "Valid123");
[](#cb189-5)
[](#cb189-6)    useCase.execute(request)
[](#cb189-7)           .await()
[](#cb189-8)           .onFailure(Assertions::fail)
[](#cb189-9)           .onSuccess(response -> assertEquals("stub-user-id", response.userId()));
[](#cb189-10)}
```

### Phase 2: Add Validation

```
[](#cb190-1)record ValidRequest(Email email, Password password) {
[](#cb190-2)    static Result<ValidRequest> validRequest(Request raw) {
[](#cb190-3)        return Result.all(Email.email(raw.email()),
[](#cb190-4)                          Password.password(raw.password()))
[](#cb190-5)                     .map(ValidRequest::new);
[](#cb190-6)    }
[](#cb190-7)}
[](#cb190-8)
[](#cb190-9)static RegisterUser registerUser() {
[](#cb190-10)    return request -> ValidRequest.validRequest(request)
[](#cb190-11)                                  .async()
[](#cb190-12)                                  .map(_ -> new Response("stub-user-id"));
[](#cb190-13)}
```

**Add validation tests:**

```
[](#cb191-1)@Test
[](#cb191-2)void execute_fails_forInvalidEmail() {
[](#cb191-3)    var request = new Request("bad", "Valid123");
[](#cb191-4)    useCase.execute(request).await().onSuccess(Assertions::fail);
[](#cb191-5)}
```

### Phase 3-6: Add Steps Incrementally

After fully implementing:

```
[](#cb192-1)static RegisterUser registerUser(CheckEmailUniqueness checkUniqueness,
[](#cb192-2)                                 HashPassword hashPassword,
[](#cb192-3)                                 SaveUser saveUser,
[](#cb192-4)                                 SendWelcomeEmail sendEmail) {
[](#cb192-5)    return request -> ValidRequest.validRequest(request)
[](#cb192-6)                                  .async()
[](#cb192-7)                                  .flatMap(checkUniqueness::apply)
[](#cb192-8)                                  .flatMap(hashPassword::apply)
[](#cb192-9)                                  .flatMap(saveUser::apply)
[](#cb192-10)                                  .flatMap(sendEmail::apply)
[](#cb192-11)                                  .map(user -> new Response(user.id()));
[](#cb192-12)}
```

**Final test suite:**

```
[](#cb193-1)class RegisterUserTest {
[](#cb193-2)    @BeforeEach
[](#cb193-3)    void setup() {
[](#cb193-4)        CheckEmailUniqueness stubUniqueness = vr -> Promise.success(vr);
[](#cb193-5)        HashPassword stubHash = vr -> Promise.success(new HashedPassword("hash"));
[](#cb193-6)        SaveUser stubSave = hp -> Promise.success(new User("user-1"));
[](#cb193-7)        SendWelcomeEmail stubEmail = u -> Promise.success(u);
[](#cb193-8)
[](#cb193-9)        useCase = RegisterUser.registerUser(stubUniqueness, stubHash, stubSave, stubEmail);
[](#cb193-10)    }
[](#cb193-11)
[](#cb193-12)    @Nested class HappyPath {
[](#cb193-13)        @Test void execute_succeeds_forValidInput() { /* ... */ }
[](#cb193-14)    }
[](#cb193-15)
[](#cb193-16)    @Nested class ValidationFailures {
[](#cb193-17)        @Test void execute_fails_forInvalidEmail() { /* ... */ }
[](#cb193-18)        @Test void execute_fails_forWeakPassword() { /* ... */ }
[](#cb193-19)    }
[](#cb193-20)
[](#cb193-21)    @Nested class StepFailures {
[](#cb193-22)        @Test void execute_fails_whenEmailExists() { /* ... */ }
[](#cb193-23)        @Test void execute_fails_whenHashingFails() { /* ... */ }
[](#cb193-24)        @Test void execute_fails_whenSaveFails() { /* ... */ }
[](#cb193-25)        @Test void execute_fails_whenEmailSendingFails() { /* ... */ }
[](#cb193-26)    }
[](#cb193-27)}
```

**Total:** 8 integration tests, complete behavior coverage, only adapters stubbed.

* * *

## Migration Guide: From Traditional to Evolutionary

### Step 1: Add Integration Tests

Start by adding integration test vectors for key scenarios:

```
[](#cb194-1)// Keep existing unit tests
[](#cb194-2)class CheckCredentialsTest {
[](#cb194-3)    @Test void validCredentials_succeeds() { /* ... */ }
[](#cb194-4)}
[](#cb194-5)
[](#cb194-6)// Add new integration tests
[](#cb194-7)class UserLoginTest {
[](#cb194-8)    @Test void execute_succeeds_forValidInput() { /* ... */ }
[](#cb194-9)    @Test void execute_fails_whenCredentialsInvalid() { /* ... */ }
[](#cb194-10)}
```

### Step 2: Identify Redundancy

As you add integration tests, notice which unit tests become redundant.

**Question:** Is the unit test adding value beyond the integration test? - If **NO** -> Delete unit test - If **YES** (complex logic, many branches) -> Keep unit test

### Step 3: Remove Redundant Unit Tests

**Keep:** - Complex business leaf tests - Value object tests (always) - Edge case tests not covered by integration

**Delete:** - Simple step tests (covered by integration) - Mock-heavy tests (testing mocking framework more than logic) - Tests that break on refactoring

### Step 4: End State

```
Before Migration:
|-- 60 unit tests (component-focused)
|-- 5 integration tests
|-- Many mocks, brittle tests

After Migration:
|-- 30 integration tests (behavior-focused)
|-- 10 value object unit tests
|-- 5 complex leaf unit tests
|-- No mocks of business logic
```

**Result:** Fewer tests, better coverage, more confidence, less brittleness.

* * *

## Test Speed Classification

### Fast Tests vs Slow Tests

| Test Type | Speed | What’s Stubbed | When to Run |
| --- | --- | --- | --- |
| **Unit tests** | < 10ms each | Nothing (pure functions) | Every build |
| **Fast integration** | < 100ms each | Real business logic, stubbed adapters | Every build |
| **Slow integration** | 100ms - 1s | Real adapters (DB, HTTP) | Pre-commit, CI |
| **E2E tests** | > 1s | Nothing (full stack) | CI only |

**Organize test suites:**

```
[](#cb196-1)// Fast tests - run always
[](#cb196-2)@Tag("fast")
[](#cb196-3)class UserLoginTest { /* stubbed adapters */ }
[](#cb196-4)
[](#cb196-5)// Slow tests - run before commit
[](#cb196-6)@Tag("slow")
[](#cb196-7)class UserLoginIntegrationTest { /* real database */ }
```

**Maven/Gradle configuration:**

```
[](#cb197-1)<!-- Run fast tests by default -->
[](#cb197-2)<excludedGroups>slow</excludedGroups>
```

### Testing Async Promise-Based Flows

**Basic pattern - use `.await()`:**

```
[](#cb198-1)@Test
[](#cb198-2)void async_succeeds() {
[](#cb198-3)    useCase.execute(request)
[](#cb198-4)           .await()  // Blocks until resolved
[](#cb198-5)           .onFailure(Assertions::fail)
[](#cb198-6)           .onSuccess(response -> assertEquals("expected", response.value()));
[](#cb198-7)}
```

**With timeout for slow operations:**

```
[](#cb199-1)@Test
[](#cb199-2)void async_completesWithinTimeout() {
[](#cb199-3)    useCase.execute(request)
[](#cb199-4)           .await(TimeSpan.seconds(5))  // Fail if takes > 5s
[](#cb199-5)           .onFailure(cause -> {
[](#cb199-6)               if (cause instanceof CoreError.Timeout) {
[](#cb199-7)                   fail("Operation timed out");
[](#cb199-8)               }
[](#cb199-9)               fail("Unexpected error: " + cause.message());
[](#cb199-10)           })
[](#cb199-11)           .onSuccess(response -> assertNotNull(response));
[](#cb199-12)}
```

**Testing timeout behavior:**

```
[](#cb200-1)@Test
[](#cb200-2)void timeout_failsSlowOperation() {
[](#cb200-3)    // Simulate slow operation
[](#cb200-4)    var slowStep = input -> Promise.<Output>promise(promise -> {
[](#cb200-5)        // Never resolves
[](#cb200-6)    });
[](#cb200-7)
[](#cb200-8)    var useCase = UseCase.create(slowStep);
[](#cb200-9)
[](#cb200-10)    useCase.execute(request)
[](#cb200-11)           .timeout(TimeSpan.millis(100))
[](#cb200-12)           .await()
[](#cb200-13)           .onSuccess(Assertions::fail)  // Should not succeed
[](#cb200-14)           .onFailure(cause -> assertInstanceOf(CoreError.Timeout.class, cause));
[](#cb200-15)}
```

**Testing parallel operations (Fork-Join):**

```
[](#cb201-1)@Test
[](#cb201-2)void forkJoin_completesAllBranches() {
[](#cb201-3)    var results = Promise.all(
[](#cb201-4)        Promise.success("a"),
[](#cb201-5)        Promise.success("b"),
[](#cb201-6)        Promise.success("c")
[](#cb201-7)    ).await();
[](#cb201-8)
[](#cb201-9)    results.onFailure(Assertions::fail)
[](#cb201-10)           .onSuccess((a, b, c) -> {
[](#cb201-11)               assertEquals("a", a);
[](#cb201-12)               assertEquals("b", b);
[](#cb201-13)               assertEquals("c", c);
[](#cb201-14)           });
[](#cb201-15)}
```

* * *

## Key Takeaways

1.  **Organize by scenario** - Nested classes, parameterized tests
2.  **Value objects: 100%** - Unit tests, always
3.  **Complex leaves: 100%** - Unit tests if 3+ branches
4.  **Use cases: 90%+** - Integration tests with stubbed adapters
5.  **Adapters: Contract tests** - Success + error modes only
6.  **Migrate incrementally** - Add integration first, then remove redundant unit tests

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 4.3: Test suite organization - Exercise 4.4: Migration from traditional testing

* * *

## What’s Next

[Chapter 12](ch12-registeruser-example.md) presents the complete RegisterUser use case - from requirements to production code, demonstrating all patterns working together.

# Chapter 12: Complete Example - RegisterUser

## What You’ll Learn

*   Complete use case from requirements to implementation
*   How all patterns work together in practice
*   Step-by-step evolutionary development

**Prerequisites:** [Chapter 11: Testing in Practice](ch11-testing-practice.md)

* * *

## Requirements

**Use case:** Register a new user account.

**Inputs (raw):** - Email (string) - Password (string) - Referral code (optional string)

**Outputs:** - User ID - Confirmation token

**Validation rules:** - Email: not null, valid format, lowercase normalized - Password: not null, min 8 chars, at least one uppercase, one digit - Referral code: optional; if present, must be exactly 6 uppercase alphanumeric characters

**Cross-field rules:** - Email must not be registered yet

**Steps:** 1\. Validate input 2\. Check email uniqueness (async, database) 3\. Hash password (sync, expensive computation) 4\. Save the user to the database (async) 5\. Generate confirmation token (async, calls external service)

* * *

## Step 1: Use Case Interface

```
[](#cb202-1)package com.example.app.usecase.registeruser;
[](#cb202-2)
[](#cb202-3)import org.pragmatica.lang.*;
[](#cb202-4)
[](#cb202-5)public interface RegisterUser {
[](#cb202-6)    record Request(String email, String password, String referralCode) {}
[](#cb202-7)    record Response(UserId userId, ConfirmationToken token) {}
[](#cb202-8)
[](#cb202-9)    Promise<Response> execute(Request request);
[](#cb202-10)
[](#cb202-11)    interface CheckEmailUniqueness {
[](#cb202-12)        Promise<ValidRequest> apply(ValidRequest valid);
[](#cb202-13)    }
[](#cb202-14)
[](#cb202-15)    interface CreateValidUser {
[](#cb202-16)        Promise<ValidUser> apply(ValidRequest valid);
[](#cb202-17)    }
[](#cb202-18)
[](#cb202-19)    interface SaveUser {
[](#cb202-20)        Promise<User> apply(ValidUser validUser);
[](#cb202-21)    }
[](#cb202-22)
[](#cb202-23)    interface GenerateToken {
[](#cb202-24)        Promise<Response> apply(User user);
[](#cb202-25)    }
[](#cb202-26)
[](#cb202-27)    static RegisterUser registerUser(CheckEmailUniqueness checkEmail,
[](#cb202-28)                                     CreateValidUser createValidUser,
[](#cb202-29)                                     SaveUser saveUser,
[](#cb202-30)                                     GenerateToken generateToken) {
[](#cb202-31)        return request -> ValidRequest.validRequest(request)
[](#cb202-32)                                      .async()
[](#cb202-33)                                      .flatMap(checkEmail::apply)
[](#cb202-34)                                      .flatMap(createValidUser::apply)
[](#cb202-35)                                      .flatMap(saveUser::apply)
[](#cb202-36)                                      .flatMap(generateToken::apply);
[](#cb202-37)    }
[](#cb202-38)}
```

This is a **Sequencer pattern**: validate -> check uniqueness -> create user -> save -> generate token.

* * *

## Step 2: Validated Request

```
[](#cb203-1)record ValidRequest(Email email, Password password, Option<ReferralCode> referralCode) {
[](#cb203-2)
[](#cb203-3)    public static Result<ValidRequest> validRequest(Request raw) {
[](#cb203-4)        return Result.all(Email.email(raw.email()),
[](#cb203-5)                          Password.password(raw.password()),
[](#cb203-6)                          ReferralCode.referralCode(raw.referralCode()))
[](#cb203-7)                     .flatMap(ValidRequest::new);
[](#cb203-8)    }
[](#cb203-9)}
```

This is **Fork-Join pattern**: validate three fields independently, collect results.

* * *

## Step 3: Value Objects

**Email:**

```
[](#cb204-1)package com.example.app.domain.shared;
[](#cb204-2)
[](#cb204-3)public record Email(String value) {
[](#cb204-4)    private static final Pattern EMAIL_PATTERN =
[](#cb204-5)        Pattern.compile("^[a-z0-9+_.-]+@[a-z0-9.-]+$");
[](#cb204-6)    private static final Fn1<Cause, String> INVALID_EMAIL =
[](#cb204-7)        Causes.forOneValue("Invalid email format: %s");
[](#cb204-8)
[](#cb204-9)    public static Result<Email> email(String raw) {
[](#cb204-10)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb204-11)                     .map(String::trim)
[](#cb204-12)                     .map(String::toLowerCase)
[](#cb204-13)                     .filter(INVALID_EMAIL, EMAIL_PATTERN.asMatchPredicate())
[](#cb204-14)                     .map(Email::new);
[](#cb204-15)    }
[](#cb204-16)}
```

**Password:**

```
[](#cb205-1)public record Password(String value) {
[](#cb205-2)    private static final Cause TOO_SHORT =
[](#cb205-3)        Causes.cause("Password must be at least 8 characters");
[](#cb205-4)    private static final Cause MISSING_UPPERCASE =
[](#cb205-5)        Causes.cause("Password must contain uppercase letter");
[](#cb205-6)    private static final Cause MISSING_DIGIT =
[](#cb205-7)        Causes.cause("Password must contain digit");
[](#cb205-8)
[](#cb205-9)    public static Result<Password> password(String raw) {
[](#cb205-10)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb205-11)                     .filter(TOO_SHORT, s -> Verify.Is.lenBetween(s, 8, 128))
[](#cb205-12)                     .flatMap(Password::ensureUppercase)
[](#cb205-13)                     .flatMap(Password::ensureDigit)
[](#cb205-14)                     .map(Password::new);
[](#cb205-15)    }
[](#cb205-16)
[](#cb205-17)    private static Result<String> ensureUppercase(String raw) {
[](#cb205-18)        return contains(raw, Character::isUpperCase)
[](#cb205-19)                ? Result.success(raw)
[](#cb205-20)                : MISSING_UPPERCASE.result();
[](#cb205-21)    }
[](#cb205-22)
[](#cb205-23)    private static Result<String> ensureDigit(String raw) {
[](#cb205-24)        return contains(raw, Character::isDigit)
[](#cb205-25)                ? Result.success(raw)
[](#cb205-26)                : MISSING_DIGIT.result();
[](#cb205-27)    }
[](#cb205-28)
[](#cb205-29)    private static boolean contains(CharSequence sequence, IntPredicate predicate) {
[](#cb205-30)        return sequence.chars().anyMatch(predicate);
[](#cb205-31)    }
[](#cb205-32)}
```

**ReferralCode (optional-with-validation):**

```
[](#cb206-1)public record ReferralCode(String value) {
[](#cb206-2)    private static final Pattern PATTERN = Pattern.compile("^[A-Z0-9]{6}$");
[](#cb206-3)    private static final Cause INVALID_FORMAT = Causes.cause("Invalid referral code format");
[](#cb206-4)
[](#cb206-5)    public static Result<Option<ReferralCode>> referralCode(String raw) {
[](#cb206-6)        return Verify.ensureOption(
[](#cb206-7)            Option.option(raw).map(String::trim).filter(s -> !s.isEmpty()),
[](#cb206-8)            PATTERN.asMatchPredicate(),
[](#cb206-9)            INVALID_FORMAT
[](#cb206-10)        ).map(opt -> opt.map(ReferralCode::new));
[](#cb206-11)    }
[](#cb206-12)
[](#cb206-13)    public boolean isPremium() {
[](#cb206-14)        return value.startsWith("VIP");
[](#cb206-15)    }
[](#cb206-16)}
```

The `Verify.ensureOption()` method (Pragmatica Lite 0.9.0+) handles `Result<Option<ReferralCode>>` elegantly: if the `Option` is empty, succeeds with `Option.none()`; if present and valid, succeeds with `Option.some(value)`; if present and invalid, fails.

* * *

## Step 4: Step Implementations

**CheckEmailUniqueness (adapter leaf):**

```
[](#cb207-1)interface CheckEmailUniqueness {
[](#cb207-2)    Promise<ValidRequest> apply(ValidRequest request);
[](#cb207-3)
[](#cb207-4)    static CheckEmailUniqueness checkEmailUniqueness(UserRepository repository) {
[](#cb207-5)        return request -> repository.findByEmail(request.email())
[](#cb207-6)                                    .flatMap(user -> checkPresence(user, request));
[](#cb207-7)    }
[](#cb207-8)
[](#cb207-9)    static Promise<ValidRequest> checkPresence(Option<User> user, ValidRequest request) {
[](#cb207-10)        return user.isPresent()
[](#cb207-11)                ? RegistrationError.General.EMAIL_ALREADY_REGISTERED.promise()
[](#cb207-12)                : Promise.success(request);
[](#cb207-13)    }
[](#cb207-14)}
```

**HashPassword (business leaf):**

```
[](#cb208-1)interface HashPassword {
[](#cb208-2)    Result<HashedPassword> apply(Password password);
[](#cb208-3)
[](#cb208-4)    static HashPassword hashPassword(BCryptPasswordEncoder encoder) {
[](#cb208-5)        return password -> Result.lift1(RegistrationError.PasswordHashingFailed::new,
[](#cb208-6)                                        encoder::encode,
[](#cb208-7)                                        password.value())
[](#cb208-8)                                 .map(HashedPassword::new);
[](#cb208-9)    }
[](#cb208-10)}
```

**SaveUser (adapter leaf):**

```
[](#cb209-1)class JooqUserRepository implements SaveUser {
[](#cb209-2)    private final DSLContext dsl;
[](#cb209-3)
[](#cb209-4)    public Promise<User> apply(ValidUser user) {
[](#cb209-5)        return Promise.lift(RepositoryError.DatabaseFailure::cause,
[](#cb209-6)                            () -> saveUser(user));
[](#cb209-7)    }
[](#cb209-8)
[](#cb209-9)    private User saveUser(ValidUser user) {
[](#cb209-10)        String id = dsl.insertInto(USERS)
[](#cb209-11)                       .set(USERS.EMAIL, user.email().value())
[](#cb209-12)                       .set(USERS.PASSWORD_HASH, user.hashed().value())
[](#cb209-13)                       .set(USERS.REFERRAL_CODE,
[](#cb209-14)                            user.refCode().map(ReferralCode::value).orElse(null))
[](#cb209-15)                       .returningResult(USERS.ID)
[](#cb209-16)                       .fetchSingle()
[](#cb209-17)                       .value1();
[](#cb209-18)
[](#cb209-19)        return new User(new UserId(id), user.email());
[](#cb209-20)    }
[](#cb209-21)}
```

**GenerateToken (adapter leaf):**

```
[](#cb210-1)class TokenServiceClient implements GenerateToken {
[](#cb210-2)    private final HttpClient httpClient;
[](#cb210-3)
[](#cb210-4)    public Promise<Response> apply(User user) {
[](#cb210-5)        return httpClient.post("/tokens/confirm",
[](#cb210-6)                               Map.of("userId", user.id().value()))
[](#cb210-7)                         .map(resp -> buildResponse(user.id(), resp))
[](#cb210-8)                         .recover(this::mapTokenError);
[](#cb210-9)    }
[](#cb210-10)
[](#cb210-11)    private Response buildResponse(UserId userId, Map<String, String> resp) {
[](#cb210-12)        return new Response(userId, new ConfirmationToken(resp.get("token")));
[](#cb210-13)    }
[](#cb210-14)
[](#cb210-15)    private Promise<Response> mapTokenError(Cause cause) {
[](#cb210-16)        return RegistrationError.General.TOKEN_GENERATION_FAILED.promise();
[](#cb210-17)    }
[](#cb210-18)}
```

* * *

## Step 5: Error Types

```
[](#cb211-1)public sealed interface RegistrationError extends Cause {
[](#cb211-2)    enum General implements RegistrationError {
[](#cb211-3)        EMAIL_ALREADY_REGISTERED("Email already registered"),
[](#cb211-4)        WEAK_PASSWORD_FOR_PREMIUM("Premium codes require 10+ char passwords"),
[](#cb211-5)        TOKEN_GENERATION_FAILED("Token generation failed");
[](#cb211-6)
[](#cb211-7)        private final String message;
[](#cb211-8)
[](#cb211-9)        General(String message) {
[](#cb211-10)            this.message = message;
[](#cb211-11)        }
[](#cb211-12)
[](#cb211-13)        @Override
[](#cb211-14)        public String message() {
[](#cb211-15)            return message;
[](#cb211-16)        }
[](#cb211-17)    }
[](#cb211-18)
[](#cb211-19)    record PasswordHashingFailed(Throwable cause) implements RegistrationError {
[](#cb211-20)        @Override
[](#cb211-21)        public String message() {
[](#cb211-22)            return "Password hashing failed: " + Causes.fromThrowable(cause);
[](#cb211-23)        }
[](#cb211-24)    }
[](#cb211-25)}
```

Sealed interface ensures exhaustive pattern matching.

* * *

## Step 6: Tests

**Validation tests:**

```
[](#cb212-1)@Test
[](#cb212-2)void validRequest_fails_forInvalidEmail() {
[](#cb212-3)    var request = new Request("not-an-email", "Valid1234", null);
[](#cb212-4)
[](#cb212-5)    ValidRequest.validRequest(request)
[](#cb212-6)                .onSuccess(Assertions::fail);
[](#cb212-7)}
[](#cb212-8)
[](#cb212-9)@Test
[](#cb212-10)void validRequest_succeeds_forValidInput() {
[](#cb212-11)    var request = new Request("user@example.com", "Valid1234", "ABC123");
[](#cb212-12)
[](#cb212-13)    ValidRequest.validRequest(request)
[](#cb212-14)                .onFailure(Assertions::fail)
[](#cb212-15)                .onSuccess(valid -> {
[](#cb212-16)                    assertEquals("user@example.com", valid.email().value());
[](#cb212-17)                    assertTrue(valid.referralCode().isPresent());
[](#cb212-18)                });
[](#cb212-19)}
```

**Happy path test:**

```
[](#cb213-1)@Test
[](#cb213-2)void execute_succeeds_forValidInput() {
[](#cb213-3)    CheckEmailUniqueness checkEmail = req -> Promise.success(req);
[](#cb213-4)    CreateValidUser createUser = req -> Promise.success(
[](#cb213-5)        new ValidUser(req.email(), new HashedPassword("hashed"), req.referralCode()));
[](#cb213-6)    SaveUser saveUser = user -> Promise.success(new User(new UserId("user-123"), user.email()));
[](#cb213-7)    GenerateToken generateToken = user -> Promise.success(
[](#cb213-8)        new Response(user.id(), new ConfirmationToken("token-456")));
[](#cb213-9)
[](#cb213-10)    var useCase = RegisterUser.registerUser(checkEmail, createUser, saveUser, generateToken);
[](#cb213-11)    var request = new Request("user@example.com", "Valid1234", null);
[](#cb213-12)
[](#cb213-13)    useCase.execute(request)
[](#cb213-14)          .await()
[](#cb213-15)          .onFailure(Assertions::fail)
[](#cb213-16)          .onSuccess(response -> {
[](#cb213-17)              assertEquals("user-123", response.userId().value());
[](#cb213-18)              assertEquals("token-456", response.token().value());
[](#cb213-19)          });
[](#cb213-20)}
```

**Failure scenario:**

```
[](#cb214-1)@Test
[](#cb214-2)void execute_fails_whenEmailAlreadyExists() {
[](#cb214-3)    CheckEmailUniqueness checkEmail = req ->
[](#cb214-4)        RegistrationError.General.EMAIL_ALREADY_REGISTERED.promise();
[](#cb214-5)    // ... other stubs
[](#cb214-6)
[](#cb214-7)    useCase.execute(request)
[](#cb214-8)          .await()
[](#cb214-9)          .onSuccess(Assertions::fail);
[](#cb214-10)}
```

* * *

## Pattern Summary

| Component | Pattern | Purpose |
| --- | --- | --- |
| RegisterUser.execute | Sequencer | Chain dependent steps |
| ValidRequest.validRequest | Fork-Join | Validate independent fields |
| Email.email | Leaf | Atomic validation |
| Password.password | Leaf | Atomic validation with Sequencer internally |
| CheckEmailUniqueness | Leaf + Condition | Database check with branching |
| SaveUser | Adapter Leaf | Database write |
| RegistrationError | Sealed Interface | Typed error hierarchy |

* * *

## Key Takeaways

1.  **Use case interface** - Contains factory, step interfaces, types
2.  **Sequencer for main flow** - Chain steps with flatMap
3.  **Fork-Join for validation** - Accumulate errors with Result.all()
4.  **Value objects as Leaves** - Parse-don’t-validate
5.  **Adapters implement step interfaces** - JOOQ, HTTP clients
6.  **Tests use stubs** - Only adapters stubbed

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 5.1: Extend RegisterUser with email verification - Exercise 5.3: Add premium referral validation

* * *

## What’s Next

[Chapter 13](ch13-placeorder-example.md) presents another complete example - PlaceOrder - demonstrating more complex patterns including Fork-Join for parallel data fetching.

# Chapter 13: Complete Example - PlaceOrder

This chapter walks through building a complete e-commerce order placement use case from requirements to production-ready code.

* * *

## Requirements

**Business Goal:** Allow customers to place orders for items in their cart.

**Flow:** 1\. Validate the order request 2\. Check inventory for all items (parallel) 3\. Reserve inventory 4\. Process payment 5\. Create order record 6\. Send confirmation notification

**Business Rules:** - All items must be in stock - Payment must succeed before inventory is committed - If payment fails, release reserved inventory - Order confirmation is best-effort (don’t fail order if notification fails)

**Error Scenarios:** - Invalid request (missing fields, invalid quantities) - Insufficient inventory for one or more items - Payment declined - Payment timeout - Database failure

* * *

## Domain Analysis

### Value Objects

| Type | Validation | Notes |
| --- | --- | --- |
| OrderId | UUID format | Generated, not user input |
| CustomerId | Non-empty, UUID format | From session/auth |
| ProductId | Non-empty, UUID format |  |
| Quantity | Positive integer, max 100 | Per-item limit |
| Money | Non-negative, max 2 decimal places |  |
| Address | Street, city, postal code, country | Composite |

### Patterns Identified

| Step | Pattern | Rationale |
| --- | --- | --- |
| Validate request | Fork-Join | Multiple independent field validations |
| Check inventory | Fork-Join | Check all items in parallel |
| Reserve + Pay + Create | Sequencer | Strict ordering required |
| Send notification | Leaf with Aspect | Best-effort, don’t fail order |

* * *

## Package Structure

```
com.example.shop.usecase.placeorder/
  PlaceOrder.java           # Use case interface + factory
  OrderError.java           # Sealed error interface
  ValidOrderRequest.java    # Validated request record
  OrderLine.java            # Validated line item
  ReservedInventory.java    # Intermediate state

com.example.shop.domain.shared/
  CustomerId.java
  ProductId.java
  Quantity.java
  Money.java
  Address.java
  OrderId.java
```

* * *

## Step 1: Value Objects

### ProductId

```
[](#cb216-1)package com.example.shop.domain.shared;
[](#cb216-2)
[](#cb216-3)import org.pragmatica.lang.Result;
[](#cb216-4)import org.pragmatica.lang.Cause;
[](#cb216-5)import org.pragmatica.lang.utils.Causes;
[](#cb216-6)import org.pragmatica.lang.parse.Network;
[](#cb216-7)
[](#cb216-8)public record ProductId(String value) {
[](#cb216-9)    private static final Cause INVALID_PRODUCT_ID = Causes.cause("Invalid product ID format");
[](#cb216-10)
[](#cb216-11)    public static Result<ProductId> productId(String raw) {
[](#cb216-12)        return Network.parseUUID(raw)
[](#cb216-13)            .mapError(_ -> INVALID_PRODUCT_ID)
[](#cb216-14)            .map(uuid -> new ProductId(uuid.toString()));
[](#cb216-15)    }
[](#cb216-16)}
```

### Quantity

```
[](#cb217-1)package com.example.shop.domain.shared;
[](#cb217-2)
[](#cb217-3)import org.pragmatica.lang.Result;
[](#cb217-4)import org.pragmatica.lang.Cause;
[](#cb217-5)import org.pragmatica.lang.utils.Causes;
[](#cb217-6)import org.pragmatica.lang.utils.Verify;
[](#cb217-7)
[](#cb217-8)public record Quantity(int value) {
[](#cb217-9)    private static final Cause NOT_POSITIVE = Causes.cause("Quantity must be positive");
[](#cb217-10)    private static final Cause EXCEEDS_LIMIT = Causes.cause("Quantity cannot exceed 100");
[](#cb217-11)
[](#cb217-12)    public static Result<Quantity> quantity(int raw) {
[](#cb217-13)        return Verify.ensure(raw, Verify.Is::positive)
[](#cb217-14)            .mapError(_ -> NOT_POSITIVE)
[](#cb217-15)            .filter(EXCEEDS_LIMIT, v -> Verify.Is.lessThanOrEqualTo(v, 100))
[](#cb217-16)            .map(Quantity::new);
[](#cb217-17)    }
[](#cb217-18)
[](#cb217-19)    public boolean isGreaterThan(Quantity other) {
[](#cb217-20)        return this.value > other.value;
[](#cb217-21)    }
[](#cb217-22)}
```

### Money

```
[](#cb218-1)package com.example.shop.domain.shared;
[](#cb218-2)
[](#cb218-3)import org.pragmatica.lang.Result;
[](#cb218-4)import org.pragmatica.lang.Cause;
[](#cb218-5)import org.pragmatica.lang.utils.Causes;
[](#cb218-6)
[](#cb218-7)import java.math.BigDecimal;
[](#cb218-8)import java.math.RoundingMode;
[](#cb218-9)
[](#cb218-10)public record Money(BigDecimal value) {
[](#cb218-11)    private static final Cause NEGATIVE = Causes.cause("Money cannot be negative");
[](#cb218-12)    private static final Cause TOO_MANY_DECIMALS = Causes.cause("Money allows max 2 decimal places");
[](#cb218-13)
[](#cb218-14)    public static Result<Money> money(BigDecimal raw) {
[](#cb218-15)        if (raw.compareTo(BigDecimal.ZERO) < 0) {
[](#cb218-16)            return NEGATIVE.result();
[](#cb218-17)        }
[](#cb218-18)        if (raw.scale() > 2) {
[](#cb218-19)            return TOO_MANY_DECIMALS.result();
[](#cb218-20)        }
[](#cb218-21)        return Result.success(new Money(raw.setScale(2, RoundingMode.HALF_UP)));
[](#cb218-22)    }
[](#cb218-23)
[](#cb218-24)    public static Result<Money> money(String raw) {
[](#cb218-25)        return Result.lift(() -> new BigDecimal(raw))
[](#cb218-26)            .mapError(_ -> Causes.cause("Invalid money format"))
[](#cb218-27)            .flatMap(Money::money);
[](#cb218-28)    }
[](#cb218-29)
[](#cb218-30)    public Money add(Money other) {
[](#cb218-31)        return new Money(this.value.add(other.value));
[](#cb218-32)    }
[](#cb218-33)
[](#cb218-34)    public Money multiply(int quantity) {
[](#cb218-35)        return new Money(this.value.multiply(BigDecimal.valueOf(quantity)));
[](#cb218-36)    }
[](#cb218-37)
[](#cb218-38)    public static final Money ZERO = new Money(BigDecimal.ZERO.setScale(2, RoundingMode.HALF_UP));
[](#cb218-39)}
```

### Address

```
[](#cb219-1)package com.example.shop.domain.shared;
[](#cb219-2)
[](#cb219-3)import org.pragmatica.lang.Result;
[](#cb219-4)import org.pragmatica.lang.Cause;
[](#cb219-5)import org.pragmatica.lang.utils.Causes;
[](#cb219-6)import org.pragmatica.lang.utils.Verify;
[](#cb219-7)
[](#cb219-8)public record Address(
[](#cb219-9)    String street,
[](#cb219-10)    String city,
[](#cb219-11)    String postalCode,
[](#cb219-12)    String country
[](#cb219-13)) {
[](#cb219-14)    private static final Cause STREET_REQUIRED = Causes.cause("Street is required");
[](#cb219-15)    private static final Cause CITY_REQUIRED = Causes.cause("City is required");
[](#cb219-16)    private static final Cause POSTAL_CODE_REQUIRED = Causes.cause("Postal code is required");
[](#cb219-17)    private static final Cause COUNTRY_REQUIRED = Causes.cause("Country is required");
[](#cb219-18)
[](#cb219-19)    public static Result<Address> address(String street, String city, String postalCode, String country) {
[](#cb219-20)        return Result.all(
[](#cb219-21)            validateField(street, STREET_REQUIRED),
[](#cb219-22)            validateField(city, CITY_REQUIRED),
[](#cb219-23)            validateField(postalCode, POSTAL_CODE_REQUIRED),
[](#cb219-24)            validateField(country, COUNTRY_REQUIRED)
[](#cb219-25)        ).map(Address::new);
[](#cb219-26)    }
[](#cb219-27)
[](#cb219-28)    private static Result<String> validateField(String value, Cause error) {
[](#cb219-29)        return Verify.ensure(value, Verify.Is::notBlank)
[](#cb219-30)            .mapError(_ -> error)
[](#cb219-31)            .map(String::trim);
[](#cb219-32)    }
[](#cb219-33)}
```

* * *

## Step 2: Error Types

```
[](#cb220-1)package com.example.shop.usecase.placeorder;
[](#cb220-2)
[](#cb220-3)import org.pragmatica.lang.Cause;
[](#cb220-4)import org.pragmatica.lang.utils.Causes;
[](#cb220-5)import com.example.shop.domain.shared.ProductId;
[](#cb220-6)import com.example.shop.domain.shared.Quantity;
[](#cb220-7)
[](#cb220-8)import java.util.List;
[](#cb220-9)
[](#cb220-10)public sealed interface OrderError extends Cause {
[](#cb220-11)
[](#cb220-12)    // Fixed-message errors grouped in enum
[](#cb220-13)    enum General implements OrderError {
[](#cb220-14)        EMPTY_ORDER("Order must contain at least one item"),
[](#cb220-15)        PAYMENT_DECLINED("Payment was declined"),
[](#cb220-16)        PAYMENT_TIMEOUT("Payment service timed out"),
[](#cb220-17)        DATABASE_ERROR("Failed to save order");
[](#cb220-18)
[](#cb220-19)        private final String message;
[](#cb220-20)
[](#cb220-21)        General(String message) {
[](#cb220-22)            this.message = message;
[](#cb220-23)        }
[](#cb220-24)
[](#cb220-25)        @Override
[](#cb220-26)        public String message() {
[](#cb220-27)            return message;
[](#cb220-28)        }
[](#cb220-29)    }
[](#cb220-30)
[](#cb220-31)    // Errors with data
[](#cb220-32)    record InsufficientInventory(List<ProductId> products) implements OrderError {
[](#cb220-33)        @Override
[](#cb220-34)        public String message() {
[](#cb220-35)            return "Insufficient inventory for products: " +
[](#cb220-36)                products.stream().map(ProductId::value).toList();
[](#cb220-37)        }
[](#cb220-38)    }
[](#cb220-39)
[](#cb220-40)    record InvalidQuantity(ProductId productId, Quantity requested, Quantity available)
[](#cb220-41)        implements OrderError {
[](#cb220-42)        @Override
[](#cb220-43)        public String message() {
[](#cb220-44)            return String.format("Product %s: requested %d, available %d",
[](#cb220-45)                productId.value(), requested.value(), available.value());
[](#cb220-46)        }
[](#cb220-47)    }
[](#cb220-48)
[](#cb220-49)    record PaymentFailed(Throwable cause) implements OrderError {
[](#cb220-50)        @Override
[](#cb220-51)        public String message() {
[](#cb220-52)            return "Payment processing failed: " + Causes.fromThrowable(cause);
[](#cb220-53)        }
[](#cb220-54)    }
[](#cb220-55)}
```

* * *

## Step 3: Validated Request

### Raw Request (from API)

```
[](#cb221-1)package com.example.shop.usecase.placeorder;
[](#cb221-2)
[](#cb221-3)import java.util.List;
[](#cb221-4)
[](#cb221-5)public record OrderRequest(
[](#cb221-6)    String customerId,
[](#cb221-7)    List<LineItemRequest> items,
[](#cb221-8)    AddressRequest shippingAddress
[](#cb221-9)) {
[](#cb221-10)    public record LineItemRequest(String productId, int quantity) {}
[](#cb221-11)    public record AddressRequest(String street, String city, String postalCode, String country) {}
[](#cb221-12)}
```

### Validated Order Line

```
[](#cb222-1)package com.example.shop.usecase.placeorder;
[](#cb222-2)
[](#cb222-3)import org.pragmatica.lang.Result;
[](#cb222-4)import com.example.shop.domain.shared.ProductId;
[](#cb222-5)import com.example.shop.domain.shared.Quantity;
[](#cb222-6)
[](#cb222-7)public record OrderLine(ProductId productId, Quantity quantity) {
[](#cb222-8)
[](#cb222-9)    public static Result<OrderLine> orderLine(OrderRequest.LineItemRequest raw) {
[](#cb222-10)        return Result.all(
[](#cb222-11)            ProductId.productId(raw.productId()),
[](#cb222-12)            Quantity.quantity(raw.quantity())
[](#cb222-13)        ).map(OrderLine::new);
[](#cb222-14)    }
[](#cb222-15)}
```

### Validated Request

```
[](#cb223-1)package com.example.shop.usecase.placeorder;
[](#cb223-2)
[](#cb223-3)import org.pragmatica.lang.Result;
[](#cb223-4)import org.pragmatica.lang.Cause;
[](#cb223-5)import org.pragmatica.lang.utils.Causes;
[](#cb223-6)import com.example.shop.domain.shared.CustomerId;
[](#cb223-7)import com.example.shop.domain.shared.Address;
[](#cb223-8)
[](#cb223-9)import java.util.List;
[](#cb223-10)
[](#cb223-11)public record ValidOrderRequest(
[](#cb223-12)    CustomerId customerId,
[](#cb223-13)    List<OrderLine> items,
[](#cb223-14)    Address shippingAddress
[](#cb223-15)) {
[](#cb223-16)    private static final Cause EMPTY_ORDER = OrderError.General.EMPTY_ORDER;
[](#cb223-17)
[](#cb223-18)    public static Result<ValidOrderRequest> validOrderRequest(OrderRequest raw) {
[](#cb223-19)        return Result.all(
[](#cb223-20)            CustomerId.customerId(raw.customerId()),
[](#cb223-21)            validateItems(raw.items()),
[](#cb223-22)            Address.address(
[](#cb223-23)                raw.shippingAddress().street(),
[](#cb223-24)                raw.shippingAddress().city(),
[](#cb223-25)                raw.shippingAddress().postalCode(),
[](#cb223-26)                raw.shippingAddress().country()
[](#cb223-27)            )
[](#cb223-28)        ).map(ValidOrderRequest::new);
[](#cb223-29)    }
[](#cb223-30)
[](#cb223-31)    private static Result<List<OrderLine>> validateItems(List<OrderRequest.LineItemRequest> items) {
[](#cb223-32)        if (items == null || items.isEmpty()) {
[](#cb223-33)            return EMPTY_ORDER.result();
[](#cb223-34)        }
[](#cb223-35)
[](#cb223-36)        return Result.allOf(
[](#cb223-37)            items.stream()
[](#cb223-38)                .map(OrderLine::orderLine)
[](#cb223-39)                .toList()
[](#cb223-40)        );
[](#cb223-41)    }
[](#cb223-42)}
```

* * *

## Step 4: Step Interfaces

```
[](#cb224-1)package com.example.shop.usecase.placeorder;
[](#cb224-2)
[](#cb224-3)import org.pragmatica.lang.Promise;
[](#cb224-4)import org.pragmatica.lang.Result;
[](#cb224-5)import com.example.shop.domain.shared.OrderId;
[](#cb224-6)import com.example.shop.domain.shared.Money;
[](#cb224-7)
[](#cb224-8)public interface PlaceOrder {
[](#cb224-9)
[](#cb224-10)    record Response(OrderId orderId, Money total) {}
[](#cb224-11)
[](#cb224-12)    Promise<Response> execute(OrderRequest request);
[](#cb224-13)
[](#cb224-14)    // Step 1: Check inventory for all items (Fork-Join)
[](#cb224-15)    interface CheckInventory {
[](#cb224-16)        Promise<ValidOrderRequest> apply(ValidOrderRequest request);
[](#cb224-17)    }
[](#cb224-18)
[](#cb224-19)    // Step 2: Reserve inventory
[](#cb224-20)    interface ReserveInventory {
[](#cb224-21)        Promise<ReservedInventory> apply(ValidOrderRequest request);
[](#cb224-22)    }
[](#cb224-23)
[](#cb224-24)    // Step 3: Process payment
[](#cb224-25)    interface ProcessPayment {
[](#cb224-26)        Promise<PaymentConfirmation> apply(ReservedInventory reservation, Money total);
[](#cb224-27)    }
[](#cb224-28)
[](#cb224-29)    // Step 4: Create order record
[](#cb224-30)    interface CreateOrder {
[](#cb224-31)        Promise<OrderId> apply(ReservedInventory reservation, PaymentConfirmation payment);
[](#cb224-32)    }
[](#cb224-33)
[](#cb224-34)    // Step 5: Send confirmation (best-effort)
[](#cb224-35)    interface SendConfirmation {
[](#cb224-36)        Promise<Void> apply(OrderId orderId, ValidOrderRequest request);
[](#cb224-37)    }
[](#cb224-38)
[](#cb224-39)    // Step 6: Release inventory (compensation)
[](#cb224-40)    interface ReleaseInventory {
[](#cb224-41)        Promise<Void> apply(ReservedInventory reservation);
[](#cb224-42)    }
[](#cb224-43)
[](#cb224-44)    // Factory
[](#cb224-45)    static PlaceOrder placeOrder(
[](#cb224-46)        CheckInventory checkInventory,
[](#cb224-47)        ReserveInventory reserveInventory,
[](#cb224-48)        ProcessPayment processPayment,
[](#cb224-49)        CreateOrder createOrder,
[](#cb224-50)        SendConfirmation sendConfirmation,
[](#cb224-51)        ReleaseInventory releaseInventory,
[](#cb224-52)        PriceCalculator priceCalculator
[](#cb224-53)    ) {
[](#cb224-54)        return request -> ValidOrderRequest.validOrderRequest(request)
[](#cb224-55)            .async()
[](#cb224-56)            .flatMap(checkInventory::apply)
[](#cb224-57)            .flatMap(valid -> executeWithCompensation(
[](#cb224-58)                valid,
[](#cb224-59)                reserveInventory,
[](#cb224-60)                processPayment,
[](#cb224-61)                createOrder,
[](#cb224-62)                releaseInventory,
[](#cb224-63)                priceCalculator
[](#cb224-64)            ))
[](#cb224-65)            .onSuccess(response -> sendConfirmation.apply(response.orderId(), null)
[](#cb224-66)                .onFailure(e -> { /* log but don't fail */ }));
[](#cb224-67)    }
[](#cb224-68)
[](#cb224-69)    private static Promise<Response> executeWithCompensation(
[](#cb224-70)        ValidOrderRequest request,
[](#cb224-71)        ReserveInventory reserveInventory,
[](#cb224-72)        ProcessPayment processPayment,
[](#cb224-73)        CreateOrder createOrder,
[](#cb224-74)        ReleaseInventory releaseInventory,
[](#cb224-75)        PriceCalculator priceCalculator
[](#cb224-76)    ) {
[](#cb224-77)        var total = priceCalculator.calculate(request);
[](#cb224-78)
[](#cb224-79)        return reserveInventory.apply(request)
[](#cb224-80)            .flatMap(reservation -> processPayment.apply(reservation, total)
[](#cb224-81)                .flatMap(payment -> createOrder.apply(reservation, payment))
[](#cb224-82)                .map(orderId -> new Response(orderId, total))
[](#cb224-83)                .recover(cause -> compensateAndFail(reservation, releaseInventory, cause)));
[](#cb224-84)    }
[](#cb224-85)
[](#cb224-86)    private static Promise<Response> compensateAndFail(
[](#cb224-87)        ReservedInventory reservation,
[](#cb224-88)        ReleaseInventory releaseInventory,
[](#cb224-89)        Cause cause
[](#cb224-90)    ) {
[](#cb224-91)        return releaseInventory.apply(reservation)
[](#cb224-92)            .flatMap(_ -> cause.promise());
[](#cb224-93)    }
[](#cb224-94)}
```

* * *

## Step 5: Supporting Types

### ReservedInventory

```
[](#cb225-1)package com.example.shop.usecase.placeorder;
[](#cb225-2)
[](#cb225-3)import java.time.Instant;
[](#cb225-4)import java.util.List;
[](#cb225-5)
[](#cb225-6)public record ReservedInventory(
[](#cb225-7)    String reservationId,
[](#cb225-8)    List<ReservedItem> items,
[](#cb225-9)    Instant expiresAt
[](#cb225-10)) {
[](#cb225-11)    public record ReservedItem(String productId, int quantity) {}
[](#cb225-12)}
```

### PaymentConfirmation

```
[](#cb226-1)package com.example.shop.usecase.placeorder;
[](#cb226-2)
[](#cb226-3)import java.time.Instant;
[](#cb226-4)
[](#cb226-5)public record PaymentConfirmation(
[](#cb226-6)    String transactionId,
[](#cb226-7)    Instant processedAt
[](#cb226-8)) {}
```

### PriceCalculator

```
[](#cb227-1)package com.example.shop.usecase.placeorder;
[](#cb227-2)
[](#cb227-3)import com.example.shop.domain.shared.Money;
[](#cb227-4)
[](#cb227-5)public interface PriceCalculator {
[](#cb227-6)    Money calculate(ValidOrderRequest request);
[](#cb227-7)}
```

* * *

## Step 6: Step Implementations

### CheckInventory (Fork-Join Pattern)

```
[](#cb228-1)package com.example.shop.adapter.inventory;
[](#cb228-2)
[](#cb228-3)import org.pragmatica.lang.Promise;
[](#cb228-4)import com.example.shop.usecase.placeorder.PlaceOrder.CheckInventory;
[](#cb228-5)import com.example.shop.usecase.placeorder.ValidOrderRequest;
[](#cb228-6)import com.example.shop.usecase.placeorder.OrderLine;
[](#cb228-7)import com.example.shop.usecase.placeorder.OrderError;
[](#cb228-8)import com.example.shop.domain.shared.ProductId;
[](#cb228-9)
[](#cb228-10)import java.util.List;
[](#cb228-11)
[](#cb228-12)public class InventoryChecker implements CheckInventory {
[](#cb228-13)    private final InventoryClient inventoryClient;
[](#cb228-14)
[](#cb228-15)    public InventoryChecker(InventoryClient inventoryClient) {
[](#cb228-16)        this.inventoryClient = inventoryClient;
[](#cb228-17)    }
[](#cb228-18)
[](#cb228-19)    @Override
[](#cb228-20)    public Promise<ValidOrderRequest> apply(ValidOrderRequest request) {
[](#cb228-21)        // Check all items in parallel (Fork-Join)
[](#cb228-22)        var checks = request.items().stream()
[](#cb228-23)            .map(this::checkItem)
[](#cb228-24)            .toList();
[](#cb228-25)
[](#cb228-26)        return Promise.allOf(checks)
[](#cb228-27)            .flatMap(results -> aggregateResults(results, request));
[](#cb228-28)    }
[](#cb228-29)
[](#cb228-30)    private Promise<OrderLine> checkItem(OrderLine line) {
[](#cb228-31)        return inventoryClient.getAvailable(line.productId())
[](#cb228-32)            .flatMap(available -> available.value() >= line.quantity().value()
[](#cb228-33)                ? Promise.success(line)
[](#cb228-34)                : OrderError.InvalidQuantity(
[](#cb228-35)                    line.productId(),
[](#cb228-36)                    line.quantity(),
[](#cb228-37)                    available
[](#cb228-38)                  ).promise());
[](#cb228-39)    }
[](#cb228-40)
[](#cb228-41)    private Promise<ValidOrderRequest> aggregateResults(
[](#cb228-42)        List<Result<OrderLine>> results,
[](#cb228-43)        ValidOrderRequest request
[](#cb228-44)    ) {
[](#cb228-45)        var failures = results.stream()
[](#cb228-46)            .filter(Result::isFailure)
[](#cb228-47)            .map(r -> r.cause())
[](#cb228-48)            .toList();
[](#cb228-49)
[](#cb228-50)        if (failures.isEmpty()) {
[](#cb228-51)            return Promise.success(request);
[](#cb228-52)        }
[](#cb228-53)
[](#cb228-54)        var failedProducts = failures.stream()
[](#cb228-55)            .filter(c -> c instanceof OrderError.InvalidQuantity)
[](#cb228-56)            .map(c -> ((OrderError.InvalidQuantity) c).productId())
[](#cb228-57)            .toList();
[](#cb228-58)
[](#cb228-59)        return new OrderError.InsufficientInventory(failedProducts).promise();
[](#cb228-60)    }
[](#cb228-61)}
```

### ProcessPayment (Leaf with Error Mapping)

```
[](#cb229-1)package com.example.shop.adapter.payment;
[](#cb229-2)
[](#cb229-3)import org.pragmatica.lang.Promise;
[](#cb229-4)import com.example.shop.usecase.placeorder.PlaceOrder.ProcessPayment;
[](#cb229-5)import com.example.shop.usecase.placeorder.ReservedInventory;
[](#cb229-6)import com.example.shop.usecase.placeorder.PaymentConfirmation;
[](#cb229-7)import com.example.shop.usecase.placeorder.OrderError;
[](#cb229-8)import com.example.shop.domain.shared.Money;
[](#cb229-9)
[](#cb229-10)import java.time.Instant;
[](#cb229-11)import java.util.concurrent.TimeoutException;
[](#cb229-12)
[](#cb229-13)public class PaymentProcessor implements ProcessPayment {
[](#cb229-14)    private final PaymentGateway gateway;
[](#cb229-15)
[](#cb229-16)    public PaymentProcessor(PaymentGateway gateway) {
[](#cb229-17)        this.gateway = gateway;
[](#cb229-18)    }
[](#cb229-19)
[](#cb229-20)    @Override
[](#cb229-21)    public Promise<PaymentConfirmation> apply(ReservedInventory reservation, Money total) {
[](#cb229-22)        return Promise.lift(
[](#cb229-23)            OrderError.PaymentFailed::new,
[](#cb229-24)            () -> gateway.charge(total.value())
[](#cb229-25)        ).map(txId -> new PaymentConfirmation(txId, Instant.now()))
[](#cb229-26)         .recover(this::mapPaymentError);
[](#cb229-27)    }
[](#cb229-28)
[](#cb229-29)    private Promise<PaymentConfirmation> mapPaymentError(Cause cause) {
[](#cb229-30)        return switch (cause) {
[](#cb229-31)            case OrderError.PaymentFailed pf -> {
[](#cb229-32)                if (pf.cause() instanceof TimeoutException) {
[](#cb229-33)                    yield OrderError.General.PAYMENT_TIMEOUT.promise();
[](#cb229-34)                }
[](#cb229-35)                if (isDeclined(pf.cause())) {
[](#cb229-36)                    yield OrderError.General.PAYMENT_DECLINED.promise();
[](#cb229-37)                }
[](#cb229-38)                yield cause.promise();
[](#cb229-39)            }
[](#cb229-40)            default -> cause.promise();
[](#cb229-41)        };
[](#cb229-42)    }
[](#cb229-43)
[](#cb229-44)    private boolean isDeclined(Throwable t) {
[](#cb229-45)        return t.getMessage() != null && t.getMessage().contains("declined");
[](#cb229-46)    }
[](#cb229-47)}
```

### CreateOrder (Leaf - Database)

```
[](#cb230-1)package com.example.shop.adapter.persistence;
[](#cb230-2)
[](#cb230-3)import org.pragmatica.lang.Promise;
[](#cb230-4)import org.jooq.DSLContext;
[](#cb230-5)import com.example.shop.usecase.placeorder.PlaceOrder.CreateOrder;
[](#cb230-6)import com.example.shop.usecase.placeorder.ReservedInventory;
[](#cb230-7)import com.example.shop.usecase.placeorder.PaymentConfirmation;
[](#cb230-8)import com.example.shop.usecase.placeorder.OrderError;
[](#cb230-9)import com.example.shop.domain.shared.OrderId;
[](#cb230-10)
[](#cb230-11)import java.util.UUID;
[](#cb230-12)
[](#cb230-13)import static com.example.shop.adapter.persistence.Tables.*;
[](#cb230-14)
[](#cb230-15)public class JooqOrderRepository implements CreateOrder {
[](#cb230-16)    private final DSLContext dsl;
[](#cb230-17)
[](#cb230-18)    public JooqOrderRepository(DSLContext dsl) {
[](#cb230-19)        this.dsl = dsl;
[](#cb230-20)    }
[](#cb230-21)
[](#cb230-22)    @Override
[](#cb230-23)    public Promise<OrderId> apply(ReservedInventory reservation, PaymentConfirmation payment) {
[](#cb230-24)        return Promise.lift(
[](#cb230-25)            _ -> OrderError.General.DATABASE_ERROR,
[](#cb230-26)            () -> {
[](#cb230-27)                var orderId = UUID.randomUUID().toString();
[](#cb230-28)
[](#cb230-29)                dsl.insertInto(ORDERS)
[](#cb230-30)                    .set(ORDERS.ID, orderId)
[](#cb230-31)                    .set(ORDERS.RESERVATION_ID, reservation.reservationId())
[](#cb230-32)                    .set(ORDERS.PAYMENT_TX_ID, payment.transactionId())
[](#cb230-33)                    .set(ORDERS.STATUS, "CONFIRMED")
[](#cb230-34)                    .execute();
[](#cb230-35)
[](#cb230-36)                for (var item : reservation.items()) {
[](#cb230-37)                    dsl.insertInto(ORDER_ITEMS)
[](#cb230-38)                        .set(ORDER_ITEMS.ORDER_ID, orderId)
[](#cb230-39)                        .set(ORDER_ITEMS.PRODUCT_ID, item.productId())
[](#cb230-40)                        .set(ORDER_ITEMS.QUANTITY, item.quantity())
[](#cb230-41)                        .execute();
[](#cb230-42)                }
[](#cb230-43)
[](#cb230-44)                return new OrderId(orderId);
[](#cb230-45)            }
[](#cb230-46)        );
[](#cb230-47)    }
[](#cb230-48)}
```

* * *

## Step 7: Testing

### Value Object Tests

```
[](#cb231-1)class QuantityTest {
[](#cb231-2)
[](#cb231-3)    @Nested
[](#cb231-4)    class ValidationSucceeds {
[](#cb231-5)        @Test
[](#cb231-6)        void quantity_succeeds_forPositiveValue() {
[](#cb231-7)            Quantity.quantity(5)
[](#cb231-8)                .onFailure(Assertions::fail)
[](#cb231-9)                .onSuccess(q -> assertEquals(5, q.value()));
[](#cb231-10)        }
[](#cb231-11)
[](#cb231-12)        @Test
[](#cb231-13)        void quantity_succeeds_forMaxValue() {
[](#cb231-14)            Quantity.quantity(100)
[](#cb231-15)                .onFailure(Assertions::fail)
[](#cb231-16)                .onSuccess(q -> assertEquals(100, q.value()));
[](#cb231-17)        }
[](#cb231-18)    }
[](#cb231-19)
[](#cb231-20)    @Nested
[](#cb231-21)    class ValidationFails {
[](#cb231-22)        @Test
[](#cb231-23)        void quantity_fails_forZero() {
[](#cb231-24)            Quantity.quantity(0).onSuccess(Assertions::fail);
[](#cb231-25)        }
[](#cb231-26)
[](#cb231-27)        @Test
[](#cb231-28)        void quantity_fails_forNegative() {
[](#cb231-29)            Quantity.quantity(-1).onSuccess(Assertions::fail);
[](#cb231-30)        }
[](#cb231-31)
[](#cb231-32)        @Test
[](#cb231-33)        void quantity_fails_forExceedingLimit() {
[](#cb231-34)            Quantity.quantity(101).onSuccess(Assertions::fail);
[](#cb231-35)        }
[](#cb231-36)    }
[](#cb231-37)}
```

### Use Case Integration Test

```
[](#cb232-1)class PlaceOrderTest {
[](#cb232-2)    private PlaceOrder useCase;
[](#cb232-3)
[](#cb232-4)    @BeforeEach
[](#cb232-5)    void setup() {
[](#cb232-6)        // All stubs - happy path
[](#cb232-7)        PlaceOrder.CheckInventory checkInventory = req -> Promise.success(req);
[](#cb232-8)        PlaceOrder.ReserveInventory reserveInventory = req -> Promise.success(
[](#cb232-9)            new ReservedInventory("res-123", List.of(), Instant.now().plusMinutes(15))
[](#cb232-10)        );
[](#cb232-11)        PlaceOrder.ProcessPayment processPayment = (res, total) -> Promise.success(
[](#cb232-12)            new PaymentConfirmation("tx-456", Instant.now())
[](#cb232-13)        );
[](#cb232-14)        PlaceOrder.CreateOrder createOrder = (res, pay) -> Promise.success(
[](#cb232-15)            new OrderId("order-789")
[](#cb232-16)        );
[](#cb232-17)        PlaceOrder.SendConfirmation sendConfirmation = (id, req) -> Promise.success(null);
[](#cb232-18)        PlaceOrder.ReleaseInventory releaseInventory = res -> Promise.success(null);
[](#cb232-19)        PriceCalculator priceCalculator = req -> new Money(BigDecimal.valueOf(99.99));
[](#cb232-20)
[](#cb232-21)        useCase = PlaceOrder.placeOrder(
[](#cb232-22)            checkInventory, reserveInventory, processPayment,
[](#cb232-23)            createOrder, sendConfirmation, releaseInventory, priceCalculator
[](#cb232-24)        );
[](#cb232-25)    }
[](#cb232-26)
[](#cb232-27)    @Nested
[](#cb232-28)    class HappyPath {
[](#cb232-29)        @Test
[](#cb232-30)        void execute_succeeds_forValidOrder() {
[](#cb232-31)            var request = new OrderRequest(
[](#cb232-32)                "550e8400-e29b-41d4-a716-446655440000",
[](#cb232-33)                List.of(new OrderRequest.LineItemRequest(
[](#cb232-34)                    "660e8400-e29b-41d4-a716-446655440001", 2
[](#cb232-35)                )),
[](#cb232-36)                new OrderRequest.AddressRequest("123 Main St", "City", "12345", "US")
[](#cb232-37)            );
[](#cb232-38)
[](#cb232-39)            useCase.execute(request)
[](#cb232-40)                .await()
[](#cb232-41)                .onFailure(Assertions::fail)
[](#cb232-42)                .onSuccess(response -> {
[](#cb232-43)                    assertEquals("order-789", response.orderId().value());
[](#cb232-44)                });
[](#cb232-45)        }
[](#cb232-46)    }
[](#cb232-47)
[](#cb232-48)    @Nested
[](#cb232-49)    class ValidationFailures {
[](#cb232-50)        @Test
[](#cb232-51)        void execute_fails_forEmptyOrder() {
[](#cb232-52)            var request = new OrderRequest(
[](#cb232-53)                "550e8400-e29b-41d4-a716-446655440000",
[](#cb232-54)                List.of(),
[](#cb232-55)                new OrderRequest.AddressRequest("123 Main St", "City", "12345", "US")
[](#cb232-56)            );
[](#cb232-57)
[](#cb232-58)            useCase.execute(request)
[](#cb232-59)                .await()
[](#cb232-60)                .onSuccess(Assertions::fail);
[](#cb232-61)        }
[](#cb232-62)    }
[](#cb232-63)
[](#cb232-64)    @Nested
[](#cb232-65)    class StepFailures {
[](#cb232-66)        @Test
[](#cb232-67)        void execute_fails_whenInventoryInsufficient() {
[](#cb232-68)            PlaceOrder.CheckInventory failingCheck = req ->
[](#cb232-69)                new OrderError.InsufficientInventory(List.of()).promise();
[](#cb232-70)
[](#cb232-71)            var failingUseCase = PlaceOrder.placeOrder(
[](#cb232-72)                failingCheck, null, null, null, null, null, null
[](#cb232-73)            );
[](#cb232-74)
[](#cb232-75)            failingUseCase.execute(validRequest())
[](#cb232-76)                .await()
[](#cb232-77)                .onSuccess(Assertions::fail);
[](#cb232-78)        }
[](#cb232-79)
[](#cb232-80)        @Test
[](#cb232-81)        void execute_releasesInventory_whenPaymentFails() {
[](#cb232-82)            var released = new AtomicBoolean(false);
[](#cb232-83)
[](#cb232-84)            PlaceOrder.ReserveInventory reserveInventory = req -> Promise.success(
[](#cb232-85)                new ReservedInventory("res-123", List.of(), Instant.now().plusMinutes(15))
[](#cb232-86)            );
[](#cb232-87)            PlaceOrder.ProcessPayment failingPayment = (res, total) ->
[](#cb232-88)                OrderError.General.PAYMENT_DECLINED.promise();
[](#cb232-89)            PlaceOrder.ReleaseInventory releaseInventory = res -> {
[](#cb232-90)                released.set(true);
[](#cb232-91)                return Promise.success(null);
[](#cb232-92)            };
[](#cb232-93)
[](#cb232-94)            var failingUseCase = PlaceOrder.placeOrder(
[](#cb232-95)                req -> Promise.success(req),
[](#cb232-96)                reserveInventory,
[](#cb232-97)                failingPayment,
[](#cb232-98)                null,
[](#cb232-99)                null,
[](#cb232-100)                releaseInventory,
[](#cb232-101)                req -> Money.ZERO
[](#cb232-102)            );
[](#cb232-103)
[](#cb232-104)            failingUseCase.execute(validRequest())
[](#cb232-105)                .await()
[](#cb232-106)                .onSuccess(Assertions::fail);
[](#cb232-107)
[](#cb232-108)            assertTrue(released.get(), "Inventory should be released on payment failure");
[](#cb232-109)        }
[](#cb232-110)    }
[](#cb232-111)
[](#cb232-112)    private OrderRequest validRequest() {
[](#cb232-113)        return new OrderRequest(
[](#cb232-114)            "550e8400-e29b-41d4-a716-446655440000",
[](#cb232-115)            List.of(new OrderRequest.LineItemRequest(
[](#cb232-116)                "660e8400-e29b-41d4-a716-446655440001", 2
[](#cb232-117)            )),
[](#cb232-118)            new OrderRequest.AddressRequest("123 Main St", "City", "12345", "US")
[](#cb232-119)        );
[](#cb232-120)    }
[](#cb232-121)}
```

* * *

## Key Patterns Demonstrated

| Pattern | Where Used | Purpose |
| --- | --- | --- |
| Fork-Join | ValidOrderRequest, CheckInventory | Parallel field validation, parallel inventory checks |
| Sequencer | Main flow | Reserve -> Pay -> Create |
| Leaf | ProcessPayment, CreateOrder | Single I/O operations |
| Condition | Error mapping in ProcessPayment | Route to specific error types |
| Aspects | SendConfirmation | Best-effort with failure tolerance |

## Compensation Pattern

This example demonstrates compensation (rollback) when payment fails after inventory is reserved:

```
reserve() -> pay() -> create()
              |
              v (failure)
         release() -> propagate error
```

The `recover()` method enables clean compensation logic without try-catch.

* * *

## Exercises

1.  **Add discount support:** Modify `PriceCalculator` to accept a discount code and validate it as a value object.

2.  **Add idempotency:** Ensure the same order request doesn’t create duplicate orders. What value object would you create?

3.  **Add retry aspect:** Wrap `ProcessPayment` with a retry aspect that retries on timeout but not on declined.

4.  **Test the compensation:** Write a test verifying that inventory is released when `CreateOrder` fails (not just `ProcessPayment`).

* * *

## Summary

PlaceOrder demonstrates:

*   **Fork-Join for validation** - All fields validated in parallel, errors accumulated
*   **Fork-Join for I/O** - Inventory checked for all items in parallel
*   **Sequencer with compensation** - Reserve -> Pay -> Create with rollback on failure
*   **Error type hierarchy** - Grouped enum for fixed messages, records for data-carrying errors
*   **Best-effort operations** - Notification doesn’t fail the order
*   **Adapter isolation** - All external calls wrapped in Promise.lift

The pattern composition remains simple despite the complex business requirements. Each step is independently testable, and the compensation logic is explicit rather than hidden in catch blocks.

# Chapter 14a: Focused Example - PublishArticle

This focused example demonstrates the **Condition pattern** for routing logic in a content management domain.

* * *

## Requirements

**Business Goal:** Allow authors to submit articles for publication through an approval workflow.

**Flow:** 1\. Validate article submission 2\. Route based on author tier: - **Premium authors:** Auto-approve, publish immediately - **Standard authors:** Queue for editorial review - **New authors:** Queue for senior review + plagiarism check

**Business Rules:** - Premium authors bypass review (auto-publish) - Standard authors need one editorial approval - New authors need senior approval AND plagiarism check passes - All articles go through content validation (length, format)

* * *

## Domain Model

```
[](#cb234-1)public enum AuthorTier { PREMIUM, STANDARD, NEW }
[](#cb234-2)
[](#cb234-3)public record ArticleId(String value) { /* factory omitted for brevity */ }
[](#cb234-4)
[](#cb234-5)public record AuthorId(String value) { /* factory omitted for brevity */ }
[](#cb234-6)
[](#cb234-7)public record Article(
[](#cb234-8)    ArticleId id,
[](#cb234-9)    AuthorId authorId,
[](#cb234-10)    String title,
[](#cb234-11)    String content,
[](#cb234-12)    AuthorTier authorTier
[](#cb234-13)) {}
[](#cb234-14)
[](#cb234-15)public enum PublishStatus {
[](#cb234-16)    PUBLISHED,
[](#cb234-17)    PENDING_EDITORIAL_REVIEW,
[](#cb234-18)    PENDING_SENIOR_REVIEW
[](#cb234-19)}
[](#cb234-20)
[](#cb234-21)public record PublishResult(ArticleId articleId, PublishStatus status) {}
```

* * *

## Error Types

```
[](#cb235-1)public sealed interface PublishError extends Cause {
[](#cb235-2)
[](#cb235-3)    enum General implements PublishError {
[](#cb235-4)        TITLE_TOO_SHORT("Title must be at least 10 characters"),
[](#cb235-5)        CONTENT_TOO_SHORT("Content must be at least 500 characters"),
[](#cb235-6)        PLAGIARISM_DETECTED("Content failed plagiarism check"),
[](#cb235-7)        SAVE_FAILED("Failed to save article");
[](#cb235-8)
[](#cb235-9)        private final String message;
[](#cb235-10)
[](#cb235-11)        General(String message) {
[](#cb235-12)            this.message = message;
[](#cb235-13)        }
[](#cb235-14)
[](#cb235-15)        @Override
[](#cb235-16)        public String message() {
[](#cb235-17)            return message;
[](#cb235-18)        }
[](#cb235-19)    }
[](#cb235-20)}
```

* * *

## Validated Request

```
[](#cb236-1)public record ValidArticle(
[](#cb236-2)    AuthorId authorId,
[](#cb236-3)    String title,
[](#cb236-4)    String content,
[](#cb236-5)    AuthorTier authorTier
[](#cb236-6)) {
[](#cb236-7)    private static final int MIN_TITLE_LENGTH = 10;
[](#cb236-8)    private static final int MIN_CONTENT_LENGTH = 500;
[](#cb236-9)
[](#cb236-10)    public static Result<ValidArticle> validArticle(
[](#cb236-11)        String authorId,
[](#cb236-12)        String title,
[](#cb236-13)        String content,
[](#cb236-14)        AuthorTier tier
[](#cb236-15)    ) {
[](#cb236-16)        return Result.all(
[](#cb236-17)            AuthorId.authorId(authorId),
[](#cb236-18)            validateTitle(title),
[](#cb236-19)            validateContent(content),
[](#cb236-20)            Result.success(tier)
[](#cb236-21)        ).map(ValidArticle::new);
[](#cb236-22)    }
[](#cb236-23)
[](#cb236-24)    private static Result<String> validateTitle(String title) {
[](#cb236-25)        return Verify.ensure(title, Verify.Is::notBlank)
[](#cb236-26)            .flatMap(t -> t.trim().length() >= MIN_TITLE_LENGTH
[](#cb236-27)                ? Result.success(t.trim())
[](#cb236-28)                : PublishError.General.TITLE_TOO_SHORT.result());
[](#cb236-29)    }
[](#cb236-30)
[](#cb236-31)    private static Result<String> validateContent(String content) {
[](#cb236-32)        return Verify.ensure(content, Verify.Is::notBlank)
[](#cb236-33)            .flatMap(c -> c.trim().length() >= MIN_CONTENT_LENGTH
[](#cb236-34)                ? Result.success(c.trim())
[](#cb236-35)                : PublishError.General.CONTENT_TOO_SHORT.result());
[](#cb236-36)    }
[](#cb236-37)}
```

* * *

## Use Case with Condition Pattern

```
[](#cb237-1)public interface PublishArticle {
[](#cb237-2)
[](#cb237-3)    Promise<PublishResult> execute(ArticleRequest request);
[](#cb237-4)
[](#cb237-5)    // Step interfaces
[](#cb237-6)    interface SaveArticle {
[](#cb237-7)        Promise<ArticleId> apply(ValidArticle article);
[](#cb237-8)    }
[](#cb237-9)
[](#cb237-10)    interface CheckPlagiarism {
[](#cb237-11)        Promise<ValidArticle> apply(ValidArticle article);
[](#cb237-12)    }
[](#cb237-13)
[](#cb237-14)    interface QueueForReview {
[](#cb237-15)        Promise<PublishResult> apply(ArticleId id, PublishStatus status);
[](#cb237-16)    }
[](#cb237-17)
[](#cb237-18)    // Factory demonstrating Condition pattern
[](#cb237-19)    static PublishArticle publishArticle(
[](#cb237-20)        SaveArticle saveArticle,
[](#cb237-21)        CheckPlagiarism checkPlagiarism,
[](#cb237-22)        QueueForReview queueForReview
[](#cb237-23)    ) {
[](#cb237-24)        return request -> ValidArticle.validArticle(
[](#cb237-25)                request.authorId(),
[](#cb237-26)                request.title(),
[](#cb237-27)                request.content(),
[](#cb237-28)                request.authorTier()
[](#cb237-29)            )
[](#cb237-30)            .async()
[](#cb237-31)            .flatMap(article -> routeByAuthorTier(
[](#cb237-32)                article, saveArticle, checkPlagiarism, queueForReview
[](#cb237-33)            ));
[](#cb237-34)    }
[](#cb237-35)
[](#cb237-36)    // CONDITION PATTERN: Routing only, no transformation
[](#cb237-37)    private static Promise<PublishResult> routeByAuthorTier(
[](#cb237-38)        ValidArticle article,
[](#cb237-39)        SaveArticle saveArticle,
[](#cb237-40)        CheckPlagiarism checkPlagiarism,
[](#cb237-41)        QueueForReview queueForReview
[](#cb237-42)    ) {
[](#cb237-43)        return switch (article.authorTier()) {
[](#cb237-44)            case PREMIUM -> publishImmediately(article, saveArticle);
[](#cb237-45)            case STANDARD -> queueForEditorialReview(article, saveArticle, queueForReview);
[](#cb237-46)            case NEW -> queueWithPlagiarismCheck(article, saveArticle, checkPlagiarism, queueForReview);
[](#cb237-47)        };
[](#cb237-48)    }
[](#cb237-49)
[](#cb237-50)    // Route 1: Premium - auto-publish
[](#cb237-51)    private static Promise<PublishResult> publishImmediately(
[](#cb237-52)        ValidArticle article,
[](#cb237-53)        SaveArticle saveArticle
[](#cb237-54)    ) {
[](#cb237-55)        return saveArticle.apply(article)
[](#cb237-56)            .map(id -> new PublishResult(id, PublishStatus.PUBLISHED));
[](#cb237-57)    }
[](#cb237-58)
[](#cb237-59)    // Route 2: Standard - editorial review
[](#cb237-60)    private static Promise<PublishResult> queueForEditorialReview(
[](#cb237-61)        ValidArticle article,
[](#cb237-62)        SaveArticle saveArticle,
[](#cb237-63)        QueueForReview queueForReview
[](#cb237-64)    ) {
[](#cb237-65)        return saveArticle.apply(article)
[](#cb237-66)            .flatMap(id -> queueForReview.apply(id, PublishStatus.PENDING_EDITORIAL_REVIEW));
[](#cb237-67)    }
[](#cb237-68)
[](#cb237-69)    // Route 3: New - plagiarism check + senior review
[](#cb237-70)    private static Promise<PublishResult> queueWithPlagiarismCheck(
[](#cb237-71)        ValidArticle article,
[](#cb237-72)        SaveArticle saveArticle,
[](#cb237-73)        CheckPlagiarism checkPlagiarism,
[](#cb237-74)        QueueForReview queueForReview
[](#cb237-75)    ) {
[](#cb237-76)        return checkPlagiarism.apply(article)
[](#cb237-77)            .flatMap(saveArticle::apply)
[](#cb237-78)            .flatMap(id -> queueForReview.apply(id, PublishStatus.PENDING_SENIOR_REVIEW));
[](#cb237-79)    }
[](#cb237-80)}
```

* * *

## Key Points: Condition Pattern

### What Condition Does

The Condition pattern performs **routing only** - it selects which execution path to follow based on input data. The switch expression returns a `Promise<PublishResult>` from each branch.

```
[](#cb238-1)return switch (article.authorTier()) {
[](#cb238-2)    case PREMIUM -> publishImmediately(...);      // Route to path A
[](#cb238-3)    case STANDARD -> queueForEditorialReview(...); // Route to path B
[](#cb238-4)    case NEW -> queueWithPlagiarismCheck(...);    // Route to path C
[](#cb238-5)};
```

### What Condition Does NOT Do

Condition does not transform data inline. Each route delegates to a separate method:

```
[](#cb239-1)// WRONG: Transformation in condition
[](#cb239-2)return switch (article.authorTier()) {
[](#cb239-3)    case PREMIUM -> saveArticle.apply(article)
[](#cb239-4)        .map(id -> new PublishResult(id, PublishStatus.PUBLISHED));  // Too much here
[](#cb239-5)    ...
[](#cb239-6)};
[](#cb239-7)
[](#cb239-8)// CORRECT: Route to method that handles the path
[](#cb239-9)return switch (article.authorTier()) {
[](#cb239-10)    case PREMIUM -> publishImmediately(article, saveArticle);  // Delegation
[](#cb239-11)    ...
[](#cb239-12)};
```

### Benefits

1.  **Clear routing logic** - One place shows all possible paths
2.  **Testable branches** - Each route method can be tested independently
3.  **Extensible** - Adding new author tiers requires adding one case
4.  **Type-safe** - Compiler warns if switch is non-exhaustive

* * *

## Testing

```
[](#cb240-1)class PublishArticleTest {
[](#cb240-2)
[](#cb240-3)    @Nested
[](#cb240-4)    class Routing {
[](#cb240-5)        @Test
[](#cb240-6)        void execute_publishesImmediately_forPremiumAuthor() {
[](#cb240-7)            var saved = new AtomicReference<ValidArticle>();
[](#cb240-8)
[](#cb240-9)            PublishArticle.SaveArticle saveArticle = article -> {
[](#cb240-10)                saved.set(article);
[](#cb240-11)                return Promise.success(new ArticleId("art-123"));
[](#cb240-12)            };
[](#cb240-13)
[](#cb240-14)            var useCase = PublishArticle.publishArticle(
[](#cb240-15)                saveArticle,
[](#cb240-16)                article -> Promise.success(article),
[](#cb240-17)                (id, status) -> Promise.success(new PublishResult(id, status))
[](#cb240-18)            );
[](#cb240-19)
[](#cb240-20)            useCase.execute(requestWithTier(AuthorTier.PREMIUM))
[](#cb240-21)                .await()
[](#cb240-22)                .onFailure(Assertions::fail)
[](#cb240-23)                .onSuccess(result -> {
[](#cb240-24)                    assertEquals(PublishStatus.PUBLISHED, result.status());
[](#cb240-25)                    assertNotNull(saved.get());
[](#cb240-26)                });
[](#cb240-27)        }
[](#cb240-28)
[](#cb240-29)        @Test
[](#cb240-30)        void execute_queuesForEditorialReview_forStandardAuthor() {
[](#cb240-31)            var useCase = PublishArticle.publishArticle(
[](#cb240-32)                article -> Promise.success(new ArticleId("art-123")),
[](#cb240-33)                article -> Promise.success(article),
[](#cb240-34)                (id, status) -> Promise.success(new PublishResult(id, status))
[](#cb240-35)            );
[](#cb240-36)
[](#cb240-37)            useCase.execute(requestWithTier(AuthorTier.STANDARD))
[](#cb240-38)                .await()
[](#cb240-39)                .onFailure(Assertions::fail)
[](#cb240-40)                .onSuccess(result ->
[](#cb240-41)                    assertEquals(PublishStatus.PENDING_EDITORIAL_REVIEW, result.status())
[](#cb240-42)                );
[](#cb240-43)        }
[](#cb240-44)
[](#cb240-45)        @Test
[](#cb240-46)        void execute_checksPlagiarism_forNewAuthor() {
[](#cb240-47)            var plagiarismChecked = new AtomicBoolean(false);
[](#cb240-48)
[](#cb240-49)            PublishArticle.CheckPlagiarism checkPlagiarism = article -> {
[](#cb240-50)                plagiarismChecked.set(true);
[](#cb240-51)                return Promise.success(article);
[](#cb240-52)            };
[](#cb240-53)
[](#cb240-54)            var useCase = PublishArticle.publishArticle(
[](#cb240-55)                article -> Promise.success(new ArticleId("art-123")),
[](#cb240-56)                checkPlagiarism,
[](#cb240-57)                (id, status) -> Promise.success(new PublishResult(id, status))
[](#cb240-58)            );
[](#cb240-59)
[](#cb240-60)            useCase.execute(requestWithTier(AuthorTier.NEW))
[](#cb240-61)                .await()
[](#cb240-62)                .onFailure(Assertions::fail)
[](#cb240-63)                .onSuccess(result -> {
[](#cb240-64)                    assertTrue(plagiarismChecked.get());
[](#cb240-65)                    assertEquals(PublishStatus.PENDING_SENIOR_REVIEW, result.status());
[](#cb240-66)                });
[](#cb240-67)        }
[](#cb240-68)
[](#cb240-69)        @Test
[](#cb240-70)        void execute_fails_whenPlagiarismDetected() {
[](#cb240-71)            PublishArticle.CheckPlagiarism failingCheck = article ->
[](#cb240-72)                PublishError.General.PLAGIARISM_DETECTED.promise();
[](#cb240-73)
[](#cb240-74)            var useCase = PublishArticle.publishArticle(
[](#cb240-75)                article -> Promise.success(new ArticleId("art-123")),
[](#cb240-76)                failingCheck,
[](#cb240-77)                (id, status) -> Promise.success(new PublishResult(id, status))
[](#cb240-78)            );
[](#cb240-79)
[](#cb240-80)            useCase.execute(requestWithTier(AuthorTier.NEW))
[](#cb240-81)                .await()
[](#cb240-82)                .onSuccess(Assertions::fail);
[](#cb240-83)        }
[](#cb240-84)    }
[](#cb240-85)
[](#cb240-86)    private ArticleRequest requestWithTier(AuthorTier tier) {
[](#cb240-87)        return new ArticleRequest(
[](#cb240-88)            "author-123",
[](#cb240-89)            "This is a valid title for testing",
[](#cb240-90)            "x".repeat(600),  // Valid content length
[](#cb240-91)            tier
[](#cb240-92)        );
[](#cb240-93)    }
[](#cb240-94)}
```

* * *

## Exercises

1.  **Add tier upgrade:** If a NEW author has 10+ published articles, route them as STANDARD. Where does this logic belong?

2.  **Add scheduled publishing:** PREMIUM authors can specify a publish date. Modify the Condition to route scheduled articles differently.

3.  **Extract to filter:** Rewrite the plagiarism check using `.filter()` instead of a separate step interface.

* * *

## Summary

PublishArticle demonstrates:

*   **Condition pattern for routing** - Switch expression selects execution path
*   **No transformation in conditions** - Each branch delegates to a method
*   **Pattern matching with enums** - Type-safe, exhaustive routing
*   **Testable branches** - Each route tested independently
*   **Composable with other patterns** - Routes contain Sequencer chains

# Chapter 14b: Focused Example - TransferFunds

This focused example demonstrates **Aspects** for cross-cutting concerns in a financial domain with audit requirements.

* * *

## Requirements

**Business Goal:** Transfer funds between accounts with full audit trail.

**Flow:** 1\. Validate transfer request 2\. Verify source account has sufficient balance 3\. Execute the transfer (debit source, credit destination) 4\. Record audit log

**Regulatory Requirements:** - Every operation must be logged with timestamp, actor, and outcome - Failed operations must also be logged (not just successes) - Audit logging must not fail the transfer (best-effort) - All transfers above threshold require additional authorization

**Technical Requirements:** - Idempotency - same request ID must not execute twice - Timeout - external calls must timeout after 5 seconds - Retry - transient failures should retry up to 3 times

* * *

## Domain Model

```
[](#cb241-1)public record AccountId(String value) { /* factory omitted */ }
[](#cb241-2)
[](#cb241-3)public record TransferId(String value) { /* factory omitted */ }
[](#cb241-4)
[](#cb241-5)public record Money(BigDecimal value) {
[](#cb241-6)    public boolean isGreaterThan(Money other) {
[](#cb241-7)        return this.value.compareTo(other.value) > 0;
[](#cb241-8)    }
[](#cb241-9)
[](#cb241-10)    public Money subtract(Money other) {
[](#cb241-11)        return new Money(this.value.subtract(other.value));
[](#cb241-12)    }
[](#cb241-13)
[](#cb241-14)    public Money add(Money other) {
[](#cb241-15)        return new Money(this.value.add(other.value));
[](#cb241-16)    }
[](#cb241-17)}
[](#cb241-18)
[](#cb241-19)public record TransferRequest(
[](#cb241-20)    String requestId,
[](#cb241-21)    String sourceAccountId,
[](#cb241-22)    String destinationAccountId,
[](#cb241-23)    String amount,
[](#cb241-24)    String initiatedBy
[](#cb241-25)) {}
[](#cb241-26)
[](#cb241-27)public record TransferResult(
[](#cb241-28)    TransferId transferId,
[](#cb241-29)    Money amount,
[](#cb241-30)    Instant completedAt
[](#cb241-31)) {}
```

* * *

## Error Types

```
[](#cb242-1)public sealed interface TransferError extends Cause {
[](#cb242-2)
[](#cb242-3)    enum General implements TransferError {
[](#cb242-4)        INSUFFICIENT_FUNDS("Insufficient funds in source account"),
[](#cb242-5)        SAME_ACCOUNT("Cannot transfer to same account"),
[](#cb242-6)        DUPLICATE_REQUEST("Transfer request already processed"),
[](#cb242-7)        ACCOUNT_NOT_FOUND("Account not found"),
[](#cb242-8)        TRANSFER_FAILED("Transfer execution failed");
[](#cb242-9)
[](#cb242-10)        private final String message;
[](#cb242-11)
[](#cb242-12)        General(String message) {
[](#cb242-13)            this.message = message;
[](#cb242-14)        }
[](#cb242-15)
[](#cb242-16)        @Override
[](#cb242-17)        public String message() {
[](#cb242-18)            return message;
[](#cb242-19)        }
[](#cb242-20)    }
[](#cb242-21)
[](#cb242-22)    record AuthorizationRequired(Money amount, Money threshold) implements TransferError {
[](#cb242-23)        @Override
[](#cb242-24)        public String message() {
[](#cb242-25)            return String.format("Transfer of %s requires authorization (threshold: %s)",
[](#cb242-26)                amount.value(), threshold.value());
[](#cb242-27)        }
[](#cb242-28)    }
[](#cb242-29)}
```

* * *

## Validated Request

```
[](#cb243-1)public record ValidTransfer(
[](#cb243-2)    String requestId,
[](#cb243-3)    AccountId sourceAccount,
[](#cb243-4)    AccountId destinationAccount,
[](#cb243-5)    Money amount,
[](#cb243-6)    String initiatedBy
[](#cb243-7)) {
[](#cb243-8)    public static Result<ValidTransfer> validTransfer(TransferRequest raw) {
[](#cb243-9)        return Result.all(
[](#cb243-10)            validateRequestId(raw.requestId()),
[](#cb243-11)            AccountId.accountId(raw.sourceAccountId()),
[](#cb243-12)            AccountId.accountId(raw.destinationAccountId()),
[](#cb243-13)            Money.money(raw.amount()),
[](#cb243-14)            validateInitiator(raw.initiatedBy())
[](#cb243-15)        ).flatMap(ValidTransfer::validateNotSameAccount);
[](#cb243-16)    }
[](#cb243-17)
[](#cb243-18)    private static Result<ValidTransfer> validateNotSameAccount(
[](#cb243-19)        String requestId,
[](#cb243-20)        AccountId source,
[](#cb243-21)        AccountId destination,
[](#cb243-22)        Money amount,
[](#cb243-23)        String initiatedBy
[](#cb243-24)    ) {
[](#cb243-25)        if (source.value().equals(destination.value())) {
[](#cb243-26)            return TransferError.General.SAME_ACCOUNT.result();
[](#cb243-27)        }
[](#cb243-28)        return Result.success(new ValidTransfer(requestId, source, destination, amount, initiatedBy));
[](#cb243-29)    }
[](#cb243-30)
[](#cb243-31)    private static Result<String> validateRequestId(String requestId) {
[](#cb243-32)        return Verify.ensure(requestId, Verify.Is::notBlank)
[](#cb243-33)            .mapError(_ -> Causes.cause("Request ID is required"));
[](#cb243-34)    }
[](#cb243-35)
[](#cb243-36)    private static Result<String> validateInitiator(String initiatedBy) {
[](#cb243-37)        return Verify.ensure(initiatedBy, Verify.Is::notBlank)
[](#cb243-38)            .mapError(_ -> Causes.cause("Initiator is required"));
[](#cb243-39)    }
[](#cb243-40)}
```

* * *

## Use Case with Aspects

```
[](#cb244-1)public interface TransferFunds {
[](#cb244-2)
[](#cb244-3)    Promise<TransferResult> execute(TransferRequest request);
[](#cb244-4)
[](#cb244-5)    // Step interfaces
[](#cb244-6)    interface CheckIdempotency {
[](#cb244-7)        Promise<ValidTransfer> apply(ValidTransfer transfer);
[](#cb244-8)    }
[](#cb244-9)
[](#cb244-10)    interface CheckBalance {
[](#cb244-11)        Promise<ValidTransfer> apply(ValidTransfer transfer);
[](#cb244-12)    }
[](#cb244-13)
[](#cb244-14)    interface ExecuteTransfer {
[](#cb244-15)        Promise<TransferResult> apply(ValidTransfer transfer);
[](#cb244-16)    }
[](#cb244-17)
[](#cb244-18)    interface AuditLog {
[](#cb244-19)        Promise<Unit> apply(AuditEntry entry);
[](#cb244-20)    }
[](#cb244-21)
[](#cb244-22)    // Factory with aspect composition
[](#cb244-23)    static TransferFunds transferFunds(
[](#cb244-24)        CheckIdempotency checkIdempotency,
[](#cb244-25)        CheckBalance checkBalance,
[](#cb244-26)        ExecuteTransfer executeTransfer,
[](#cb244-27)        AuditLog auditLog,
[](#cb244-28)        TimeSpan timeout,
[](#cb244-29)        RetryPolicy retryPolicy
[](#cb244-30)    ) {
[](#cb244-31)        // Wrap executeTransfer with aspects
[](#cb244-32)        var decoratedExecute = withRetry(retryPolicy,
[](#cb244-33)            withTimeout(timeout,
[](#cb244-34)                withAudit(auditLog, executeTransfer)
[](#cb244-35)            )
[](#cb244-36)        );
[](#cb244-37)
[](#cb244-38)        return request -> ValidTransfer.validTransfer(request)
[](#cb244-39)            .async()
[](#cb244-40)            .flatMap(checkIdempotency::apply)
[](#cb244-41)            .flatMap(checkBalance::apply)
[](#cb244-42)            .flatMap(decoratedExecute);
[](#cb244-43)    }
[](#cb244-44)
[](#cb244-45)    // ASPECT: Timeout
[](#cb244-46)    private static Fn1<ValidTransfer, Promise<TransferResult>> withTimeout(
[](#cb244-47)        TimeSpan timeout,
[](#cb244-48)        Fn1<ValidTransfer, Promise<TransferResult>> step
[](#cb244-49)    ) {
[](#cb244-50)        return transfer -> step.apply(transfer).timeout(timeout);
[](#cb244-51)    }
[](#cb244-52)
[](#cb244-53)    // ASPECT: Retry
[](#cb244-54)    private static Fn1<ValidTransfer, Promise<TransferResult>> withRetry(
[](#cb244-55)        RetryPolicy policy,
[](#cb244-56)        Fn1<ValidTransfer, Promise<TransferResult>> step
[](#cb244-57)    ) {
[](#cb244-58)        return transfer -> retryWithPolicy(policy, () -> step.apply(transfer));
[](#cb244-59)    }
[](#cb244-60)
[](#cb244-61)    private static Promise<TransferResult> retryWithPolicy(
[](#cb244-62)        RetryPolicy policy,
[](#cb244-63)        Supplier<Promise<TransferResult>> operation
[](#cb244-64)    ) {
[](#cb244-65)        return operation.get()
[](#cb244-66)            .recover(cause -> {
[](#cb244-67)                if (policy.shouldRetry(cause) && policy.attemptsRemaining() > 0) {
[](#cb244-68)                    return retryWithPolicy(policy.decrementAttempts(), operation);
[](#cb244-69)                }
[](#cb244-70)                return cause.promise();
[](#cb244-71)            });
[](#cb244-72)    }
[](#cb244-73)
[](#cb244-74)    // ASPECT: Audit (wraps execution with before/after logging)
[](#cb244-75)    private static Fn1<ValidTransfer, Promise<TransferResult>> withAudit(
[](#cb244-76)        AuditLog auditLog,
[](#cb244-77)        Fn1<ValidTransfer, Promise<TransferResult>> step
[](#cb244-78)    ) {
[](#cb244-79)        return transfer -> {
[](#cb244-80)            var startTime = Instant.now();
[](#cb244-81)
[](#cb244-82)            return step.apply(transfer)
[](#cb244-83)                .onResult(result -> logAuditEntry(auditLog, transfer, result, startTime));
[](#cb244-84)        };
[](#cb244-85)    }
[](#cb244-86)
[](#cb244-87)    private static void logAuditEntry(
[](#cb244-88)        AuditLog auditLog,
[](#cb244-89)        ValidTransfer transfer,
[](#cb244-90)        Result<TransferResult> result,
[](#cb244-91)        Instant startTime
[](#cb244-92)    ) {
[](#cb244-93)        var entry = new AuditEntry(
[](#cb244-94)            transfer.requestId(),
[](#cb244-95)            "TRANSFER",
[](#cb244-96)            transfer.initiatedBy(),
[](#cb244-97)            startTime,
[](#cb244-98)            Instant.now(),
[](#cb244-99)            result.isSuccess() ? "SUCCESS" : "FAILURE",
[](#cb244-100)            result.fold(Cause::message, r -> "Transfer completed: " + r.transferId().value())
[](#cb244-101)        );
[](#cb244-102)
[](#cb244-103)        // Best-effort: log but don't fail if audit fails
[](#cb244-104)        auditLog.apply(entry)
[](#cb244-105)            .onFailure(e -> { /* log to fallback */ });
[](#cb244-106)    }
[](#cb244-107)}
```

* * *

## Supporting Types

### AuditEntry

```
[](#cb245-1)public record AuditEntry(
[](#cb245-2)    String requestId,
[](#cb245-3)    String operation,
[](#cb245-4)    String initiatedBy,
[](#cb245-5)    Instant startedAt,
[](#cb245-6)    Instant completedAt,
[](#cb245-7)    String outcome,
[](#cb245-8)    String details
[](#cb245-9)) {}
```

### RetryPolicy

```
[](#cb246-1)public record RetryPolicy(
[](#cb246-2)    int maxAttempts,
[](#cb246-3)    int attemptsRemaining,
[](#cb246-4)    Set<Class<? extends Cause>> retryableErrors
[](#cb246-5)) {
[](#cb246-6)    public static RetryPolicy retryPolicy(int maxAttempts, Set<Class<? extends Cause>> retryableErrors) {
[](#cb246-7)        return new RetryPolicy(maxAttempts, maxAttempts, retryableErrors);
[](#cb246-8)    }
[](#cb246-9)
[](#cb246-10)    public boolean shouldRetry(Cause cause) {
[](#cb246-11)        return retryableErrors.stream()
[](#cb246-12)            .anyMatch(errorClass -> errorClass.isInstance(cause));
[](#cb246-13)    }
[](#cb246-14)
[](#cb246-15)    public RetryPolicy decrementAttempts() {
[](#cb246-16)        return new RetryPolicy(maxAttempts, attemptsRemaining - 1, retryableErrors);
[](#cb246-17)    }
[](#cb246-18)}
```

* * *

## Step Implementations

### CheckIdempotency

```
[](#cb247-1)public class IdempotencyChecker implements TransferFunds.CheckIdempotency {
[](#cb247-2)    private final IdempotencyStore store;
[](#cb247-3)
[](#cb247-4)    public IdempotencyChecker(IdempotencyStore store) {
[](#cb247-5)        this.store = store;
[](#cb247-6)    }
[](#cb247-7)
[](#cb247-8)    @Override
[](#cb247-9)    public Promise<ValidTransfer> apply(ValidTransfer transfer) {
[](#cb247-10)        return Promise.lift(
[](#cb247-11)            _ -> TransferError.General.TRANSFER_FAILED,
[](#cb247-12)            () -> store.exists(transfer.requestId())
[](#cb247-13)        ).flatMap(exists -> exists
[](#cb247-14)            ? TransferError.General.DUPLICATE_REQUEST.promise()
[](#cb247-15)            : Promise.success(transfer));
[](#cb247-16)    }
[](#cb247-17)}
```

### CheckBalance

```
[](#cb248-1)public class BalanceChecker implements TransferFunds.CheckBalance {
[](#cb248-2)    private final AccountRepository accounts;
[](#cb248-3)
[](#cb248-4)    public BalanceChecker(AccountRepository accounts) {
[](#cb248-5)        this.accounts = accounts;
[](#cb248-6)    }
[](#cb248-7)
[](#cb248-8)    @Override
[](#cb248-9)    public Promise<ValidTransfer> apply(ValidTransfer transfer) {
[](#cb248-10)        return accounts.getBalance(transfer.sourceAccount())
[](#cb248-11)            .flatMap(balance -> balance.isGreaterThan(transfer.amount())
[](#cb248-12)                ? Promise.success(transfer)
[](#cb248-13)                : TransferError.General.INSUFFICIENT_FUNDS.promise());
[](#cb248-14)    }
[](#cb248-15)}
```

### ExecuteTransfer

```
[](#cb249-1)public class TransferExecutor implements TransferFunds.ExecuteTransfer {
[](#cb249-2)    private final AccountRepository accounts;
[](#cb249-3)    private final IdempotencyStore idempotencyStore;
[](#cb249-4)
[](#cb249-5)    @Override
[](#cb249-6)    public Promise<TransferResult> apply(ValidTransfer transfer) {
[](#cb249-7)        return Promise.lift(
[](#cb249-8)            _ -> TransferError.General.TRANSFER_FAILED,
[](#cb249-9)            () -> executeInTransaction(transfer)
[](#cb249-10)        );
[](#cb249-11)    }
[](#cb249-12)
[](#cb249-13)    private TransferResult executeInTransaction(ValidTransfer transfer) {
[](#cb249-14)        // Transaction boundary
[](#cb249-15)        accounts.debit(transfer.sourceAccount(), transfer.amount());
[](#cb249-16)        accounts.credit(transfer.destinationAccount(), transfer.amount());
[](#cb249-17)        idempotencyStore.record(transfer.requestId());
[](#cb249-18)
[](#cb249-19)        return new TransferResult(
[](#cb249-20)            new TransferId(UUID.randomUUID().toString()),
[](#cb249-21)            transfer.amount(),
[](#cb249-22)            Instant.now()
[](#cb249-23)        );
[](#cb249-24)    }
[](#cb249-25)}
```

* * *

## Key Points: Aspects Pattern

### What Aspects Are

Aspects are **higher-order functions** that wrap step execution with cross-cutting concerns. They form a composition chain:

```
Request -> [Retry -> [Timeout -> [Audit -> Execute]]]
```

### Aspect Composition Order

The order matters. Aspects are applied **outside-in**:

```
[](#cb251-1)var decorated = withRetry(policy,      // 1\. Outer: retry wraps everything
[](#cb251-2)    withTimeout(timeout,                // 2\. Middle: timeout per attempt
[](#cb251-3)        withAudit(auditLog, execute)    // 3\. Inner: audit each attempt
[](#cb251-4)    )
[](#cb251-5));
```

This means: - Retry wraps timeout (each retry attempt has its own timeout) - Timeout wraps audit (audit happens within timeout) - Audit wraps execute (execution is audited)

### Standard Composition Order

For most use cases:

1.  **Metrics/Logging** (outermost) - Observe everything
2.  **Timeout** - Limit total time
3.  **Circuit Breaker** - Fail fast if service unhealthy
4.  **Retry** - Retry transient failures
5.  **Rate Limit** - Control request rate
6.  **Business Logic** (innermost) - Actual operation

### Aspect Independence

Each aspect is independent and testable:

```
[](#cb252-1)@Test
[](#cb252-2)void withTimeout_fails_whenTimeoutExceeds() {
[](#cb252-3)    var slowStep = transfer -> Promise.<TransferResult>promise()
[](#cb252-4)        .timeout(TimeSpan.timeSpan(100).millis());  // Never resolves
[](#cb252-5)
[](#cb252-6)    var decorated = withTimeout(TimeSpan.timeSpan(50).millis(), slowStep);
[](#cb252-7)
[](#cb252-8)    decorated.apply(validTransfer())
[](#cb252-9)        .await()
[](#cb252-10)        .onSuccess(Assertions::fail);  // Should timeout
[](#cb252-11)}
```

* * *

## Testing

```
[](#cb253-1)class TransferFundsTest {
[](#cb253-2)
[](#cb253-3)    @Nested
[](#cb253-4)    class Aspects {
[](#cb253-5)
[](#cb253-6)        @Test
[](#cb253-7)        void execute_retriesOnTransientFailure() {
[](#cb253-8)            var attempts = new AtomicInteger(0);
[](#cb253-9)
[](#cb253-10)            TransferFunds.ExecuteTransfer failingThenSucceeding = transfer -> {
[](#cb253-11)                if (attempts.incrementAndGet() < 3) {
[](#cb253-12)                    return new TransientError().promise();
[](#cb253-13)                }
[](#cb253-14)                return Promise.success(new TransferResult(
[](#cb253-15)                    new TransferId("tx-123"),
[](#cb253-16)                    transfer.amount(),
[](#cb253-17)                    Instant.now()
[](#cb253-18)                ));
[](#cb253-19)            };
[](#cb253-20)
[](#cb253-21)            var policy = RetryPolicy.retryPolicy(3, Set.of(TransientError.class));
[](#cb253-22)
[](#cb253-23)            var useCase = TransferFunds.transferFunds(
[](#cb253-24)                t -> Promise.success(t),
[](#cb253-25)                t -> Promise.success(t),
[](#cb253-26)                failingThenSucceeding,
[](#cb253-27)                e -> Promise.success(Unit.INSTANCE),
[](#cb253-28)                TimeSpan.timeSpan(5).seconds(),
[](#cb253-29)                policy
[](#cb253-30)            );
[](#cb253-31)
[](#cb253-32)            useCase.execute(validRequest())
[](#cb253-33)                .await()
[](#cb253-34)                .onFailure(Assertions::fail)
[](#cb253-35)                .onSuccess(result -> assertEquals(3, attempts.get()));
[](#cb253-36)        }
[](#cb253-37)
[](#cb253-38)        @Test
[](#cb253-39)        void execute_auditsSuccessfulTransfer() {
[](#cb253-40)            var auditedEntries = new ArrayList<AuditEntry>();
[](#cb253-41)
[](#cb253-42)            TransferFunds.AuditLog auditLog = entry -> {
[](#cb253-43)                auditedEntries.add(entry);
[](#cb253-44)                return Promise.success(Unit.INSTANCE);
[](#cb253-45)            };
[](#cb253-46)
[](#cb253-47)            var useCase = TransferFunds.transferFunds(
[](#cb253-48)                t -> Promise.success(t),
[](#cb253-49)                t -> Promise.success(t),
[](#cb253-50)                t -> Promise.success(new TransferResult(new TransferId("tx-123"), t.amount(), Instant.now())),
[](#cb253-51)                auditLog,
[](#cb253-52)                TimeSpan.timeSpan(5).seconds(),
[](#cb253-53)                RetryPolicy.retryPolicy(0, Set.of())
[](#cb253-54)            );
[](#cb253-55)
[](#cb253-56)            useCase.execute(validRequest())
[](#cb253-57)                .await()
[](#cb253-58)                .onFailure(Assertions::fail);
[](#cb253-59)
[](#cb253-60)            assertEquals(1, auditedEntries.size());
[](#cb253-61)            assertEquals("SUCCESS", auditedEntries.get(0).outcome());
[](#cb253-62)        }
[](#cb253-63)
[](#cb253-64)        @Test
[](#cb253-65)        void execute_auditsFailedTransfer() {
[](#cb253-66)            var auditedEntries = new ArrayList<AuditEntry>();
[](#cb253-67)
[](#cb253-68)            TransferFunds.AuditLog auditLog = entry -> {
[](#cb253-69)                auditedEntries.add(entry);
[](#cb253-70)                return Promise.success(Unit.INSTANCE);
[](#cb253-71)            };
[](#cb253-72)
[](#cb253-73)            var useCase = TransferFunds.transferFunds(
[](#cb253-74)                t -> Promise.success(t),
[](#cb253-75)                t -> TransferError.General.INSUFFICIENT_FUNDS.promise(),
[](#cb253-76)                t -> Promise.success(new TransferResult(new TransferId("tx-123"), t.amount(), Instant.now())),
[](#cb253-77)                auditLog,
[](#cb253-78)                TimeSpan.timeSpan(5).seconds(),
[](#cb253-79)                RetryPolicy.retryPolicy(0, Set.of())
[](#cb253-80)            );
[](#cb253-81)
[](#cb253-82)            useCase.execute(validRequest())
[](#cb253-83)                .await()
[](#cb253-84)                .onSuccess(Assertions::fail);
[](#cb253-85)
[](#cb253-86)            // Audit still captured even though transfer failed
[](#cb253-87)            assertEquals(1, auditedEntries.size());
[](#cb253-88)            assertEquals("FAILURE", auditedEntries.get(0).outcome());
[](#cb253-89)        }
[](#cb253-90)
[](#cb253-91)        @Test
[](#cb253-92)        void execute_succeedsEvenIfAuditFails() {
[](#cb253-93)            TransferFunds.AuditLog failingAudit = entry ->
[](#cb253-94)                Causes.cause("Audit service unavailable").promise();
[](#cb253-95)
[](#cb253-96)            var useCase = TransferFunds.transferFunds(
[](#cb253-97)                t -> Promise.success(t),
[](#cb253-98)                t -> Promise.success(t),
[](#cb253-99)                t -> Promise.success(new TransferResult(new TransferId("tx-123"), t.amount(), Instant.now())),
[](#cb253-100)                failingAudit,
[](#cb253-101)                TimeSpan.timeSpan(5).seconds(),
[](#cb253-102)                RetryPolicy.retryPolicy(0, Set.of())
[](#cb253-103)            );
[](#cb253-104)
[](#cb253-105)            // Transfer should succeed even if audit fails
[](#cb253-106)            useCase.execute(validRequest())
[](#cb253-107)                .await()
[](#cb253-108)                .onFailure(Assertions::fail);
[](#cb253-109)        }
[](#cb253-110)    }
[](#cb253-111)
[](#cb253-112)    private TransferRequest validRequest() {
[](#cb253-113)        return new TransferRequest(
[](#cb253-114)            "req-123",
[](#cb253-115)            "acc-source",
[](#cb253-116)            "acc-dest",
[](#cb253-117)            "100.00",
[](#cb253-118)            "user@example.com"
[](#cb253-119)        );
[](#cb253-120)    }
[](#cb253-121)
[](#cb253-122)    static class TransientError implements Cause {
[](#cb253-123)        @Override
[](#cb253-124)        public String message() {
[](#cb253-125)            return "Transient error";
[](#cb253-126)        }
[](#cb253-127)    }
[](#cb253-128)}
```

* * *

## Exercises

1.  **Add circuit breaker:** Implement a circuit breaker aspect that fails fast after N consecutive failures.

2.  **Add rate limiting:** Implement a rate limit aspect that rejects requests exceeding N per second.

3.  **Add metrics:** Create a metrics aspect that records duration and success/failure counts.

4.  **Conditional aspects:** Modify the factory to only apply audit logging for transfers above a threshold amount.

* * *

## Summary

TransferFunds demonstrates:

*   **Aspects as higher-order functions** - Wrap step execution with cross-cutting concerns
*   **Composition order matters** - Outside-in application (retry wraps timeout wraps audit)
*   **Independent and testable** - Each aspect tested in isolation
*   **Best-effort operations** - Audit failure doesn’t fail the transfer
*   **Idempotency pattern** - Prevent duplicate processing
*   **Retry with policy** - Configurable retry behavior based on error type

# Chapter 15: Project Structure & Framework Integration

## What You’ll Learn

*   Vertical slicing philosophy and package organization
*   Module organization for larger systems
*   File structure guidelines: import ordering, member ordering, utility interfaces
*   Framework integration with Spring Boot and JOOQ
*   Where types go (placement rules)

**Prerequisites:** [Chapter 14: More Examples](ch14a-publisharticle-example.md)

* * *

## Vertical Slicing Philosophy

This technology organizes code around **vertical slices** - each use case is self-contained with its own business logic, validation, and error handling. Unlike architectures that centralize all business logic into one functional core, we **isolate business logic within each use case package**.

**Why vertical slicing (by criteria):** - **Complexity**: Minimizes coupling between unrelated features (+3) - **Business/Technical Ratio**: Package names reflect domain use cases, not technical layers (+2) - **Mental Overhead**: All related code in one place - less navigation (+2) - **Design Impact**: Forces proper boundaries - business logic cannot leak between use cases (+2)

* * *

## Package Structure

```
com.example.app/
|-- usecase/
|   |-- registeruser/              # Use case 1 (vertical slice)
|   |   |-- RegisterUser.java      # Use case interface + factory
|   |   |-- RegistrationError.java # Sealed error interface
|   |   |-- [internal types]       # ValidRequest, intermediate records
|   |
|   |-- getuserprofile/            # Use case 2 (vertical slice)
|       |-- GetUserProfile.java
|       |-- ProfileError.java
|       |-- [internal types]
|
|-- domain/
|   |-- shared/                    # Reusable value objects only
|       |-- Email.java
|       |-- Password.java
|       |-- UserId.java
|
|-- adapter/
|   |-- rest/                      # Inbound adapters (HTTP)
|   |   |-- UserController.java
|   |
|   |-- persistence/               # Outbound adapters (DB)
|       |-- JooqUserRepository.java
|
|-- config/                        # Framework configuration
    |-- UseCaseConfig.java
```

* * *

## Package Placement Rules

### Use Case Packages

`com.example.app.usecase.<usecasename>`: - Use case interface and factory method - Error types specific to this use case (sealed interface) - Step interfaces (nested in use case interface) - Internal validation types (ValidRequest, intermediate records)

**Rule**: If a type is used only by this use case, it stays here.

### Domain Shared

`com.example.app.domain.shared`: - Value objects reused across multiple use cases

**Rule**: Move here immediately when a second use case needs the same value object.

**Anti-pattern**: Don’t create this upfront - let reuse drive the move.

### Adapter Packages

`com.example.app.adapter.*`: - `adapter.rest` - HTTP controllers, request/response DTOs - `adapter.persistence` - Database repositories, ORM entities - `adapter.messaging` - Message queue consumers/producers - `adapter.external` - HTTP clients for external services

**Rule**: Adapters implement step interfaces from use cases.

### Config Package

`com.example.app.config`: - Spring/framework configuration - Bean wiring, dependency injection setup

**Rule**: No business logic, only infrastructure configuration.

* * *

## Module Organization (Optional)

For larger systems, split into Gradle/Maven modules:

```
:domain          # Pure Java - value objects
:application     # Use cases and step interfaces
:adapters        # Adapter implementations
:bootstrap       # Main class, configuration
```

### When to Use Modules

*   Team size > 5 developers
*   Multiple deployment units from same codebase
*   Enforcing compile-time dependency boundaries
*   Independent library publication

### When Single Module is Sufficient

*   Small to medium teams (< 5 developers)
*   Monolithic deployment
*   Package conventions provide sufficient structure

### Module Dependencies

```
domain         -> (no dependencies)
  |
application    -> domain
  |
adapters       -> application, domain
  |
bootstrap      -> adapters, application, domain
```

* * *

## File Structure Guidelines

Beyond package organization, JBCT standardizes the internal structure of source files. This ensures consistency and enables automated linting.

**Scope:** Use case interfaces, step implementations, value objects, error interfaces, and utility interfaces. Adapters are excluded—they are too framework-specific.

### Import Ordering

```
1\. java.*
2\. javax.*
3\. org.pragmatica.*
4\. third-party (org.*, com.* - alphabetically)
5\. project imports
6\. (blank line)
7\. static imports (same grouping order)
```

### Member Ordering by File Type

**Use Case Interface:** 1\. Public API (Request, Response records) 2\. Execute method 3\. Internal types (ValidRequest + validation helpers) 4\. Step interfaces 5\. Domain fragments (records used only by this use case) 6\. Factory method

**Value Object:** 1\. Static constants (patterns, cause factories) 2\. Factory method 3\. Helper methods

**Error Interface:** 1\. Enum variants (fixed-message errors, grouped) 2\. Record variants (errors carrying data)

**Step Implementation:** 1\. Dependencies (final fields) 2\. Constructor 3\. Interface method(s) 4\. Private helpers

**Utility Interface:** 1\. Constants 2\. Static methods 3. `unused` record (always last—prevents implementation)

### Utility Interface Pattern

Utility interfaces replace utility classes. The `sealed` modifier with an `unused` record prevents implementation:

```
[](#cb258-1)public sealed interface ValidationUtils {
[](#cb258-2)
[](#cb258-3)    Pattern PHONE_PATTERN = Pattern.compile("^\\+?[0-9]{10,14}$");
[](#cb258-4)
[](#cb258-5)    static Result<String> normalizePhone(String raw) {
[](#cb258-6)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb258-7)                     .map(s -> s.replaceAll("[\\s\\-()]", ""))
[](#cb258-8)                     .filter(INVALID_PHONE, PHONE_PATTERN.asMatchPredicate());
[](#cb258-9)    }
[](#cb258-10)
[](#cb258-11)    record unused() implements ValidationUtils {}
[](#cb258-12)}
```

**Key points:** - `sealed` prevents external implementation - `unused` record satisfies permit requirement - No visibility modifiers needed (implicit `public`)

### Section Separation

Use blank lines to separate logical sections. Comments are optional—use only when they add clarity.

* * *

## Framework Integration

### Complete Example: Spring REST -> Use Case -> JOOQ

#### 1\. Use Case (Functional Core)

```
[](#cb259-1)public interface GetUserProfile {
[](#cb259-2)    record Request(String userId) {}
[](#cb259-3)    record Response(String userId, String email, String displayName) {
[](#cb259-4)        static Response fromUser(User user) {
[](#cb259-5)            return new Response(user.id().value(),
[](#cb259-6)                                user.email().value(),
[](#cb259-7)                                user.displayName());
[](#cb259-8)        }
[](#cb259-9)    }
[](#cb259-10)
[](#cb259-11)    Promise<Response> execute(Request request);
[](#cb259-12)
[](#cb259-13)    interface FetchUser {
[](#cb259-14)        Promise<User> apply(UserId userId);
[](#cb259-15)    }
[](#cb259-16)
[](#cb259-17)    static GetUserProfile getUserProfile(FetchUser fetchUser) {
[](#cb259-18)        return request -> UserId.userId(request.userId())
[](#cb259-19)                                .async()
[](#cb259-20)                                .flatMap(fetchUser::apply)
[](#cb259-21)                                .map(Response::fromUser);
[](#cb259-22)    }
[](#cb259-23)}
```

Pure business logic. No framework dependencies.

#### 2\. REST Controller (Adapter In)

```
[](#cb260-1)@RestController
[](#cb260-2)@RequestMapping("/api/users")
[](#cb260-3)public class UserController {
[](#cb260-4)    private final GetUserProfile getUserProfile;
[](#cb260-5)
[](#cb260-6)    public UserController(GetUserProfile getUserProfile) {
[](#cb260-7)        this.getUserProfile = getUserProfile;
[](#cb260-8)    }
[](#cb260-9)
[](#cb260-10)    @GetMapping("/{userId}")
[](#cb260-11)    public ResponseEntity<?> getProfile(@PathVariable String userId) {
[](#cb260-12)        var request = new GetUserProfile.Request(userId);
[](#cb260-13)
[](#cb260-14)        return getUserProfile.execute(request)
[](#cb260-15)            .await()
[](#cb260-16)            .fold(this::toErrorResponse,
[](#cb260-17)                  response -> ResponseEntity.ok(response));
[](#cb260-18)    }
[](#cb260-19)
[](#cb260-20)    private ResponseEntity<?> toErrorResponse(Cause cause) {
[](#cb260-21)        return switch (cause) {
[](#cb260-22)            case ProfileError.UserNotFound _ ->
[](#cb260-23)                ResponseEntity.status(HttpStatus.NOT_FOUND)
[](#cb260-24)                              .body(Map.of("error", cause.message()));
[](#cb260-25)
[](#cb260-26)            case ProfileError.InvalidUserId _ ->
[](#cb260-27)                ResponseEntity.status(HttpStatus.BAD_REQUEST)
[](#cb260-28)                              .body(Map.of("error", cause.message()));
[](#cb260-29)
[](#cb260-30)            default ->
[](#cb260-31)                ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR)
[](#cb260-32)                              .body(Map.of("error", "Internal server error"));
[](#cb260-33)        };
[](#cb260-34)    }
[](#cb260-35)}
```

Thin adapter: HTTP -> Request -> use case -> Response/Cause -> HTTP.

#### 3\. JOOQ Repository (Adapter Out)

```
[](#cb261-1)@Repository
[](#cb261-2)public class JooqUserRepository implements GetUserProfile.FetchUser {
[](#cb261-3)    private final DSLContext dsl;
[](#cb261-4)
[](#cb261-5)    public JooqUserRepository(DSLContext dsl) {
[](#cb261-6)        this.dsl = dsl;
[](#cb261-7)    }
[](#cb261-8)
[](#cb261-9)    public Promise<User> apply(UserId userId) {
[](#cb261-10)        return Promise.lift(ProfileError.DatabaseFailure::cause,
[](#cb261-11)            () -> dsl.selectFrom(USERS)
[](#cb261-12)                     .where(USERS.ID.eq(userId.value()))
[](#cb261-13)                     .fetchOptional()
[](#cb261-14)                     .map(this::toDomain)
[](#cb261-15)                     .orElseThrow(() -> new NotFoundException()));
[](#cb261-16)    }
[](#cb261-17)
[](#cb261-18)    private User toDomain(Record record) {
[](#cb261-19)        return new User(
[](#cb261-20)            new UserId(record.get(USERS.ID)),
[](#cb261-21)            new Email(record.get(USERS.EMAIL)),
[](#cb261-22)            record.get(USERS.DISPLAY_NAME)
[](#cb261-23)        );
[](#cb261-24)    }
[](#cb261-25)}
```

Wraps JOOQ exceptions in domain Causes.

#### 4\. Wiring (Spring Config)

```
[](#cb262-1)@Configuration
[](#cb262-2)public class UseCaseConfig {
[](#cb262-3)
[](#cb262-4)    @Bean
[](#cb262-5)    public GetUserProfile getUserProfile(JooqUserRepository repository) {
[](#cb262-6)        return GetUserProfile.getUserProfile(repository);
[](#cb262-7)    }
[](#cb262-8)}
```

* * *

## Key Principles

### 1\. Vertical Slicing

Each use case package is a vertical slice containing everything needed for that feature.

### 2\. Minimal Sharing

Only share value objects when truly reusable. Premature sharing creates coupling.

### 3\. Framework at Edges

Business logic (use cases, domain) has zero framework dependencies. Adapters handle framework integration.

### 4\. Clear Dependencies

*   Use cases depend on: domain.shared
*   Adapters depend on: use cases (implement step interfaces)
*   Config depends on: use cases + adapters (wires them together)
*   **Never**: use case depending on adapter

### 5\. Adapter Isolation

All I/O operations live in adapters. Framework swapping (Spring -> Micronaut) affects only adapters.

* * *

## Where Things Go

| Type | Location | Rationale |
| --- | --- | --- |
| Use case interface | `usecase.<name>` | Entry point for feature |
| Step interfaces | Inside use case | Part of use case contract |
| Errors (sealed) | `usecase.<name>` | Feature-specific |
| ValidRequest | `usecase.<name>` | Internal validation |
| Shared value objects | `domain.shared` | Reused across features |
| Controllers | `adapter.rest` | HTTP handling |
| Repositories | `adapter.persistence` | Database access |
| Config | `config` | Bean wiring |

* * *

## Key Takeaways

1.  **Vertical slices** - Each use case is self-contained
2.  **Move to shared on reuse** - Not upfront
3.  **Framework at edges** - Pure business logic in use cases
4.  **Adapters implement step interfaces** - Clear contracts
5.  **Modules when needed** - Don’t prematurely modularize

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 5.4: Package organization - Exercise 6.2: Module setup

* * *

## What’s Next

[Chapter 16](ch16-systematic-application.md) covers systematic application - checkpoints and checklists for writing and reviewing JBCT code.

# Chapter 16: Systematic Application Guide

## What You’ll Learn

*   8 checkpoints for consistent JBCT application
*   Quick reference tables for immediate lookup
*   Violation -> Fix patterns for common mistakes
*   Application order for new code and reviews

**Prerequisites:** [Chapter 15: Project Structure](ch15-project-structure.md)

* * *

## The Checkpoint Approach

JBCT application works through **checkpoints** - specific moments during coding where you pause and verify compliance. Each checkpoint has: - **Trigger**: When to apply this checkpoint - **Rules**: What to check - **Fixes**: How to correct violations

The goal is 100% compliance through systematic verification, not heroic effort.

* * *

## CHECKPOINT 1: Before Writing Any Lambda

**Trigger**: You’re about to write `->`

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| L1 | Is method reference possible? | Use `Type::method` |
| L2 | Does lambda have braces `{}`? | Extract to named method |
| L3 | Nested monadic operations inside? | Extract inner operation |
| L4 | Control flow (if/switch/try)? | Extract to named method |
| L5 | Multiple statements? | Extract to named method |

### Allowed Lambda Forms (Exhaustive)

```
[](#cb263-1)// Method references (ALWAYS PREFERRED)
[](#cb263-2).map(Email::new)
[](#cb263-3).flatMap(this::validate)
[](#cb263-4)
[](#cb263-5)// Single-value expression (no braces)
[](#cb263-6).map(value -> expression)
[](#cb263-7).filter(s -> !s.isBlank())
[](#cb263-8)
[](#cb263-9)// Multi-value expression (no braces)
[](#cb263-10).map((a, b) -> new Pair(a, b))
```

### Extraction Pattern

```
[](#cb264-1)// BEFORE (violation)
[](#cb264-2).map(data -> {
[](#cb264-3)    cache.put(key, data);
[](#cb264-4)    log.info("Cached: {}", data);
[](#cb264-5)    return data.size();
[](#cb264-6)})
[](#cb264-7)
[](#cb264-8)// AFTER (compliant)
[](#cb264-9).map(this::cacheAndCount)
[](#cb264-10)
[](#cb264-11)private int cacheAndCount(Data data) {
[](#cb264-12)    cache.put(key, data);
[](#cb264-13)    log.info("Cached: {}", data);
[](#cb264-14)    return data.size();
[](#cb264-15)}
```

* * *

## CHECKPOINT 2: Choosing Return Type

**Trigger**: Writing a method signature

### Decision Tree

```
Can this operation fail?
|-- NO: Can the value be absent?
|   |-- NO -> return T
|   |-- YES -> return Option<T>
|-- YES: Is it async/IO?
    |-- NO -> return Result<T>
    |-- YES -> return Promise<T>
```

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| R1 | Does Result always succeed? | Change to T |
| R2 | Is Option always present? | Change to T |
| R3 | Using `Promise<Result<T>>`? | Use `Promise<T>` only |
| R4 | Returning Void? | Use Unit |
| R5 | Returning null? | Use `Option<T>` |

* * *

## CHECKPOINT 3: Writing Factory Methods

**Trigger**: Creating construction logic for a type

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| F1 | Name follows `TypeName.typeName()`? | Rename |
| F2 | Validation happens at construction? | Move to factory |
| F3 | Return type matches validation needs? | Apply Checkpoint 2 |
| F4 | Constructor exposed publicly? | Make factory only entry |

### Pattern

```
[](#cb266-1)public record Email(String value) {
[](#cb266-2)    // Factory with validation -> Result<T>
[](#cb266-3)    public static Result<Email> email(String raw) {
[](#cb266-4)        return Verify.ensure(raw, Verify.Is::notNull)
[](#cb266-5)            .map(String::trim)
[](#cb266-6)            .filter(INVALID_EMAIL, s -> PATTERN.matcher(s).matches())
[](#cb266-7)            .map(Email::new);
[](#cb266-8)    }
[](#cb266-9)}
[](#cb266-10)
[](#cb266-11)public record Config(DbUrl url, DbPassword pass) {
[](#cb266-12)    // Factory without validation -> T
[](#cb266-13)    public static Config config(DbUrl url, DbPassword pass) {
[](#cb266-14)        return new Config(url, pass);
[](#cb266-15)    }
[](#cb266-16)}
```

* * *

## CHECKPOINT 4: Designing a Class/Interface

**Trigger**: Creating a new type

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| D1 | What zone does this belong to? | Place in correct package |
| D2 | Does it mix I/O with domain logic? | Split into separate types |
| D3 | Are primitives used for domain concepts? | Extract value objects |
| D4 | Does naming match the zone? | Adjust naming style |

### Zone Placement

```
Zone A (Entry): Controllers, handlers, main
  -> Business action verbs: handleRegistration(), processOrder()

Zone B (Domain): Use cases, value objects, domain services
  -> Domain vocabulary: Email.email(), ValidRequest.validRequest()

Zone C (Infrastructure): DB, external APIs, config loading
  -> Technical names: loadAllGenerations(), saveUser(), readFile()
```

* * *

## CHECKPOINT 5: Writing Monadic Chains

**Trigger**: Chaining `.map()/.flatMap()/.filter()` etc.

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| M1 | Single pattern per method? | Extract mixed patterns |
| M2 | Chain length <= 5 steps? | Split into composed methods |
| M3 | Side effects only in terminal ops? | Move to `.onSuccess()/.onFailure()` |
| M4 | Logging mixed with logic? | Move logging to appropriate layer |

### Pattern Separation

```
[](#cb268-1)// VIOLATION: Mixing Sequencer + Fork-Join
[](#cb268-2)return validate(request)
[](#cb268-3)    .flatMap(req -> Result.all(
[](#cb268-4)        checkInventory(req),
[](#cb268-5)        validatePayment(req)
[](#cb268-6)    ).map((inv, pay) -> proceed(req)));
[](#cb268-7)
[](#cb268-8)// FIX: Extract Fork-Join
[](#cb268-9)return validate(request)
[](#cb268-10)    .flatMap(this::validateOrder)
[](#cb268-11)    .flatMap(this::processOrder);
[](#cb268-12)
[](#cb268-13)private Result<ValidRequest> validateOrder(ValidRequest req) {
[](#cb268-14)    return Result.all(checkInventory(req), validatePayment(req))
[](#cb268-15)        .map((inv, pay) -> req);
[](#cb268-16)}
```

* * *

## CHECKPOINT 6: Adding Logging

**Trigger**: Adding log statements

### Rules to Check

| Rule | Check | Fix |
| --- | --- | --- |
| G1 | Is logging conditional on data? | Remove condition |
| G2 | Logger passed as parameter? | Move logging to owner |
| G3 | Logging in pure transformation? | Move to terminal operation |
| G4 | Duplicate logging across layers? | Single layer logs |

### Ownership Pattern

```
[](#cb269-1)// VIOLATION: Caller logs for callee
[](#cb269-2)cache.refresh()
[](#cb269-3)    .onSuccess(count -> log.debug("Refreshed {}", count));
[](#cb269-4)
[](#cb269-5)// FIX: Cache owns its logging
[](#cb269-6)// In GenerationCache:
[](#cb269-7)public Result<Integer> refresh() {
[](#cb269-8)    return doRefresh()
[](#cb269-9)        .onSuccess(count -> log.debug("Refreshed {}", count));
[](#cb269-10)}
```

* * *

## CHECKPOINT 7: Review Completeness

**Trigger**: Before submitting code for review

### Verification Checklist

* * *

## CHECKPOINT 8: Implementation Patterns

**Trigger**: Choosing implementation style

### Nested Record vs Lambda Pattern

```
Does implementation need state beyond parameters?
|-- YES -> Use nested record pattern
|-- NO: Is it a functional interface?
    |-- YES -> Use lambda pattern
    |-- NO -> Use nested record pattern
```

**Nested record pattern** (state needed):

```
[](#cb271-1)static GenerationCache generationCache(WorkConfig config) {
[](#cb271-2)    record generationCache(
[](#cb271-3)        AtomicReference<Instant> lastRefreshTime,
[](#cb271-4)        ConcurrentMap<String, Generation> cache,
[](#cb271-5)        WorkConfig config
[](#cb271-6)    ) implements GenerationCache {
[](#cb271-7)        @Override
[](#cb271-8)        public Result<Unit> refresh() { ... }
[](#cb271-9)    }
[](#cb271-10)
[](#cb271-11)    return new generationCache(
[](#cb271-12)        new AtomicReference<>(Instant.EPOCH),
[](#cb271-13)        new ConcurrentHashMap<>(),
[](#cb271-14)        config
[](#cb271-15)    );
[](#cb271-16)}
```

**Lambda pattern** (functional interface, no state):

```
[](#cb272-1)static Step validate(Validator validator) {
[](#cb272-2)    return ctx -> validator.validate(ctx.input());
[](#cb272-3)}
```

* * *

## Quick Reference: Violation -> Fix Patterns

| Violation | Detection | Fix |
| --- | --- | --- |
| Multi-statement lambda | `{ }` with multiple lines | Extract to method |
| Nested monadic ops | `.flatMap(x -> y.map(...))` | Extract inner to method |
| Always-succeeding Result | `Result.success(new X())` | Return X directly |
| Mixed I/O and domain | File/DB ops in domain class | Split to adapter |
| Primitive obsession | `String url`, `int poolSize` | Create value object |
| Conditional logging | `if (x) log.debug()` | Remove condition |
| Logger as parameter | `method(Logger log)` | Move logging to owner |

* * *

## Application Order

### When Implementing New Code

1.  **Design phase**: Apply Checkpoint 4 (class design)
2.  **Signature phase**: Apply Checkpoint 2 (return types), Checkpoint 3 (factories)
3.  **Implementation phase**: Apply Checkpoint 1 (lambdas), Checkpoint 5 (chains), Checkpoint 8 (patterns)
4.  **Polish phase**: Apply Checkpoint 6 (logging)
5.  **Completion phase**: Apply Checkpoint 7 (review)

### When Reviewing Existing Code

1.  **Scan for lambdas** (`->`) - apply Checkpoint 1
2.  **Scan for return types** - apply Checkpoint 2
3.  **Scan for factories** - apply Checkpoint 3
4.  **Scan for mixed responsibilities** - apply Checkpoint 4
5.  **Scan for logging** - apply Checkpoint 6
6.  **Final verification** - apply Checkpoint 7

* * *

## Key Takeaways

1.  **8 checkpoints** - Cover all aspects of JBCT
2.  **Apply systematically** - Violations caught early, not in review
3.  **Quick reference tables** - For immediate lookup
4.  **Order matters** - Design -> Signature -> Implementation -> Polish
5.  **100% compliance** - Achievable through systematic verification

* * *

## Exercises

See [Appendix B](appendix-b-exercises.md) for exercises on: - Exercise 6.1: Checkpoint application practice - Exercise 6.3: Code review using checkpoints

* * *

## What’s Next

[Chapter 17](ch17-migration-strategies.md) covers migration strategies for adopting JBCT in existing codebases.

# Chapter 17: Migration Strategies

This chapter provides a practical playbook for adopting JBCT in existing codebases. Whether you’re working with a legacy monolith or a modern Spring Boot application, you’ll learn how to migrate incrementally without disrupting ongoing development.

* * *

## Assessment: Is Your Codebase Ready?

Before migrating, evaluate your starting point.

### Readiness Checklist

| Factor | Ready | Needs Work |
| --- | --- | --- |
| Java version | 17+ (records, sealed interfaces) | Upgrade first |
| Build tool | Maven or Gradle | Any modern build tool |
| Test coverage | Some tests exist | Add tests before refactoring |
| Team size | Any | Larger teams need more coordination |
| Release cycle | Regular releases | Establish before major changes |

### Code Smell Indicators

These patterns indicate high-value migration targets:

```
[](#cb273-1)// 1\. Validation scattered across layers
[](#cb273-2)@PostMapping("/users")
[](#cb273-3)public ResponseEntity<?> createUser(@RequestBody UserDto dto) {
[](#cb273-4)    if (dto.getEmail() == null || dto.getEmail().isEmpty()) {
[](#cb273-5)        return ResponseEntity.badRequest().body("Email required");
[](#cb273-6)    }
[](#cb273-7)    if (!dto.getEmail().contains("@")) {
[](#cb273-8)        return ResponseEntity.badRequest().body("Invalid email");
[](#cb273-9)    }
[](#cb273-10)    // ... more validation
[](#cb273-11)    userService.create(dto);  // Service also validates!
[](#cb273-12)}
[](#cb273-13)
[](#cb273-14)// 2\. Null checks everywhere
[](#cb273-15)public Order processOrder(Order order) {
[](#cb273-16)    if (order == null) return null;
[](#cb273-17)    if (order.getCustomer() == null) return null;
[](#cb273-18)    if (order.getCustomer().getAddress() == null) {
[](#cb273-19)        throw new ValidationException("Address required");
[](#cb273-20)    }
[](#cb273-21)    // ... actual logic buried under null checks
[](#cb273-22)}
[](#cb273-23)
[](#cb273-24)// 3\. Exception-based control flow
[](#cb273-25)public User findUser(Long id) {
[](#cb273-26)    try {
[](#cb273-27)        return repository.findById(id)
[](#cb273-28)            .orElseThrow(() -> new UserNotFoundException(id));
[](#cb273-29)    } catch (DataAccessException e) {
[](#cb273-30)        throw new ServiceException("Database error", e);
[](#cb273-31)    }
[](#cb273-32)}
[](#cb273-33)
[](#cb273-34)// 4\. Mixed concerns in services
[](#cb273-35)@Service
[](#cb273-36)public class UserService {
[](#cb273-37)    public User register(UserDto dto) {
[](#cb273-38)        // Validation
[](#cb273-39)        validateEmail(dto.getEmail());
[](#cb273-40)        validatePassword(dto.getPassword());
[](#cb273-41)
[](#cb273-42)        // Business logic
[](#cb273-43)        if (userRepository.existsByEmail(dto.getEmail())) {
[](#cb273-44)            throw new EmailExistsException();
[](#cb273-45)        }
[](#cb273-46)
[](#cb273-47)        // Infrastructure
[](#cb273-48)        String hashedPassword = passwordEncoder.encode(dto.getPassword());
[](#cb273-49)        User user = new User(dto.getEmail(), hashedPassword);
[](#cb273-50)        return userRepository.save(user);
[](#cb273-51)    }
[](#cb273-52)}
```

* * *

## Migration Phases

### Phase 1: Value Objects Only (Week 1-2)

**Goal:** Introduce parse-don’t-validate without changing existing code structure.

**What to do:** 1\. Add Pragmatica Lite dependency 2. Create value objects for commonly validated fields 3\. Use value objects in new code 4\. Gradually replace primitives in existing code

**Start with these value objects:** - Email - Password - UserId / CustomerId / OrderId - Money / Currency - Phone number

**Example: Adding Email value object**

```
[](#cb274-1)// NEW: Value object
[](#cb274-2)public record Email(String value) {
[](#cb274-3)    private static final Pattern PATTERN = Pattern.compile("^[a-z0-9+_.-]+@[a-z0-9.-]+$");
[](#cb274-4)    private static final Cause INVALID = Causes.cause("Invalid email format");
[](#cb274-5)
[](#cb274-6)    public static Result<Email> email(String raw) {
[](#cb274-7)        return Verify.ensure(raw, Verify.Is::notBlank)
[](#cb274-8)            .map(String::trim)
[](#cb274-9)            .map(String::toLowerCase)
[](#cb274-10)            .filter(INVALID, PATTERN.asMatchPredicate())
[](#cb274-11)            .map(Email::new);
[](#cb274-12)    }
[](#cb274-13)}
[](#cb274-14)
[](#cb274-15)// EXISTING: Service method (unchanged initially)
[](#cb274-16)@Service
[](#cb274-17)public class UserService {
[](#cb274-18)    public User register(String email, String password) {
[](#cb274-19)        // Existing validation still here
[](#cb274-20)        if (email == null || !email.contains("@")) {
[](#cb274-21)            throw new ValidationException("Invalid email");
[](#cb274-22)        }
[](#cb274-23)        // ... rest of method
[](#cb274-24)    }
[](#cb274-25)}
[](#cb274-26)
[](#cb274-27)// NEW: Parallel method using value object
[](#cb274-28)public Result<User> registerValidated(Email email, Password password) {
[](#cb274-29)    // No validation needed - email and password are already valid
[](#cb274-30)    return checkEmailUnique(email)
[](#cb274-31)        .flatMap(e -> hashPassword(password))
[](#cb274-32)        .map(hashed -> createUser(email, hashed));
[](#cb274-33)}
```

**Migration pattern:** 1\. Create value object 2\. Add parallel method accepting value object 3\. Update callers one by one 4. Delete old method when all callers migrated

### Phase 2: Result in New Code (Week 3-4)

**Goal:** Stop adding new exception-based code.

**Team agreement:** - All new methods return `Result<T>` or `Promise<T>` for fallible operations - New validation uses value object factories - Exceptions only at adapter boundaries (wrapping external libraries)

**Example: New feature with Result**

```
[](#cb275-1)// NEW FEATURE: Apply discount code
[](#cb275-2)public interface ApplyDiscount {
[](#cb275-3)    Result<DiscountedPrice> apply(OrderId orderId, DiscountCode code);
[](#cb275-4)}
[](#cb275-5)
[](#cb275-6)// Implementation
[](#cb275-7)public class ApplyDiscountImpl implements ApplyDiscount {
[](#cb275-8)    @Override
[](#cb275-9)    public Result<DiscountedPrice> apply(OrderId orderId, DiscountCode code) {
[](#cb275-10)        return findOrder(orderId)
[](#cb275-11)            .flatMap(order -> validateCode(code, order))
[](#cb275-12)            .map(discount -> calculateDiscountedPrice(order, discount));
[](#cb275-13)    }
[](#cb275-14)
[](#cb275-15)    private Result<Order> findOrder(OrderId id) {
[](#cb275-16)        return Option.option(orderRepository.findById(id.value()))
[](#cb275-17)            .toResult(OrderError.NOT_FOUND);
[](#cb275-18)    }
[](#cb275-19)
[](#cb275-20)    private Result<Discount> validateCode(DiscountCode code, Order order) {
[](#cb275-21)        return discountRepository.findByCode(code.value())
[](#cb275-22)            .toResult(DiscountError.INVALID_CODE)
[](#cb275-23)            .filter(DiscountError.EXPIRED, d -> !d.isExpired())
[](#cb275-24)            .filter(DiscountError.MIN_ORDER, d -> order.total().isGreaterThan(d.minOrder()));
[](#cb275-25)    }
[](#cb275-26)}
```

**Bridging old and new:**

```
[](#cb276-1)// Controller bridges exception world to Result world
[](#cb276-2)@PostMapping("/orders/{orderId}/discount")
[](#cb276-3)public ResponseEntity<?> applyDiscount(
[](#cb276-4)    @PathVariable String orderId,
[](#cb276-5)    @RequestBody DiscountRequest request
[](#cb276-6)) {
[](#cb276-7)    return Result.all(
[](#cb276-8)        OrderId.orderId(orderId),
[](#cb276-9)        DiscountCode.discountCode(request.code())
[](#cb276-10)    )
[](#cb276-11)    .flatMap((oid, code) -> applyDiscount.apply(oid, code))
[](#cb276-12)    .fold(
[](#cb276-13)        cause -> toErrorResponse(cause),
[](#cb276-14)        price -> ResponseEntity.ok(price)
[](#cb276-15)    );
[](#cb276-16)}
```

### Phase 3: Extract Use Cases (Week 5-8)

**Goal:** Separate business logic from framework code.

**Process:** 1\. Identify a service method with clear business logic 2\. Extract to use case interface 3\. Move implementation to use case factory 4\. Convert service to thin adapter

**Before: Fat service**

```
[](#cb277-1)@Service
[](#cb277-2)public class OrderService {
[](#cb277-3)    @Autowired private OrderRepository orderRepository;
[](#cb277-4)    @Autowired private PaymentGateway paymentGateway;
[](#cb277-5)    @Autowired private NotificationService notificationService;
[](#cb277-6)
[](#cb277-7)    @Transactional
[](#cb277-8)    public Order placeOrder(OrderDto dto) {
[](#cb277-9)        // Validation
[](#cb277-10)        if (dto.getItems().isEmpty()) {
[](#cb277-11)            throw new ValidationException("Order must have items");
[](#cb277-12)        }
[](#cb277-13)
[](#cb277-14)        // Check inventory
[](#cb277-15)        for (ItemDto item : dto.getItems()) {
[](#cb277-16)            if (!inventoryService.hasStock(item.getProductId(), item.getQuantity())) {
[](#cb277-17)                throw new InsufficientStockException(item.getProductId());
[](#cb277-18)            }
[](#cb277-19)        }
[](#cb277-20)
[](#cb277-21)        // Process payment
[](#cb277-22)        PaymentResult payment;
[](#cb277-23)        try {
[](#cb277-24)            payment = paymentGateway.charge(dto.getPaymentMethod(), calculateTotal(dto));
[](#cb277-25)        } catch (PaymentException e) {
[](#cb277-26)            throw new OrderException("Payment failed", e);
[](#cb277-27)        }
[](#cb277-28)
[](#cb277-29)        // Create order
[](#cb277-30)        Order order = new Order(dto.getCustomerId(), dto.getItems(), payment.getTransactionId());
[](#cb277-31)        orderRepository.save(order);
[](#cb277-32)
[](#cb277-33)        // Send notification (best effort)
[](#cb277-34)        try {
[](#cb277-35)            notificationService.sendOrderConfirmation(order);
[](#cb277-36)        } catch (Exception e) {
[](#cb277-37)            log.warn("Failed to send notification", e);
[](#cb277-38)        }
[](#cb277-39)
[](#cb277-40)        return order;
[](#cb277-41)    }
[](#cb277-42)}
```

**After: Use case + thin service**

```
[](#cb278-1)// Use case interface
[](#cb278-2)public interface PlaceOrder {
[](#cb278-3)    Promise<OrderConfirmation> execute(OrderRequest request);
[](#cb278-4)
[](#cb278-5)    interface CheckInventory {
[](#cb278-6)        Promise<ValidOrder> apply(ValidOrder order);
[](#cb278-7)    }
[](#cb278-8)
[](#cb278-9)    interface ProcessPayment {
[](#cb278-10)        Promise<PaymentConfirmation> apply(ValidOrder order);
[](#cb278-11)    }
[](#cb278-12)
[](#cb278-13)    interface SaveOrder {
[](#cb278-14)        Promise<OrderId> apply(ValidOrder order, PaymentConfirmation payment);
[](#cb278-15)    }
[](#cb278-16)
[](#cb278-17)    interface SendNotification {
[](#cb278-18)        Promise<Unit> apply(OrderId orderId);
[](#cb278-19)    }
[](#cb278-20)
[](#cb278-21)    static PlaceOrder placeOrder(
[](#cb278-22)        CheckInventory checkInventory,
[](#cb278-23)        ProcessPayment processPayment,
[](#cb278-24)        SaveOrder saveOrder,
[](#cb278-25)        SendNotification sendNotification
[](#cb278-26)    ) {
[](#cb278-27)        return request -> ValidOrder.validOrder(request)
[](#cb278-28)            .async()
[](#cb278-29)            .flatMap(checkInventory::apply)
[](#cb278-30)            .flatMap(order -> processPayment.apply(order)
[](#cb278-31)                .map(payment -> Pair.of(order, payment)))
[](#cb278-32)            .flatMap(pair -> saveOrder.apply(pair.first(), pair.second()))
[](#cb278-33)            .onSuccess(orderId -> sendNotification.apply(orderId)
[](#cb278-34)                .onFailure(e -> { /* log but don't fail */ }))
[](#cb278-35)            .map(OrderConfirmation::new);
[](#cb278-36)    }
[](#cb278-37)}
[](#cb278-38)
[](#cb278-39)// Thin service (adapter)
[](#cb278-40)@Service
[](#cb278-41)public class OrderService {
[](#cb278-42)    private final PlaceOrder placeOrder;
[](#cb278-43)
[](#cb278-44)    public OrderService(
[](#cb278-45)        InventoryChecker inventoryChecker,
[](#cb278-46)        PaymentProcessor paymentProcessor,
[](#cb278-47)        JooqOrderRepository orderRepository,
[](#cb278-48)        EmailNotificationSender notificationSender
[](#cb278-49)    ) {
[](#cb278-50)        this.placeOrder = PlaceOrder.placeOrder(
[](#cb278-51)            inventoryChecker,
[](#cb278-52)            paymentProcessor,
[](#cb278-53)            orderRepository,
[](#cb278-54)            notificationSender
[](#cb278-55)        );
[](#cb278-56)    }
[](#cb278-57)
[](#cb278-58)    public Order placeOrder(OrderDto dto) {
[](#cb278-59)        return placeOrder.execute(toRequest(dto))
[](#cb278-60)            .await()
[](#cb278-61)            .fold(
[](#cb278-62)                cause -> { throw toException(cause); },
[](#cb278-63)                confirmation -> toOrder(confirmation)
[](#cb278-64)            );
[](#cb278-65)    }
[](#cb278-66)}
```

### Phase 4: Adapter Isolation (Week 9-12)

**Goal:** All I/O wrapped in adapter leaves with Promise.lift.

**Identify adapters:** - Database repositories - HTTP clients - Message queue producers/consumers - File system access - Cache clients

**Example: Repository adapter**

```
[](#cb279-1)// Step interface
[](#cb279-2)public interface SaveUser {
[](#cb279-3)    Promise<UserId> apply(ValidUser user);
[](#cb279-4)}
[](#cb279-5)
[](#cb279-6)// Adapter implementation
[](#cb279-7)@Repository
[](#cb279-8)public class JooqUserRepository implements SaveUser {
[](#cb279-9)    private final DSLContext dsl;
[](#cb279-10)
[](#cb279-11)    @Override
[](#cb279-12)    public Promise<UserId> apply(ValidUser user) {
[](#cb279-13)        return Promise.lift(
[](#cb279-14)            RepositoryError.DatabaseFailure::new,
[](#cb279-15)            () -> {
[](#cb279-16)                String id = dsl.insertInto(USERS)
[](#cb279-17)                    .set(USERS.EMAIL, user.email().value())
[](#cb279-18)                    .set(USERS.PASSWORD_HASH, user.passwordHash().value())
[](#cb279-19)                    .returningResult(USERS.ID)
[](#cb279-20)                    .fetchSingle()
[](#cb279-21)                    .value1();
[](#cb279-22)                return new UserId(id);
[](#cb279-23)            }
[](#cb279-24)        );
[](#cb279-25)    }
[](#cb279-26)}
```

* * *

## Interoperability with Java Standard Library

### `Optional<T>` → `Option<T>`

```
[](#cb280-1)// Direct conversion
[](#cb280-2)Optional<User> javaOptional = repository.findById(id);
[](#cb280-3)Option<User> option = Option.from(javaOptional);
[](#cb280-4)
[](#cb280-5)// In adapter methods
[](#cb280-6)public Option<User> findById(UserId id) {
[](#cb280-7)    return Option.from(jpaRepository.findById(id.value()));
[](#cb280-8)}
[](#cb280-9)
[](#cb280-10)// Back to Optional (for framework integration)
[](#cb280-11)Optional<User> back = option.toOptional();
```

### `CompletableFuture<T>` → `Promise<T>`

```
[](#cb281-1)// Wrapping CompletableFuture in adapter
[](#cb281-2)public Promise<User> fetchUser(UserId id) {
[](#cb281-3)    var promise = Promise.<User>promise();
[](#cb281-4)
[](#cb281-5)    CompletableFuture<User> cf = httpClient.getUser(id.value());
[](#cb281-6)    cf.whenComplete((result, error) -> {
[](#cb281-7)        if (error != null) {
[](#cb281-8)            promise.fail(Causes.fromThrowable(error));
[](#cb281-9)        } else {
[](#cb281-10)            promise.succeed(result);
[](#cb281-11)        }
[](#cb281-12)    });
[](#cb281-13)
[](#cb281-14)    return promise;
[](#cb281-15)}
[](#cb281-16)
[](#cb281-17)// Helper method for common pattern
[](#cb281-18)public static <T> Promise<T> fromCompletableFuture(
[](#cb281-19)        CompletableFuture<T> cf,
[](#cb281-20)        Fn1<Cause, Throwable> errorMapper) {
[](#cb281-21)    var promise = Promise.<T>promise();
[](#cb281-22)    cf.whenComplete((result, error) -> {
[](#cb281-23)        if (error != null) {
[](#cb281-24)            promise.fail(errorMapper.apply(error));
[](#cb281-25)        } else {
[](#cb281-26)            promise.succeed(result);
[](#cb281-27)        }
[](#cb281-28)    });
[](#cb281-29)    return promise;
[](#cb281-30)}
```

### Exceptions → Cause Mapping

**In adapters - use Promise.lift:**

```
[](#cb282-1)public Promise<User> findUser(UserId id) {
[](#cb282-2)    return Promise.lift(
[](#cb282-3)        DatabaseError::new,  // Exception → Cause
[](#cb282-4)        () -> jdbcTemplate.queryForObject(SQL, mapper, id.value())
[](#cb282-5)    );
[](#cb282-6)}
```

**Custom exception mapping:**

```
[](#cb283-1)public Promise<Payment> processPayment(PaymentRequest request) {
[](#cb283-2)    return Promise.lift(
[](#cb283-3)        this::mapPaymentException,  // Custom mapper
[](#cb283-4)        () -> paymentGateway.charge(request)
[](#cb283-5)    );
[](#cb283-6)}
[](#cb283-7)
[](#cb283-8)private Cause mapPaymentException(Throwable t) {
[](#cb283-9)    return switch (t) {
[](#cb283-10)        case InsufficientFundsException e -> new PaymentError.InsufficientFunds(e.getMessage());
[](#cb283-11)        case CardDeclinedException e -> new PaymentError.CardDeclined(e.getMessage());
[](#cb283-12)        case NetworkException e -> new PaymentError.ServiceUnavailable(e.getMessage());
[](#cb283-13)        default -> Causes.fromThrowable(t);
[](#cb283-14)    };
[](#cb283-15)}
```

### Transitional Adapter Layer

During migration, create adapter methods that bridge old and new code:

```
[](#cb284-1)// Legacy service (throws exceptions)
[](#cb284-2)public class LegacyUserService {
[](#cb284-3)    public User findUser(String id) throws UserNotFoundException {
[](#cb284-4)        // ... legacy implementation
[](#cb284-5)    }
[](#cb284-6)}
[](#cb284-7)
[](#cb284-8)// JBCT adapter wrapping legacy service
[](#cb284-9)public class UserServiceAdapter implements FindUser {
[](#cb284-10)    private final LegacyUserService legacy;
[](#cb284-11)
[](#cb284-12)    @Override
[](#cb284-13)    public Promise<User> apply(UserId id) {
[](#cb284-14)        return Promise.lift(
[](#cb284-15)            this::mapLegacyError,
[](#cb284-16)            () -> legacy.findUser(id.value())
[](#cb284-17)        );
[](#cb284-18)    }
[](#cb284-19)
[](#cb284-20)    private Cause mapLegacyError(Throwable t) {
[](#cb284-21)        return switch (t) {
[](#cb284-22)            case UserNotFoundException e -> UserError.NotFound.INSTANCE;
[](#cb284-23)            default -> Causes.fromThrowable(t);
[](#cb284-24)        };
[](#cb284-25)    }
[](#cb284-26)}
```

**Gradual replacement:** 1\. Create adapter wrapping legacy service 2\. Use adapter in new JBCT code 3\. Eventually replace legacy service with JBCT implementation 4\. Remove adapter when migration complete

* * *

## Team Adoption Strategies

### Strategy 1: Champion-Led

One developer becomes JBCT expert, writes initial examples, and reviews others’ code.

**Pros:** Fast start, consistent patterns **Cons:** Bottleneck, bus factor

### Strategy 2: New Feature First

All new features use JBCT. Existing code migrated only when touched.

**Pros:** No big-bang rewrite, natural adoption **Cons:** Mixed codebase for longer, context switching

### Strategy 3: Vertical Slice

Pick one use case, migrate completely from controller to database.

**Pros:** Complete example to learn from, proves value end-to-end **Cons:** Initial investment, may find integration issues late

### Recommendation

Combine strategies: 1\. Champion writes first vertical slice (Strategy 3) 2\. Team reviews and learns from example 3\. All new features use JBCT (Strategy 2) 4\. Gradual migration of existing code when touched

* * *

## Common Resistance and Responses

### “It’s too different from what we know”

**Response:** The patterns are simpler than exception handling. Compare:

```
[](#cb285-1)// Exception-based (hidden control flow)
[](#cb285-2)try {
[](#cb285-3)    User user = findUser(id);
[](#cb285-4)    if (user == null) throw new UserNotFoundException(id);
[](#cb285-5)    Order order = createOrder(user, items);
[](#cb285-6)    if (!paymentService.charge(order)) {
[](#cb285-7)        throw new PaymentException("Failed");
[](#cb285-8)    }
[](#cb285-9)    return order;
[](#cb285-10)} catch (UserNotFoundException e) {
[](#cb285-11)    return handleUserNotFound(e);
[](#cb285-12)} catch (PaymentException e) {
[](#cb285-13)    return handlePaymentFailed(e);
[](#cb285-14)} catch (Exception e) {
[](#cb285-15)    return handleUnknown(e);
[](#cb285-16)}
[](#cb285-17)
[](#cb285-18)// JBCT (explicit flow)
[](#cb285-19)return findUser(id)
[](#cb285-20)    .flatMap(user -> createOrder(user, items))
[](#cb285-21)    .flatMap(order -> chargePayment(order))
[](#cb285-22)    .fold(this::handleError, identity());
```

### “We don’t have time to rewrite everything”

**Response:** You don’t have to. Start with value objects only (Phase 1). That’s one week for immediate benefits. Each phase is incremental.

### “Our team doesn’t know functional programming”

**Response:** JBCT isn’t about FP. It’s about making code predictable. The functional patterns are just the mechanism. Focus on: - Every method declares its failure modes in the return type - Invalid data cannot be constructed - No hidden control flow

### “What about debugging?”

**Response:** Debugging is easier, not harder: - Stack traces show the actual call chain (no exception jumps) - Error causes are typed and carry context - IDE breakpoints work normally in lambdas - Logging can be added at any point in the chain

### “Performance overhead?”

**Response:** Negligible for business logic. Pragmatica Lite types are lightweight wrappers. The overhead is comparable to Optional. If you’re writing code where object allocation matters (tight loops, real-time systems), JBCT isn’t the right fit - but neither is typical Java web development.

* * *

## Migration Checklist

### Phase 1 Complete When:

### Phase 2 Complete When:

### Phase 3 Complete When:

### Phase 4 Complete When:

* * *

## Exercises

1.  **Audit your codebase:** Find three methods with scattered validation. Which value objects would consolidate them?

2.  **Plan Phase 1:** List the top 5 value objects your codebase needs. Prioritize by how many places validate the same data.

3.  **Identify extraction candidates:** Find a service method with more than 50 lines. Can you identify the Sequencer pattern in it?

4.  **Adapter inventory:** List all external dependencies (database, HTTP, message queue). Which ones throw checked exceptions?

* * *

## Summary

Migration to JBCT is incremental:

1.  **Phase 1:** Value objects only - immediate validation benefits
2.  **Phase 2:** Result in new code - stop adding exceptions
3.  **Phase 3:** Extract use cases - separate concerns
4.  **Phase 4:** Adapter isolation - complete the boundary

Key principles: - Never big-bang rewrite - Each phase delivers value independently - Mixed codebase is acceptable during transition - Team buy-in through working examples, not mandates

# Chapter 18: Comparison with Other Approaches

JBCT doesn’t exist in isolation. This chapter compares it to other architectural approaches you may encounter, helping you understand where JBCT fits and what it borrows from or rejects in other methodologies.

* * *

## Traditional Layered Architecture

The most common Java backend architecture.

### Structure

```
Controller Layer     → Receives HTTP requests, validates DTOs
    ↓
Service Layer        → Business logic, transactions, orchestration
    ↓
Repository Layer     → Database access, queries
    ↓
Entity Layer         → JPA entities, data structures
```

### Example

```
[](#cb287-1)@RestController
[](#cb287-2)public class UserController {
[](#cb287-3)    @Autowired private UserService userService;
[](#cb287-4)
[](#cb287-5)    @PostMapping("/users")
[](#cb287-6)    public ResponseEntity<UserDto> createUser(@Valid @RequestBody CreateUserDto dto) {
[](#cb287-7)        User user = userService.createUser(dto);
[](#cb287-8)        return ResponseEntity.ok(toDto(user));
[](#cb287-9)    }
[](#cb287-10)}
[](#cb287-11)
[](#cb287-12)@Service
[](#cb287-13)public class UserService {
[](#cb287-14)    @Autowired private UserRepository userRepository;
[](#cb287-15)    @Autowired private PasswordEncoder passwordEncoder;
[](#cb287-16)
[](#cb287-17)    @Transactional
[](#cb287-18)    public User createUser(CreateUserDto dto) {
[](#cb287-19)        if (userRepository.existsByEmail(dto.getEmail())) {
[](#cb287-20)            throw new EmailExistsException();
[](#cb287-21)        }
[](#cb287-22)        User user = new User();
[](#cb287-23)        user.setEmail(dto.getEmail());
[](#cb287-24)        user.setPassword(passwordEncoder.encode(dto.getPassword()));
[](#cb287-25)        return userRepository.save(user);
[](#cb287-26)    }
[](#cb287-27)}
[](#cb287-28)
[](#cb287-29)@Repository
[](#cb287-30)public interface UserRepository extends JpaRepository<User, Long> {
[](#cb287-31)    boolean existsByEmail(String email);
[](#cb287-32)}
```

### What JBCT Changes

| Aspect | Layered | JBCT |
| --- | --- | --- |
| Error handling | Exceptions | Result/Promise with Cause |
| Validation | @Valid + manual checks | Parse-don’t-validate |
| Business logic location | Service layer | Use case interface |
| Data flow | Mutable entities | Immutable value objects |
| Dependencies | Field injection | Constructor injection via factory |

### What JBCT Keeps

*   Separation of concerns (different responsibility per layer)
*   Controllers at the boundary
*   Repository pattern for data access

### Verdict

JBCT refines layered architecture rather than replacing it. The layers still exist, but with explicit error handling and immutable data flow.

* * *

## Hexagonal Architecture (Ports and Adapters)

Popularized by Alistair Cockburn. Core idea: business logic at the center, adapters at the edges.

### Structure

```
 ┌─────────────────────┐
   HTTP Adapter ───→│                     │←─── Database Adapter
                    │   Domain / Core     │
  Queue Adapter ───→│   (Business Logic)  │←─── External API Adapter
                    │                     │
                    └─────────────────────┘
                           ↑   ↑
                        Ports (Interfaces)
```

### Example

```
[](#cb289-1)// Port (interface defined by domain)
[](#cb289-2)public interface UserRepository {
[](#cb289-3)    Optional<User> findByEmail(Email email);
[](#cb289-4)    void save(User user);
[](#cb289-5)}
[](#cb289-6)
[](#cb289-7)// Domain service (pure business logic)
[](#cb289-8)public class UserRegistrationService {
[](#cb289-9)    private final UserRepository userRepository;
[](#cb289-10)    private final PasswordHasher passwordHasher;
[](#cb289-11)
[](#cb289-12)    public User register(Email email, Password password) {
[](#cb289-13)        if (userRepository.findByEmail(email).isPresent()) {
[](#cb289-14)            throw new EmailAlreadyExistsException(email);
[](#cb289-15)        }
[](#cb289-16)        HashedPassword hashed = passwordHasher.hash(password);
[](#cb289-17)        User user = new User(email, hashed);
[](#cb289-18)        userRepository.save(user);
[](#cb289-19)        return user;
[](#cb289-20)    }
[](#cb289-21)}
[](#cb289-22)
[](#cb289-23)// Adapter (implements port)
[](#cb289-24)public class JpaUserRepository implements UserRepository {
[](#cb289-25)    private final JpaUserEntityRepository jpaRepo;
[](#cb289-26)
[](#cb289-27)    @Override
[](#cb289-28)    public Optional<User> findByEmail(Email email) {
[](#cb289-29)        return jpaRepo.findByEmail(email.value())
[](#cb289-30)            .map(this::toDomain);
[](#cb289-31)    }
[](#cb289-32)}
```

### What JBCT Borrows

*   **Ports concept** → Step interfaces
*   **Adapters concept** → Adapter leaves
*   **Domain at center** → Use cases with pure business logic
*   **Dependency inversion** → Steps injected into use case factory

### What JBCT Adds

*   **Explicit error handling** - Hexagonal doesn’t prescribe how to handle errors
*   **Functional composition** - Hexagonal uses imperative style
*   **Typed failures** - Cause types instead of exceptions
*   **Structural patterns** - Leaf, Sequencer, Fork-Join provide composition vocabulary

### Key Difference

Hexagonal focuses on **where** code lives (inside vs outside the hexagon). JBCT focuses on **how** code composes (patterns, error handling, data flow).

### Verdict

JBCT and Hexagonal are complementary. Use Hexagonal for high-level architecture, JBCT for implementation patterns within that architecture.

* * *

## Clean Architecture

Uncle Bob’s architecture with explicit dependency rules.

### Structure

```
┌───────────────────────────────────────────────┐
│              Frameworks & Drivers              │
│  ┌───────────────────────────────────────┐    │
│  │           Interface Adapters           │    │
│  │  ┌───────────────────────────────┐    │    │
│  │  │        Application Layer       │    │    │
│  │  │  ┌───────────────────────┐    │    │    │
│  │  │  │     Domain Layer      │    │    │    │
│  │  │  │     (Entities)        │    │    │    │
│  │  │  └───────────────────────┘    │    │    │
│  │  └───────────────────────────────┘    │    │
│  └───────────────────────────────────────┘    │
└───────────────────────────────────────────────┘
```

Dependencies point inward. Inner layers don’t know about outer layers.

### Example

```
[](#cb291-1)// Entity (innermost)
[](#cb291-2)public class User {
[](#cb291-3)    private UserId id;
[](#cb291-4)    private Email email;
[](#cb291-5)    private HashedPassword password;
[](#cb291-6)
[](#cb291-7)    public boolean canLogin(Password attempt, PasswordHasher hasher) {
[](#cb291-8)        return hasher.verify(attempt, this.password);
[](#cb291-9)    }
[](#cb291-10)}
[](#cb291-11)
[](#cb291-12)// Use Case (application layer)
[](#cb291-13)public class RegisterUserUseCase {
[](#cb291-14)    private final UserGateway userGateway;
[](#cb291-15)    private final PasswordHasher passwordHasher;
[](#cb291-16)
[](#cb291-17)    public RegisterUserResponse execute(RegisterUserRequest request) {
[](#cb291-18)        Email email = new Email(request.email);
[](#cb291-19)        if (userGateway.existsByEmail(email)) {
[](#cb291-20)            return RegisterUserResponse.failure("Email exists");
[](#cb291-21)        }
[](#cb291-22)        // ... rest of use case
[](#cb291-23)    }
[](#cb291-24)}
[](#cb291-25)
[](#cb291-26)// Gateway interface (application layer, implemented by adapter)
[](#cb291-27)public interface UserGateway {
[](#cb291-28)    boolean existsByEmail(Email email);
[](#cb291-29)    void save(User user);
[](#cb291-30)}
```

### What JBCT Borrows

*   **Use case as first-class concept** → UseCase interface
*   **Dependency rule** → Use cases don’t depend on adapters
*   **Request/Response models** → Request/ValidRequest/Response records

### What JBCT Changes

| Aspect | Clean Architecture | JBCT |
| --- | --- | --- |
| Use case return | Response objects | Result/Promise |
| Error handling | Response codes or exceptions | Typed Cause |
| Entity behavior | Rich domain model | Value objects + pure functions |
| Composition | Imperative orchestration | Monadic chains |

### Key Difference

Clean Architecture prescribes **dependency direction** but not **composition style**. JBCT prescribes both.

### Verdict

JBCT can be implemented within Clean Architecture. The layers map naturally: - Entities → Value objects - Use Cases → Use case interfaces - Interface Adapters → Adapter leaves - Frameworks → Spring configuration

* * *

## Railway-Oriented Programming

Scott Wlaschin’s approach from F#, using “two-track” types for error handling.

### Concept

```
Success Track:  ───●───────●───────●───────●─── → Success
                   │       │       │       │
                   ↓       ↓       ↓       ↓
Failure Track:  ───────────────────────────────→ Failure
```

Each function either stays on success track or switches to failure track.

### Example (F# style in Java)

```
[](#cb293-1)public Result<User> registerUser(String email, String password) {
[](#cb293-2)    return validateEmail(email)           // Success or Failure
[](#cb293-3)        .flatMap(this::validatePassword)  // Continue or stay failed
[](#cb293-4)        .flatMap(this::checkUniqueness)   // Continue or stay failed
[](#cb293-5)        .flatMap(this::createUser);       // Continue or stay failed
[](#cb293-6)}
```

### What JBCT Borrows

*   **Two-track model** → `Result<T>` is exactly this
*   **flatMap for composition** → Same chaining style
*   **Errors as values** → Cause instead of exceptions

### What JBCT Adds

*   **Four tracks, not two** - T, Option, Result, Promise for different semantics
*   **Structural patterns** - Named patterns (Sequencer, Fork-Join) beyond just chaining
*   **Aggregation** - Result.all() for parallel validation
*   **Async integration** - Promise extends the model to async operations

### Key Difference

ROP is a technique for error handling. JBCT is a complete methodology including project structure, testing, and team practices.

### Verdict

JBCT incorporates ROP as its error handling model, then builds a full methodology around it.

* * *

## vavr (formerly Javaslang)

Functional programming library for Java.

### What vavr Provides

```
[](#cb294-1)import io.vavr.control.Try;
[](#cb294-2)import io.vavr.control.Either;
[](#cb294-3)import io.vavr.control.Option;
[](#cb294-4)
[](#cb294-5)// Try - captures exceptions
[](#cb294-6)Try<Integer> result = Try.of(() -> Integer.parseInt(input));
[](#cb294-7)
[](#cb294-8)// Either - success or failure with typed error
[](#cb294-9)Either<Error, User> user = findUser(id);
[](#cb294-10)
[](#cb294-11)// Option - presence or absence
[](#cb294-12)Option<User> maybeUser = Option.of(nullableUser);
[](#cb294-13)
[](#cb294-14)// Pattern matching
[](#cb294-15)String message = Match(result).of(
[](#cb294-16)    Case($Success($()), "Parsed"),
[](#cb294-17)    Case($Failure($()), "Failed")
[](#cb294-18));
```

### Comparison

| Feature | vavr | Pragmatica Lite |
| --- | --- | --- |
| Option type | `Option<T>` | `Option<T>` |
| Error type | `Either<L, R>` or `Try<T>` | `Result<T>` with `Cause` |
| Async type | None (use CompletableFuture) | `Promise<T>` |
| Collections | Immutable collections | Uses Java collections |
| Pattern matching | Built-in DSL | Standard switch expressions |
| Tuples | Tuple1-8 | Use records |

### Key Differences

1.  **vavr is a library, JBCT is a methodology** - vavr provides types, JBCT provides patterns, structure, and practices.

2.  **Error typing** - vavr’s Either has generic left type. Pragmatica Lite’s Result always uses Cause, providing consistent error handling.

3.  **Async story** - vavr doesn’t provide async primitives. JBCT’s Promise integrates error handling with async operations.

4.  **Simplicity** - vavr includes many FP features (persistent collections, pattern matching DSL, streams). Pragmatica Lite focuses on the minimum needed for JBCT.

### When to Use vavr

*   You want immutable collections
*   You’re building a library with FP patterns
*   You need persistent data structures
*   You want pattern matching DSL

### When to Use Pragmatica Lite

*   You’re building backend services
*   You want a complete methodology (not just types)
*   You need integrated async support
*   You prefer simplicity over features

### Verdict

vavr is a more comprehensive FP library. Pragmatica Lite is purpose-built for JBCT. You could use vavr to implement JBCT patterns, but you’d need to add your own Promise type and establish your own structural patterns.

* * *

## Arrow-kt (Kotlin)

Functional programming library for Kotlin.

### What Arrow Provides

```
[](#cb295-1)// Either for errors
[](#cb295-2)fun divide(a: Int, b: Int): Either<DivisionError, Int> =
[](#cb295-3)    if (b == 0) DivisionError.DivideByZero.left()
[](#cb295-4)    else (a / b).right()
[](#cb295-5)
[](#cb295-6)// Validated for accumulating errors
[](#cb295-7)fun validateUser(name: String, age: Int): ValidatedNel<ValidationError, User> =
[](#cb295-8)    ValidatedNel.applicative<ValidationError>().mapN(
[](#cb295-9)        validateName(name),
[](#cb295-10)        validateAge(age)
[](#cb295-11)    ) { (n, a) -> User(n, a) }
[](#cb295-12)
[](#cb295-13)// Effect for async
[](#cb295-14)suspend fun fetchUser(id: UserId): Either<Error, User> =
[](#cb295-15)    either { userRepository.findById(id).bind() }
```

### Why Mention It?

Arrow-kt demonstrates that these patterns work well in a JVM language. Key insights:

*   **Kotlin’s coroutines + Either** = Similar to `Promise<T>`
*   **Validated type** = Similar to Result.all() accumulation
*   **Typed errors** = Same as JBCT’s Cause

### Verdict

If you’re on Kotlin, Arrow-kt provides similar capabilities to JBCT. The concepts transfer, but the syntax differs due to language features (coroutines, extension functions, sealed classes).

* * *

## Summary: Where JBCT Fits

```
 Architectural Style
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
    Layered           Hexagonal           Clean
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                    Implementation Style
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
   Imperative        Railway (ROP)         FP Library
   (exceptions)      (Result types)        (vavr, Arrow)
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                         JBCT
                           │
                    ┌──────┴──────┐
                    │             │
              Pragmatica     Structural
              Lite Core      Patterns
```

JBCT: - Works within any architectural style (Layered, Hexagonal, Clean) - Uses railway-oriented error handling - Is simpler than full FP libraries - Provides structural patterns other approaches lack - Includes methodology beyond just types

* * *

## Exercises

1.  **Map your architecture:** Does your current project use Layered, Hexagonal, or Clean Architecture? Where would JBCT patterns fit?

2.  **Compare error handling:** Take one exception-based method in your codebase. Rewrite it using ROP style with Result. What errors were implicit?

3.  **Evaluate vavr:** If you use vavr, identify which features you actually use. Could you replace it with Pragmatica Lite?

4.  **Cross-language patterns:** If you have Kotlin services, compare how Arrow-kt’s Either compares to JBCT’s Result. Are the patterns similar?

* * *

## Summary

JBCT is not revolutionary - it combines proven ideas:

| Idea | Source |
| --- | --- |
| Ports and Adapters | Hexagonal Architecture |
| Use Cases as first-class | Clean Architecture |
| Errors as values | Railway-Oriented Programming |
| Functional types | vavr, Arrow-kt, Haskell |
| Parse don’t validate | Type-driven design |

What JBCT adds: - **Unified methodology** - Architecture + implementation + testing - **Structural patterns** - Named, composable patterns - **Team practices** - Migration path, code review guidelines - **AI optimization** - Predictable code for AI collaboration

The goal isn’t originality - it’s unification.

# Chapter 19: Troubleshooting & FAQ

This chapter consolidates common issues, debugging techniques, and frequently asked questions about JBCT.

* * *

## Debugging Monadic Chains

### Problem: “I can’t see what’s happening inside flatMap”

**Symptom:** You have a chain like this and can’t figure out where it fails:

```
[](#cb297-1)return validateRequest(request)
[](#cb297-2)    .flatMap(this::checkPermissions)
[](#cb297-3)    .flatMap(this::processData)
[](#cb297-4)    .flatMap(this::saveResult);
```

**Solution 1: Add intermediate logging**

```
[](#cb298-1)return validateRequest(request)
[](#cb298-2)    .onSuccess(r -> log.debug("Validated: {}", r))
[](#cb298-3)    .onFailure(c -> log.debug("Validation failed: {}", c.message()))
[](#cb298-4)    .flatMap(this::checkPermissions)
[](#cb298-5)    .onSuccess(r -> log.debug("Permissions OK: {}", r))
[](#cb298-6)    .onFailure(c -> log.debug("Permission denied: {}", c.message()))
[](#cb298-7)    .flatMap(this::processData)
[](#cb298-8)    // ...
```

**Solution 2: Use IDE breakpoints**

Set breakpoints inside the lambda:

```
[](#cb299-1).flatMap(data -> {
[](#cb299-2)    return processData(data);  // Breakpoint on this line
[](#cb299-3)})
```

**Solution 3: Extract to named methods**

```
[](#cb300-1)return validateRequest(request)
[](#cb300-2)    .flatMap(this::checkPermissionsStep)  // Breakpoint in method
[](#cb300-3)    .flatMap(this::processDataStep)
[](#cb300-4)    .flatMap(this::saveResultStep);
[](#cb300-5)
[](#cb300-6)private Result<Permissions> checkPermissionsStep(ValidRequest request) {
[](#cb300-7)    // Breakpoint here, full visibility
[](#cb300-8)    return checkPermissions(request);
[](#cb300-9)}
```

### Problem: “My Promise never resolves”

**Symptom:** Test hangs on `.await()` or production code times out.

**Checklist:**

1.  **Is the Promise created but never resolved?**

```
[](#cb301-1)Promise<User> promise = Promise.promise();  // Unresolved!
[](#cb301-2)// Missing: promise.succeed(user) or promise.fail(cause)
```

2.  **Is there a deadlock in async code?**

```
[](#cb302-1)// WRONG: Blocking inside async chain
[](#cb302-2).flatMap(data -> {
[](#cb302-3)    return otherPromise.await().async();  // Blocks the thread!
[](#cb302-4)})
[](#cb302-5)
[](#cb302-6)// CORRECT: Chain without blocking
[](#cb302-7).flatMap(data -> otherPromise)
```

3.  **Is Promise.lift wrapping blocking code?**

```
[](#cb303-1)// This runs async - make sure the thread pool isn't exhausted
[](#cb303-2)Promise.lift(() -> {
[](#cb303-3)    Thread.sleep(10000);  // Blocks a thread
[](#cb303-4)    return result;
[](#cb303-5)});
```

**Debug technique:** Add timeout to isolate:

```
[](#cb304-1)promise
[](#cb304-2)    .timeout(TimeSpan.timeSpan(5).seconds())
[](#cb304-3)    .await()
[](#cb304-4)    .onFailure(cause -> log.error("Timed out or failed: {}", cause));
```

### Problem: “I’m getting CompositeCause but don’t know which validations failed”

**Symptom:** Result.all() fails but you only see “Multiple failures”.

**Solution:** Inspect the CompositeCause:

```
[](#cb305-1)result.onFailure(cause -> {
[](#cb305-2)    if (cause instanceof CompositeCause composite) {
[](#cb305-3)        composite.causes().forEach(c ->
[](#cb305-4)            log.error("Validation failure: {}", c.message())
[](#cb305-5)        );
[](#cb305-6)    } else {
[](#cb305-7)        log.error("Single failure: {}", cause.message());
[](#cb305-8)    }
[](#cb305-9)});
```

**Better solution:** Create specific error messages in value objects:

```
[](#cb306-1)public record Email(String value) {
[](#cb306-2)    private static final Fn1<Cause, String> INVALID =
[](#cb306-3)        Causes.forOneValue("Invalid email format: %s");
[](#cb306-4)
[](#cb306-5)    public static Result<Email> email(String raw) {
[](#cb306-6)        return Verify.ensure(raw, Verify.Is::notBlank)
[](#cb306-7)            .filter(INVALID, PATTERN.asMatchPredicate())
[](#cb306-8)            .map(Email::new);
[](#cb306-9)    }
[](#cb306-10)}
```

Now CompositeCause contains “Invalid email format: xyz” instead of generic message.

* * *

## Common Mistakes and Fixes

### Mistake: Nested Result/Promise

```
[](#cb307-1)// WRONG: Returns Result<Result<User>>
[](#cb307-2)public Result<Result<User>> findUser(String id) {
[](#cb307-3)    return UserId.userId(id)
[](#cb307-4)        .map(this::lookupUser);  // lookupUser returns Result<User>
[](#cb307-5)}
```

**Fix:** Use flatMap instead of map:

```
[](#cb308-1)// CORRECT: Returns Result<User>
[](#cb308-2)public Result<User> findUser(String id) {
[](#cb308-3)    return UserId.userId(id)
[](#cb308-4)        .flatMap(this::lookupUser);
[](#cb308-5)}
```

### Mistake: Ignoring the Result

```
[](#cb309-1)// WRONG: Result is created but never used
[](#cb309-2)public void processOrder(Order order) {
[](#cb309-3)    validateOrder(order);  // Returns Result<ValidOrder> but ignored!
[](#cb309-4)    saveOrder(order);
[](#cb309-5)}
```

**Fix:** Always handle the Result:

```
[](#cb310-1)// CORRECT: Result flows through
[](#cb310-2)public Result<OrderId> processOrder(Order order) {
[](#cb310-3)    return validateOrder(order)
[](#cb310-4)        .flatMap(this::saveOrder);
[](#cb310-5)}
```

### Mistake: Throwing inside monadic chain

```
[](#cb311-1)// WRONG: Exception breaks the chain
[](#cb311-2).flatMap(data -> {
[](#cb311-3)    if (data.isEmpty()) {
[](#cb311-4)        throw new IllegalStateException("Empty data");  // Escapes!
[](#cb311-5)    }
[](#cb311-6)    return process(data);
[](#cb311-7)})
```

**Fix:** Return failure instead:

```
[](#cb312-1)// CORRECT: Error stays in the chain
[](#cb312-2).flatMap(data -> {
[](#cb312-3)    if (data.isEmpty()) {
[](#cb312-4)        return EMPTY_DATA_ERROR.result();
[](#cb312-5)    }
[](#cb312-6)    return process(data);
[](#cb312-7)})
[](#cb312-8)
[](#cb312-9)// BETTER: Use filter
[](#cb312-10).filter(EMPTY_DATA_ERROR, data -> !data.isEmpty())
[](#cb312-11).flatMap(this::process)
```

### Mistake: Multi-statement lambda

```
[](#cb313-1)// WRONG: Violates single level of abstraction
[](#cb313-2).map(user -> {
[](#cb313-3)    log.info("Processing user: {}", user.id());
[](#cb313-4)    String normalized = user.email().toLowerCase();
[](#cb313-5)    cache.put(user.id(), user);
[](#cb313-6)    return new ProcessedUser(user.id(), normalized);
[](#cb313-7)})
```

**Fix:** Extract to named method:

```
[](#cb314-1)// CORRECT: Simple lambda, logic in method
[](#cb314-2).map(this::processUser)
[](#cb314-3)
[](#cb314-4)private ProcessedUser processUser(User user) {
[](#cb314-5)    log.info("Processing user: {}", user.id());
[](#cb314-6)    String normalized = user.email().toLowerCase();
[](#cb314-7)    cache.put(user.id(), user);
[](#cb314-8)    return new ProcessedUser(user.id(), normalized);
[](#cb314-9)}
```

### Mistake: Using Optional instead of Option

```
[](#cb315-1)// WRONG: Mixing Java Optional with Pragmatica types
[](#cb315-2)public Result<User> findUser(UserId id) {
[](#cb315-3)    Optional<User> optional = repository.findById(id);
[](#cb315-4)    if (optional.isPresent()) {
[](#cb315-5)        return Result.success(optional.get());
[](#cb315-6)    }
[](#cb315-7)    return USER_NOT_FOUND.result();
[](#cb315-8)}
```

**Fix:** Convert at the boundary:

```
[](#cb316-1)// CORRECT: Wrap immediately
[](#cb316-2)public Result<User> findUser(UserId id) {
[](#cb316-3)    return Option.option(repository.findById(id).orElse(null))
[](#cb316-4)        .toResult(USER_NOT_FOUND);
[](#cb316-5)}
[](#cb316-6)
[](#cb316-7)// OR: Use Option.from()
[](#cb316-8)public Result<User> findUser(UserId id) {
[](#cb316-9)    return Option.from(repository.findById(id))
[](#cb316-10)        .toResult(USER_NOT_FOUND);
[](#cb316-11)}
```

### Mistake: Bypassing factory method

```
[](#cb317-1)// WRONG: Direct constructor call
[](#cb317-2)Email email = new Email("user@example.com");  // Skips validation!
[](#cb317-3)
[](#cb317-4)// CORRECT: Use factory method
[](#cb317-5)Result<Email> email = Email.email("user@example.com");
```

* * *

## IDE Setup

### IntelliJ IDEA

**Recommended settings:**

1.  **Enable parameter hints for lambdas:**
    *   Settings → Editor → Inlay Hints → Java → Parameter hints
    *   Enable “Show hints for lambdas”
2.  **Fold anonymous classes:**
    *   Settings → Editor → General → Code Folding
    *   Enable “Lambda expressions”
3.  **Live templates for JBCT patterns:**

```
// Template: jbctvo (Value Object)
public record $NAME$($TYPE$ value) {
    private static final Cause INVALID = Causes.cause("Invalid $NAME$");

    public static Result<$NAME$> $FACTORY$(String raw) {
        return Verify.ensure(raw, Verify.Is::notBlank)
            .map($NAME$::new);
    }
}

// Template: jbctuc (Use Case)
public interface $NAME$ {
    Promise<Response> execute(Request request);

    record Request($PARAMS$) {}
    record Response($RESULT$) {}

    static $NAME$ $FACTORY$($DEPS$) {
        return request -> ValidRequest.validRequest(request)
            .async()
            .flatMap($STEPS$);
    }
}
```

### VS Code

**Recommended extensions:** - Extension Pack for Java - Java Test Runner

**settings.json:**

```
[](#cb319-1){
[](#cb319-2)    "java.completion.chain.enabled": true,
[](#cb319-3)    "java.completion.filteredTypes": [
[](#cb319-4)        "java.util.Optional"  // Suggest Option instead
[](#cb319-5)    ]
[](#cb319-6)}
```

* * *

## Testing Troubleshooting

### Problem: “Test passes but shouldn’t”

**Symptom:** You expect failure but test passes silently.

```
[](#cb320-1)@Test
[](#cb320-2)void shouldFail() {
[](#cb320-3)    Email.email("invalid");  // Returns Result, but test doesn't check it!
[](#cb320-4)}
```

**Fix:** Always assert:

```
[](#cb321-1)@Test
[](#cb321-2)void email_fails_forInvalidInput() {
[](#cb321-3)    Email.email("invalid")
[](#cb321-4)        .onSuccess(Assertions::fail);  // Fail if unexpectedly succeeds
[](#cb321-5)}
```

### Problem: “Async test is flaky”

**Symptom:** Test sometimes passes, sometimes fails.

**Checklist:**

1.  **Are you awaiting the Promise?**

```
[](#cb322-1)// WRONG: Test completes before Promise resolves
[](#cb322-2)@Test
[](#cb322-3)void asyncTest() {
[](#cb322-4)    useCase.execute(request);  // Returns Promise, not awaited!
[](#cb322-5)}
[](#cb322-6)
[](#cb322-7)// CORRECT: Await before asserting
[](#cb322-8)@Test
[](#cb322-9)void asyncTest() {
[](#cb322-10)    useCase.execute(request)
[](#cb322-11)        .await()
[](#cb322-12)        .onFailure(Assertions::fail);
[](#cb322-13)}
```

2.  **Is there shared mutable state between tests?**

```
[](#cb323-1)// WRONG: Shared state
[](#cb323-2)private static List<String> logs = new ArrayList<>();
[](#cb323-3)
[](#cb323-4)// CORRECT: Per-test state
[](#cb323-5)private List<String> logs;
[](#cb323-6)
[](#cb323-7)@BeforeEach
[](#cb323-8)void setup() {
[](#cb323-9)    logs = new ArrayList<>();
[](#cb323-10)}
```

3.  **Are Promise timeouts too short?**

```
[](#cb324-1)// Increase timeout for CI environments
[](#cb324-2).await(TimeSpan.timeSpan(30).seconds())
```

### Problem: “Can’t create stub for step interface”

**Symptom:** Compilation error when creating lambda stub.

```
[](#cb325-1)// ERROR: Target type must be a functional interface
[](#cb325-2)var stub = req -> Promise.success(req);  // What type is this?
```

**Fix:** Declare the type explicitly:

```
[](#cb326-1)// CORRECT: Type declaration
[](#cb326-2)CheckEmail checkEmail = req -> Promise.success(req);
```

* * *

## FAQ

### General

**Q: Is JBCT only for microservices?**

A: No. JBCT works for any backend Java application - monoliths, microservices, serverless functions. The patterns are about code organization, not deployment topology.

**Q: Does JBCT require Spring Boot?**

A: No. JBCT is framework-agnostic. The examples use Spring Boot because it’s common, but the patterns work with Micronaut, Quarkus, plain Java, or any other framework.

**Q: Can I use JBCT with Kotlin?**

A: Yes, but consider Arrow-kt instead. Kotlin’s coroutines and extension functions provide more idiomatic alternatives. The concepts transfer directly.

**Q: What about reactive streams (Project Reactor, RxJava)?**

A: JBCT’s Promise is simpler than reactive streams. Use reactive streams when you need backpressure or complex stream operations. Use Promise for simple async request/response patterns.

### Error Handling

**Q: When should I use exceptions instead of Result?**

A: Use exceptions for: - Programming errors (IllegalArgumentException, NullPointerException) - Unrecoverable system failures - Framework requirements (Spring’s @Transactional rollback)

Use Result for: - Business failures (validation, not found, conflict) - Expected error conditions - Anything the caller might want to handle

**Q: How do I handle errors from third-party libraries that throw?**

A: Wrap at the adapter boundary:

```
[](#cb327-1)public Promise<User> findUser(UserId id) {
[](#cb327-2)    return Promise.lift(
[](#cb327-3)        DatabaseError::new,
[](#cb327-4)        () -> jdbcTemplate.queryForObject(sql, mapper, id.value())
[](#cb327-5)    );
[](#cb327-6)}
```

**Q: Should every method return Result?**

A: No. Pure functions that cannot fail should return T directly:

```
[](#cb328-1)// Returns T - pure computation, cannot fail
[](#cb328-2)public Money calculateTotal(List<LineItem> items) {
[](#cb328-3)    return items.stream()
[](#cb328-4)        .map(LineItem::subtotal)
[](#cb328-5)        .reduce(Money.ZERO, Money::add);
[](#cb328-6)}
[](#cb328-7)
[](#cb328-8)// Returns Result<T> - validation can fail
[](#cb328-9)public Result<Money> parseAmount(String raw) {
[](#cb328-10)    return Money.money(raw);
[](#cb328-11)}
```

### Performance

**Q: Is there overhead from wrapping everything in Result/Promise?**

A: Minimal. The types are thin wrappers. Overhead is comparable to Optional. For typical web applications, this is negligible compared to I/O latency.

**Q: Are lambdas slower than methods?**

A: No. The JVM inlines simple lambdas. There’s no significant performance difference for typical use cases.

**Q: Does creating many small objects (value objects) hurt GC?**

A: Modern JVMs handle short-lived objects efficiently. Value objects are typically small and short-lived. If profiling shows GC pressure, the issue is usually elsewhere.

### Testing

**Q: Should I test value object validation separately from use cases?**

A: Yes. Value objects get unit tests for each validation rule. Use cases get integration tests with stubbed steps.

**Q: How many tests should a use case have?**

A: At minimum: - 1 happy path test - 1 test per step failure - 1 test per validation rule in ValidRequest

**Q: Should I use mocks or stubs?**

A: Prefer stubs (simple lambda implementations). Mocks add complexity and verification overhead. JBCT’s functional style makes stubbing easy.

### Architecture

**Q: Where do DTOs belong?**

A: At adapter boundaries: - Request DTOs in controller (convert to domain types immediately) - Response DTOs from use case Response records - No DTOs in domain layer

**Q: Can use cases call other use cases?**

A: Generally no. If use case A needs functionality from use case B, extract that functionality to a shared step interface.

**Q: How do I handle transactions?**

A: At the adapter layer:

```
[](#cb329-1)@Repository
[](#cb329-2)public class JooqOrderRepository implements SaveOrder {
[](#cb329-3)    @Transactional
[](#cb329-4)    @Override
[](#cb329-5)    public Promise<OrderId> apply(ValidOrder order) {
[](#cb329-6)        return Promise.lift(
[](#cb329-7)            DatabaseError::new,
[](#cb329-8)            () -> saveInTransaction(order)
[](#cb329-9)        );
[](#cb329-10)    }
[](#cb329-11)}
```

* * *

## Error Message Reference

### “Cannot infer functional interface type”

**Cause:** Lambda target type is ambiguous.

**Fix:** Add explicit type declaration:

```
[](#cb330-1)CheckEmail checkEmail = req -> Promise.success(req);
```

### “Incompatible types: `Result<X>` cannot be converted to `Result<Y>`”

**Cause:** Using map when flatMap is needed.

**Fix:** Check if the mapping function returns a Result. If so, use flatMap:

```
[](#cb331-1)// WRONG: validate returns Result<ValidEmail>
[](#cb331-2).map(this::validate)  // Results in Result<Result<ValidEmail>>
[](#cb331-3)
[](#cb331-4)// CORRECT
[](#cb331-5).flatMap(this::validate)  // Results in Result<ValidEmail>
```

### “No instances of type variable(s) T exist”

**Cause:** Type inference failure, often with Cause.result() or Cause.promise().

**Fix:** Add type witness or assign to typed variable:

```
[](#cb332-1)// Option 1: Type witness
[](#cb332-2)return ERROR.<User>result();
[](#cb332-3)
[](#cb332-4)// Option 2: Assign to variable
[](#cb332-5)Result<User> failure = ERROR.result();
[](#cb332-6)return failure;
```

### “Promise.await() blocks forever”

**Cause:** Promise never resolved.

**Fix:** Ensure all code paths resolve the Promise:

```
[](#cb333-1)Promise<User> promise = Promise.promise();
[](#cb333-2)
[](#cb333-3)// Ensure both success and failure paths resolve
[](#cb333-4)if (condition) {
[](#cb333-5)    promise.succeed(user);
[](#cb333-6)} else {
[](#cb333-7)    promise.fail(cause);  // Don't forget this!
[](#cb333-8)}
```

* * *

## Summary

When debugging JBCT code:

1.  **Add logging at chain points** - Use onSuccess/onFailure for visibility
2.  **Extract to named methods** - Easier breakpoints and stack traces
3.  **Check for common mistakes** - Nested results, ignored returns, thrown exceptions
4.  **Use explicit types** - Helps IDE and compiler catch errors
5.  **Test both success and failure** - Always assert on Result/Promise

The functional style may feel unfamiliar initially, but debugging becomes easier once you internalize the patterns. The explicit error handling means fewer surprises at runtime.

# Appendix A: Pragmatica Lite Core API Reference

## Library Information

**Maven:**

```
[](#cb334-1)<dependency>
[](#cb334-2)   <groupId>org.pragmatica-lite</groupId>
[](#cb334-3)   <artifactId>core</artifactId>
[](#cb334-4)   <version>0.9.9</version>
[](#cb334-5)</dependency>
```

**Gradle:**

```
[](#cb335-1)implementation 'org.pragmatica-lite:core:0.9.9'
```

**Documentation:** https://central.sonatype.com/artifact/org.pragmatica-lite/core

* * *

## Type Conversions

### Option Conversions

| From | To | Method |
| --- | --- | --- |
| `Option<T>` | `Result<T>` | `.toResult(Cause cause)` or `.await(Cause cause)` |
| `Option<T>` | `Result<T>` | `.toResult()` (uses CoreError.emptyOption) |
| `Option<T>` | `Promise<T>` | `.async(Cause cause)` |
| `Option<T>` | `Promise<T>` | `.async()` (uses CoreError.emptyOption) |
| `Option<T>` | `Optional<T>` | `.toOptional()` |

### Result Conversions

| From | To | Method |
| --- | --- | --- |
| `Result<T>` | `Option<T>` | `.option()` (loses error) |
| `Result<T>` | `Promise<T>` | `.async()` |

### Promise Conversions

| From | To | Method |
| --- | --- | --- |
| `Promise<T>` | `Promise<T>` | `.async()` (identity) |
| `Promise<T>` | `Result<T>` | `.await()` (blocks) |
| `Promise<T>` | `Result<T>` | `.await(TimeSpan timeout)` |

### Cause Conversions

| From | To | Method |
| --- | --- | --- |
| `Cause` | `Result<T>` | `.result()` |
| `Cause` | `Promise<T>` | `.promise()` |

* * *

## Creating Instances

### Option

```
[](#cb336-1)Option.some(value)           // Create present option
[](#cb336-2)Option.present(value)        // Alias for some()
[](#cb336-3)Option.none()                // Create empty option
[](#cb336-4)Option.empty()               // Alias for none()
[](#cb336-5)Option.option(nullable)      // null -> none, value -> some
[](#cb336-6)Option.from(Optional<T>)     // Convert Java Optional
```

### Result

```
[](#cb337-1)Result.success(value)        // Create success
[](#cb337-2)Result.ok(value)             // Alias for success()
[](#cb337-3)Result.unitResult()          // Success with Unit value
[](#cb337-4)Result.failure(cause)        // Create failure (prefer cause.result())
[](#cb337-5)Result.err(cause)            // Alias for failure()
```

### Promise

```
[](#cb338-1)Promise.success(value)                   // Resolved success
[](#cb338-2)Promise.ok(value)                        // Alias for success()
[](#cb338-3)Promise.unitPromise()                    // Resolved with Unit
[](#cb338-4)Promise.failure(cause)                   // Resolved failure (prefer cause.promise())
[](#cb338-5)Promise.resolved(Result<T> result)       // Resolved from result
[](#cb338-6)Promise.promise()                        // Unresolved promise
[](#cb338-7)Promise.promise(Consumer<Promise<T>>)    // Unresolved, runs consumer async
[](#cb338-8)Promise.promise(Supplier<Result<T>>)     // Async execution of supplier
```

* * *

## Exception Handling (lift methods)

### Result.lift

```
[](#cb339-1)// Basic lift
[](#cb339-2)Result.lift(ThrowingFn0<U> supplier)
[](#cb339-3)Result.lift(Fn1<Cause, Throwable> mapper, ThrowingFn0<U> supplier)
[](#cb339-4)Result.lift(ThrowingRunnable runnable)  // Returns Result<Unit>
[](#cb339-5)Result.lift(Cause cause, ThrowingFn0<U> supplier)  // Fixed cause
[](#cb339-6)
[](#cb339-7)// Direct invocation (lift + apply)
[](#cb339-8)Result.lift1(ThrowingFn1<R, T1> fn, T1 value)
[](#cb339-9)Result.lift2(ThrowingFn2<R, T1, T2> fn, T1 v1, T2 v2)
[](#cb339-10)Result.lift3(ThrowingFn3<R, T1, T2, T3> fn, T1 v1, T2 v2, T3 v3)
[](#cb339-11)
[](#cb339-12)// Function factories (returns wrapped function)
[](#cb339-13)Result.liftFn1(ThrowingFn1<R, T1> fn)  // Returns Fn1<Result<R>, T1>
[](#cb339-14)Result.liftFn2(ThrowingFn2<R, T1, T2> fn)
[](#cb339-15)Result.liftFn3(ThrowingFn3<R, T1, T2, T3> fn)
```

### Promise.lift

```
[](#cb340-1)// Basic lift (async execution)
[](#cb340-2)Promise.lift(ThrowingFn0<U> supplier)
[](#cb340-3)Promise.lift(Fn1<Cause, Throwable> mapper, ThrowingFn0<U> supplier)
[](#cb340-4)Promise.lift(ThrowingRunnable runnable)  // Returns Promise<Unit>
[](#cb340-5)
[](#cb340-6)// Direct invocation (async)
[](#cb340-7)Promise.lift1(ThrowingFn1<R, T1> fn, T1 value)
[](#cb340-8)Promise.lift2(ThrowingFn2<R, T1, T2> fn, T1 v1, T2 v2)
[](#cb340-9)Promise.lift3(ThrowingFn3<R, T1, T2, T3> fn, T1 v1, T2 v2, T3 v3)
[](#cb340-10)
[](#cb340-11)// Function factories
[](#cb340-12)Promise.liftFn1(ThrowingFn1<R, T1> fn)  // Returns Fn1<Promise<R>, T1>
```

* * *

## Aggregation (all/any/allOf)

### Result.all (accumulates failures)

```
[](#cb341-1)Result.all(Result<T1>)                    // -> Mapper1<T1>
[](#cb341-2)Result.all(Result<T1>, Result<T2>)        // -> Mapper2<T1, T2>
[](#cb341-3)// ... up to Mapper9
[](#cb341-4)
[](#cb341-5)Result.allOf(Result<T>...)                // -> Result<List<T>>
[](#cb341-6)Result.allOf(List<Result<T>>)             // -> Result<List<T>>
```

### Promise.all (fail-fast)

```
[](#cb342-1)Promise.all(Promise<T1>)                  // -> Mapper1<T1>
[](#cb342-2)Promise.all(Promise<T1>, Promise<T2>)     // -> Mapper2<T1, T2>
[](#cb342-3)// ... up to Mapper9
[](#cb342-4)
[](#cb342-5)Promise.allOf(Collection<Promise<T>>)     // -> Promise<List<Result<T>>>
```

### any Methods

```
[](#cb343-1)Option.any(Option<T>...)   // First present option
[](#cb343-2)Result.any(Result<T>...)   // First success result
[](#cb343-3)Promise.any(Promise<T>...) // First success, cancels others
```

* * *

## Common Methods

### map/flatMap

```
[](#cb344-1)// All types
[](#cb344-2).map(Fn1<U, T> mapper)           // Transform value
[](#cb344-3).map(Supplier<U> supplier)        // Replace value
[](#cb344-4).flatMap(Fn1<M<U>, T> mapper)     // Chain monadic operations
[](#cb344-5).flatMap(Supplier<M<U>> supplier) // Replace with monadic value
[](#cb344-6)
[](#cb344-7)// Result/Promise only
[](#cb344-8).flatMap2(Fn2<M<U>, T, I> mapper, I param)  // flatMap with extra param
[](#cb344-9).mapToUnit()                                 // Transform to Unit
```

### filter (Result and Promise)

```
[](#cb345-1).filter(Cause cause, Predicate<T> predicate)
[](#cb345-2).filter(Fn1<Cause, T> causeMapper, Predicate<T> predicate)
```

### Callback Methods

```
[](#cb346-1)// Option
[](#cb346-2).onPresent(Consumer<T>)
[](#cb346-3).onEmpty(Runnable)
[](#cb346-4).apply(Consumer<T>, Runnable)  // Bifurcation
[](#cb346-5)
[](#cb346-6)// Result
[](#cb346-7).onSuccess(Consumer<T>)
[](#cb346-8).onFailure(Consumer<Cause>)
[](#cb346-9).onResult(Consumer<Result<T>>)
[](#cb346-10).apply(Consumer<T>, Consumer<Cause>)  // Bifurcation
[](#cb346-11)
[](#cb346-12)// Promise (same as Result, plus async variants)
[](#cb346-13).onSuccessAsync(Consumer<T>)
[](#cb346-14).onFailureAsync(Consumer<Cause>)
[](#cb346-15).withSuccess(Consumer<T>)  // Returns self for chaining
```

### fold

```
[](#cb347-1)// Option
[](#cb347-2).fold(Supplier<R> empty, Fn1<R, T> present)
[](#cb347-3)
[](#cb347-4)// Result/Promise
[](#cb347-5).fold(Fn1<R, Cause> failure, Fn1<R, T> success)
```

### Recovery

```
[](#cb348-1).or(T replacement)                    // Fallback value
[](#cb348-2).or(Supplier<T> supplier)             // Lazy fallback
[](#cb348-3).orElse(M<T> replacement)             // Fallback monadic value
[](#cb348-4).recover(Fn1<T, Cause> mapper)        // Result/Promise: recover from failure
```

* * *

## Verify.Is Predicates

```
[](#cb349-1)// Null check
[](#cb349-2)Verify.Is::notNull
[](#cb349-3)
[](#cb349-4)// String checks
[](#cb349-5)Verify.Is::empty
[](#cb349-6)Verify.Is::notEmpty
[](#cb349-7)Verify.Is::blank
[](#cb349-8)Verify.Is::notBlank
[](#cb349-9)Verify.Is::lenBetween        // lenBetween(8, 128)
[](#cb349-10)Verify.Is::contains
[](#cb349-11)Verify.Is::notContains
[](#cb349-12)Verify.Is::matches           // matches(Pattern)
[](#cb349-13)
[](#cb349-14)// Numeric checks
[](#cb349-15)Verify.Is::positive
[](#cb349-16)Verify.Is::negative
[](#cb349-17)Verify.Is::nonNegative
[](#cb349-18)Verify.Is::nonPositive
[](#cb349-19)Verify.Is::greaterThan
[](#cb349-20)Verify.Is::lessThan
[](#cb349-21)Verify.Is::between           // between(0, 150)
[](#cb349-22)Verify.Is::equalTo
[](#cb349-23)Verify.Is::notEqualTo
```

**Usage:**

```
[](#cb350-1)Verify.ensure(password, Verify.Is::lenBetween, 8, 128)
[](#cb350-2)Verify.ensure(age, Verify.Is::between, 0, 150)
```

* * *

## Parse Subpackage

### Number Parsing

```
[](#cb351-1)Number.parseInt(String)           // -> Result<Integer>
[](#cb351-2)Number.parseLong(String)          // -> Result<Long>
[](#cb351-3)Number.parseDouble(String)        // -> Result<Double>
[](#cb351-4)Number.parseBigDecimal(String)    // -> Result<BigDecimal>
```

### DateTime Parsing

```
[](#cb352-1)DateTime.parseLocalDate(String)       // -> Result<LocalDate>
[](#cb352-2)DateTime.parseLocalTime(String)       // -> Result<LocalTime>
[](#cb352-3)DateTime.parseLocalDateTime(String)   // -> Result<LocalDateTime>
[](#cb352-4)DateTime.parseInstant(String)         // -> Result<Instant>
```

### Network Parsing

```
[](#cb353-1)Network.parseUUID(String)        // -> Result<UUID>
[](#cb353-2)Network.parseURL(String)         // -> Result<URL>
[](#cb353-3)Network.parseURI(String)         // -> Result<URI>
```

* * *

## Causes Utilities

```
[](#cb354-1)Causes.cause(String message)                          // Simple cause
[](#cb354-2)Causes.cause(String message, Option<Cause> source)    // Cause with source
[](#cb354-3)Causes.fromThrowable(Throwable)                       // Convert exception
[](#cb354-4)Causes.forOneValue(String template)                   // Fn1<Cause, T> factory
[](#cb354-5)Causes.forTwoValues(String template)                  // Fn2<Cause, T1, T2>
[](#cb354-6)Causes.forThreeValues(String template)                // Fn3<Cause, T1, T2, T3>
[](#cb354-7)Causes.composite(Result<?>...)                        // Composite from results
```

**Template syntax** (uses String.format):

```
[](#cb355-1)Causes.forOneValue("Invalid email: %s")           // CORRECT
[](#cb355-2)Causes.forTwoValues("Range error: %s to %s")      // CORRECT
```

* * *

## Promise-Specific Operations

```
[](#cb356-1)// Resolution
[](#cb356-2).resolve(Result<T>)     // Resolve unresolved promise
[](#cb356-3).succeed(T value)       // Resolve with success
[](#cb356-4).fail(Cause cause)      // Resolve with failure
[](#cb356-5).cancel()               // Cancel execution
[](#cb356-6)
[](#cb356-7)// Query
[](#cb356-8).isResolved()           // Check if resolved
[](#cb356-9)
[](#cb356-10)// Timeout
[](#cb356-11).timeout(TimeSpan duration)  // Add timeout
[](#cb356-12)
[](#cb356-13)// Result manipulation
[](#cb356-14).mapResult(Fn1<Result<U>, Result<T>>)  // Transform result
[](#cb356-15).trace(Fn1<Cause, Cause>)              // Transform error (alias: mapError)
```

* * *

## Example Usage Patterns

### Adapter with exception handling

```
[](#cb357-1)public Promise<User> findUser(UserId id) {
[](#cb357-2)    return Promise.lift(
[](#cb357-3)        CoreError::database,
[](#cb357-4)        () -> jdbcTemplate.queryForObject(
[](#cb357-5)            "SELECT * FROM users WHERE id = ?",
[](#cb357-6)            new Object[]{id.value()},
[](#cb357-7)            this::mapUser)
[](#cb357-8)    );
[](#cb357-9)}
```

### Lifting sync Result to async Promise

```
[](#cb358-1)public Promise<Response> execute(Request request) {
[](#cb358-2)    return ValidRequest.validRequest(request)  // Result<ValidRequest>
[](#cb358-3)                       .async()                // Promise<ValidRequest>
[](#cb358-4)                       .flatMap(step1::apply)
[](#cb358-5)                       .flatMap(step2::apply);
[](#cb358-6)}
```

### Testing with functional assertions

```
[](#cb359-1)@Test
[](#cb359-2)void validation_fails_forInvalidInput() {
[](#cb359-3)    ValidRequest.validRequest(invalidRequest)
[](#cb359-4)                .onSuccess(Assertions::fail);
[](#cb359-5)}
[](#cb359-6)
[](#cb359-7)@Test
[](#cb359-8)void validation_succeeds_forValidInput() {
[](#cb359-9)    ValidRequest.validRequest(validRequest)
[](#cb359-10)                .onFailure(Assertions::fail)
[](#cb359-11)                .onSuccess(valid -> {
[](#cb359-12)                    assertEquals("expected", valid.field());
[](#cb359-13)                });
[](#cb359-14)}
```

# Appendix B: Exercises and Solutions

This appendix contains exercises for each part of the book, organized by difficulty level. Each exercise includes a solution with explanation.

**Difficulty Levels:** - [Beginner] Beginner - Direct application of concepts - [Intermediate] Intermediate - Combining multiple concepts - [Advanced] Advanced - Design decisions and trade-offs

* * *

## Part I: Foundations (Chapters 1-3)

### Exercise 1.1 [Beginner] - Return Type Selection

For each scenario, identify the correct return type (T, Option, Result, Promise):

1.  A method that calculates the sum of two integers
2.  A method that finds a user’s middle name (not all users have one)
3.  A method that parses a date string
4.  A method that fetches a user profile from a remote API
5.  A method that validates an email format
6.  A method that looks up a value in an in-memory cache

<details><summary>Solution</summary>

1.  **T** - Pure calculation, cannot fail
2.  **Option** - Absence is normal, not an error
3.  **Result** - Parsing can fail with a reason
4.  **Promise** - Remote I/O, can fail asynchronously
5.  **Result** - Validation can fail with a reason
6.  **Option** - Cache miss is normal, not an error</details> 

* * *

### Exercise 1.2 [Beginner] - Option vs Result

Explain why each of these uses the wrong type and provide the correct signature:

```
[](#cb360-1)// A
[](#cb360-2)public Optional<User> authenticate(String email, String password) {
[](#cb360-3)    // Returns empty if credentials invalid
[](#cb360-4)}
[](#cb360-5)
[](#cb360-6)// B
[](#cb360-7)public Result<Config> getOptionalConfig(String key) {
[](#cb360-8)    // Returns failure if config key doesn't exist
[](#cb360-9)}
```

<details><summary>Solution</summary>

**A is wrong:** Authentication failure is an error with a reason (wrong password, account locked, user not found). Should be:

```
[](#cb361-1)public Result<User> authenticate(String email, String password)
```

**B is wrong:** “Optional config” implies absence is expected, not an error. Should be:

```
[](#cb362-1)public Option<Config> getOptionalConfig(String key)
```</details> 

* * *

### Exercise 1.3 [Intermediate] - Type Lifting

Complete the following code to properly lift between types:

```
[](#cb363-1)public Promise<UserProfile> loadProfile(String userId) {
[](#cb363-2)    // 1\. Parse userId to UserId value object (Result<UserId>)
[](#cb363-3)    // 2\. Look up in cache (Option<UserProfile>)
[](#cb363-4)    // 3\. If not in cache, fetch from database (Promise<UserProfile>)
[](#cb363-5)
[](#cb363-6)    Result<UserId> id = UserId.userId(userId);
[](#cb363-7)    // TODO: Complete the chain
[](#cb363-8)}
```

<details><summary>Solution</summary>

```
[](#cb364-1)public Promise<UserProfile> loadProfile(String userId) {
[](#cb364-2)    return UserId.userId(userId)
[](#cb364-3)        .async()  // Result -> Promise
[](#cb364-4)        .flatMap(id -> cache.get(id)
[](#cb364-5)            .async(CACHE_MISS)  // Option -> Promise (with cause for empty)
[](#cb364-6)            .recover(cause -> database.fetchProfile(id)));
[](#cb364-7)}
[](#cb364-8)
[](#cb364-9)// Alternative: if cache miss should fall through silently
[](#cb364-10)public Promise<UserProfile> loadProfile(String userId) {
[](#cb364-11)    return UserId.userId(userId)
[](#cb364-12)        .async()
[](#cb364-13)        .flatMap(id -> cache.get(id)
[](#cb364-14)            .map(Promise::success)
[](#cb364-15)            .or(() -> database.fetchProfile(id)));
[](#cb364-16)}
```</details> 

* * *

### Exercise 1.4 [Beginner] - Cause Creation

Create appropriate Cause definitions for a user registration system:

1.  Email already exists
2.  Password too weak (should include the specific weakness)
3.  Username contains invalid characters (should show which characters)

<details><summary>Solution</summary>

```
[](#cb365-1)public sealed interface RegistrationError extends Cause {
[](#cb365-2)
[](#cb365-3)    record EmailExists(String email) implements RegistrationError {
[](#cb365-4)        private static final Fn1<Cause, String> FACTORY =
[](#cb365-5)            Causes.forOneValue("Email already registered: %s");
[](#cb365-6)
[](#cb365-7)        @Override
[](#cb365-8)        public String message() {
[](#cb365-9)            return FACTORY.apply(email).message();
[](#cb365-10)        }
[](#cb365-11)    }
[](#cb365-12)
[](#cb365-13)    record WeakPassword(String weakness) implements RegistrationError {
[](#cb365-14)        private static final Fn1<Cause, String> FACTORY =
[](#cb365-15)            Causes.forOneValue("Password too weak: %s");
[](#cb365-16)
[](#cb365-17)        @Override
[](#cb365-18)        public String message() {
[](#cb365-19)            return FACTORY.apply(weakness).message();
[](#cb365-20)        }
[](#cb365-21)    }
[](#cb365-22)
[](#cb365-23)    record InvalidUsername(String invalidChars) implements RegistrationError {
[](#cb365-24)        private static final Fn1<Cause, String> FACTORY =
[](#cb365-25)            Causes.forOneValue("Username contains invalid characters: %s");
[](#cb365-26)
[](#cb365-27)        @Override
[](#cb365-28)        public String message() {
[](#cb365-29)            return FACTORY.apply(invalidChars).message();
[](#cb365-30)        }
[](#cb365-31)    }
[](#cb365-32)}
```</details> 

* * *

### Exercise 1.5 [Intermediate] - Pragmatica Lite Operations

What does each expression evaluate to?

```
[](#cb366-1)// Given:
[](#cb366-2)Result<Integer> success = Result.success(10);
[](#cb366-3)Result<Integer> failure = Causes.cause("error").result();
[](#cb366-4)
[](#cb366-5)// 1.
[](#cb366-6)success.map(x -> x * 2).or(0)
[](#cb366-7)
[](#cb366-8)// 2.
[](#cb366-9)failure.map(x -> x * 2).or(0)
[](#cb366-10)
[](#cb366-11)// 3.
[](#cb366-12)success.filter(Causes.cause("not positive"), x -> x > 0)
[](#cb366-13)
[](#cb366-14)// 4.
[](#cb366-15)success.filter(Causes.cause("not negative"), x -> x < 0)
[](#cb366-16)
[](#cb366-17)// 5.
[](#cb366-18)Result.all(success, failure).map((a, b) -> a + b)
```

<details><summary>Solution</summary>

1.  `20` - maps 10 to 20, or() returns value
2.  `0` - failure skips map, or() returns fallback
3.  `Result.success(10)` - predicate passes
4.  `Result.failure(Cause("not negative"))` - predicate fails
5.  `Result.failure(Cause("error"))` - all() accumulates failure from second</details> 

* * *

## Part II: Core Principles (Chapters 4-6)

### Exercise 2.1 [Beginner] - Value Object Creation

Create a `PhoneNumber` value object that: - Accepts strings in format “+1-555-123-4567” or “5551234567” - Normalizes to digits only - Must be 10-15 digits

<details><summary>Solution</summary>

```
[](#cb367-1)public record PhoneNumber(String value) {
[](#cb367-2)    private static final Pattern DIGITS_ONLY = Pattern.compile("\\d+");
[](#cb367-3)    private static final Cause INVALID_FORMAT =
[](#cb367-4)        Causes.cause("Phone number must contain only digits, dashes, and optional leading +");
[](#cb367-5)    private static final Cause INVALID_LENGTH =
[](#cb367-6)        Causes.cause("Phone number must be 10-15 digits");
[](#cb367-7)
[](#cb367-8)    public static Result<PhoneNumber> phoneNumber(String raw) {
[](#cb367-9)        return Verify.ensure(raw, Verify.Is::notBlank)
[](#cb367-10)            .map(PhoneNumber::normalize)
[](#cb367-11)            .filter(INVALID_FORMAT, PhoneNumber::isValidFormat)
[](#cb367-12)            .filter(INVALID_LENGTH, s -> Verify.Is.lenBetween(s, 10, 15))
[](#cb367-13)            .map(PhoneNumber::new);
[](#cb367-14)    }
[](#cb367-15)
[](#cb367-16)    private static String normalize(String input) {
[](#cb367-17)        return input.replaceAll("[^0-9]", "");
[](#cb367-18)    }
[](#cb367-19)
[](#cb367-20)    private static boolean isValidFormat(String normalized) {
[](#cb367-21)        return DIGITS_ONLY.matcher(normalized).matches();
[](#cb367-22)    }
[](#cb367-23)}
```</details> 

* * *

### Exercise 2.2 [Intermediate] - Aggregate Validation

Create a `DateRange` value object with `from` and `to` LocalDate fields where: - Both dates are required - `from` must be before or equal to `to` - Neither date can be in the past

<details><summary>Solution</summary>

```
[](#cb368-1)public record DateRange(LocalDate from, LocalDate to) {
[](#cb368-2)    private static final Cause FROM_AFTER_TO =
[](#cb368-3)        Causes.cause("Start date must be before or equal to end date");
[](#cb368-4)    private static final Cause FROM_IN_PAST =
[](#cb368-5)        Causes.cause("Start date cannot be in the past");
[](#cb368-6)    private static final Cause TO_IN_PAST =
[](#cb368-7)        Causes.cause("End date cannot be in the past");
[](#cb368-8)
[](#cb368-9)    public static Result<DateRange> dateRange(String fromRaw, String toRaw) {
[](#cb368-10)        var today = LocalDate.now();
[](#cb368-11)
[](#cb368-12)        return Result.all(parseAndValidate(fromRaw, today, FROM_IN_PAST),
[](#cb368-13)                         parseAndValidate(toRaw, today, TO_IN_PAST))
[](#cb368-14)                     .flatMap(DateRange::validateOrder);
[](#cb368-15)    }
[](#cb368-16)
[](#cb368-17)    private static Result<LocalDate> parseAndValidate(String raw, LocalDate today, Cause pastError) {
[](#cb368-18)        return DateTime.parseLocalDate(raw)
[](#cb368-19)            .filter(pastError, date -> !date.isBefore(today));
[](#cb368-20)    }
[](#cb368-21)
[](#cb368-22)    private static Result<DateRange> validateOrder(LocalDate from, LocalDate to) {
[](#cb368-23)        if (from.isAfter(to)) {
[](#cb368-24)            return FROM_AFTER_TO.result();
[](#cb368-25)        }
[](#cb368-26)        return Result.success(new DateRange(from, to));
[](#cb368-27)    }
[](#cb368-28)}
```</details> 

* * *

### Exercise 2.3 [Intermediate] - Error Accumulation vs Short-Circuit

Explain the difference in behavior and output:

```
[](#cb369-1)// Version A
[](#cb369-2)Result<ValidForm> validateA(Form form) {
[](#cb369-3)    return Email.email(form.email())
[](#cb369-4)        .flatMap(email -> Password.password(form.password())
[](#cb369-5)            .map(password -> new ValidForm(email, password)));
[](#cb369-6)}
[](#cb369-7)
[](#cb369-8)// Version B
[](#cb369-9)Result<ValidForm> validateB(Form form) {
[](#cb369-10)    return Result.all(Email.email(form.email()),
[](#cb369-11)                     Password.password(form.password()))
[](#cb369-12)                 .map(ValidForm::new);
[](#cb369-13)}
```

Given input with both invalid email AND invalid password, what does each return?

<details><summary>Solution</summary>

**Version A (short-circuit):** Returns failure with ONLY the email error. flatMap stops at first failure.

**Version B (accumulation):** Returns failure with BOTH errors in a CompositeCause. Result.all() collects all failures.

**When to use each:** - Use flatMap chain when errors are dependent (later validations need earlier values) - Use Result.all() when validations are independent and you want to show all errors to user</details> 

* * *

### Exercise 2.4 [Advanced] - Null Handling Strategy

Refactor this method to eliminate null handling:

```
[](#cb370-1)public User processUser(UserDto dto) {
[](#cb370-2)    if (dto == null) {
[](#cb370-3)        throw new IllegalArgumentException("DTO cannot be null");
[](#cb370-4)    }
[](#cb370-5)
[](#cb370-6)    String email = dto.getEmail();
[](#cb370-7)    if (email == null || email.isBlank()) {
[](#cb370-8)        throw new ValidationException("Email required");
[](#cb370-9)    }
[](#cb370-10)
[](#cb370-11)    String name = dto.getName();  // Optional field
[](#cb370-12)    String normalizedName = name != null ? name.trim() : null;
[](#cb370-13)
[](#cb370-14)    Address address = null;
[](#cb370-15)    if (dto.getAddress() != null) {
[](#cb370-16)        address = processAddress(dto.getAddress());
[](#cb370-17)    }
[](#cb370-18)
[](#cb370-19)    return new User(email.toLowerCase(), normalizedName, address);
[](#cb370-20)}
```

<details><summary>Solution</summary>

```
[](#cb371-1)public Result<User> processUser(UserDto dto) {
[](#cb371-2)    return Result.all(Email.email(dto.email()),
[](#cb371-3)                     processOptionalName(dto.name()),
[](#cb371-4)                     processOptionalAddress(dto.address()))
[](#cb371-5)                 .map(User::new);
[](#cb371-6)}
[](#cb371-7)
[](#cb371-8)private Result<Option<Name>> processOptionalName(String raw) {
[](#cb371-9)    return Option.option(raw)
[](#cb371-10)        .map(String::trim)
[](#cb371-11)        .filter(s -> !s.isBlank())
[](#cb371-12)        .map(Name::new)
[](#cb371-13)        .fold(
[](#cb371-14)            () -> Result.success(Option.none()),
[](#cb371-15)            name -> Result.success(Option.some(name))
[](#cb371-16)        );
[](#cb371-17)}
[](#cb371-18)
[](#cb371-19)private Result<Option<Address>> processOptionalAddress(AddressDto dto) {
[](#cb371-20)    return Option.option(dto)
[](#cb371-21)        .map(this::validateAddress)
[](#cb371-22)        .fold(
[](#cb371-23)            () -> Result.success(Option.none()),
[](#cb371-24)            result -> result.map(Option::some)
[](#cb371-25)        );
[](#cb371-26)}
[](#cb371-27)
[](#cb371-28)// User record accepts Option types
[](#cb371-29)public record User(Email email, Option<Name> name, Option<Address> address) {}
```</details> 

* * *

### Exercise 2.5 [Beginner] - Recovery Patterns

Complete the recovery logic:

```
[](#cb372-1)public Promise<Config> loadConfig() {
[](#cb372-2)    return loadFromDatabase()
[](#cb372-3)        // TODO: If database fails with ConnectionError, try file
[](#cb372-4)        // TODO: If file fails with FileNotFound, use defaults
[](#cb372-5)        // TODO: Any other error should propagate
[](#cb372-6)        ;
[](#cb372-7)}
[](#cb372-8)
[](#cb372-9)private Promise<Config> loadFromDatabase() { /* ... */ }
[](#cb372-10)private Promise<Config> loadFromFile() { /* ... */ }
[](#cb372-11)private Config defaultConfig() { /* ... */ }
```

<details><summary>Solution</summary>

```
[](#cb373-1)public Promise<Config> loadConfig() {
[](#cb373-2)    return loadFromDatabase()
[](#cb373-3)        .recover(this::recoverFromDatabaseError);
[](#cb373-4)}
[](#cb373-5)
[](#cb373-6)private Promise<Config> recoverFromDatabaseError(Cause cause) {
[](#cb373-7)    return switch (cause) {
[](#cb373-8)        case ConnectionError ignored -> loadFromFile()
[](#cb373-9)            .recover(this::recoverFromFileError);
[](#cb373-10)        default -> cause.promise();
[](#cb373-11)    };
[](#cb373-12)}
[](#cb373-13)
[](#cb373-14)private Promise<Config> recoverFromFileError(Cause cause) {
[](#cb373-15)    return switch (cause) {
[](#cb373-16)        case FileNotFound ignored -> Promise.success(defaultConfig());
[](#cb373-17)        default -> cause.promise();
[](#cb373-18)    };
[](#cb373-19)}
```</details> 

* * *

## Part III: Patterns (Chapters 7-9)

### Exercise 3.1 [Beginner] - Pattern Identification

Identify the JBCT pattern used in each code snippet:

```
[](#cb374-1)// A
[](#cb374-2)return validateOrder(request)
[](#cb374-3)    .flatMap(this::checkInventory)
[](#cb374-4)    .flatMap(this::processPayment)
[](#cb374-5)    .flatMap(this::createShipment);
[](#cb374-6)
[](#cb374-7)// B
[](#cb374-8)return Promise.all(fetchUserProfile(userId),
[](#cb374-9)                  fetchUserOrders(userId),
[](#cb374-10)                  fetchUserPreferences(userId))
[](#cb374-11)              .map(Dashboard::new);
[](#cb374-12)
[](#cb374-13)// C
[](#cb374-14)return switch (user.tier()) {
[](#cb374-15)    case PREMIUM -> premiumProcessor.process(order);
[](#cb374-16)    case STANDARD -> standardProcessor.process(order);
[](#cb374-17)    case BASIC -> basicProcessor.process(order);
[](#cb374-18)};
[](#cb374-19)
[](#cb374-20)// D
[](#cb374-21)return Promise.lift(DatabaseError::new,
[](#cb374-22)                   () -> jdbcTemplate.query(sql, mapper));
```

<details><summary>Solution</summary>

*   **A: Sequencer** - Linear chain of dependent steps
*   **B: Fork-Join** - Parallel independent operations combined
*   **C: Condition** - Routing based on discriminator
*   **D: Leaf** - Adapter wrapping external I/O</details> 

* * *

### Exercise 3.2 [Intermediate] - Implement Fork-Join

Implement a dashboard loader that fetches three pieces of data in parallel: - User profile (required) - Recent orders (required) - Recommendations (optional - use empty list on failure)

```
[](#cb375-1)public interface LoadDashboard {
[](#cb375-2)    Promise<Dashboard> load(UserId userId);
[](#cb375-3)
[](#cb375-4)    record Dashboard(UserProfile profile, List<Order> orders, List<Product> recommendations) {}
[](#cb375-5)}
```

<details><summary>Solution</summary>

```
[](#cb376-1)public interface LoadDashboard {
[](#cb376-2)    Promise<Dashboard> load(UserId userId);
[](#cb376-3)
[](#cb376-4)    record Dashboard(UserProfile profile, List<Order> orders, List<Product> recommendations) {}
[](#cb376-5)
[](#cb376-6)    interface FetchProfile {
[](#cb376-7)        Promise<UserProfile> apply(UserId userId);
[](#cb376-8)    }
[](#cb376-9)
[](#cb376-10)    interface FetchOrders {
[](#cb376-11)        Promise<List<Order>> apply(UserId userId);
[](#cb376-12)    }
[](#cb376-13)
[](#cb376-14)    interface FetchRecommendations {
[](#cb376-15)        Promise<List<Product>> apply(UserId userId);
[](#cb376-16)    }
[](#cb376-17)
[](#cb376-18)    static LoadDashboard create(FetchProfile fetchProfile,
[](#cb376-19)                                FetchOrders fetchOrders,
[](#cb376-20)                                FetchRecommendations fetchRecommendations) {
[](#cb376-21)        return userId -> Promise.all(fetchProfile.apply(userId),
[](#cb376-22)                                    fetchOrders.apply(userId),
[](#cb376-23)                                    fetchRecommendations.apply(userId)
[](#cb376-24)                                        .recover(cause -> Promise.success(List.of())))
[](#cb376-25)                                .map(Dashboard::new);
[](#cb376-26)    }
[](#cb376-27)}
```</details> 

* * *

### Exercise 3.3 [Intermediate] - Implement Condition Pattern

Implement a notification sender that routes based on user preference:

```
[](#cb377-1)public interface SendNotification {
[](#cb377-2)    Promise<Unit> send(UserId userId, Message message);
[](#cb377-3)}
[](#cb377-4)
[](#cb377-5)public enum NotificationPreference {
[](#cb377-6)    EMAIL, SMS, PUSH, NONE
[](#cb377-7)}
```

<details><summary>Solution</summary>

```
[](#cb378-1)public interface SendNotification {
[](#cb378-2)    Promise<Unit> send(UserId userId, Message message);
[](#cb378-3)
[](#cb378-4)    interface GetPreference {
[](#cb378-5)        Promise<NotificationPreference> apply(UserId userId);
[](#cb378-6)    }
[](#cb378-7)
[](#cb378-8)    interface SendEmail {
[](#cb378-9)        Promise<Unit> apply(UserId userId, Message message);
[](#cb378-10)    }
[](#cb378-11)
[](#cb378-12)    interface SendSms {
[](#cb378-13)        Promise<Unit> apply(UserId userId, Message message);
[](#cb378-14)    }
[](#cb378-15)
[](#cb378-16)    interface SendPush {
[](#cb378-17)        Promise<Unit> apply(UserId userId, Message message);
[](#cb378-18)    }
[](#cb378-19)
[](#cb378-20)    static SendNotification create(GetPreference getPreference,
[](#cb378-21)                                   SendEmail sendEmail,
[](#cb378-22)                                   SendSms sendSms,
[](#cb378-23)                                   SendPush sendPush) {
[](#cb378-24)        return (userId, message) -> getPreference.apply(userId)
[](#cb378-25)            .flatMap(pref -> routeByPreference(pref, userId, message,
[](#cb378-26)                                               sendEmail, sendSms, sendPush));
[](#cb378-27)    }
[](#cb378-28)
[](#cb378-29)    private static Promise<Unit> routeByPreference(NotificationPreference pref,
[](#cb378-30)                                                    UserId userId,
[](#cb378-31)                                                    Message message,
[](#cb378-32)                                                    SendEmail sendEmail,
[](#cb378-33)                                                    SendSms sendSms,
[](#cb378-34)                                                    SendPush sendPush) {
[](#cb378-35)        return switch (pref) {
[](#cb378-36)            case EMAIL -> sendEmail.apply(userId, message);
[](#cb378-37)            case SMS -> sendSms.apply(userId, message);
[](#cb378-38)            case PUSH -> sendPush.apply(userId, message);
[](#cb378-39)            case NONE -> Promise.unitPromise();
[](#cb378-40)        };
[](#cb378-41)    }
[](#cb378-42)}
```</details> 

* * *

### Exercise 3.4 [Advanced] - Implement Aspects

Add retry and timeout aspects to an existing step:

```
[](#cb379-1)public interface FetchData {
[](#cb379-2)    Promise<Data> apply(DataId id);
[](#cb379-3)}
[](#cb379-4)
[](#cb379-5)// Requirements:
[](#cb379-6)// - Retry up to 3 times on TransientError
[](#cb379-7)// - Timeout after 5 seconds
[](#cb379-8)// - Log each attempt
```

<details><summary>Solution</summary>

```
[](#cb380-1)public interface FetchData {
[](#cb380-2)    Promise<Data> apply(DataId id);
[](#cb380-3)
[](#cb380-4)    static FetchData withAspects(FetchData base, Logger log) {
[](#cb380-5)        return id -> withRetry(withTimeout(base, id), id, log, 3);
[](#cb380-6)    }
[](#cb380-7)
[](#cb380-8)    private static Promise<Data> withTimeout(FetchData base, DataId id) {
[](#cb380-9)        return base.apply(id)
[](#cb380-10)            .timeout(TimeSpan.timeSpan(5).seconds());
[](#cb380-11)    }
[](#cb380-12)
[](#cb380-13)    private static Promise<Data> withRetry(Promise<Data> operation,
[](#cb380-14)                                           DataId id,
[](#cb380-15)                                           Logger log,
[](#cb380-16)                                           int remainingAttempts) {
[](#cb380-17)        return operation.recover(cause -> {
[](#cb380-18)            log.warn("Fetch failed for {}: {}", id, cause.message());
[](#cb380-19)
[](#cb380-20)            if (remainingAttempts <= 0) {
[](#cb380-21)                return cause.promise();
[](#cb380-22)            }
[](#cb380-23)
[](#cb380-24)            return switch (cause) {
[](#cb380-25)                case TransientError ignored -> {
[](#cb380-26)                    log.info("Retrying fetch for {}, {} attempts remaining",
[](#cb380-27)                             id, remainingAttempts);
[](#cb380-28)                    yield withRetry(operation, id, log, remainingAttempts - 1);
[](#cb380-29)                }
[](#cb380-30)                default -> cause.promise();
[](#cb380-31)            };
[](#cb380-32)        });
[](#cb380-33)    }
[](#cb380-34)}
```</details> 

* * *

### Exercise 3.5 [Intermediate] - Thread Safety Analysis

Identify the thread safety issue and fix it:

```
[](#cb381-1)public class OrderProcessor {
[](#cb381-2)    private List<Order> processedOrders = new ArrayList<>();
[](#cb381-3)    private int totalAmount = 0;
[](#cb381-4)
[](#cb381-5)    public Promise<OrderResult> process(Order order) {
[](#cb381-6)        return validateOrder(order)
[](#cb381-7)            .flatMap(this::chargePayment)
[](#cb381-8)            .onSuccess(result -> {
[](#cb381-9)                processedOrders.add(order);
[](#cb381-10)                totalAmount += order.amount();
[](#cb381-11)            })
[](#cb381-12)            .map(OrderResult::new);
[](#cb381-13)    }
[](#cb381-14)}
```

<details><summary>Solution</summary>

**Issues:** 1\. `processedOrders` is mutable and accessed from multiple threads (Promise callbacks) 2. `totalAmount` is a primitive with non-atomic read-modify-write 3\. State mutation in callbacks violates JBCT principles

**Fix: Remove shared mutable state, return immutable results**

```
[](#cb382-1)public class OrderProcessor {
[](#cb382-2)    public Promise<OrderResult> process(Order order) {
[](#cb382-3)        return validateOrder(order)
[](#cb382-4)            .flatMap(this::chargePayment)
[](#cb382-5)            .map(payment -> new OrderResult(order, payment));
[](#cb382-6)    }
[](#cb382-7)}
[](#cb382-8)
[](#cb382-9)// Track processed orders externally with thread-safe collection if needed
[](#cb382-10)public record OrderResult(Order order, Payment payment) {
[](#cb382-11)    public int amount() {
[](#cb382-12)        return order.amount();
[](#cb382-13)    }
[](#cb382-14)}
[](#cb382-15)
[](#cb382-16)// If aggregation is needed, do it at a higher level:
[](#cb382-17)public Promise<BatchResult> processBatch(List<Order> orders) {
[](#cb382-18)    return Promise.allOf(orders.stream()
[](#cb382-19)                               .map(this::process)
[](#cb382-20)                               .toList())
[](#cb382-21)                  .map(this::aggregateResults);
[](#cb382-22)}
[](#cb382-23)
[](#cb382-24)private BatchResult aggregateResults(List<Result<OrderResult>> results) {
[](#cb382-25)    // Immutable aggregation
[](#cb382-26)    var successful = results.stream()
[](#cb382-27)        .filter(Result::isSuccess)
[](#cb382-28)        .map(r -> r.fold(cause -> null, identity()))
[](#cb382-29)        .filter(Objects::nonNull)
[](#cb382-30)        .toList();
[](#cb382-31)
[](#cb382-32)    int total = successful.stream()
[](#cb382-33)        .mapToInt(OrderResult::amount)
[](#cb382-34)        .sum();
[](#cb382-35)
[](#cb382-36)    return new BatchResult(successful, total);
[](#cb382-37)}
```</details> 

* * *

## Part IV: Testing (Chapters 10-11)

### Exercise 4.1 [Beginner] - Test Structure

Write tests for this value object:

```
[](#cb383-1)public record Age(int value) {
[](#cb383-2)    private static final Cause TOO_YOUNG = Causes.cause("Must be at least 0");
[](#cb383-3)    private static final Cause TOO_OLD = Causes.cause("Must be at most 150");
[](#cb383-4)
[](#cb383-5)    public static Result<Age> age(int value) {
[](#cb383-6)        return Verify.ensure(value, Verify.Is::nonNegative)
[](#cb383-7)            .filter(TOO_OLD, v -> Verify.Is.lessThanOrEqualTo(v, 150))
[](#cb383-8)            .map(Age::new);
[](#cb383-9)    }
[](#cb383-10)}
```

<details><summary>Solution</summary>

```
[](#cb384-1)class AgeTest {
[](#cb384-2)
[](#cb384-3)    @Test
[](#cb384-4)    void age_succeeds_forValidValue() {
[](#cb384-5)        Age.age(25)
[](#cb384-6)           .onFailure(Assertions::fail)
[](#cb384-7)           .onSuccess(age -> assertEquals(25, age.value()));
[](#cb384-8)    }
[](#cb384-9)
[](#cb384-10)    @Test
[](#cb384-11)    void age_succeeds_forZero() {
[](#cb384-12)        Age.age(0)
[](#cb384-13)           .onFailure(Assertions::fail)
[](#cb384-14)           .onSuccess(age -> assertEquals(0, age.value()));
[](#cb384-15)    }
[](#cb384-16)
[](#cb384-17)    @Test
[](#cb384-18)    void age_succeeds_forMaximum() {
[](#cb384-19)        Age.age(150)
[](#cb384-20)           .onFailure(Assertions::fail)
[](#cb384-21)           .onSuccess(age -> assertEquals(150, age.value()));
[](#cb384-22)    }
[](#cb384-23)
[](#cb384-24)    @Test
[](#cb384-25)    void age_fails_forNegative() {
[](#cb384-26)        Age.age(-1)
[](#cb384-27)           .onSuccess(Assertions::fail);
[](#cb384-28)    }
[](#cb384-29)
[](#cb384-30)    @Test
[](#cb384-31)    void age_fails_forTooOld() {
[](#cb384-32)        Age.age(151)
[](#cb384-33)           .onSuccess(Assertions::fail);
[](#cb384-34)    }
[](#cb384-35)}
```</details> 

* * *

### Exercise 4.2 [Intermediate] - Stub Implementation

Create test stubs for this use case:

```
[](#cb385-1)public interface TransferFunds {
[](#cb385-2)    Promise<TransferResult> execute(TransferRequest request);
[](#cb385-3)
[](#cb385-4)    interface ValidateAccounts {
[](#cb385-5)        Promise<ValidatedAccounts> apply(AccountId from, AccountId to);
[](#cb385-6)    }
[](#cb385-7)
[](#cb385-8)    interface ExecuteTransfer {
[](#cb385-9)        Promise<TransferId> apply(ValidatedAccounts accounts, Money amount);
[](#cb385-10)    }
[](#cb385-11)}
```

Write stubs for: success case, source account not found, insufficient funds.

<details><summary>Solution</summary>

```
[](#cb386-1)class TransferFundsTest {
[](#cb386-2)
[](#cb386-3)    // Success stubs
[](#cb386-4)    private static final ValidateAccounts VALID_ACCOUNTS =
[](#cb386-5)        (from, to) -> Promise.success(new ValidatedAccounts(
[](#cb386-6)            new Account(from, Money.of(1000)),
[](#cb386-7)            new Account(to, Money.of(500))
[](#cb386-8)        ));
[](#cb386-9)
[](#cb386-10)    private static final ExecuteTransfer TRANSFER_SUCCESS =
[](#cb386-11)        (accounts, amount) -> Promise.success(new TransferId("TXN-001"));
[](#cb386-12)
[](#cb386-13)    // Failure stubs
[](#cb386-14)    private static final ValidateAccounts SOURCE_NOT_FOUND =
[](#cb386-15)        (from, to) -> TransferError.SOURCE_NOT_FOUND.promise();
[](#cb386-16)
[](#cb386-17)    private static final ValidateAccounts INSUFFICIENT_FUNDS =
[](#cb386-18)        (from, to) -> TransferError.INSUFFICIENT_FUNDS.promise();
[](#cb386-19)
[](#cb386-20)    @Test
[](#cb386-21)    void transfer_succeeds_forValidAccounts() {
[](#cb386-22)        var useCase = TransferFunds.create(VALID_ACCOUNTS, TRANSFER_SUCCESS);
[](#cb386-23)        var request = new TransferRequest(
[](#cb386-24)            new AccountId("ACC-001"),
[](#cb386-25)            new AccountId("ACC-002"),
[](#cb386-26)            Money.of(100)
[](#cb386-27)        );
[](#cb386-28)
[](#cb386-29)        useCase.execute(request)
[](#cb386-30)               .await()
[](#cb386-31)               .onFailure(Assertions::fail)
[](#cb386-32)               .onSuccess(result ->
[](#cb386-33)                   assertEquals("TXN-001", result.transferId().value()));
[](#cb386-34)    }
[](#cb386-35)
[](#cb386-36)    @Test
[](#cb386-37)    void transfer_fails_whenSourceNotFound() {
[](#cb386-38)        var useCase = TransferFunds.create(SOURCE_NOT_FOUND, TRANSFER_SUCCESS);
[](#cb386-39)        var request = new TransferRequest(
[](#cb386-40)            new AccountId("INVALID"),
[](#cb386-41)            new AccountId("ACC-002"),
[](#cb386-42)            Money.of(100)
[](#cb386-43)        );
[](#cb386-44)
[](#cb386-45)        useCase.execute(request)
[](#cb386-46)               .await()
[](#cb386-47)               .onSuccess(Assertions::fail);
[](#cb386-48)    }
[](#cb386-49)}
```</details> 

* * *

### Exercise 4.3 [Intermediate] - Testing Async Behavior

Test that this use case properly times out:

```
[](#cb387-1)public interface SlowService {
[](#cb387-2)    Promise<Data> fetch(DataId id);
[](#cb387-3)
[](#cb387-4)    static SlowService withTimeout(SlowService base, TimeSpan timeout) {
[](#cb387-5)        return id -> base.fetch(id).timeout(timeout);
[](#cb387-6)    }
[](#cb387-7)}
```

<details><summary>Solution</summary>

```
[](#cb388-1)class SlowServiceTest {
[](#cb388-2)
[](#cb388-3)    @Test
[](#cb388-4)    void fetch_timesOut_whenServiceTooSlow() {
[](#cb388-5)        // Stub that never resolves
[](#cb388-6)        SlowService neverResolves = id -> {
[](#cb388-7)            Promise<Data> promise = Promise.promise();
[](#cb388-8)            // Never call promise.succeed() or promise.fail()
[](#cb388-9)            return promise;
[](#cb388-10)        };
[](#cb388-11)
[](#cb388-12)        var withTimeout = SlowService.withTimeout(
[](#cb388-13)            neverResolves,
[](#cb388-14)            TimeSpan.timeSpan(100).millis()
[](#cb388-15)        );
[](#cb388-16)
[](#cb388-17)        withTimeout.fetch(new DataId("test"))
[](#cb388-18)                   .await(TimeSpan.timeSpan(500).millis())
[](#cb388-19)                   .onSuccess(Assertions::fail)
[](#cb388-20)                   .onFailure(cause ->
[](#cb388-21)                       assertTrue(cause instanceof TimeoutError));
[](#cb388-22)    }
[](#cb388-23)
[](#cb388-24)    @Test
[](#cb388-25)    void fetch_succeeds_whenServiceFastEnough() {
[](#cb388-26)        SlowService fast = id -> Promise.success(new Data("result"));
[](#cb388-27)
[](#cb388-28)        var withTimeout = SlowService.withTimeout(
[](#cb388-29)            fast,
[](#cb388-30)            TimeSpan.timeSpan(1).seconds()
[](#cb388-31)        );
[](#cb388-32)
[](#cb388-33)        withTimeout.fetch(new DataId("test"))
[](#cb388-34)                   .await()
[](#cb388-35)                   .onFailure(Assertions::fail)
[](#cb388-36)                   .onSuccess(data ->
[](#cb388-37)                       assertEquals("result", data.value()));
[](#cb388-38)    }
[](#cb388-39)}
```</details> 

* * *

## Part V: Production Systems (Chapters 12-15)

### Exercise 5.1 [Intermediate] - Complete Use Case Design

Design a use case interface for “Cancel Order” with these requirements: - Validate order exists and belongs to user - Only pending orders can be cancelled - Refund payment if already charged - Send cancellation notification

<details><summary>Solution</summary>

```
[](#cb389-1)public interface CancelOrder {
[](#cb389-2)    Promise<CancellationResult> execute(CancelRequest request);
[](#cb389-3)
[](#cb389-4)    record CancelRequest(UserId userId, OrderId orderId) {}
[](#cb389-5)    record CancellationResult(OrderId orderId, Option<RefundId> refundId) {}
[](#cb389-6)
[](#cb389-7)    // Step interfaces
[](#cb389-8)    interface FindOrder {
[](#cb389-9)        Promise<Order> apply(OrderId orderId);
[](#cb389-10)    }
[](#cb389-11)
[](#cb389-12)    interface ValidateOwnership {
[](#cb389-13)        Promise<Order> apply(Order order, UserId userId);
[](#cb389-14)    }
[](#cb389-15)
[](#cb389-16)    interface ValidateCancellable {
[](#cb389-17)        Promise<Order> apply(Order order);
[](#cb389-18)    }
[](#cb389-19)
[](#cb389-20)    interface ProcessRefund {
[](#cb389-21)        Promise<Option<RefundId>> apply(Order order);
[](#cb389-22)    }
[](#cb389-23)
[](#cb389-24)    interface UpdateOrderStatus {
[](#cb389-25)        Promise<Unit> apply(OrderId orderId, OrderStatus status);
[](#cb389-26)    }
[](#cb389-27)
[](#cb389-28)    interface SendNotification {
[](#cb389-29)        Promise<Unit> apply(UserId userId, OrderId orderId);
[](#cb389-30)    }
[](#cb389-31)
[](#cb389-32)    static CancelOrder create(FindOrder findOrder,
[](#cb389-33)                              ValidateOwnership validateOwnership,
[](#cb389-34)                              ValidateCancellable validateCancellable,
[](#cb389-35)                              ProcessRefund processRefund,
[](#cb389-36)                              UpdateOrderStatus updateStatus,
[](#cb389-37)                              SendNotification sendNotification) {
[](#cb389-38)        return request -> findOrder.apply(request.orderId())
[](#cb389-39)            .flatMap(order -> validateOwnership.apply(order, request.userId()))
[](#cb389-40)            .flatMap(validateCancellable::apply)
[](#cb389-41)            .flatMap(order -> processRefund.apply(order)
[](#cb389-42)                .flatMap(refundId -> updateStatus.apply(order.id(), OrderStatus.CANCELLED)
[](#cb389-43)                    .map(unit -> new CancellationResult(order.id(), refundId))))
[](#cb389-44)            .onSuccess(result -> sendNotification.apply(request.userId(), request.orderId())
[](#cb389-45)                .onFailure(cause -> log.warn("Notification failed", cause)));
[](#cb389-46)    }
[](#cb389-47)}
```</details> 

* * *

### Exercise 5.2 [Advanced] - Compensation Pattern

Implement a booking system where if any step fails, previous steps are rolled back:

```
[](#cb390-1)// Steps: Reserve seat → Charge payment → Send confirmation
[](#cb390-2)// If payment fails, release the seat
[](#cb390-3)// If confirmation fails, refund payment and release seat
```

<details><summary>Solution</summary>

```
[](#cb391-1)public interface BookSeat {
[](#cb391-2)    Promise<Booking> execute(BookingRequest request);
[](#cb391-3)
[](#cb391-4)    interface ReserveSeat {
[](#cb391-5)        Promise<ReservationId> apply(SeatId seatId);
[](#cb391-6)    }
[](#cb391-7)
[](#cb391-8)    interface ReleaseSeat {
[](#cb391-9)        Promise<Unit> apply(ReservationId reservationId);
[](#cb391-10)    }
[](#cb391-11)
[](#cb391-12)    interface ChargePayment {
[](#cb391-13)        Promise<PaymentId> apply(UserId userId, Money amount);
[](#cb391-14)    }
[](#cb391-15)
[](#cb391-16)    interface RefundPayment {
[](#cb391-17)        Promise<Unit> apply(PaymentId paymentId);
[](#cb391-18)    }
[](#cb391-19)
[](#cb391-20)    interface SendConfirmation {
[](#cb391-21)        Promise<Unit> apply(UserId userId, ReservationId reservationId);
[](#cb391-22)    }
[](#cb391-23)
[](#cb391-24)    static BookSeat create(ReserveSeat reserveSeat,
[](#cb391-25)                           ReleaseSeat releaseSeat,
[](#cb391-26)                           ChargePayment chargePayment,
[](#cb391-27)                           RefundPayment refundPayment,
[](#cb391-28)                           SendConfirmation sendConfirmation) {
[](#cb391-29)        return request -> reserveSeat.apply(request.seatId())
[](#cb391-30)            .flatMap(reservationId ->
[](#cb391-31)                chargePayment.apply(request.userId(), request.amount())
[](#cb391-32)                    .recover(cause -> compensateReservation(releaseSeat, reservationId, cause))
[](#cb391-33)                    .flatMap(paymentId ->
[](#cb391-34)                        sendConfirmation.apply(request.userId(), reservationId)
[](#cb391-35)                            .recover(cause -> compensatePayment(
[](#cb391-36)                                releaseSeat, refundPayment,
[](#cb391-37)                                reservationId, paymentId, cause))
[](#cb391-38)                            .map(unit -> new Booking(reservationId, paymentId))));
[](#cb391-39)    }
[](#cb391-40)
[](#cb391-41)    private static Promise<PaymentId> compensateReservation(ReleaseSeat releaseSeat,
[](#cb391-42)                                                             ReservationId reservationId,
[](#cb391-43)                                                             Cause originalCause) {
[](#cb391-44)        return releaseSeat.apply(reservationId)
[](#cb391-45)            .flatMap(unit -> originalCause.promise());
[](#cb391-46)    }
[](#cb391-47)
[](#cb391-48)    private static Promise<Unit> compensatePayment(ReleaseSeat releaseSeat,
[](#cb391-49)                                                    RefundPayment refundPayment,
[](#cb391-50)                                                    ReservationId reservationId,
[](#cb391-51)                                                    PaymentId paymentId,
[](#cb391-52)                                                    Cause originalCause) {
[](#cb391-53)        return Promise.all(releaseSeat.apply(reservationId),
[](#cb391-54)                          refundPayment.apply(paymentId))
[](#cb391-55)                      .flatMap((u1, u2) -> originalCause.promise());
[](#cb391-56)    }
[](#cb391-57)}
```</details> 

* * *

### Exercise 5.3 [Intermediate] - Project Structure

Given these classes, organize them into the correct package structure:

```
[](#cb392-1)RegisterUser (use case interface)
[](#cb392-2)RegisterUserImpl (use case implementation - if needed)
[](#cb392-3)ValidRegistration (validated request)
[](#cb392-4)Email, Password, Username (value objects)
[](#cb392-5)UserRepository (step interface)
[](#cb392-6)JpaUserRepository (repository implementation)
[](#cb392-7)RegistrationError (error types)
[](#cb392-8)UserController (REST controller)
[](#cb392-9)UserDto (API DTO)
```

<details><summary>Solution</summary>

```
src/main/java/com/example/user/
├── domain/
│   ├── Email.java              # Value object
│   ├── Password.java           # Value object
│   ├── Username.java           # Value object
│   └── RegistrationError.java  # Domain errors
├── usecase/
│   └── RegisterUser.java       # Use case with:
│                               #   - Request record
│                               #   - ValidRegistration record
│                               #   - Response record
│                               #   - Step interfaces (SaveUser, CheckEmailUnique, etc.)
│                               #   - Factory method
├── adapter/
│   ├── persistence/
│   │   └── JpaUserRepository.java  # Implements step interface
│   └── web/
│       ├── UserController.java     # REST controller
│       └── UserDto.java            # API DTO
└── config/
    └── UserConfiguration.java      # Spring wiring
```

**Notes:** - `RegisterUserImpl` is not needed - factory method in interface creates implementation - `ValidRegistration` is nested in `RegisterUser` as `ValidRequest` record - `UserRepository` doesn’t exist separately - it’s a step interface inside use case</details> 

* * *

## Part VI: Adoption (Chapters 16-19)

### Exercise 6.1 [Beginner] - Code Review Checklist

Review this code for JBCT violations:

```
[](#cb394-1)@Service
[](#cb394-2)public class UserService {
[](#cb394-3)    @Autowired
[](#cb394-4)    private UserRepository userRepository;
[](#cb394-5)
[](#cb394-6)    public User createUser(String email, String password) {
[](#cb394-7)        if (email == null || !email.contains("@")) {
[](#cb394-8)            throw new ValidationException("Invalid email");
[](#cb394-9)        }
[](#cb394-10)
[](#cb394-11)        if (userRepository.findByEmail(email).isPresent()) {
[](#cb394-12)            throw new EmailExistsException();
[](#cb394-13)        }
[](#cb394-14)
[](#cb394-15)        User user = new User();
[](#cb394-16)        user.setEmail(email);
[](#cb394-17)        user.setPassword(passwordEncoder.encode(password));
[](#cb394-18)
[](#cb394-19)        return userRepository.save(user);
[](#cb394-20)    }
[](#cb394-21)}
```

<details><summary>Solution</summary>

**Violations found:**

1.  **Primitive obsession** - Using raw `String` for email and password instead of value objects
2.  **Validation in wrong place** - Controller or service validating instead of value object factory
3.  **Exceptions for business errors** - EmailExistsException should be a Cause in Result
4.  **Mutable entity** - Using setters instead of immutable record
5.  **Field injection** - Using @Autowired instead of constructor injection
6.  **Missing use case interface** - Business logic directly in service

**Refactored:**

```
[](#cb395-1)public interface CreateUser {
[](#cb395-2)    Promise<UserId> execute(CreateUserRequest request);
[](#cb395-3)
[](#cb395-4)    record CreateUserRequest(String email, String password) {}
[](#cb395-5)    record ValidRequest(Email email, Password password) {}
[](#cb395-6)
[](#cb395-7)    interface CheckEmailUnique {
[](#cb395-8)        Promise<Email> apply(Email email);
[](#cb395-9)    }
[](#cb395-10)
[](#cb395-11)    interface SaveUser {
[](#cb395-12)        Promise<UserId> apply(ValidRequest request);
[](#cb395-13)    }
[](#cb395-14)
[](#cb395-15)    static CreateUser create(CheckEmailUnique checkEmail, SaveUser saveUser) {
[](#cb395-16)        return request -> ValidRequest.validRequest(request)
[](#cb395-17)            .async()
[](#cb395-18)            .flatMap(valid -> checkEmail.apply(valid.email())
[](#cb395-19)                .map(email -> valid))
[](#cb395-20)            .flatMap(saveUser::apply);
[](#cb395-21)    }
[](#cb395-22)}
```</details> 

* * *

### Exercise 6.2 [Intermediate] - Migration Planning

You have this legacy service. Plan a phase-by-phase migration:

```
[](#cb396-1)@Service
[](#cb396-2)public class OrderService {
[](#cb396-3)    public Order placeOrder(OrderDto dto) {
[](#cb396-4)        // 50 lines of validation
[](#cb396-5)        // 30 lines of inventory check
[](#cb396-6)        // 40 lines of payment processing
[](#cb396-7)        // 20 lines of order creation
[](#cb396-8)        // 15 lines of notification
[](#cb396-9)    }
[](#cb396-10)}
```

<details><summary>Solution</summary>

**Phase 1: Value Objects (Week 1)** - Create: OrderId, ProductId, Quantity, Money, CustomerId - Parallel method: `placeOrderValidated(ValidOrderRequest request)` - Keep original method, call validated version internally

**Phase 2: Result in New Code (Week 2)** - Extract validation to `ValidOrderRequest.validRequest(OrderDto)` - Return `Result<Order>` instead of throwing - Create `OrderError` sealed interface

**Phase 3: Extract Use Case (Week 3-4)** - Create `PlaceOrder` interface with step interfaces: - `CheckInventory` - `ProcessPayment` - `CreateOrder` - `SendNotification` - Move business logic to factory method - Service becomes thin wrapper calling use case

**Phase 4: Adapter Isolation (Week 5)** - Wrap inventory check in `Promise.lift()` - Wrap payment gateway in `Promise.lift()` - Wrap repository in `Promise.lift()` - Email service as fire-and-forget Promise

**Migration commits:** 1\. Add value objects 2\. Add ValidOrderRequest 3\. Add OrderError types 4\. Extract PlaceOrder interface 5\. Implement step interfaces as adapters 6\. Convert service to use case wrapper 7\. Remove legacy method</details> 

* * *

### Exercise 6.3 [Beginner] - Debugging Practice

This chain fails silently. Add debugging to find where:

```
[](#cb397-1)public Promise<Report> generateReport(ReportRequest request) {
[](#cb397-2)    return validateRequest(request)
[](#cb397-3)        .flatMap(this::fetchData)
[](#cb397-4)        .flatMap(this::transformData)
[](#cb397-5)        .flatMap(this::formatReport);
[](#cb397-6)}
```

<details><summary>Solution</summary>

```
[](#cb398-1)public Promise<Report> generateReport(ReportRequest request) {
[](#cb398-2)    return validateRequest(request)
[](#cb398-3)        .onSuccess(r -> log.debug("Validated: {}", r))
[](#cb398-4)        .onFailure(c -> log.error("Validation failed: {}", c.message()))
[](#cb398-5)        .flatMap(this::fetchData)
[](#cb398-6)        .onSuccess(d -> log.debug("Fetched {} records", d.size()))
[](#cb398-7)        .onFailure(c -> log.error("Fetch failed: {}", c.message()))
[](#cb398-8)        .flatMap(this::transformData)
[](#cb398-9)        .onSuccess(t -> log.debug("Transformed to {} items", t.size()))
[](#cb398-10)        .onFailure(c -> log.error("Transform failed: {}", c.message()))
[](#cb398-11)        .flatMap(this::formatReport)
[](#cb398-12)        .onSuccess(r -> log.debug("Report generated: {} pages", r.pageCount()))
[](#cb398-13)        .onFailure(c -> log.error("Format failed: {}", c.message()));
[](#cb398-14)}
```

**Alternative: Extract to named methods for breakpoints:**

```
[](#cb399-1)public Promise<Report> generateReport(ReportRequest request) {
[](#cb399-2)    return validateRequestStep(request)
[](#cb399-3)        .flatMap(this::fetchDataStep)
[](#cb399-4)        .flatMap(this::transformDataStep)
[](#cb399-5)        .flatMap(this::formatReportStep);
[](#cb399-6)}
[](#cb399-7)
[](#cb399-8)private Promise<ValidRequest> validateRequestStep(ReportRequest request) {
[](#cb399-9)    log.debug("Validating request");
[](#cb399-10)    return validateRequest(request);  // Breakpoint here
[](#cb399-11)}
[](#cb399-12)
[](#cb399-13)// ... similar for other steps
```</details> 

* * *

## Summary

These exercises cover the full JBCT learning path:

| Part | Focus | Key Skills |
| --- | --- | --- |
| I | Foundations | Type selection, Cause creation, basic operations |
| II | Principles | Value objects, error accumulation, null handling |
| III | Patterns | Pattern identification, implementation, thread safety |
| IV | Testing | Test structure, stubs, async testing |
| V | Production | Use case design, compensation, project structure |
| VI | Adoption | Code review, migration, debugging |

Practice these exercises to build muscle memory for JBCT patterns. The goal is to make these patterns your default way of thinking about code.

# Appendix C: Glossary

This glossary defines key terms used throughout the book.

* * *

## A

**Adapter** A component that bridges between external systems and the domain. Adapters implement step interfaces and wrap external I/O in Promise types. Examples: repositories, HTTP clients, message queue producers.

**Adapter Zone** The architectural layer containing adapters. Converts between external representations (JSON, SQL) and domain types. The only place where Promise.lift() should appear.

**Aggregation** Combining multiple Result or Promise values into one. `Result.all()` accumulates all failures. `Promise.all()` fails fast on first failure.

**Aspects Pattern** A structural pattern for cross-cutting concerns like retry, timeout, logging, and audit. Implemented as wrapper functions that compose around a core operation.

* * *

## B

**Bifurcation** Handling both success and failure cases. Methods like `fold()` and `apply()` accept two handlers - one for each outcome.

* * *

## C

**Cause** A typed error value in Pragmatica Lite. Represents why an operation failed. Defined as sealed interfaces for exhaustive handling. Preferred over exceptions for business errors.

**Chain** A sequence of monadic operations connected by `flatMap()`. Each step receives the previous step’s success value. Failures short-circuit the chain.

**Clean Architecture** Uncle Bob’s architectural style with concentric layers and the dependency rule. JBCT can be implemented within Clean Architecture.

**CompositeCause** A Cause containing multiple sub-causes. Created by `Result.all()` when multiple validations fail. Allows collecting all errors instead of stopping at first.

**Condition Pattern** A structural pattern for routing based on a discriminator value. Implemented with switch expressions. Each branch returns the same type.

* * *

## D

**Dependency Inversion** Dependencies point toward abstractions, not implementations. In JBCT, use cases depend on step interfaces (abstractions), adapters implement them.

**Domain Zone** The architectural layer containing pure business logic. Contains use cases, value objects, and step interfaces. No framework dependencies.

* * *

## E

**Error Accumulation** Collecting all errors instead of stopping at the first. `Result.all()` accumulates failures into CompositeCause.

**Exception Wrapping** Converting exceptions to Cause values at adapter boundaries. Done with `Promise.lift()` or `Result.lift()`.

**External Zone** Everything outside your application: databases, external APIs, message queues, file systems.

* * *

## F

**Factory Method** A static method that creates instances of value objects or use cases. Value object factories return `Result<T>` to enforce validation.

**Fail-Fast** Stopping at the first failure. `flatMap()` chains and `Promise.all()` are fail-fast.

**flatMap** The monadic bind operation. Chains dependent operations. If input is failure, skips the operation. Prevents nested monads (`Result<Result<T>>`).

**Fn1, Fn2, Fn3** Functional interfaces in Pragmatica Lite for functions with 1, 2, or 3 parameters. Similar to Java’s Function but with better composition.

**Fork-Join Pattern** A structural pattern for parallel independent operations. Uses `Promise.all()` to run operations concurrently and combine results.

* * *

## G

**Guard Clause** Early return on invalid input. In JBCT, replaced by parse-don’t-validate: validation happens in value object factories, not guard clauses.

* * *

## H

**Happy Path** The execution path when all operations succeed. In JBCT, the happy path is the default - failures are handled explicitly.

**Hexagonal Architecture** Ports and Adapters architecture. Domain at center, adapters at edges. JBCT’s step interfaces are similar to ports.

* * *

## I

**Immutability** Objects that cannot be modified after creation. Java records are immutable by default. Essential for thread safety in JBCT.

**Iteration Pattern** A structural pattern for processing collections. Uses `Promise.allOf()` for parallel processing or stream operations for sequential.

* * *

## J

**JBCT** Java Backend Coding Technology. A methodology for writing maintainable backend Java code using functional composition and explicit error handling.

* * *

## L

**Leaf Pattern** A structural pattern for atomic operations with no dependencies. Typically adapters wrapping external I/O with `Promise.lift()`.

**Lift** Converting a value or operation to a monadic context. `Result.lift()` wraps throwing code in Result. `result.async()` lifts Result to Promise.

* * *

## M

**map** Transform the success value while preserving the container. Does not flatten nested containers - use `flatMap()` when the mapper returns a monadic type.

**Monad** A design pattern for chaining operations that may have side effects. Option, Result, and Promise are all monads. The key operation is `flatMap()`.

* * *

## O

**Option** A type representing a value that may be absent. Use when absence is normal, not an error. Convert to Result when absence should be an error.

* * *

## P

**Parse, Don’t Validate** A principle: instead of validating data and proceeding with raw types, parse data into validated types that make invalid states unrepresentable.

**Port** In Hexagonal Architecture, an interface defining how the domain interacts with the outside world. Similar to JBCT’s step interfaces.

**Pragmatica Lite** A minimal Java library providing Option, Result, Promise, and Cause types. The foundation for JBCT patterns.

**Promise** A type representing an asynchronous operation that may fail. Combines async execution with explicit error handling.

**Pure Function** A function with no side effects that always returns the same output for the same input. Value object factories should be pure.

* * *

## R

**Railway-Oriented Programming (ROP)** An error handling approach using “two-track” types. Success track and failure track. JBCT uses this model via Result and Promise.

**Record** Java’s immutable data class (since Java 14). Used for value objects, requests, responses, and error types in JBCT.

**recover** Handle failures and potentially convert to success. Takes a function `Cause -> M<T>` that can either provide a fallback value or re-throw.

**Result** A type representing a synchronous operation that may fail. Contains either a success value or a Cause.

**Result.all** Combines multiple Results, accumulating all failures into CompositeCause. Use for independent validations.

* * *

## S

**Sealed Interface** Java’s restricted inheritance (since Java 17). All implementations must be known at compile time. Used for Cause types and exhaustive switch expressions.

**Sequencer Pattern** A structural pattern for linear chains of dependent operations. Each step depends on the previous step’s output. Uses `flatMap()` chains.

**Short-Circuit** Stopping execution at the first failure. `flatMap()` chains short-circuit. `Result.all()` does not short-circuit.

**Step Interface** A functional interface defining one operation in a use case. Declared inside the use case interface. Implemented by adapters.

**Stub** A test double that returns predetermined values. In JBCT, typically lambdas implementing step interfaces.

* * *

## T

**Three Zones** JBCT’s architectural model: External (outside systems), Adapter (boundary translation), Domain (pure business logic).

**TimeSpan** Pragmatica Lite’s duration type. Created with fluent API: `TimeSpan.timeSpan(5).seconds()`.

**Type Lifting** Converting from a lower type to a higher one: `T` → `Option` → `Result` → `Promise`. Safe direction that adds information.

* * *

## U

**Unit** A type with a single value, representing “no meaningful result”. Used instead of `Void` for operations that succeed but return nothing.

**Use Case** A single business operation exposed as a functional interface. Contains Request/ValidRequest/Response records and step interfaces.

* * *

## V

**Validation** Checking that data meets requirements. In JBCT, validation happens in value object factories, returning `Result<T>`.

**Value Object** An immutable object representing a domain concept. Created through factory methods that enforce validation. Examples: Email, Money, UserId.

**Verify** Pragmatica Lite utility class for validation predicates. `Verify.ensure()` creates Result from predicate. `Verify.Is` provides common predicates.

* * *

## W

**Wrapper** A function that adds behavior around another function. Used in the Aspects pattern for cross-cutting concerns.

* * *

## Quick Reference

| Term | One-Line Definition |
| --- | --- |
| Adapter | Bridges external systems to domain |
| Cause | Typed error value |
| flatMap | Chain dependent operations |
| Fork-Join | Parallel independent operations |
| Leaf | Atomic adapter operation |
| map | Transform success value |
| Option | Value that may be absent |
| Parse, Don’t Validate | Create validated types, not checked raw data |
| Promise | Async operation that may fail |
| Result | Sync operation that may fail |
| Sequencer | Linear chain of dependent steps |
| Step Interface | One operation in a use case |
| Unit | Type for “no result” |
| Use Case | Single business operation |
| Value Object | Immutable validated domain concept |