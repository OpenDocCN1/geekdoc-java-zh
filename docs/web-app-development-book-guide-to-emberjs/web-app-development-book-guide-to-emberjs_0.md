
# Web 应用开发指南：Ember.js 指南

## 免责声明

尽管已尽力核实书中提供的信息，但作者对书中包含的错误、遗漏或对主题内容的相反阐释不承担任何责任。书中提供的信息仅供教育和娱乐之用。读者对其自己的行为负责，作者对使用这些信息而导致的任何实际或感知的责任或损害不承担任何责任。书中使用的商标均未经任何许可，且该商标的发布未获得商标所有者的许可或支持。书中的所有商标和品牌仅用于说明目的，归其所有者所有，与本文档无关。

## 引言

对 Web 应用的需求日益增长。`Ember JS` 是一种可以辅助开发此类应用的 JavaScript。该框架易于学习，特别是对于 JavaScript 专家而言。然而，即使你完全不熟悉 JavaScript，也不必担心，因为书中的解释对你来说非常容易理解。通过这种 JavaScript，你可以创建具有高度交互用户界面的 Web 应用，你的用户一定会喜欢你的应用。

## 第 1 章 控制器

控制器（Controllers）非常类似于组件（components），人们认为未来它们将被组件取代。在大多数当前的应用中，控制器并不经常使用。当使用它们时，它们承担以下职责：

1. 用于根据当前正在使用的路由维护状态。
2. 当用户操作从组件传递到路由时，它们必须经过控制器。

我们需要通过使用路由来演示这一点，路由将帮助我们显示博客文章。模板将绑定到模板中的以下属性：

```html
<h1>{{model.title}}</h1>
<h2>by {{model.author}}</h2>
<div class="intro">
  {{model.intro}}
</div>
<hr>
<div class="body">
  {{model.body}}
</div>
```

如上例所示，我们没有特定的属性或需要显示的操作（actions）。假设我们需要添加一个功能，允许用户在正文部分的显示之间进行切换。为了实现这一点，我们将代码修改为：

```html
<h1>{{model.title}}</h1>
<h2>by {{model.author}}</h2>
<div class='intro'>
  {{model.intro}}
</div>
<hr>
{{#if isExpanded}}
  <button {{action "toggleBody"}}>Hide the Body</button>
  <div class="body">
    {{model.body}}
  </div>
{{else}}
  <button {{action "toggleBody"}}>Show the Body</button>
{{/if}}
```

在控制器的 `actions` 钩子中，我们可以定义操作将做什么，就像我们在组件中做的那样。如下面的代码所示：

```javascript
export default Ember.Controller.extend({
  actions: {
    toggleBody() {
      this.toggleProperty('isExpanded');
    }
  }
});
```

### 控制器之间的依赖关系管理

有时，当我们嵌套资源时，我们通常需要在两个控制器之间建立连接。考虑下面的路由：

```javascript
Router.map(function() {
  this.route('post', { path: '/p/:post_id' }, function() {
    this.route('comments', { path: '/comments' });
  });
});
```

在访问 URL `/posts/1/comments` 时，模型 `post` 将加载到 `PostController` 的模型中。然而，与其相关的某些信息可能会显示在 `comments` 的模板中。为了实现这一点，我们必须将 `pController` 注入到我们的 `CommentsController` 中。如下所示：

```javascript
export default Ember.Controller.extend({
  pController: Ember.inject.controller('post')
});
```

我们的注释将能够访问 `PController`，这是一个只读别名，可以用于从控制器读取模型。考虑下面的代码：

```javascript
export default Ember.Controller.extend({
  pController: Ember.inject.controller('post'),
  post: Ember.computed.reads('pController.model')
});
```

考虑用于 `.hbs` 文件的下一个：

```html
<h1>Comments for the {{post.title}}</h1>
<ul>
  {{#each model as |comment|}}
    <li>{{comment.text}}</li>
  {{/each}}
</ul>
```

## 第 2 章 模型

构建 Web 应用的方法之一是实现与数据获取高度耦合的用户界面组件。考虑一种你正在创建一个博客应用的情况。如果你正在创建应用的管理部分，你可能被迫赋予组件负责获取和存储数据的责任。考虑下面的代码：

```html
<h1>Comments for {{post.title}}</h1>
<ul>
  {{#each model as |comment|}}
    <li>{{comment.text}}</li>
  {{/each}}
</ul>
```

模板中包含的草稿列表可以显示。下面的代码演示了这一点：

```html
<ul>
  {{#each drafts key="id" as |draft|}}
    <li>{{draft.title}}</li>
  {{/each}}
</ul>
```

注意，应用是由许多组件组成的。你可能希望将所有的显示在另一个页面。这可能将旧代码拷贝到新组件：

```javascript
export default Ember.Component.extend({
  willRender() {
    $.getJSON('/myDrafts').then(data => {
      this.set('drafts', data);
    });
  }
});
```

按钮的 `.hbs` 文件如下：

```html
{{#link-to 'drafts' tagName="button"}}
Drafts ({{drafts.length}})
{{/link-to}}
```

通过上述方法，我们的应用将发出两次请求，但针对相同的信息。在 Ember 数据中，模型的表示是使用子类完成的。通过模型，可以定义服务器将提供我们的数据类型。考虑名为 `human` 的模型示例：

```javascript
export default DS.Model.extend({
  fName: DS.attr('string'),
  birthday: DS.attr('date')
});
```

模型还可以描述它自己与其他模型之间的关系。考虑下面的示例，展示了如何这样做：

```javascript
export default DS.Model.extend({
  lItems: DS.hasMany('line-item')
});
```

上面的代码用于 `order`。`line.js` 的代码如下：

```javascript
export default DS.Model.extend({
  order: DS.belongsTo('order')
});
```

