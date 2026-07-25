![](cover.jpeg)

# Secure and Quality Java Coding using Sensei

A ‘How To’ Guide for Writing Secure and Quality Code with Secure Code Warrior’s Sensei IntelliJ Plugin

Alan Richardson, Head of Developer Relations at Secure Code Warrior

SecureCodeWarrior.com

# Secure and Quality Java Coding using Sensei

1.  [Introduction](#text00002.html_introduction)
    1.  [What is Sensei?](#text00002.html_what-is-sensei)
    2.  [What is Static Analysis?](#text00002.html_what-is-static-analysis)
    3.  [Example Recipe Repositories](#text00002.html_example-recipe-repositories)
    4.  [Useful Documentation and Links](#text00002.html_useful-documentation-and-links)
    5.  [Sensei Team Support](#text00002.html_sensei-team-support)
    6.  [Running IntelliJ Inspections From Continuous Integration](#text00002.html_running-intellij-inspections-from-continuous-integration)
2.  [Sensei GUI Overview](#text00003_split_000.html_sensei-gui-overview)
    1.  [Sensei Menu](#text00003_split_000.html_sensei-menu)
    2.  [Cookbook Manager](#text00003_split_000.html_cookbook-manager)
    3.  [Manage Recipes](#text00003_split_001.html_manage-recipes)
    4.  [Cookbook Recipe Editor List](#text00003_split_001.html_cookbook-recipe-editor-list)
    5.  [Recipe Editor](#text00003_split_002.html_recipe-editor)
    6.  [General Settings](#text00003_split_002.html_general-settings)
    7.  [Recipe Settings - Search](#text00003_split_002.html_recipe-settings---search)
    8.  [QuickFix Settings](#text00003_split_002.html_quickfix-settings)
    9.  [Creating A Recipe](#text00003_split_002.html_creating-a-recipe)
    10.  [Spotting Issues in the IDE](#text00003_split_002.html_spotting-issues-in-the-ide)
    11.  [Triggering a Quick Fix](#text00003_split_002.html_triggering-a-quick-fix)
3.  [Section - Use-Cases](#text00004.html_section---use-cases)
4.  [POJO Use-Cases](#text00005.html_pojo-use-cases)
    1.  [Converting System.out.println to logger](#text00005.html_converting-system.out.println-to-logger)
5.  [Junit 5 Use-Cases](#text00006.html_junit-5-use-cases)
    1.  [Adding Annotations and Method Renaming](#text00006.html_adding-annotations-and-method-renaming)
    2.  [Adding Parameters to Annotations Using Rewrite Actions](#text00006.html_adding-parameters-to-annotations-using-rewrite-actions)
    3.  [Documentation Links](#text00006.html_documentation-links)
6.  [Guice Use-cases](#text00007.html_guice-use-cases)
    1.  [How to catch and fix a dependency injection issue using Sensei](#text00007.html_how-to-catch-and-fix-a-dependency-injection-issue-using-sensei)
7.  [Next Steps](#text00008.html_next-steps-1)
    1.  [Install Sensei](#text00008.html_install-sensei)
    2.  [Study Some Examples](#text00008.html_study-some-examples)
    3.  [Read the Documentation](#text00008.html_read-the-documentation)
    4.  [Experiment](#text00008.html_experiment)
    5.  [Summary](#text00008.html_summary-6)
8.  [About Secure Code Warrior](#text00009.html_about-secure-code-warrior)
9.  [About the Author](#text00010.html_about-the-author)

1.  [Title Page](#text00000.html)
2.  [Cover](Image00000.jpg)
3.  [Table of Contents](#text00001.html_toc)

# Introduction

[Sensei](https://scw.buzz/38n5uPu) is a free IntelliJ plugin from [Secure Code Warrior](https://scw.buzz/2PBhLJp) that helps you codify quality coding practices as real-time warnings in your IDE, and create Quick Fix solutions to educate you or rewrite your code.

*   [securecodewarrior.com/sensei](https://scw.buzz/3qvDvDt)

This document has example recipes and explanations to help you get started using Sensei to write better quality code.

Numerous staff from Secure Code Warrior have been involved in the creation of this document:

*   Charlie Eriksen and Robin Claerhout created the Guice example
*   Nathan Desmet created the `System.out.println` to `Logger` example
*   Additional help, recipes, code and reviews were provided by: Matthieu Calie, Brysen Ackx, Downey Robersscheuten.

For a quick overview of what Sensei can do, watch: [youtu.be/HPj1Lo97aTQ](https://youtu.be/HPj1Lo97aTQ)

[![](OEBPS/Image00001.jpg)](https://www.youtube.com/watch?v=HPj1Lo97aTQ)

## What is Sensei?

The Sensei plugin provides an easy way to find specific code patterns in your source code and apply rewrite rules to amend the matching code - all within the Intellij IDE, and in real-time.

For example, you could create a rule that matches on JUnit `@Disabled` annotations which do not have a reason. Sensei would then tell you about the issue by highlighting the code in the IDE.

Additionally, when you `alt+enter` , you can have the option to `Add a todo comment parameter` .

When selected, this will amend the code to add a boilerplate reason, which you can then amend. If you don’t, it will show up in your TODO panel.

e.g. `@Disabled` would become `@Disabled("TODO: add a description here")`

Sensei combines the functionality of a Static Analysis code scanner with a code rewriting engine.

### IntelliJ Intention Actions

Based on the above description, the obvious alternative (if you were not using Sensei) is to use the IntelliJ Intention Actions functionality.

Sensei differs from IntelliJ Intention Actions because the aim with Sensei is to provide a way to create matchers and rewriters which are project specific, or even local to an individual developer.

We have tried to put together a GUI that makes both the matching and rewrite rules easy to write and experiment with.

### How can it help me personally improve?

When I’m learning a new library, it takes me time to build up muscle memory around the methods and formatting. So I might choose to create personal recipes which

*   link off to the official documentation or tutorial pages
*   have boilerplate templates which are most effective
*   fix poor coding practices
*   add boilerplate code to help use a library

I can use Sensei to build temporary recipes which prompt me for the current practices I’ve chosen to use and help me build up effective habits. The recipes are temporary because I can remove them when I outgrow them.

### How can it help my team improve?

In the same way, we can help teams build up muscle memory around agreed coding standards.

Creating cookbooks of recipes that we apply when we find the same comments in pull request reviews. Since the cookbooks are stored in version control with the project, they are available to everyone on the project and we can switch them off when we no longer need prompting.

### Sensei helps provide feedback early

We’ve tried to build a way of pulling the feedback that helps us improve and provide reminders of corrective action as early on in the coding process as we can with Sensei.

Rather than wait for:

*   the results of a static analyser
*   the comments from a code review

We can instead see the feedback for custom standards we want to enforce as we code.

We provide either reminders, or actual rewrite rules, to help us write code that complies with the standards.

### Sensei is flexible

Sensei is a mix of:

*   part Static Analyser
*   part coding tutor
*   part rewrite engine

Sensei is so flexible that it makes it hard to answer the question: “What is Sensei?”

### Sensei fills a gap in the programming workflow

We’ve tried to make Sensei the missing piece of the programmer workflow that helps you improve specific elements in your coding style, or library use, that you and your team are currently working with.

This flexibility means that it takes a little more time to get to grips with Sensei than a static analysis tool or the built-in IntelliJ Intensions. By spending the time to experiment, you will gain a new way of speeding up your learning in your personal development process.

### How to experiment?

Download and install Sensei from the [Intellij Marketplace](https://plugins.jetbrains.com/plugin/14015) . We recommend installing Sensei via the plugins manager in IntelliJ preferences (just search for ‘Sensei secure code’ and you’ll find it).

We have also created a getting started guide on the Intellij Marketplace - [get started page](https://scw.buzz/3rveXvC) .

Once you’ve downloaded and installed Sensei, the easiest way to make it work for you is to look at your coding process and consider:

*   What documentation do you keep looking up?
    *   You could add some Sensei recipes that link back to that documentation.

*   What simple mistakes do you keep making?
    *   You can temporarily codify that poor coding pattern as a matcher and write a Quick Fix rewrite that amends the code to be what you really want to write.
*   What boilerplate code do you write to use a library?
    *   You can create a Quick Fix rule to write the code for you.

Sensei is designed to work alongside whatever static analysis tool you’re using. That means that if you find that the same violations are being reported from static analysis, then you could replicate the condition in a Sensei recipe. You can then add a Quick Fix to help train you not to just identify the mistake, but also to move quickly to writing the correct code.

## What is Static Analysis?

Static Analysis is the automated analysis of source code without executing the application.

When the analysis is performed during program execution then it is known as Dynamic Analysis.

Static Analysis is often used to detect:

*   Security vulnerabilities.
*   Performance issues.
*   Non-compliance with standards.
*   Use of out of date programming constructs.

### How does a Static Analysis tool work?

The basic concept common to all Static Analysis tools is searching source code to identify specific coding patterns that have some sort of warning or information associated with them.

This could be as simple as “JUnit 5 test classes do not need to be ‘public’” or something complex to identify like “Untrusted String input being used in an SQL execution statement”.

Static Analysis tools vary in how they implement this functionality.

*   Source code parsing technology to create an Abstract Syntax Tree (AST),
*   Text Regular Expression matching,
*   A combination of the above.

Regular Expression matching on text is very flexible and easy to write rules to match, but can often lead to a lot of false positives and the matching rules are ignorant of the surrounding code context.

AST matching treats the source code as program code and not just files filled with text. This allows for more specific, contextual matching and can reduce the number of false positives reported against the code.

### Static Analysis in Continuous Integration

Static Analysis is often performed during the Continuous Integration (CI) process to generate a report of compliance issues which can be reviewed to receive an objective view of the code-base over time.

Some people use Static Analysis as an objective measure of their code quality by configuring the static analysis tool to only measure specific parts of the code, and only report on a subset of rules.

The objectivity is provided by the rules used since these do not vary in their evaluation of code over time. Clearly, the combination of rules used and their configuration is a subjective decision and different teams choose to use different rules at different times.

Having the Static Analysis performed in CI is useful but might delay the feedback to the programmer. Programmers don’t receive feedback when coding, they receive feedback later when the code is run through the Static Analysis tool. Another side-effect of running the Static Analysis in CI is that the results are easier to ignore.

To help make teams pay more attention to the results from Static Analysis it is usually possible to configure a threshold metric in the build process to fail the build if the metric is exceeded e.g. a number of rules triggered.

### Static Analysis in the IDE

To receive feedback faster, there are many IDE plugins that run the Static Analysis rules in the IDE on demand, or periodically as the code changes.

The rule violations can then be seen in the IDE as the programmer is writing code, and to make the rules harder to ignore, the violations can often be configured to render as underlined code in the editor.

I personally find this a useful way to improve my coding, particularly when working with a new library that is covered by the Static Analysis tool. Although it can be ‘noisy’ with false positives, or rules you are not interested in. But this is solved by taking the extra step to configure the Static Analysis tool to ignore certain rules.

### Fixing Code Based on Static Analysis Rules

With most Static Analysis tools, the fixing of the rule is left to the programmer, so they have to understand the cause of the rule violation and how to fix it.

Very few static analysis tools also include the ability to fix the violations because the fix is so often contextual to the team and the technology used and their agreed coding styles.

### Default Rules

False confidence in the quality of the rules may arise when the Static Analysis tools come with default rules. It is tempting to believe that they cover all the issues that a programmer might encounter and all the circumstances that rule should apply. Sometimes the circumstances in which a rule should apply can be subtle and may not be easy to detect.

The hope is that by using a Static Analysis tool and researching the rules and violations in more detail, programmers will develop the skill to detect and avoid the issue in the context of their specific domain.

When the domain requires contextual rules, the Static Analysis tools may not have any rules that match your domain or library. Additionally, the tools can often be difficult to configure and expand.

### Annoyances

None of these ‘annoyances’ are insurmountable. These include:

*   False positives
*   Lack of fixes
*   Configuration to ignore rules
*   Adding context-specific rules

They are often used as excuses to avoid using the Static Analysis tools in the first place, which is a pity because the use of Static Analysis can be enormously useful as a way to:

*   Highlight better approaches to junior developers.
*   Gain fast feedback on clear coding violations.
*   Identify obscure issues that the programmer has not encountered before.
*   Reinforce that the programmer has adopted a good coding approach (when no violations are reported).

### IDE Based Static Analysis Tools

As an individual contributor to a project, I like to use Static Analysis tools that run from within the IDE so that I receive fast feedback on my code.

This supplements any pull request review process and CI integration that a project may have.

I try to identify tools that will give me an edge and improve my individual workflow.

When tools run in the IDE, because they tend to share the same basic GUI and configuration approach, it can be tempting to view them interchangeably.

The tools may have overlapping functionality or rule sets. To gain maximum advantage I install multiple tools to take advantage of their strengths.

The Static Analysis IDE tools I actively use when coding are:

*   The inbuilt IntelliJ Inspections - common coding patterns.
*   SpotBugs - common errors.
*   SonarLint - common usage patterns.
*   CheckStyle - common style patterns.
*   Sensei from Secure Code Warrior - custom rule creation.

I use them all because they work well together to augment and supplement each other.

#### IntelliJ Inspections

If you use IntelliJ, then you are already using their Inspections.

These are Static Analysis rules which are flagged in the IDE. Some of them also have QuickFix options to rewrite the code to address the issue.

The rules are configurable on and off, and to choose the error level used to highlight it in the IDE.

![](OEBPS/Image00002.jpg)

There are a lot of good IntelliJ Inspections. I know that because I read through them while writing this. I use the IntelliJ Inspections as the defaults and haven’t configured them, but to gain full value from the Inspections you should read through them, identify those relevant to your coding style, and configure the warning level so that you notice them in the code.

The great thing about the IntelliJ Inspections is that they come free with the IDE and they help build the muscle memory of:

*   Noticing warnings and errors in the source as you write code.
*   Hovering the mouse over flagged code to learn the rule violations.
*   Using `alt+enter` to apply a QuickFix for the issue.

![](OEBPS/Image00003.jpg)

#### SpotBugs

The [SpotBugs](https://plugins.jetbrains.com/plugin/14014-spotbugs) IntelliJ plugin uses Static Analysis to try and alert you to bugs in your code.

SpotBugs can be configured from the IntelliJ Preferences to scan your code. The actual rules used can be found in the Detector tab.

![](OEBPS/Image00004.jpg)

I tend to use SpotBugs after I’ve written and reviewed my code. I’ll then run the ‘Analyze Project Files Including Test Sources’.

![](OEBPS/Image00005.jpg)

This does help me identify bugs, dead code, and obvious optimizations. It also forces me to research some of the flagged violations to help me decide what to do.

SpotBugs will find issues but does not offer any QuickFix actions to attempt to resolve the issues.

SpotBugs is easy to configure and I find it to be a useful objective second opinion to consult in my IDE.

#### SonarLint

The [SonarLint](https://plugins.jetbrains.com/plugin/7973-sonarlint) plugin.

SonarLint can be configured from the IntelliJ Preferences to select which rules the code is validated against.

![](OEBPS/Image00006.jpg)

By default, SonarLint runs in realtime and shows issues for the current code that you are editing.

SonarLint does not offer quick fixes, but the documentation associated with the violation reports is usually clear and well documented.

I’ve found SonarLint to be useful in the past for alerting me to new Java features that I was aware of in the newer versions of Java.

#### CheckStyle

The [CheckStyle](https://plugins.jetbrains.com/plugin/1065-checkstyle-idea) plugin offers a mix of formatting and code-quality rules.

The CheckStyle plugin comes bundled with ‘Sun Checks’ and ‘Google Checks’.

The definitions of these can be easily [found online](https://checkstyle.sourceforge.io/style_configs.html) .

CheckStyle adds the most value when a project has spent the time creating its own ruleset. Then the IDE plugin can be configured to use that ruleset and programmers can perform a scan, prior to committing the code to CI.

CheckStyle is very often used as a build failing plugin for CI processes when the number of CheckStyle violations exceeds a threshold.

### Sensei

[Sensei](https://scw.buzz/38n5uPu) uses Static Analysis based on an Abstract Syntax Tree (AST) for matching code and for creating Quick Fixes, this allows for very specific identification of code with issues.

The AST allows Quick Fixes associated with a recipe to understand the surrounding code e.g. when adding a new class into the code any import for that class will only be added to the source file once, and not for each replacement.

Sensei was created to make it easy to build custom matching rules which may not exist, or which would be hard to configure, in other tools.

Rather than amend a configuration file, all the configuration can be performed in the GUI. When creating new recipes the GUI makes it easy to see which code the recipe matches. When defining the Quick Fixes the before and after state of the code can be compared immediately. This makes it easier to create very contextual recipes i.e. unique to teams, or technology, and even individual programmers.

![](OEBPS/Image00007.jpg)

I use Sensei in combination with other Static Analysis tools e.g. most Static Analysis tools will find issues, but not fix them. A common use case for Sensei is to replicate the other tool’s matching search in Sensei and expand it with a Quick Fix. This has the benefit that the custom fix applied already meets the coding standards for your project.

I periodically find myself creating Sensei recipes that already exist in the IntelliJ Intensions set because the Intension report doesn’t quite match the context I’ve created or because the QuickFix provided by IntelliJ doesn’t match the code pattern I want to use.

I augment the existing tools, rather than attempt to fully replace them.

Sensei can also be very useful when you identify a contextual variant of a common rule e.g. if you are using an SQL library not supported by the Static Analysis tool, but the common SQL rules in the Static Analysis engine still apply, then you can create library-specific variants of those rules using Sensei.

Sensei does not come out-of-the-box with a lot of generic recipes like the Static Analysis tools mentioned, its strength is in making it easy to create new recipes, complete with Quick Fixes configured to match your specific coding style and use-cases.

*NOTE: we are working on a public repository of recipes to cover generic use-cases, and [you can find it here](https://scw.buzz/30pk1FN) .*

### Summary

I tend to pick tools that work together, are configurable, and easy to expand to meet my specific context. I’ve used Static Analysis tools in the IDE for years to help me identify issues, and learn more about the programming languages and libraries I use.

I use all of the tools mentioned in combination:

*   IntelliJ Intentions helps flag common code issues out the box, often with associated Quick Fixes.
*   SpotBugs finds simple bugs I might have missed and alerts me to performance issues.
*   SonarLint identifies Java features I was unaware of and prompts me to additional ways of modelling my code.
*   CheckStyle helps me conform to an agreed coding style that is also enforced during CI.
*   Sensei helps me create Quick Fixes to augment common scenarios found by Static Analysis tools and create specific project or technology recipes that can be hard to configure in another tool.

## Example Recipe Repositories

We have created some example repositories on GitHub that you might find useful for learning Sensei.

*   [github.com/SecureCodeWarrior/sensei-blog-examples](https://scw.buzz/3cixLrq)
*   [github.com/SecureCodeWarrior/public-cookbooks](https://scw.buzz/30pk1FN)

### Blog Examples

This project has example recipes and code to experiment with.

*   [github.com/SecureCodeWarrior/sensei-blog-examples](https://scw.buzz/3cixLrq)

**How to Use:**

*   [Install Sensei Plugin](https://scw.buzz/3rveXvC) .
*   Clone or download project.
*   Open in IDE.
*   Example Sensei recipes in `.sensei` will be loaded.
*   Read through Use Cases to see how recipes identify issues and fix code.

*This is a Multi-module maven project. When you clone this project, or download it as a zip, remember to open the top level `pom.xml` as the project. The `.sensei` folder contains example recipes which support the examples and embedded `readme.md` files.*

### Public Cookbooks

The Public Cookbooks repo is a list of all the public Sensei Cookbooks that we know of.

*   [github.com/SecureCodeWarrior/public-cookbooks](https://scw.buzz/30pk1FN)
*   [securecodewarrior.github.io/public-cookbooks](https://scw.buzz/3btJZhV)

Full instructions and documentation for the cookbooks should be in the listing for each cookbook.

The cookbooks in the public listing are useful:

*   To use as cookbooks for the technology they cover.
*   For studying to see how to create recipes.
*   To understand the range of domains that Sensei recipes can be applied to.

## Useful Documentation and Links

The documentation for Sensei:

*   [Official Documentation](https://scw.buzz/3emSI7l)
*   [https://sensei-docs-beta.securecodewarrior.com/](https://scw.buzz/3emSI7l)

IntelliJ on the JetBrains marketplace:

*   [Instructions to install the plugin from the IntelliJ Marketplace](https://scw.buzz/3rveXvC)
*   [https://plugins.jetbrains.com/plugin/14015-sensei-by-secure-code-warrior-/getstarted](https://scw.buzz/3rveXvC)

The Secure Code Warrior Sensei Blog:

*   [Blog Posts](https://scw.buzz/2OBxgk0)
*   Also on [dev.to/securecodewarrior](https://dev.to/securecodewarrior)

[securecodewarrior.com/blog-tags/sensei](https://scw.buzz/2OBxgk0)

Videos from Secure Code Warrior:

*   [youtube.com/c/SecureCodeWarrior/videos](https://www.youtube.com/c/SecureCodeWarrior/videos)

To see the Sensei videos, select the [Sensei playlist](https://www.youtube.com/playlist?list=PL7KK7fPcGxbbmIxZJzkJKXbjtc6K_nJjX) .

Useful Github Repositories:

*   [Examples Project on Github](https://scw.buzz/3cixLrq)
    *   [github.com/SecureCodeWarrior/sensei-blog-examples](https://scw.buzz/3cixLrq)
*   [Public Sensei Cookbooks Index](https://scw.buzz/30pk1FN)
    *   [github.com/SecureCodeWarrior/public-cookbooks](https://scw.buzz/30pk1FN)
    *   [securecodewarrior.github.io/public-cookbooks/](https://scw.buzz/3btJZhV)

## Sensei Team Support

When one person creates a recipe to improve their code quality or productivity, everyone on the team can benefit when the cookbooks are shared.

Sensei provides a number of mechanisms for sharing cookbooks:

*   Store Cookbooks in the Project Under Version Control.
*   Storing Cookbooks in a shared folder.
*   Store Cookbooks in Github.
*   Zipped files over HTTP(s).

By sharing the cookbooks, Sensei helps teams collaborate on knowledge sharing. The collaboration helps improve communication and embed the agreed code quality approaches.

For example, sharing a cookbook allows:

*   Team members to share useful recipes with each other.
*   Team leads to codify agreed coding practices for junior staff.
    *   To identify common violations with a quick fix for the agreed version.
*   Increased Inter-team co-operation.
    *   An AppSec team might create recipes to highlight a problem in the code, and the development team could write the quick fix.

The next few sections explain how to implement each of the sharing mechanisms.

### Store Cookbooks in the Project Under Version Control

The project `.sensei` folder is the default option when creating a cookbook file.

*   `project://.sensei’

All cookbooks and recipes would be stored in a `.sensei` folder in your project.

The easiest approach to sharing is to add the project `.sensei` folder to version control.

Then the `.sensei` folder can be managed like any other shared code artifact associated with the project. The cookbooks are stored as YAML configuration, making them easy to merge during any commit and review process.

This is the approach taken for the public `sensei-blog-examples` project.

https://github.com/SecureCodeWarrior/sensei-blog-examples

The `.sensei` folder contains the cookbook with all the recipes, and they are available to anyone that clones the repository.

### Store Cookbooks in Any Folder

Teams can also use cookbooks stored in central locations.

Saving the cookbook to any folder with shared write access permissions will allow the whole team to update the recipes, and import them into any project that they happen to be working on.

The location would be set to the directory path.

### Store Recipes in Github

Sensei can also access recipes that are stored in a Github repo. Both private and public repositories are supported.

#### Github over SSH

SSH Repository access is configured using the following syntax for the `Location`

`git@github.com:SecureCodeWarrior/acookbook.git`

For this to work, the repository would contain the contents of a cookbook folder.

e.g. our Basic Protection Cookbook takes this approach and could be added as a “Locally configured Cookbook” using the location

`git@github.com:SecureCodeWarrior/cookbook-basic-protection-set.git`

It is also possible to configure the branch and the subfolder for the cookbook e.g. in the `master` branch in the `cookbook` subfolder

e.g.

`git@github.com:SecureCodeWarrior/sensei-blog-examples.git|master|.sensei`

An SSH key needs to be configured for private repositories.

*   https://github.com/settings/keys

And the key should not have a passphrase.

#### Github over HTTPS

It is also possible to access public repositories over HTTPS, and the same `repo.git|branch|folder` syntax is used e.g.

`https://github.com/SecureCodeWarrior/sensei-blog-examples.git|master|.sensei`

#### Zipped over HTTP(s)

Sensei can also access cookbooks that are zipped, over HTTP or HTTPS.

e.g.

`http://localhost:8000/rules.sensei.zip`

The zip cookbook file should contain the contents of a cookbook folder e.g the `rules.sensei` file.

### Sharing Summary

Sensei supports using multiple cookbooks so that an individual programmer can have recipes that support their own learning and productivity.

More importantly, we know that teams work most effectively when knowledge is shared. Having shared team repositories, e.g. for a specific project, or a specific library, or for a shared set of migration patterns, can help boost team productivity and codify the team’s experience.

When a cookbook is shared, multiple teams can use the same cookbook which can also improve inter-team collaboration from different disciplines e.g. AppSec to development.

With four core sharing mechanisms available, Sensei hopefully has at least one approach you can use to increase collaboration on knowledge sharing.

## Running IntelliJ Inspections From Continuous Integration

IntelliJ IDEA offers functionality to help improve our coding, within the IDE when writing code as Intentions. Intentions can be used in batch to inspect code for patterns throughout the source and even extending to Command-Line analysis or added to Continuous Integration. This section covers the out-of-the-box IntelliJ functionality and expanding with custom Intentions created in Sensei.

### IntelliJ Inspections

The Inspections feature of IntelliJ drives the display of many of the errors that are reported dynamically in the IDE when coding e.g.

*   Detecting abstract classes that can be converted to interfaces.
*   Identifying redundant class fields which can be local.
*   Warning about uses of deprecated methods.
*   etc.

These Inspections highlight code that matches in the IDE as Intention Actions which often have an associated QuickFix.

![](OEBPS/Image00008.jpg)

The real-time IDE highlighting when code matches an Inspection can help us improve our coding dynamically. After identifying the issue in the code, using IntelliJ Intention Actions to QuickFix the code can reinforce better patterns.

### Inspections Profile

Inspections can run as a batch from within the IDE and from the Command Line or in a Continuous Integration process.

The key to working with IntelliJ inspections in a batch is through the use of an Inspections Profile.

IntelliJ has two default Inspection Profiles: one stored in the Project, and one stored in the IDE.

New Inspection Profiles can be created to configure specific plugins or use-cases e.g.

*   Run Checkstyle real-time scan only
*   Run a specific set of Sensei rules
*   Run the HTML checks

The Inspections in a profile can be enabled or disabled from the IntelliJ Preferences. The Preferences dialog is also an easy way to learn the range of Inspections available.

![](OEBPS/Image00009.jpg)

The ‘tool’ icon allows you to duplicate a Profile and create a new Profile to collect a specific set of rules.

![](OEBPS/Image00010.jpg)

### Running an Inspection Profile in the IDE

Inspection Profiles can be run from within the IDE using the `Analyze \ Inspect Code...` menu.

![](OEBPS/Image00011.jpg)

The Analyze functionality allows you to control the scope that the Inspection will run against e.g. the whole project, including or excluding test sources, or against a specific set of files.

![](OEBPS/Image00012.jpg)

You can also manage the Inspection Profiles from here to create or configure a particular profile.

Clicking `[OK]` on the “Specify Inspection Scope” dialog will trigger IntelliJ into running all the selected Inspections in the profile across the defined scope.

IntelliJ will report the results of running the Inspections in the `Inspection Results` tab.

![](OEBPS/Image00013.jpg)

The [Sensei](https://scw.buzz/3qvDvDt) plugin from Secure Code Warrior allows you to create custom code matching recipes. Sensei tightly integrates with IntelliJ to make these custom recipes as natural to use as the IntelliJ Intention Actions. This means they are loaded into IntelliJ as Inspections and can be grouped, enabled, and disabled using Inspection Profiles. Creating a custom Inspection Profile and then using the Analyze Inspect Code functionality is the recommended way of running Sensei recipes in bulk across a project.

### Running an Inspection Profile from the Command Line

IntelliJ has the ability to run inspections from the command line as documented by JetBrains:

*   https://www.jetbrains.com/help/idea/working-with-the-ide-features-from-command-line.html

I primarily use Mac OS, and can run a single instance of IntelliJ from the command line with:

```
 open -na "IntelliJ IDEA CE.app"
```

To support easier execution I add this to a shell command script.

`vi /usr/local/bin/idea`

The contents of the script are from the official documentation provided by IntelliJ.

```
 #!/bin/sh

open -na "IntelliJ IDEA CE.app" --args "$@"
```

I then made this executable to allow me to simplify the command line inspection process.

`chmod 755 /usr/local/bin/idea`

The official intellij docs describe the general form of the inspection command as:

`idea inspect <project> <inspection-profile> <output> [<options>]`

In practice, I fully qualify the paths:

```
 idea inspect /Users/user/GitHub/sensei-blog-examples /Users/user/GitHub/sensei-blog-examples/.idea/inspectionProfiles/senseiprofile.xml /Users/user/GitHub/sensei-blog-examples/scan-results
```

Or use them relative to my user directory:

```
 idea inspect ~/Documents/GitHub/sensei-blog-examples ~/Documents/GitHub/sensei-blog-examples/.idea/inspectionProfiles/senseiprofile.xml scan-results
```

This runs all the Inspections I added to the `senseiprofile` and reports the results in the `scan-results` folder.

![](OEBPS/Image00014.jpg)

### Viewing Inspection Results

We can report these results from within Continuous Integration, as we’ll see later.

We can also view them within IntelliJ itself using the `Analyse \ View Offline Inspection Results…` feature.

![](OEBPS/Image00015.jpg)

This will load the results into the `Inspection Results` tab.

![](OEBPS/Image00016.jpg)

This is officially documented on the JetBrains site:

*   https://www.jetbrains.com/help/idea/command-line-code-inspector.html#inspection-results

This might be used during a code review process if the command line execution was incorporated into a Continuous Integration process and the reviewers wanted to check the full source context of any of the Inspection result entries.

### Inspection Profiles in Continuous Integration

When adding the Command Line inspection into Continuous Integration we ideally want a report to be generated automatically and there are a number of options open to us.

TeamCity offers out-of-the-box support for Inspection Profiles in Continuous Integration.

*   https://www.jetbrains.com/help/teamcity/inspections.html

The Jenkins Warnings NG plugin supports the Command Line output from IntelliJ Inspections as one of the report formats.

*   https://github.com/jenkinsci/warnings-ng-plugin
*   https://github.com/jenkinsci/warnings-ng-plugin/blob/master/SUPPORTED-FORMATS.md

Community projects like `idea CLI Inspector` exist to support using Inspection Profiles in other CI tooling i.e.

*   https://github.com/bentolor/idea-cli-inspector

The future of Inspection Profiles in a CI process looks even brighter with the introduction of the JetBrains Qodana project. The Qodana project is a headless version of IntelliJ with official Github Actions and Docker images.

*   https://github.com/JetBrains/Qodana

*Qodana is currently in beta, but the Sensei team is monitoring it so that it becomes an officially supported platform for running Sensei rules as part of Continuous Integration.*

### Summary

Intention Actions allow us to reinforce coding patterns and quickly fix them in the IDE when we make mistakes during coding.

Inspection Profiles allow us to collect these into profiles which can run in batch as an Analyze and Inspect Code action. This can be useful if we encounter a pattern and want to double-check if we have missed that anywhere else in our code.

Inspection Profiles can be run from the command line and even incorporated into Continuous Integration processes supporting a “trust, but verify” model and catch any accidental slippage.

All of the above is built in IntelliJ functionality and JetBrains are improving their Continuous Integration process with the introduction of Qodana.

Sensei recipes are loaded into IntelliJ to act as native Intention Actions and be collected into Inspection Profiles to support batch checking through Inspect Code and Continuous Integration support provided by the official JetBrains Command Line execution functionality.

### Watch On YouTube

We created a YouTube video showing all the steps and tools in this section.

[![](OEBPS/Image00017.jpg)](https://www.youtube.com/watch?v=Gk0ASNhKH2Q)

[youtu.be/Gk0ASNhKH2Q](https://youtu.be/Gk0ASNhKH2Q)

# Sensei GUI Overview

The Sensei IntelliJ plugin lets me create searches to match on code implementing a pattern I want to change, and then create Code amendment Quick Fixes to automatically change the code.

This section will walk through the main parts of the GUI and how we can use them.

## Sensei Menu

When Sensei has been installed, we will see the Sensei menu in the Tools menu.

![](OEBPS/Image00018.jpg)

## Cookbook Manager

From here we can show the Cookbook Manager tool which will list all the ‘cookbooks’, or lists of recipes, that I have available to me.

![](OEBPS/Image00019.jpg)

I can use this dialog to switch cookbooks on and off. And can use the `Sensei Cookbooks` tab on the bottom of the screen to navigate back here when I need to. I don’t have to use the main Sensei menu.

## Manage Recipes

Since this is the example project from Github, I have some Recipes stored in the project’s `.sensei` folder and these have been automatically loaded.

I can manage them to see what recipes are available to me by clicking the `[Manage recipes]` button.

## Cookbook Recipe Editor List

Each recipe has a configuration with the name and description and warning level which all configure how they are rendered in the IDE when code matches the pattern in the search.

![](OEBPS/Image00020.jpg)

By clicking on a Recipe, I can edit it.

## Recipe Editor

The Recipe Editor has four main components.

*   The list of recipes where we can add, delete, and duplicate recipes.
*   The General Settings tab where we can configure the recipe.
*   Recipe Settings tab where we create the search and matching conditions.
*   QuickFix settings where we configure the Quick Fix changes to amend or generate code.

![](OEBPS/Image00021.jpg)

## General Settings

General Settings is where we primarily configure the:

*   `Name` and `Description` are shown in the intentions Quick Fix popup when we use `alt+enter` .
*   `Level` defines how the matching Recipe is rendered in the IDE.

If I mark a recipe as ‘Error’, then the code will have a red underline and show as a syntax error, but a warning will have a light highlighting.

There are other settings but these are for more advanced use and will be covered in the documentation.

*   Documentation - [sensei-docs-beta.securecodewarrior.com](https://scw.buzz/3emSI7l)

![](OEBPS/Image00022.jpg)

## Recipe Settings - Search

The ‘Recipe Settings’ contains the search configuration.

This is the search we perform in the code to match coding patterns.

In this example, I am searching for any annotations on a method which are a Junit 5 Test annotation.

And you can see the annotations in the code have been highlighted in the code itself.

![](OEBPS/Image00023.jpg)

If I changed the annotation type then the code would not match, so we can visually see if our searches are valid or not for the code we are working with.

![](OEBPS/Image00024.jpg)

## QuickFix Settings

The QuickFix Settings are the Quick Fixes that are shown in IntelliJ when I use alt+enter to fix the problem.

And you can see at the bottom of the screen a diff view that shows the results of applying a QuickFix.

The recipe shown in the screenshot adds a `Logger` into the class and the diff view shows the before and after state in the code.

![](OEBPS/Image00025.jpg)

## Creating A Recipe

In the code, usually at the point you want to start a search.

Pressing `alt+enter` shows the context menu to create a recipe.

![](OEBPS/Image00026.jpg)

Often we ‘start from scratch’ with an empty recipe.

![](OEBPS/Image00027.jpg)

## Spotting Issues in the IDE

### In the Code

When recipes have been activated, they will be marked in the code.

The following code shows some ‘errors’ and some ‘warnings’.

![](OEBPS/Image00028.jpg)

I’ll save this now, then we can use it in the IDE.

### Problem Icons

Issues will also be shown with the Sensei problem icons in the top right corner.

![](OEBPS/Image00029.jpg)

I could right-click here to fix the problem via the Problems tab.

![](OEBPS/Image00030.jpg)

## Triggering a Quick Fix

There are many ways to trigger a QuickFix.

### Using Problems Tab

In the Problems Tab.

Right-click on the reported problem and choose “Show Quick Fixes”

![](OEBPS/Image00031.jpg)

Then choose the Quick Fix from the list.

![](OEBPS/Image00032.jpg)

### Contextual `alt+enter`

The most common way to fix code is with an `alt+enter` where we will see any Intellij suggestions and Sensei Quick Fixes.

![](OEBPS/Image00033.jpg)

And if I choose the action then the code will be amended.

### Fixing Multiple Actions

If there were multiple occurrences in the file then I could fix them all at once.

Pressing `alt+enter` and navigating to the next menu level down on the QuickFix, we find the option to fix all problems in the current source file.

![](OEBPS/Image00034.jpg)

# Section - Use-Cases

Sensei can help improve the writing of Quality Code, regardless of the underlying domain or technology.

This section is split into sub-sections categorised by technology to help demonstrate:

*   Some features of Sensei.
*   How those features can be applied.

The technology examples have been kept as small as possible to illustrate the interaction with the technology, but still keep the learning curve small. That way, even if you don’t know the technology you should still be able to follow along.

The descriptions here have full code examples in the Github repo:

*   [github.com/SecureCodeWarrior/sensei-blog-examples](https://scw.buzz/3cixLrq)

Links or descriptions of the specific code to look at will be contained in the use-case description.

# POJO Use-Cases

The use-cases which follow use plain old Java.

No external dependencies are required so they are a good introduction to the basic functionality of Sensei.

## Converting System.out.println to logger

When writing the code below I made a bunch of mistakes:

```
 private String getCountdownString() {

        String output = "";
        String prefix="";

        for(int countdown = 10; countdown > 0; countdown-- ){

            output = output + prefix + countdown;

            System.out.println(output);

            prefix=", ";
        }

        System.out.println(output);

        return output;
    }
```

Initially, I had `countdown++` and the loop didn’t finish.

And I used `countdown > 1` , so I didn’t get the output I wanted.

In the end, I littered my code with `System.out.println` to help me debug.

Then I realised, I really need to learn how to use a logger.

### Research

Fortunately, I read through the [Sensei documentation](https://scw.buzz/3emSI7l) and decided to use the “Getting Started” guide to help me create a recipe to convert from `System.out.println` and encourage me to use a logger:

*   `java.util.logging.Logger`

### Creating a Recipe

The first thing I do is click on the `println` then `alt+enter` to create a new recipe.

![](OEBPS/Image00035.jpg)

I create it with the following details:

```
 Name: Logger: use logger instead of println
Description: use logger instead of println - remember stop using System.out.println
Level: Error
```

And I’ll start by matching a `methodcall` with the name `println`

```
 search:
  methodcall:
    name: "println"
```

And the preview shows me all the matches in my code.

![](OEBPS/Image00036.jpg)

I can see that all the matches in my code are for `System.out.println` but I don’t trust that long term this will be the only match. I want to match a more qualified statement I want to change.

I expand the matcher to search for a `methodcall` on a `field` named `out` in the class `System` .

```
 search:
  methodcall:
    name: "println"
    "on":
      field:
        in:
          class:
            name: "System"
        name: "out"
```

I could, if I wanted, fully qualify the `System` name to `java.lang.System`

![](OEBPS/Image00037.jpg)

### Amending the Code to log

Next, I want to create the QuickFix.

First I want to amend the line of code that logs the output:

```
 availableFixes:
- name: "use Logger"
  actions:
  - rewrite:
      to: "logger.log(Level.INFO, {{{ arguments.0 }}})"
```

I don’t have to remember the mustache format. I used the `Show Variables` in the GUI to show me the argument and double-clicked on it. Then the GUI filled in the appropriate matching mustache template.

![](OEBPS/Image00038.jpg)

When I try it out, I can see that I still have to `alt+enter` to import the `Level` enum. But if I amend my QuickFix to have a fully qualified item then Sensei will add the import for me e.g.

*   It will replace `System.out.println(output);` with

```
 logger.log(Level.INFO, output);
```

*   And add an import for the enum:

```
 import java.util.logging.Level;
```

*   If I rewrite to:

```
 logger.log(java.util.logging.Level.INFO, {{{ arguments.0 }}})
```

And this will work, but I will still have to remember the syntax to instantiate the logger in the first place.

![](OEBPS/Image00039.jpg)

### Amending the code to add the logger field

I can amend my QuickFix to create the `logger` field for me as well.

I will code the `logger` first, and then add that to my recipe so I never have to code it again.

```
 Logger logger2 = Logger.getLogger(SysOutTest.class.getName());
```

I tend to write the code first because then I can use IntelliJ code completion and syntax checking to make sure I get it right. As a side-effect, it will then be in the code preview when I edit the recipe to add the QuickFix lines that will create that code.

And when I write the code, I want to use a different field name (here I’m using `logger2` ) because Sensei is clever enough not to add a duplicate field, so I have to fool it by using a different name.

So I’ll amend the recipe to create this code by adding a field called logger.

```
 availableFixes:
- name: "use Logger"
  actions:
  - rewrite:
      to: "logger.log(java.util.logging.Level.INFO, {{{ arguments.0 }}})"
  - addField:
      field: "java.util.logging.Logger logger = Logger.getLogger({{{ containingClass.name\
        \ }}}.class.getName())"
      target: "parentClass"
```

Note that I changed `SysOutTest` to be a mustache variable so that it picks up the name of any class I use this recipe in. And again, I didn’t remember the mustache syntax, I used the GUI `show variables` to find the replacement I needed.

And by fully qualifying the `Logger` to `java.util.logging.Logger` , Sensei will add the import and write the line of code that I want i.e.

```
 Logger logger = Logger.getLogger(SysOutTest.class.getName());
```

![](OEBPS/Image00040.jpg)

One useful thing about this recipe is that because it will only add the logger field once, I can use this on any existing code where I have used `System.out.println` and use Sensei to change all the occurrences in my code.

![](OEBPS/Image00041.jpg)

### Next Steps

Once I get used to this, I’ll eventually train myself away from using `System.out.println` .

And I can use Sensei to help me proactively write code by creating a second recipe which helps me create a logger.

e.g. I can match on a class, where there is no field called logger, and add one.

I created a recipe of level `Information`

```
 Name: Logger: add logger
Description: Add logger to class
Level: Information
```

To match on a class without a logger field:

```
 search:
  class:
    without:
      child:
        field:
          name: "logger"
```

And then I will reuse part of the QuickFix we saw earlier

```
 availableFixes:
  - name: "Add Logger"
    actions:
      - addField:
          field: "java.util.logging.Logger logger = Logger.getLogger({{{ containingClass.name\
        \ }}}.class.getName())"
          target: "self"
```

*Note the difference in `target` here compared to the first QuickFix. This uses `self` because our Search matched the class. The first QuickFix uses `parentClass` because we matched code within the class itself.*

### Summary

This represents one of the key flows associated with using Sensei to help improve your personal programming skillset:

*   Create a recipe to help with your immediate ‘best practice’.
*   Once you know how to use that best practice… create a recipe to make your workflow faster.

### Code Links

In the Github repo:

*   https://github.com/SecureCodeWarrior/sensei-blog-examples
*   module: `pojoexamples`
*   `src\test\java\logging`

`AddLoggerTest.java` has some instructions for applying the recipe.

`SysOutTest.java` is an example of a class that you can experiment with.

### See Sensei In Action

[![](OEBPS/Image00042.jpg)](https://www.youtube.com/watch?v=qPlNm0yaSto)

[youtu.be/qPlNm0yaSto](https://youtu.be/qPlNm0yaSto)

# Junit 5 Use-Cases

[JUnit 5](https://junit.org/junit5/) is a popular Unit Testing Framework for Java.

The use-cases which follow, all use JUnit 5 as their implementation, but the basic concepts can be applied to JUnit 4, or other unit testing frameworks, with minor amendments to the recipes.

## Adding Annotations and Method Renaming

*Improving A Personal Programming Process Using Sensei*

For this section, I’ve recreated a ‘bad’ coding approach that I used when I was learning JUnit, and will demonstrate how to convert the ‘bad’ pattern to an agreed, and “better”, coding pattern using Sensei.

When I was learning JUnit, I could only keep so much in my head at any one time. I constantly forgot how to skip tests when they were not working.

If we are working in a Team then we can use code reviews on pull requests to help enforce coding styles. And we can shorten the feedback cycle when pair programming with a more experienced programmer.

We can also augment our process with tooling and have the tools prompt us to do the right thing. Thoughtworks describe this as “tools over rules,” in their [Technology Radar listing for Sensei](https://www.thoughtworks.com/radar/tools/sensei) :

> “make it easy to do the right thing over applying checklist-like governance rules and procedures”

### Disabling a JUnit Test

Ideally, I would, as we all know, use the `@Disabled` annotation and write:

```
 @Disabled
    @Test
    void canWeAddTwoNumbers(){
        Assertions.fail("this test was skipped and should not run");
    }
```

But, when learning, I had to train myself to use `@Disabled` .

When I forgot how to disable a Test method I would remove the `@Test` annotation and rename the test:

```
 class SkipThisTest {

    void SKIPTHIScanWeAddTwoNumbers(){
        Assertions.fail("this test was skipped and should not run");
    }   
}
```

It wasn’t good, but it got the job done. I didn’t have something like Sensei to help me remember and so I fell into using poor coding patterns.

The tasks I’ve taken on board for this readme are to:

*   Create a rule which finds methods that have been ‘skipped’ or ‘disabled’ by renaming the method.
*   Create a QuickFix to rename the method and add both an @Test and @Disabled annotation.

### Recipe Settings

The first step I take with Sensei is to “add new recipe” and search for the coding pattern I want the recipe to act on.

```
 Name: JUnit: Make @Disabled @Test from SKIPTHIS
Short Description: Stop naming methods SKIPTHIS, use @Disabled @Test instead
```

And my search is very simple. I use a basic regex to match the method name.

```
 search:
  method:
    name:
      matches: "SKIPTHIS.*"
```

![](OEBPS/Image00043.jpg)

### QuickFix Settings

The QuickFix is a little more complicated because it will rewrite the code, and I’ll use a few steps to achieve my final code.

I want to:

*   Add an `@Test` annotation to the method.
*   Add an `@Disabled` annotation to the method.
*   Amend the method name.

Adding the annotations is simple enough using the `addAnnotation` fix. If I use a fully qualified name for the annotation then Sensei will automatically add the imports for me.

```
 availableFixes:
- name: "Add @Disabled and @Test Annotation"
  actions:
  - addAnnotation:
       annotation: "@org.junit.jupiter.api.Test"
  - addAnnotation:
      annotation: "@org.junit.jupiter.api.Disabled"
```

The actual renaming seems a little more complicated but I’m just using a regex replacement, and the generic way to do this with Sensei is to use `sed` in a rewrite action.

Because the rewrite actions a Mustache templates, Sensei has some functional extensions in the template mechanism. A function is represented with `{{#...}}` so for `sed` the function is `{{#sed}}` . The function takes two arguments which are comma-separated.

The first argument is the `sed` statement:

*   `s/(.*) SKIPTHIS(.*)/$1 $2/`

The second argument is the String to apply the `sed` statement to, which in this case is the method itself, and this is represented in the Mustache variables as:

*   `{{{.}}}`

```
 - rewrite:
       to: "{{#sed}}s/(.*) SKIPTHIS(.*)/$1 $2/,{{{.}}}{{/sed}}"
```

![](OEBPS/Image00044.jpg)

The `sed` implementation requires that when the arguments themselves contain commas, that they are wrapped with `{{#encodeString}}` and `{{/encodeString}}` - e.g. `{{#encodeString}}{{{.}}}{{/encodeString}}`

### Reverse Recipe

Since this is an example, and we might want to use this in demos, I wanted to explore how to reverse out the above change using a Sensei recipe.

Thinking it through I want to find a method annotated with `@Disabled` but only in the class `SkipThisTest` where I do the demo:

```
 Name: JUnit: demo in SkipThisTest remove @Disabled and revert to SKIPTHIS
Short Description: remove @Disabled and revert to SKIPTHIS for demo purposes in the project
Level: warning
```

The Recipe Settings Search is very simple, matching the annotation in a specific class.

```
 search:
  method:
    annotation:
      type: "Disabled"
    in:
      class:
        name: "SkipThisTest"
```

To avoid making the code look like it is an error I defined the general setting on the recipe to be a Warning. Warnings are shown with highlights in the code and it doesn’t make the code look like it has a major problem.

For the Quick fix, since we have matched the method, I use the rewrite action and populate the template using the variables.

```
 availableFixes:
- name: "Remove Disabled and rename to SKIPTHIS..."
  actions:
  - rewrite:
      to: "{{{ returnTypeElement }}} SKIPTHIS{{{ nameIdentifier }}}{{{ parameterList\
        \ }}}{{{ body }}}"
```

I basically add every variable except the modifier (since I want to get rid of the annotations) and add the `SKIPTHIS` text into the template.

This fix has the weakness that by removing the modifiers, I remove any other annotations as well.

### Add another Action

I can add another named fix, to give me a choice when the `alt+enter` is used to display the QuickFix.

```
 availableFixes:
- name: "Remove Disabled and rename to SKIPTHIS..."
  actions:
  - rewrite:
      to: "{{{ returnTypeElement }}} SKIPTHIS{{{ nameIdentifier }}}{{{ parameterList\
        \ }}}{{{ body }}}"
      target: "self"
- name: "Remove Disabled, keep other annotations, and rename to SKIPTHIS..."
  actions:
  - rewrite:
      to: "{{#sed}}s/(@Disabled\n.*@Test)//,{{{ modifierList }}}{{/sed}}\n\
        {{{ returnTypeElement }}} SKIPTHIS{{{ nameIdentifier }}}{{{ parameterList\
        \ }}}{{{ body }}}"
      target: "self"
```

Here, I added an additional line in the new Quick Fix.

```
 {{#sed}}s/(@Disabled\n.*@Test)//,{{{ modifierList }}}{{/sed}}
```

This takes the modifier list, encodes it as a string, then uses `sed` to remove the line with `@Disabled` from the string, but leaves all other lines in the modifier, i.e. it leaves all other annotations alone.

*NOTE: Remember to add the “,” in the `sed` , otherwise you will see a comment added to your preview because this is how Sensei alerts you to syntax errors in the `sed` command.*

### Nested `sed` calls

I was lucky that I could match both the `@Disabled` and `@Test` in a single search and replace.

In the event that the code is more complicated and I wanted to have a sequence of sed commands then I can do that by nesting them:

```
 {{#sed}}s/@Test//,{{#sed}}s/@Disabled\n//,{{{ modifierList }}}{{/sed}}{{/sed}}
```

In the above example, I apply the `@Test` replacement to the results of applying the `@Disabled` replacement on the `{{{ modifierList }}}` .

### Summary

`sed` is a very flexible way to achieve code rewriting and it is possible to nest the `sed` function calls for complicated rewrite conditions.

Recipes like this often end up being temporary because we are using them to improve our programming process, and once we have built up the muscle memory and no longer use the poor programming pattern we can remove or disable them in the Cookbook.

*NOTE: Rather than add two available fixes, I could clone the recipe, but if I do, then I have to remember to uncheck the “Add disable entry for cloned recipe” checkbox, otherwise only the cloned recipe will be available for use.*

## Adding Parameters to Annotations Using Rewrite Actions

In this example, we will:

*   Demonstrate searching and matching annotations.
*   Amend annotations using mustache templates.

Sensei provides the ability to match problematic code patterns and then amend them to agreed implementations. In this example, I am using `@Disabled` without a parameter as the problematic code pattern.

### See This In Action on YouTube

[![](OEBPS/Image00045.jpg)](https://www.youtube.com/watch?v=mjXGliXJ7M8)

[youtu.be/mjXGliXJ7M8](https://youtu.be/mjXGliXJ7M8)

### Disabled Test Annotation

Disabled tests without a specified reason can prove problematic over the long term because we forget why we disabled them.

```
 @Disabled
void thisTestMethodHasNoDisabledReason(){
    Assertions.fail("This test is disabled and should not run");
}
```

The risk is that, over time, the code base moves on, the disabled test is not updated in step with the purpose of the code and eventually becomes redundant and irrelevant, and potentially never re-enabled.

During code reviews, we will often point out that it is a good idea to add an explanatory description as the annotation parameter.

```
 @Disabled("Disabled to demonstrate adding a reason")
void thisTestMethodHasDisabledReason(){
    Assertions.fail("This test is disabled and should not run");
}
```

### A Sensei Recipe

We can write a recipe to detect when `@Disabled` is added without explanation and a Quick Fix that reminds us to add the actual reason explaining why we disabled it.

When I think about what I’m going to do, I have to:

*   Match the `Disabled` annotation without any parameters.
*   Change the `Disabled` annotation to have a parameter with marker text “TODO: add a description here”.

### Create a Warning Recipe

I use `Alt+Enter` to Create a new Recipe.

![](OEBPS/Image00046.jpg)

Then add the basic descriptive text in the general information.

![](OEBPS/Image00047.gif)

General:

```
 name: remember to add disabled description
short description: @Disabled should really have a description explaining why
Level: Warning
```

By making the rule a warning, any matching code is highlighted but not shown as a glaring error.

![](OEBPS/Image00048.jpg)

### Find the Annotation

In the recipe editor, I change the Search to match an annotation.

This will highlight all annotations in the preview.

![](OEBPS/Image00049.jpg)

Having done that, I want to filter on the `type` . I could just use `Disabled` but I fully qualify the class with the package so that it only matches the annotation from JUnit 5\. Because the preview is displayed, I can easily copy and paste this from the code.

I then want to match only annotations without Parameters, and I can use the GUI to do that.

![](OEBPS/Image00050.jpg)

i.e. Search:

```
 search:
  annotation:
    type: "org.junit.jupiter.api.Disabled"
    without:
      parameters:
      - {}
```

### Create a Rewrite Quick Fix Action

For my QuickFix I will use a rewrite action.

I use the `Show Variables` functionality to show me the Mustache variables and preview the contents.

![](OEBPS/Image00051.jpg)

And then I add the extra code needed to create the place marker comment.

![](OEBPS/Image00052.jpg)

i.e. QuickFix:

```
 availableFixes:
- name: "Add a todo comment parameter"
  actions:
  - rewrite:
      to: "{{{ . }}}(\"TODO: add a description here\")"
      target: "self"
```

### Summary

When building a rewrite Quick Fix, it is easier when we can search for the code element that we want to rewrite, because it is then the `self` entity we can act on.

In this example, I used a rewrite action to amend the Annotation. Rewrite is a general-purpose action that can apply to any code element and is a good default to explore.

## Documentation Links

One of the difficulties with learning a new library, or sharing agreed upon practices across our team is documenting and creating examples.

Very often we create small example projects, but we don’t have them open when working with actual code.

I’ve often thought it would be great to have the ability to link to our examples or online examples and be able to go to a URL for more explanation when needed.

With Java, we have JavaDoc comments, which can have a `see` annotation:

```
 /**
 * @see <a href="https://junit.org/junit5/docs/current/user-guide/#writing-tests-annotations">Junit 5 Annotation docs</a>
 */
```

JavaDoc like this in 3rd party libraries is a great help because we can use the `Quick Documentation` functionality in IntelliJ to have access to more detailed examples.

![](OEBPS/Image00053.jpg)

But, we all know that comments don’t get updated as often as code, and web presence maintenance is often disconnected from library maintenance and sometimes performed by a different team entirely.

### How Sensei Helps

Sensei provides the ability to match on library annotations and methods to provide links to long-form documentation on a wiki or third-party tutorial site.

As an example, I’m using the `@Test` annotation from JUnit.

The JavaDoc is very detailed, and the `Quick Documentation` view explains how to use the annotation.

But the official documentation on the website is often easier to read and has more examples.

When a team starts learning a library, having a set of recommended tutorials can be very useful.

Sensei has a `goto` action that can open a URL, allowing us to link to external sites and examples for documentation that we, as a team, find useful.

### Implementing the `goto` URL

To implement this I would create a search that matches the `@Test` annotation from Junit.

```
 search:
  annotation:
    owner:
      method: {}
    type: "org.junit.jupiter.api.Test"
```

And then I would add `goto` actions for each of the URLs I find useful.

e.g.

*   https://junit.org/junit5/docs/current/user-guide/#writing-tests-annotations
*   https://junit.org/junit5/docs/current/user-guide/#writing-tests-classes-and-methods

The example below would create a single Action `JUnit Annotations (learn)` which would open both URLs in a browser at the same time.

```
 availableFixes:
- name: "Learn about JUnit Annotations"
  actions:
  - goto:
      type: "URL"
      value: "https://junit.org/junit5/docs/current/user-guide/#writing-tests-annotations"
  - goto:
      type: "URL"
      value: "https://junit.org/junit5/docs/current/user-guide/#writing-tests-classes-and-methods"
```

When I activate it in IntelliJ with `alt+Enter` I see the context menu which I can select to jump to the documentation.

![](OEBPS/Image00054.jpg)

### Multiple Actions

I might choose to have multiple Actions so that each URL or tutorial has its own option in the `alt+enter` QuickFix pop-up menu.

For example, for the `@Parameterized` annotation, I might want to link to the official documentation and a set of online example code.

*   https://junit.org/junit5/docs/current/user-guide/#writing-tests-parameterized-tests
*   https://github.com/eviltester/junitexamples/blob/master/src/test/java/parameterized/junit5/InitialExampleTest.java

I would simply create a recipe that searches for the annotation:

```
 search:
  annotation:
    owner:
      method: {}
    type: "org.junit.jupiter.params.ParameterizedTest"
```

And links off to the sites I identified as being useful:

```
 availableFixes:
- name: "JUnit Annotations (learn)"
  actions:
  - goto:
      type: "URL"
      value: "https://junit.org/junit5/docs/current/user-guide/#writing-tests-annotations"
- name: "What is a JUnit Test? (learn)"
  actions:
  - goto:
      type: "URL"
      value: "https://junit.org/junit5/docs/current/user-guide/#writing-tests-classes-and-methods"
```

Both links would then appear in the pop-up dialog.

![](OEBPS/Image00055.jpg)

### Who would benefit?

I would have found this useful when using and learning libraries, especially when leading teams and helping them adopt a new library.

This could also benefit teams creating libraries by creating a standard set of documentation recipes to help guide people through the adoption of the library or new features in the library.

This would be especially useful if the code maintenance and documentation maintenance are performed by different teams.

# Guice Use-cases

Every new technology adds risk to a project. Dependency Injection can save time when coding and adds additional flexibility around configuration, but there is always the risk that we forget to wire something up, or inject the wrong thing.

The use-case in this section explores ways in which Sensei can help.

## How to catch and fix a dependency injection issue using Sensei

The Sensei project itself has its own set of recipes that have built up over time, this is an example of one of the scenarios the Sensei team built a recipe to cover. A misconfiguration of Guice, which led to a `NullPointerException` being reported at runtime during our testing.

This could be generalised to many Dependency Injection scenarios where code is syntactically correct, but because the wiring configuration was incorrect, an error slips through.

This often happens when we are learning the technology, and we keep making the simple mistake of forgetting to wire things up. But this also happens to experienced professionals because, well… we all make mistakes, and we may not have Unit Tests to cover everything.

### RunTime Exceptions from Incorrect Dependency Injection Wiring

The code below fails at runtime with a `NullPointerException` .

```
 Injector injector = Guice.createInjector(new SystemOutModule());
CountReporter reporter = injector.getInstance(CountReporter.class);

String [] lines5 = {"1: line", "2: line", "3: line", "4: line", "5: line"};

reporter.reportThisMany(Arrays.asList(lines5));
Assertions.assertEquals(5, reporter.getCount());
```

The code is syntactically correct but fails because we missed out a `requestStaticInjection` in our `SystemOutModule` configuration.

```
 public class SystemOutModule extends AbstractModule {

    @Override
    protected void configure() {
        binder().bind(ILineReporter.class).to(SystemOutReporter.class);
    }
}
```

When we try to use the `reporter` , created using the `Injector` , it is not fully instantiated and we receive a `NullPointerException` when we call `reportThisMany` .

We may well have missed that in our code review or we didn’t have unit tests that triggered the dependency injection, and it slipped out into our build.

### Warning Signs

In this case there is a warning sign, the `CountReporter` has a static field annotated with `@Inject` but… the `CountReporter` class itself is `package private` . In a complicated code base this could be a warning sign that it isn’t used because the Module class configuring the bindings needs to be in the same package for this to work.

```
 class CountReporter {

    @Inject
    private static ILineReporter reporter;
```

Another error that we made, which we might have picked up in a code review, is that we forgot to actually bind the fields in the `SystemOutModule` `configure` method.

```
 binder().requestStaticInjection(CountReporter.class);
```

Had we written the `requestStaticInjection` code then the Syntax Error generated when trying to use the `CountReporter` would have alerted us to the simple error.

```
 > 'reporters.CountReporter' is not public in 'reporters'.
  Cannot be accessed from outside package
```

Sadly we forgot, and there were no syntactic warning signs in the code.

### How could Sensei help?

We probably wouldn’t use Sensei to pick up the missing `requestStaticInjection` , since all our Guice configuration wiring would need to use that method and we can’t guarantee that all wiring is going to be as simple as this use-case.

We could write a Sensei rule to look for some warning signs that our code is not up to scratch.

In this case that would mean:

*   Find any classes with `@Inject` annotated fields
*   Where the classes are not public.

The above was the warning sign that they were unlikely to have been wired up.

By creating a recipe, we get an early warning sign during the coding and can therefore reduce the reliance on our pull requests or resolving our tech debt to allow us to add Unit Tests.

### How to create a recipe?

The task I want to complete is:

*   Create a recipe that matches fields annotated with `@Inject` which are in `protected private` classes

That should hopefully give us enough warning to identify any Modules using it and add the missing wiring code.

In my `CountReporter` class, I will use `Alt+Enter` to `Create a new Recipe` and I will `start from scratch`

I will name this and add a description:

```
 Name: Guice: Injected Field Not Public
Description: If the Injected field is not public then the code might not be wired up
Level: Warning
```

The search I write looks for a field with the `Inject` annotation which has not been scoped as `public` .

```
 search:
  field:
    with:
      annotation:
        type: "com.google.inject.Inject"
    in:
      class:
        without:
          modifier: "public"
```

![](OEBPS/Image00056.jpg)

### Fix

The QuickFix in the recipe will amend the injected class, but that is not the only code I have to change.

```
 availableFixes:
- name: "Change class to public. Remember to also request injection on this class"
  actions:
  - changeModifiers:
      visibility: "public"
      target: "parentClass"
```

When the recipe is triggered I still have a manual step to perform in my code, adding the line containing `requestStaticInjection` to fully instantiate the object.

```
 public class SystemOutModule extends AbstractModule {

    @Override
    protected void configure() {
        binder().bind(ILineReporter.class).to(SystemOutReporter.class);
        // instantiate via dependency injection
        binder().requestStaticInjection(CountReporter.class);
    }
}
```

I could potentially write another recipe to pick this up. I probably wouldn’t do that unless forgetting to add the static injection became a semi-regular error that I made when coding.

### Summary

If we ever find ourselves making a mistake with a common root pattern, then Sensei can help codify the knowledge around detecting and fixing the issue. It will then, hopefully, not slip through code reviews and into production.

Sometimes the recipes we write identify heuristic patterns i.e. matching them doesn’t guarantee that there is a problem, but is likely that there is a problem.

The recipes and Quick Fixes that we write,don’t have to be fully comprehensive, but they need to be good enough that they help us identify and fix problems without being overly complicated. When they become overly complicated, they become harder to understand and harder to maintain.

# Next Steps

*   Install Sensei
*   Study Some Examples
*   Read the Documentation
*   Experiment

## Install Sensei

If you haven’t already then, install Sensei. You can do this from the Jetbrains marketplace, either from in the IDE, or at jetbrains.marketplace.com

*To install within the IDE, use “Preferences  Plugins” (Mac) “Settings  Plugins” (Windows) and search for “sensei secure code”, then Install.*

*   [Sensei plugin on marketplace](https://scw.buzz/38n5uPu)
    *   [plugins.jetbrains.com/plugin/14015-sensei-by-secure-code-warrior-](https://scw.buzz/38n5uPu)

For support in installing IntelliJ plugins, consider reading the Jetbrains support documentation:

*   [jetbrains.com/help/idea/managing-plugins.html](https://www.jetbrains.com/help/idea/managing-plugins.html)

## Study Some Examples

Earlier in the text, we mentioned two main Github Repositories.

The [Sensei Blog Examples](https://scw.buzz/3cixLrq) contains sample code, recipes that apply to that code, and readme.md files explaining the use-case.

The [Public Cookbooks](https://scw.buzz/30pk1FN) index lists publicly accessible cookbooks with sample recipes and documentation.

*   [github.com/SecureCodeWarrior/sensei-blog-examples](https://scw.buzz/3cixLrq)
*   [github.com/SecureCodeWarrior/public-cookbooks](https://scw.buzz/30pk1FN)

Both of these repositories contain a lot of recipes to study to understand how Sensei works.

## Read the Documentation

The [Official Documentation](https://scw.buzz/3emSI7l) includes a reference guide to all the Sensei features and functions. Additionally, it contains a walkthrough getting started tutorial to help you create your own recipe from scratch.

*   [https://sensei-docs-beta.securecodewarrior.com/](https://scw.buzz/3emSI7l)

## Experiment

Sensei adds the most value when you create recipes that help you improve your own process or codify knowledge from your team.

A few things you might want to try:

*   Replicate some of the rules that Static Analysis tools warn you about, but create a QuickFix for the most used code changes you apply.
*   Create some helper code to generate boilerplate code for some of the libraries that you often use.
*   Make notes about the type of errors you make as you code. Create a recipe with a fix to help you avoid the problem next time.

## Summary

The [Public Cookbooks](https://scw.buzz/30pk1FN) index lists recipes that you can immediately use. The maximum value from Sensei comes, however, when you create recipes that help you write better quality code to your own standards for the technology you work with.

Codify your knowledge in Sensei and share it with your team, or with the world, by contributing your cookbooks to the [Public Cookbooks](https://scw.buzz/30pk1FN) index.

Be sure to visit us to find out what else is new in Sensei at:

*   [securecodewarrior.com/sensei](https://scw.buzz/3qvDvDt)

# About Secure Code Warrior

Secure Code Warrior is a global security company that makes software development better and more secure. Our vision is to empower developers to be the first line of defense in their organization by making security highly visible and providing them with the skills and tools to write secure code from the beginning. Our powerful platform moves the focus from reaction to prevention, training and equipping developers to think and act with a security mindset as they build and verify their skills, gain real-time advice and monitor skill development. Our customers include financial institutions, telecommunications providers and global technology companies in Europe, North America and Asia Pacific.

[SecureCodeWarrior.com](https://scw.buzz/2PBhLJp)

# About the Author

Alan Richardson is Head of Developer Relations at Secure Code Warrior. Alan has over twenty years of professional software development experience and author of the books “Automating and Testing a REST API”, and “Java For Testers”.

For more information about Alan visit [EvilTester.com](https://eviltester.com)