你必须注意，模型本身没有数据，但它们用于定义属性、关系以及被称为 `records` 的特定实例的行为。

### 创建记录

当你需要创建记录时，只需在 store 上调用 `createRecord()` 方法。考虑下面的代码：

```javascript
store.createRecord('post', {
  title: 'Ember is a Great Framework',
  body: 'Lorem ipsum'
});
```

存储的对象将通过 `this.store` 使控制器和路由器可用。

### 更新记录

你可以通过设置需要更改的属性来更改 Ember JS 数据记录。如下面所示：

```javascript
this.store.findRecord('human', 1).then(function(myfunction) {
  // ...一旦记录被加载
});
```

```javascript
myfunction.set('fName', "John");

});
```

所有 Ember.js 的便利方法始终可以用于修改属性。可以通过如下所示的方法：

```javascript
human.incrementProperty('age'); // Happy birthday!
```

### 持久化记录

在 Ember JS 中，记录是基于实例进行持久化的。当你对 `DS.Model` 的任何实例调用 `save()` 方法时，将发出一个网络请求。

默认情况下，EmberJS 中新创建的记录会被 POST 到 Ember data 中对应的类型 URL。代码示所示：

```javascript
var p = store.createRecord('post', {
  title: 'Ember is Great',
  body: 'Lorem ipsum'
});
p.save(); // => POST to '/posts'
```

后端已存在的记录将通过 HTTP `PATCH` 动词进行更新。代码如下：

```javascript
store.findRecord('post', 1).then(function(p) {
  p.get('title'); // => "Ember JS is Great"
  p.set('title', 'New post');
  p.save(); // => PATCH to '/posts/1'
});
```

考虑以下代码：

```javascript
human.get('isAdmin');            //=> false
human.get('hasDirtyAttributes'); //=> false
human.set('isAdmin', true);
human.get('hasDirtyAttributes'); //=> true
human.changedAttributes();      //=> { isAdmin: [false, true] }
```

人们可以通过检查记录属性 `hasDirtyAttributes` 来判断待处理记录是否有某些尚未保存的更改。

在上述节点，你可以通过调用 `save()` 方法来保存更改，或者直接将它们回滚。考虑以下代码：

```javascript
human.get('hasDirtyAttributes'); //=> true
human.changedAttributes();      //=> { isAdmin: [false, true] }
human.rollbackAttributes();
human.get('hasDirtyAttributes'); //=> false
human.get('isAdmin');            //=> false
human.changedAttributes();      //=> {}
```

### 处理验证错误

如果在尝试保存时后端服务器返回了验证错误，你的模型的 `errors` 属性将包含这些错误。错误可以如下所示显示：

```handlebars
{{#each p.errors.title as |err|}}
  <div class="error">{{err.message}}</</div>
{{/each}}
{{#each p.errors.body as |err|}}
  <div class="error">{{err.message}}</</div>
{{/each}}
```

### Promises

`save()` 方法将返回一个 promise，这将使我们能够轻松处理成功或失败的情况。考虑下面所示常见模式：

```javascript
var p = store.createRecord('post', {
  title: 'Ember is Great',
  body: 'Lorem ipsum'
});
var self = this;

function transitionToPost(p) {
  self.transitionToRoute('posts.show', p);
}

function failure(reason) {
  // 处理错误
}

p.save().then(transitionToPost).catch(failure);
// => POST to '/posts'
// => transitioning to posts.show route
```

### 删除记录

记录的删除可以采用创建记录的方式。可以在 `DS.Model` 实例上调用 `deleteRecord()` 方法。这会将记录标记为 `isDeleted`。随后应该调用 `save()` 方法来保存记录的删除操作。考虑以下代码：

```javascript
store.findRecord('post', 1).then(function(p) {
  p.deleteRecord();
  p.get('isDeleted'); // => true
  p.save(); // => DELETE to /posts/1
});

// 或者
store.findRecord('post', 2).then(function(post) {
  p.destroyRecord(); // => DELETE to /posts/2
});
```

### 关系

Ember 具有几种内置关系，定义了模型之间的相互关系。

### 一对一

如果你需要在两个模型之间声明这种关系，请使用下面的代码。这里是文件 `myuser.js` 的代码：

```javascript
export default DS.Model.extend({
  profile: DS.belongsTo('profile')
});
```

那么 `profile.js` 文件应该如下：

```javascript
export default DS.Model.extend({
  user: DS.belongsTo('myuser')
});
```

### 一对多关系

这种关系可以在两个模型之间如下声明：考虑以下文件 `myposts.js` 的代码：

```javascript
export default DS.Model.extend({
  comments: DS.hasMany('comment')
});
```

这里应该是文件 `ourcomments.js` 的代码：

```javascript
export default DS.Model.extend({
  post: DS.belongsTo('p')
});
```

### 显式反向

Ember JS 会尽力发现组件之间存在的关系类型。有时，你可能对同类型有多种不同的关系。考虑以下代码：

```javascript
export default DS.Model.extend({
  firstPost: DS.belongsTo('post'),
  secondPost: DS.belongsTo('mypost')
});
```

这里是文件 `mypost.js` 的代码：

```javascript
export default DS.Model.extend({
  comments: DS.hasMany('comment')
});
```

### 反映关系

为了定义反向关系，你应该已经有了反向。下面的示例展示了一对一反向关系：

```javascript
export default DS.Model.extend({
  parent: DS.belongsTo('folder', { 'children' })
});
```

### 创建记录

假设我们有两个模型，`myposts` 和 `comments`。它们的关系如下：

```javascript
export default DS.Model.extend({
  comments: DS.hasMany('comment')
});
```

文件 `comment.js` 如下：

```javascript
export default DS.Model.extend({
  post: DS.belongsTo('post')
});
```

### 更新现有记录

有时，我们可能需要为现有记录设置关系。这可以通过使用 `belongsTo` 关系简单实现。代码如下：

```javascript
let p = this.store.peekRecord('post', 1);
let comm = this.store.peekRecord('comment', 1);
comm.set('post', p);
comm.save();
```

或者，可以将记录推入 `hasMany` 关系以进行更新。如下所示：

```javascript
let p = this.store.peekRecord('post', 1);
let comm = this.store.peekRecord('comment', 1);
p.get('comments').pushObject(comm);
p.save();
```



要移除一个 `belongsTo` 关系，只需将其设置为 `null`。这将将其从 `hasMany` 关系的一侧移除。考虑下方的代码，它很好地演示了这一点：

```javascript
let comm = this.store.peekRecord('comment', 1);
comm.set('post', null);
comm.save();
```

记录也可以从 `hasMany` 关系中移除。考虑下面的代码，它很好地展示了如何实现：

```javascript
let p = this.store.peekRecord('post', 1);
let comm = this.store.peekRecord('comment', 1);
p.get('comments').removeObject(comm);
p.save();
```

### 关系即承诺（Promises）

每当你处理关系时，最好始终记住这些关系将返回承诺（promises）。假设我们要处理一个文章的异步评论，我们应该等待承诺已完成。考虑下面的代码：

```javascript
let p = this.store.peekRecord('post', 1);
p.get('comments').then((comments) => {
  // 我们现在可以处理这些评论了
});
```

同样的规则也适用于 `hasMany` 关系，如下：

```javascript
let comm = this.store.peekRecord('comment', 1);
comm.get('post').then((p) => {
  // 文章在这里是可用的
});
```

Handlebars 模板会自动更新，以反映已解析的承诺。如下所示，文章中可以显示评论列表：

```html
<ul>
  {{#each p.comments as |comm|}}
    <li>{{comm.id}}</li>
  {{/each}}
</ul>
```

### 将记录推入存储器（Pushing Records into Store）

存储器（store）可以被看作是一个缓存，包含了应用加载的所有记录。

若要将记录推入存储器，你只需要调用 `push()` 方法。考虑一种情况：在应用首次启动后，我们需要向存储器中预加载一些数据。这可以使用 `route:application` 轻松完成。考虑下面的代码：

```javascript
export default DS.Model.extend({
  title: DS.attr(),
  artist: DS.attr(),
  songCount: DS.attr()
});
```

考虑接这段代码：

```javascript
export default Ember.Route.extend({
  model() {
    this.store.push({
      data: [{
        id: 1,
        type: 'album',
        attributes: {
          title: 'Very Few Moving Parts',
          artist: 'John Joel',
          songCount: 5
        },
        relationships: {}
      }, {
        id: 2,
        type: 'album',
        attributes: {
          title: 'Our God is Great all the time',
          artist: 'Steve John',
          songCount: 3
        },
        relationships: {}
      }]
    });
  }
});
```

如果数据在推入存储器之前需要通过模型的默认序列化器（serializer）进行归一化处理，可以使用 `story.pushPayload()` 方法。下方的代码所示：

```javascript
export default DS.RestSerializer.extend({
  normalize(typeHash, hash) {
    hash['songCount'] = hash['song_count']
    delete hash['song_count']
    return this._super(typeHash, hash);
  }
})
```

接下来的代码应该如下所示：

```javascript
export default Ember.Route.extend({
  model() {
    this.store.pushPayload({
      albums: [
        {
          id: 1,
          title: 'Very Fever Moving Parts',
          artist: 'John Joel',
          song_count: 5
        },
        {
          id: 2,
          title: 'Our God is Great all the time',
          artist: 'Steve John',
          song_count: 2
        }
      ]
    });
  }
});
```

在处理复杂的端点（endpoints）时，`push()` 方法非常重要。你的应用程序可能有一个端点负责执行某些逻辑并创建多个记录。下面的代码演示了这一点：

```javascript
export default Ember.Route.extend({
  actions: {
    confirm: function(d) {
      $.ajax({
        data: d,
        method: 'POST',
        url: 'process-payment'
      }).then((digInventory) => {
        this.store.pushPayload(digInventory);
        this.transitionTo('Thanks');
      });
    }
  }
});
```

### 处理元数据（Handling Metadata）

除了从存储器返回的记录，还需要处理某些形式的元数据（metadata）。元数据只是伴随特定模型或类型而非记录的数据。

分页是元数据使用的一种常用方式。考虑一个包含许多文章的博客，它们无法一次性显示。可以如下所示进行查询：

```javascript
let res = this.store.query('post', {
  limit: 10,
  offset: 0
});
```

为了获取不同页的数据，可以以 10 为增量更改 `offset`。问题在于知道你有多少页数据。为了获取不同页的数据，`offset` 可以以 10 为增量设置。对于服务器来说，它需要返回总记录数作为元数据的一部分。每个序列化器期望元数据的返回方式不同。考虑下面的代码：

```json
{
  "post": {
    "id": 1,
    "title": "Ember is easy to learn for beginners",
    "comments": ["1", "2"],
    "links": {
      "user": "/posts/ember"
    }
  },
  "meta": {
    "total": 100
  }
}
```

无论使用哪种序列化器，元数据都会从响应中提取。要读取它，可以使用 `.get('meta')`。这可以应用于 `store.query()` 调用的结果。代码如下：

```javascript
store.query('post').then((res) => {
  let metad = res.get('meta');
})
```

如果我们有一个 `belongsTo` 关系，可以如下所示操作：

```javascript
let p = this.store.peekRecord('post', 1);
p.get('author').then((author) => {
  let metad = author.get('meta');
});
```

在 `hasMany` 关系上，可以如下所示操作：

```javascript
let p = this.store.peekRecord('post', 1);
p.get('comments').then((comments) => {
  let metad = comments.get('meta');
});
```

### 适配器的自定义（Customizations of Adapters）

在 Ember Data 中，适配器（Adapter）负责确定数据如何持久化到存储器，例如 RESTful API 的 URL 格式和头部。

对于具有某些规则的端点，可以定义 `adapter:application`。这将优默认适配器，但会被特定模型的适配器覆盖。如下方的所示：

```javascript
export default DS.JSONAPIAdapter.extend({
  // 在此处应用特定的配置
});
```

默认情况下，Ember Data 带有多个内置适配器。如果你需要创建自己的自定义适配器，请以这些为起点。

一个好的例子是，当你运行命令 `ember generate adapter adapter-name` 时，将创建如下文件：

```javascript
export default DS.JSONAPIAdapter.extend({
  namespace: 'api/v1'
});
```

#### URL 约定（URL Conventions）

`JSONAPIAdapter` 适配器在根据模型类型确定通信时使用的 URL 时非常好。考虑下面这个通过 ID 请求文章的示例：

```javascript
store.find('post', 1).then(function(p) {
});
```

#### 复数自定义（Pluralization Customization）

有时，在生成路由 URL 时，你可能需要辅助模型名称的复数处理。可以使用 Ember 反射器来实现此目的。这是一个用于在单数和复数之间转换单词的库。对于不可数或不规则的复数，可以使用 `Ember.Inflector.inflector()`。如下所示轻松完成：

```javascript
// 设置 Ember.Inflector
import './models/custom-inflector-rules';
```

接下来的代码如下：

```javascript
import Inflector from 'ember-inflector';

const inflect = Inflector.inflector;

inflect.irregular('formula', 'formulae');
inflect.uncountable('advice');

// 符合 Ember Inspector 对导出的预期
export default {};
```

```javascript
export default DS.JSONAPIAdapter.extend({
  namespace: 'api/1'
});
```

这就是它的实现方法。

### 主机自定义 (Host Customizations)

适配器默认针对当前域名。如果你需要指定新域名，只需在新适配器上设置 `host` 属性即可。下面的代码最好地展示了如何实现这一点：

```javascript
export default DS.JSONAPIAdapter.extend({
  host: 'https://api.sample.com'
});
```

就是这样。

### 路径自定义 (Path Customizations)

可以像下面的代码一样重写 `pathForType` 方法：

```javascript
export default DS.JSONAPIAdapter.extend({
  pathForType: function(type) {
    return Ember.String.underscore(type);
  }
});
```

在这种情况下，我们不需要对模型的名称进行复数化，并且我们需要下划线（underscore）而不是驼峰命名（camelCase）。

### 请求头自定义 (Headers Customizations)

某些 API 需要 HTTP 请求头，一个很好的例子是需要提供 API key 的时候。可以将任意请求头作为键值对设置在 `JSONAPIAdapter` 的头头对象上，Ember data 将在我们的每个 Ajax 请求中发送这些内容。考虑下面的代码：

```javascript
export default DS.JSONAPIAdapter.extend({
  headers: {
    'API_KEY': 'secret key',
    'ANOTHER_HEADER': 'A header value'
  }
});
```

人们还可以将 `headers` 作为计算属性（computed property）来支持动态请求头。考虑下面的示例，请求头将根据 session 服务通过计算属性生成。以下是该示例的代码：

```javascript
export default DS.JSONAPIAdapter.extend({
  session: Ember.inject.service('session'),
  headers: Ember.computed('session.authToken', function() {
    return {
      'API_KEY': this.get('session.authToken'),
      'ANOTHER_HEADER': 'A header value'
    };
  })
});
```

在某些情况下，动态请求头需要从 Ember 观察系统之外的对象获取某些数据。`volatile` 函数也可以用于将属性设置为非缓存模式，这将导致每次请求都重新计算请求头。下方的代码所示：

```javascript
export default DS.JSONAPIAdapter.extend({
  headers: Ember.computed(function() {
    return {
      'API_KEY': Ember.get(document.cookie.match(/apiKey\=([^;]*)/), '1'),
      'ANOTHER_HEADER': 'A header value'
    };
  }).volatile()
});
```

### 编写适配器 (Authoring Adapters)

`defaultSerializer` 属性将用于指定适配器将使用的序列化器（serializer）。这仅在没有指定 `serializer:application` 或特定模型的适配器时才会使用。在任何应用程序中指定 `serializer:application` 都非常。考虑下面的示例展示了如何实现：

```javascript
export default DS.JSONAPIAdapter.extend({
  defaultSerializer: '-default'
});
```

### 自定义序列化器 (Customizing Serializers)

在 Ember data 中，序列化器用于格式化发送到我们的后端存储以及从后端存储接收的数据。默认设置是 Ember data 将使用 JSON API 格式对数据进行序列化。

#### JSON API 文档

考虑我们请求的如下响应：

```json
{
  "data": {
    "type": "people",
    "id": "567",
    "attributes": {
      "first-name": "John",
      "last-name": "Joel"
    }
  }
}
```

在上面的示例中，我们得到了一个对 `/people/567` 请求的响应。包含多个记录的响应可以在 `data` 属性中有一个数组，如下所示：

```json
{
  "data": [{
    {
      "type": "people",
      "id": "567",
      "attributes": {
        "first-name": "John",
        "last-name": "Joel"
      }
  }, {
    "type": "people",
    "id": "345",
    "attributes": {
        "first-name": "Mercy",
        "last-name": "Donald"
      }
  }]
}
```

#### 加载数据 (Sideloaded Data)

这类数据不是主请求的一部分，但具有一些关联关系，这些关系应该添加到 `included` 键下的数组中。考虑下面的代码：



```json
{
  "data": {
    "type": "blogs",
    "id": "1",
    "attributes": {
      "title": "I really like and enjoy blogging!"
    },
    "links": {
      "self": "http://mysite.com/blogs/1"
    },
    "relationships": {
      "comments": {
        "data": [
          { "type": "comments", "id": "5" },
          { "type": "comments", "id": "12" }
        ]
      }
    }
  },
  "included": [{
    "type": "comments",
    "id": "5",
    "attributes": {
      "body": "First!"
    },
    "links": {
      "self": "http://mysite.com/comments/5"
    }
  }, {
    "type": "comments",
    "id": "12",
    "attributes": {
      "body": "Ember is easy to learn"
    },
    "links": {
      "self": "http://mysite.com/comments/12"
    }
  }]
}
```

在上面的示例中，我们请求了`/blogs/1`，服务器给了我们`included`数据。

## 自定义序列化器 (Serializers)

在 Ember data 中，默认使用`JSONSerializer`，但可以使用自定义序列化器。自定义序列化器有两种定义方式。人们可以选择为整个应用程序定义序列化器，也可以为特定模型定义。

数据可以如下更改：

```javascript
import DS from 'ember-data';

export default DS.JSONSerializer.extend({
  serialize(snapshot, opts) {
    var json = this._super(...arguments);
    json.data.cost = {
      amount: json.data.attributes.amount,
      currency: json.data.attributes.currency
    };
    delete json.data.attributes.amount;
    delete json.data.attributes.currency;
    return json;
  },
});
```

如果后端存储提供的是 JSON API 以外的格式，可以使用`normalizeResponse()`钩子。通过上面的示例，服务器向我们提供的数据如下：

```json
{
  "data": {
    "attributes": {
      "id": "1",
      "name": "A Product",
      "cost": {
        "amount": 200,
        "currency": "USD"
      }
    },
    "type": "product"
  }
}
```

上述内容应改为：

```json
{
  "data": {
    "attributes": {
      "id": "1",
      "name": "A Product",
      "amount": 200,
      "currency": "USD"
    },
    "type": "product"
  }
}
```

它应该如下所示处理：

```javascript
import DS from 'ember-data';

export default DS.JSONSerializer.extend({
  normalizeResponse(store, primModelClass, payload, id, reqType) {
    payload.data.attributes.amount = payload.data.attributes.cost.amount;
    payload.data.attributes.currency = payload.data.attributes.cost.currency;
    delete payload.data.attributes.cost;
    return this._super(...arguments);
  },
});
```

如果你需要跟踪存储（store）中包含唯一记录，Ember data 期望负载（payload）中的每个记录都应该有一个唯一的`id`属性。对于特定类型的每条记录，`id`也应该是唯一的。如果后端使用的不是`id`而是其他键，可以使用序列化器（serializer）的主键属性，以便在数据的序列化和反序列化过程中正确地转换`id`。下文代码所示：

```javascript
export default DS.JSONSerializer.extend({
  primaryKey: '_id'
});
```

### 属性名称

Ember data 的约定是对特定模型上的属性名称进行驼峰命名法（camelize）。考虑下例示例：

```javascript
export default DS.Model.extend({
  fName: DS.attr('string'),
  lName:  DS.attr('string'),
  isPersonOfTheYear: DS.attr('boolean')
});
```

`JSONAPISerializer`期望服务器返回的文档负载中的属性是短横线形式（dasherized）的。下文代码所示：

```json
{
  "data": {
    "id": "44",
    "type": "people",
    "attributes": {
      "first-name": "John",
      "last-name": "Joel",
      "is-person-of-the-year": true
    }
  }
}
```

如果服务器返回的属性使用了非常不同的约定，可以使用序列化器的`keyForAttribute()`方法将模型中的属性名转换为 JSON 负载中的键。考虑下文代码：

```javascript
export default DS.JSONAPISerializer.extend({
  keyForAttribute: function(attribute) {
    return Ember.String.underscore(attribute);
  }
});
```

可以使用自定义序列化器来映射不规则的键。`attrs`对象可以用于在`DS`中不同属性名之间声明简单的映射。考虑下文示例代码：

```javascript
export default DS.Model.extend({
  lName: DS.attr('string')
});
```

我们所做的是为我们的模型创建了一个自定义序列化器，然后重写了`attrs`属性。接下来的代码如下：

```javascript
export default DS.JSONAPISerializer.extend({
  attrs: {
    lName: 'lastNameOfPerson'
  }
});
```

### 关系

`id`属性应该用于引用其他记录。考虑你的模型具有如下所示的`hasMany`关系的情况：

```javascript
export default DS.Model.extend({
  comments: DS.hasMany('comment', { async: true })
});
```

此时 JSON 应该将关系编码为类型和 ID 的数组。下文代码所示：

```json
{
  "data": {
    "type": "posts",
    "id": "1",
    "relationships": {
      "comments": {
        "data": [
          { "type": "comments", "id": "5" },
          { "type": "comments", "id": "12" }
        ]
      }
    }
  }
}
```

考虑你有一个如下模型的情况：

```javascript
export default DS.Model.extend({
  origPost: DS.belongsTo('post')
});
```

那么该关系应该通过 JSON 编码为另一个记录中的一个 ID。下文代码所示：

```json
{
  "data": {
    "type": "comment",
    "id": "1",
    "relationships": {
      "original-post": {
        "data": { "type": "post", "id": "5" },
      }
    }
  }
}
```

如果需要这些命名约定，则可以通过`keyForRelationship`方法对其进行重写。下文代码最清楚地说明了这一点：

```javascript
export default DS.JSONAPISerializer.extend({
  keyForRelationship: function(key, relship) {
    return key + 'Ids';
  }
});
```

### 自定义转换的创建

在某些情况下，内置类型（如`string`、`Boolean`等）可能不足以让我们实现所需的功能。一个很好的例子是特定服务器给您提供了非标准的日期格式。

在 Ember data 中，我们可能注册新的 JSON 转换以作属性。下文代码最完整地描述了这一点：

```javascript
export default DS.Transform.extend({
  serialize: function(val) {
    return [value.get('a'), value.get('b')];
  },
  deserialize: function(val) {
    return Ember.Object.create({ a: value[0], b: value[1] });
  }
});
```

接下来的代码如下：

```javascript
export default DS.Model.extend({
  position: DS.attr('coordinate-point')
});
```

在从 API 接收`coordinatePoint`后，预期它是一个如下所示的数组：

```json
{
  "cursor": {
    "position": [5,9]
  }
}
```

一旦加载到模型实例上，它将如下所示作为一个对象运行：

```javascript
var c = store.findRecord('cursor', 1);
c.get('position.x'); // 5
c.get('position.y'); // 9
```

一旦位置被修改并保存，它将通过我们转换中的`serialize`函数，并以数组的形式呈现在 JSON 中。要在应用中使用`JSONSerializer`，必须定义`serializer`，它只是`JSONSerializer`的扩展。考虑下文代码，它展示了这种做法：

```javascript
export default DS.JSONSerializer.extend({
  // ...
});
```

在某些请求的情况下，预期的结果应该有一个记录。预期响应应该是类似于下文的 JSON：

```json
{
  "id": "1",
  "title": "Ember is easy to Learn",
  "tag": "rails",
  "comments": ["1", "2"]
}
```

如果结果返回 0 或更多条记录，预期结果应该是如下所示的 JSON 数组：

```json
[
  {
    "id": "1",
    "title": "Ember is easy to Learn",
    "tag": "ember",
    "comments": ["1", "2"]
  },
  {
    "id": "2",
    "title": "When I was young, I aspired to become an athlete!",
    "tag": "w3c",
    "comments": ["3"]
  }
]
```

### EmbeddedRecordMixin

在 Ember data 中，我们鼓励对关系进行侧载（sideload），但有时在与旧留 API 工作时，你可能会发现需要处理包含嵌入在记录中的关系的 JSON。`EmbeddedRecordsMixin`的创建就是为了解决这个问题。要设置嵌入记录，只需在扩展序列化器的过程中包含该 mixin，然后对嵌入关系进行配置。

考虑模型`post`具有如下`author`记录的情况：

```json
{
  "id": "1",
  "title": "Ember is easy to Learn",
  "tag": "ember",
  "authors": [
    {
      "id": "2",
      "name": "Mark"
    }
  ]
}
```

此时关系将如下所示定义：

```javascript
export default DS.JSONSerializer.extend(EmbeddedRecordsMixin, {
  attrs: {
    authors: {
      serialize: 'records',
      deserialize: 'records'
    }
  }
});
```

如果你自己定义并需要序列化和反序列化嵌入关系，可以使用快捷选项`{ embedded: 'always' }`。考虑与下文类似的示例：

```javascript
export default DS.JSONSerializer.extend(EmbeddedRecordsMixin, {
  attrs: {
    authors: { embedded: 'always' }
  }
});
```

考虑你希望在提取 JSON 负载的过程中读取嵌入记录，但在序列化记录时仅包含关系的 ID。这可以通过使用`serialize: 'ids'`选项轻松实现。若要排除关系的序列化，可以使用`serialize: false`选项。下文代码演示了如何操作：

```javascript
export default DS.JSONSerializer.extend(EmbeddedRecordsMixin, {
  attrs: {
    author: {
      serialize: false,
      deserialize: 'records'
    },
    comments: {
      deserialize: 'records',
      serialize: 'ids'
    }
  }
});
```

#### EmbeddedRecordsMixin 默认值

如果你不需要为特定关系重写`attrs`属性，那么`EmbeddedRecordsMixin`的行为如下：

- `BelongsTo: { serialize: 'id', deserialize: 'id' }`
- `HasMany: { serialize: false, deserialize: 'ids' }`

### 编写序列化器

对于需要创建自定义序列化器的那些，我们建议从`JSONAPISerializer`或`JSONSerializer`开始，然后扩展其中之一以匹配我们的需求。然而，如果负载（payload）与其中一个序列化器不同，请考虑你获得了下面的模型“posts”：

```javascript
export default DS.Model.extend({
  title: DS.attr('string'),
  tag: DS.attr('string'),
  comments: hasMany('comment', { async: false }),
  relatedPosts: hasMany('blogs')
});
```

`store.push`将接受一个如下所示的对象：

```json
{
  data: {
    id: "1",
    type: 'post',
    attributes: {
      title: "Ember is easy to Learn",
      tag: "ember",
    },
    relationships: {
      comments: {
        data: [{ id: "1", type: 'comment' },
               { id: "2", type: 'comment' }],
      },
      relatedPosts: {
        data: {
          related: "/api/v1/blogs/1/related-posts/"
        }
      }
    }
}
```



为了让每个序列化的记录都能转换为 Ember data 记录，必须遵循上述格式。

# 第 3 章 应用关注点

## 依赖注入

这种技术在 EmberJS 中用于声明和实例化对象类以及它们之间的依赖关系。应用程序和应用程序实例将在 Ember 的 DI（依赖注入）实现中发挥作用。

## 工厂注册

工厂（Factory）可以用于表示应用的一部分，例如模板、路由或自定义类。这方面一个很好的例子是使用键`template:index`注册的索引模板。

请注意，工厂注册必须在应用程序内部或应用实例初始化器中完成，但前者更为常见。

考虑下例示例，它展示了应用初始化如何使用键名`logger:main`注册一个`logger`工厂：

```javascript
export function initialize(app) {
  var Logger = Ember.Object.extend({
    log(n) {
      console.log(n);
    }
  });
  app.register('logger:main', Logger);
}

export default {
  name: 'logger',
  initialize: initialize
};
```

### 注册已实例化的对象

默认设置是 Ember 在查找后会尝试实例化已注册的工厂。在特定类的已实例化对象的注册过程中，你必须使用`instantiate: false`选项，以避免它在查找期间被重复实例化。

在下例示例中，`logger`是 JavaScript 中的一个对象，它在查找时应该原样返回。以下是该示例的代码：

```javascript
export function initialize(app) {
  var logger = {
    log(n) {
      console.log(n);
    }
  };
  app.register('logger:main', logger, { instantiate: false });
}

export default {
  name: 'logger',
  initialize: initialize
};
```

### 单例与非单例注册

在 Ember data 中，注册被视为单例。这意味着在查找后必须创建一个实例，并且相同的实例将将被缓存并在后续的查找中返回。

在下例示例中，类`message`将被注册为非单例：

```javascript
export function initialize(app) {
  var Msge = Ember.Object.extend({
    text: ''
  });
  app.register('notification:message', Message, { singleton: false });
}

export default {
  name: 'notification',
  initialize: initialize
};
```

### 工厂注入

一旦完成了工厂注册，我们就可以需要时对其进行注入。工厂的注入可以在具有类型注入的所有工厂类型中进行。考虑下例示例：

```javascript
export function initialize(app) {
  var Logger = Ember.Object.extend({
    log(n) {
      console.log(n);
    }
  });
  app.register('logger:main', Logger);
  app.inject('route', 'logger', 'logger:main');
}

export default {
  name: 'logger',
  initialize: initialize
};
```

由于这种类型注入，类型为`route`的工厂将使用已注入的`logger`进行实例化。`logger`的值将从名为`logger:main`的工厂获取。

考虑下例示例，它展示了如何通过注入的`logger`访问应用。以下是示例：

```javascript
export default Ember.Route.extend({
  activate() {
    // 属性 logger 被注入到所有路由中
    this.get('logger').log('Entered your index route!');
  }
});
```

当使用完整键时，可以在如下所示的完整键上进行注入：

`app.inject('route:index', 'logger', 'logger:main');`

### 临时注入 (Ad Hoc)

依赖注入通过使用`Ember.inject`直接在 Ember 类上声明。目前，该属性支持服务（services）和控制器（controllers）的注入。

考虑下面的代码，它展示了如何将服务`shopping-cart`作为`cart`注入到组件`cart-contents`中。以下是代码：

```javascript
export default Ember.Component.extend({
  cart: Ember.inject.service('shopping-cart')
});
```

如果你需要注入一个与属性名称相似的服务，只需省略服务的名称即可。下方的代码演示了这一点：

```javascript
export default Ember.Component.extend({
  shoppingCart: Ember.inject.service()
});
```

实例初始化器（Instance initializers）通常接收应用实例作为参数，这为我们提供了查找工厂实例的机会。考虑下面的代码：

```javascript
export function initialize(appInstance) {
  let logger = appInstance.lookup('logger:main');
  logger.log('Hello from an instance initializer!');
}

export default {
  name: 'logger',
  initialize: initialize
};
```

我们我们也可能从工厂集中获取应用实例。考虑下例示例，它根据歌曲的`audioType`播放具有不同服务的歌曲。以下是代码：

```javascript
import Ember from 'ember';

const {
  Component,
  computed,
  getOwner
} = Ember;

// 使用方法:
// {{play-audio song=song}}

export default Component.extend({
  audioService: computed('song.audioType', function() {
    let appInstance = getOwner(this);
    let audioType = this.get('song.audioType');
    return appInstance.lookup(`service:${audioType}`);
  }),

  click() {
    let p = this.get('audioService');
    p.play(this.get('mysong.file'));
  }
});
```

## 初始化器 (Initializers)

它们为我们在启动过程中配置应用的机会。存在两种类型的初始化器：应用实例初始化器和应用初始化器。

应用初始化器在启动过程中执行，并为我们提供了在应用中配置依赖注入的方法。另一种初始化器在加载应用实例时配置。它们为我们提供了配置应用初始状态以及设置局部于应用实例的应用的方法。

### 应用初始化器 (Application Initializers)

应用初始化器使用 Ember CLI 的初始化生成器创建。

下面的命令描述了这一点：

`ember generate initializer shopping-cart`

然后我们可以自定义`shopping-cart`初始化器，将属性`cart`注入到应用中的所有路由中。下面的代码描述了这一点：

```javascript
export function initialize(app) {
  app.inject('route', 'cart', 'service:shopping-cart');
}

export default {
  name: 'shopping-cart',
  initialize: initialize
};
```

### 应用实例初始化器 (Application Instance Initializers)

这些可以使用 Ember CLI 的`instance-initializer`生成器创建。如下所示：

`ember generate instance-initializer logger`

考虑下面的代码，它展示了如何实现简单的日志记录以指示实例已经启动。下方的代码如下：

```javascript
export function initialize(appInstance) {
  var logger = appInstance.lookup('logger:main');
}
```

```javascript
logger.log('Hi from our instance initializer!');
}

export default {
  name: 'logger',
  initialize: initialize
};
```

# 指定初始化器顺序

如果你需要控制初始化器运行的顺序，可以使用`before`和`after`选项来实现目的。考虑下面的代码：

```javascript
export function initialize(app) {
  // ...在此处添加你的代码 ...
};

export default {
  name: 'configReader',
  before: 'websocketInit',
  initialize: initialize
};
```

接下来的代码应该如下所示：

```javascript
export function initialize(application) {
  // ...在此处添加你的代码...
};

export default {
  name: 'websocketInit',
  after: 'configReader',
  initialize: initialize
};
```

# 服务 (Services)

`Ember.service`属性是 Ember 中的一个对象，可以在应用程序的不同部分使用并可用。以下是服务使用的领域：

* `Geolocation`（地理位置）。

* `User/session authentication`（用户/会话身份验证）。

* `Web Sockets`（网络 WebSocket）。

* `Server-backed API calls`（无法适应`Ember Data`的后端支持 API 调用）。

* `Third-party APIs`（第三方 API）。

* `Server-sent events`（服务器发送事件）或通知。

## 服务的定义

Ember CLI 中的`service`生成器可用于生成服务。考虑下面的命令，它可以用于创建一个`shoppingCart`服务：

```bash
ember generate service shopping-cart
```

服务必须扩展基类`Ember.Service`。下方的代码所示：

```javascript
export default Ember.Service.extend({
});
```

就像 Ember 中的对象一样，服务必须经过初始化，并且它应该有自己的方法和属性。考虑下面所示的购物车服务，它最好地演示了这种工作原理：

```javascript
export default Ember.Service.extend({
  items: null,
  init() {
    this._super(args);
    this.set('items', []);
  },
  add(item) {
    this.get('items').pushObject(item);
  },
  remove(item) {
    this.get('items').removeObject(item);
  },
  empty() {
    this.get('items').setObjects([]);
  }
});
```

# 访问服务

为了访问服务，可以使用函数`Ember.inject.service`将其注入到任何由容器解析（container-resolved）的对象中，例如另一个服务或组件。该函数有两种使用方式。你可以选择不带参数调用它，或者将你的服务的注册名称传递给它。

在不传递参数的情况下，服务必须根据其变量键名加载。要在不带参数的情况下加载购物车服务，请按如下所示操作：

```javascript
export default Ember.Component.extend({
  // 想在文件 /app/services/shopping-cart.js 中加载服务
  shoppingCart: Ember.inject.service()
});
```

另一种方法涉及使用服务的名称作为参数。下方的代码所示：

```javascript
export default Ember.Component.extend({
  // 想在文件 /app/services/shopping-cart.js 中加载我们的服务
  cart: Ember.inject.service('shopping-cart')
});
```

通过上面的代码，购物车服务将注入到我们的组件中，然后供`cart`属性可用。被注入的属性是懒加载的，这意味着在显式调用该属性之前，不会执行服务的实例化。这意味着必须使用`get`函数来访问特定组件的服务，否则你将获得 undefined 。

加载后，服务将一直持续到服务退出。

考虑下面的代码：

```javascript
export default Ember.Component.extend({
  cart: Ember.inject.service('shopping-cart'),
  actions: {
    remove(item) {
      this.get('cart').remove(item);
    }
  }
});
```

在上面的代码中，我们为组件`cart-contacts`添加了`remove`动作。一旦被注入到组件中，该服务将在模板中使用。注意下面的代码中使用了`cart`来从购物车中获取数据：

```html
<ul>
  {{#each cart.items as |item|}}
    <li>
      {{item.name}}
      <button {{action "remove" item}}>移除</button>
    </li>
  {{/each}}
</ul>
```

# 运行循环 (The Run Loop)

在 Ember 中为我们的应用程序编写的大部分内部机制和代码都发生在运行循环中。运行循环用于批量处理和排序工作，以一种更高效、有效的方式进行。

当我们批量处理相似的工作时，会获得巨大的收益。为了让网络浏览器执行相关的操作，它们必须对 DOM 所所的更改进行批量处理。考虑下面的 HTML 片段：

```html
<div id="foo"></div>
<div id="bar"></div>
<div id="baz"></div>
```

然后你可以运行以下代码：

```javascript
foo.style.height = '500px' // 写入
foo.offsetHeight // 读取
bar.style.height = '400px' // 写入
bar.offsetHeight // 读取
baz.style.height = '200px' // 写入
baz.offsetHeight // 读取
```

在上面的示例中，代码的顺序强制浏览器在每一步之后重新计算样式和布局。然而，如果我们能够将相似的任务合并在一起，那么浏览器只需要重新计算一次样式和布局。下方的代码所示：

```javascript
foo.style.height = '500px' // 写入
bar.style.height = '400px' // 写入
baz.style.height = '200px' // 写入
foo.offsetHeight // 读取
bar.offsetHeight // 读取
baz.offsetHeight // 读取
```

这种做法的好处在于它适用于许多其他类型的工作。当我们批量处理相似的工作时，我们发现很容易进行流水线处理并进一步优化。

考虑下面的示例，它在 Ember 中经过了优化：

```javascript
var MyUser = Ember.Object.extend({
  fName: null,
  lName: null,
  fullName: Ember.computed('fName', 'lName', function() {
    return `${this.get('fName')} ${this.get('lName')}`;
  })
});
```

# 结论

我们已经到达本指南的结论。Ember 是目前使用的 JavaScript 框架之一。该框架主要用于我们需要开发 Web 应用程序客户端时使用。

该框架具有许多我们可以利用的特性来增强我们的应用程序。



在 Ember JS 中，控制器（controllers）非常重要，大多数人会将它们与组件（components）混淆。人们认为，控制器很快将被组件取代。控制器的目的是控制状态，而这取决于当前使用的路由类型。在将信息从组件传递到路由时，也会使用控制器，因为信息必须通过它进行传递。此外，控制器之间需要建立依赖关系。

当我们需要嵌套资源时，通常就是如此。我们必须想出一种机制来在控制器之间建立连接。了解如何在 Ember JS 中创建自定义转换（custom transformations）对你很有帮助。这是因为现有的数据类型可能不足以满足你的需求，Ember JS 中的自定义转换可以在这方面为你提供帮助。

我希望这本书能够帮助你理解如何在 Ember JS 中构建应用程序。祝使用得愉快！
