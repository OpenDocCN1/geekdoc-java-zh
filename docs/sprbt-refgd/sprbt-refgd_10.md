
# 附录 A. 常见应用属性

你可以在`application.properties`/`application.yml`文件内部或通过命令行开关来指定各种属性。本章节提供了一个常见 Spring Boot 属性的列表及使用这些属性的底层类的引用。

**注**：属性可以来自 classpath 下的其他 jar 文件中，所以你不应该把它当成详尽的列表。定义你自己的属性也是相当合法的。

**注**：示例文件只是一个指导。不要拷贝/粘贴整个内容到你的应用，而是只提取你需要的属性。



# COMMON SPRING BOOT PROPERTIES

本示例文件仅作为参考指南。请勿将其完整复制到您自己的应用程序中。

## CORE PROPERTIES

### SPRING CONFIG (ConfigFileApplicationListener)

- `spring.config.name` — 配置文件名称（默认为 `application`）
- `spring.config.location` — 配置文件位置

### PROFILES

- `spring.profiles.active` — 激活的配置文件列表（逗号分隔）
- `spring.profiles.include` — 无条件激活指定的逗号分隔配置文件

### APPLICATION SETTINGS (SpringApplication)

- `spring.main.sources`
- `spring.main.web-environment` — 默认自动检测
- `spring.main.show-banner=true`
- `spring.main....` — 查看类以获取所有属性

### LOGGING

- `logging.path=/var/logs`
- `logging.file=myapp.log`
- `logging.config` — 配置文件位置（logback 默认为 `classpath:logback.xml`）
- `logging.level.*` — 日志记录器级别，例如 `logging.level.org.springframework=DEBUG`（`TRACE`, `DEBUG`, `INFO`, `WARN`, `ERROR`, `FATAL`, `OFF`）

### IDENTITY (ContextIdApplicationContextInitializer)

- `spring.application.name`
- `spring.application.index`

### EMBEDDED SERVER CONFIGURATION (ServerProperties)

- `server.port=8080`
- `server.address` — 绑定到特定的 NIC
- `server.session-timeout` — 会话超时时间（秒）
- `server.context-parameters.*` — Servlet 上下文初始化参数，例如 `server.context-parameters.a=alpha`
- `server.context-path` — 上下文路径，默认为 `/`
- `server.servlet-path` — Servlet 路径，默认为 `/`
- `server.ssl.enabled=true` — 是否启用 SSL 支持
- `server.ssl.client-auth` — `want` 或 `need`
- `server.ssl.key-alias`
- `server.ssl.ciphers` — 支持的 SSL 密码套件
- `server.ssl.key-password`
- `server.ssl.key-store`
- `server.ssl.key-store-password`
- `server.ssl.key-store-provider`
- `server.ssl.key-store-type`
- `server.ssl.protocol=TLS`
- `server.ssl.trust-store`
- `server.ssl.trust-store-password`
- `server.ssl.trust-store-provider`
- `server.ssl.trust-store-type`
- `server.tomcat.access-log-pattern` — 访问日志的日志模式
- `server.tomcat.access-log-enabled=false` — 是否启用访问日志
- `server.tomcat.compression=off` — 是否启用压缩（`off`、`on` 或整数内容长度限制）
- `server.tomcat.compressable-mime-types=text/html,text/xml,text/plain` — Tomcat 将压缩的 MIME 类型列表（逗号分隔）
- `server.tomcat.internal-proxies=10\\.\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}|\\ 192\\.168\\.\\d{1,3}\\.\\d{1,3}|\\ 169\\.254\\.\\d{1,3}\\.\\d{1,3}|\\ 127\\.\\d{1,3}\\.\\d{1,3}\\.\\d{1,3}` — 匹配受信任 IP 地址的正则表达式
- `server.tomcat.protocol-header=x-forwarded-proto` — 前端代理转发头
- `server.tomcat.port-header` — 前端代理端口头
- `server.tomcat.remote-ip-header=x-forwarded-for`
- `server.tomcat.basedir=/tmp` — 基础目录（通常不需要，默认为临时目录）
- `server.tomcat.background-processor-delay=30` — 以秒为单位
- `server.tomcat.max-http-header-size` — HTTP 消息头的最大大小（字节）
- `server.tomcat.max-threads = 0` — 协议处理器中的线程数
- `server.tomcat.uri-encoding = UTF-8` — 用于 URL 解码的字符编码

### SPRING MVC (WebMvcProperties)

- `spring.mvc.locale` — 设置固定区域设置，例如 `en_UK`
- `spring.mvc.date-format` — 设置固定日期格式，例如 `dd/MM/yyyy`
- `spring.mvc.favicon.enabled=true`
- `spring.mvc.message-codes-resolver-format` — `PREFIX_ERROR_CODE` / `POSTFIX_ERROR_CODE`
- `spring.mvc.ignore-default-model-on-redirect=true` — 重定向时是否忽略“默认”模型的内容
- `spring.view.prefix` — MVC 视图前缀
- `spring.view.suffix` — MVC 视图后缀

### SPRING RESOURCES HANDLING (ResourceProperties)

- `spring.resources.cache-period` — 发送到浏览器的头中的缓存超时时间
- `spring.resources.add-mappings=true` — 是否应添加默认映射

### MULTIPART (MultipartProperties)

- `multipart.enabled=true`
- `multipart.file-size-threshold=0` — 文件写入磁盘的阈值
- `multipart.location` — 上传文件的中间位置
- `multipart.max-file-size=1Mb` — 最大文件大小
- `multipart.max-request-size=10Mb` — 最大请求大小

### SPRING HATEOAS (HateoasProperties)

- `spring.hateoas.apply-to-primary-object-mapper=true` — 是否也应配置主映射器

### HTTP encoding (HttpEncodingProperties)

- `spring.http.encoding.charset=UTF-8` — HTTP 请求/响应的编码
- `spring.http.encoding.enabled=true` — 启用 HTTP 编码支持
- `spring.http.encoding.force=true` — 强制使用配置的编码

### HTTP message conversion

- `spring.http.converters.preferred-json-mapper` — 用于 HTTP 消息转换的首选 JSON 映射器。当 Gson 和 Jackson 都在类路径上时，设置为 `gson` 以强制使用 Gson。

### HTTP response compression (GzipFilterProperties)

- `spring.http.gzip.buffer-size` — 输出缓冲区大小（字节）
- `spring.http.gzip.deflate-compression-level` — 用于 deflate 压缩的级别（0-9）
- `spring.http.gzip.deflate-no-wrap` — deflate 压缩的 noWrap 设置（`true` 或 `false`）
- `spring.http.gzip.enabled=true` — 启用 gzip 过滤器支持
- `spring.http.gzip.excluded-agents` — 从压缩中排除的用户代理列表（逗号分隔）
- `spring.http.gzip.excluded-agent-patterns` — 控制从压缩中排除的用户代理的正则表达式模式列表（逗号分隔）
- `spring.http.gzip.excluded-paths` — 从压缩中排除的路径列表（逗号分隔）
- `spring.http.gzip.excluded-path-patterns` — 控制从压缩中排除的路径的正则表达式模式列表（逗号分隔）
- `spring.http.gzip.methods` — 启用压缩的 HTTP 方法列表（逗号分隔）
- `spring.http.gzip.mime-types` — 应压缩的 MIME 类型列表（逗号分隔）
- `spring.http.gzip.min-gzip-size` — 触发压缩所需的最小内容长度
- `spring.http.gzip.vary` — 在可能被压缩的响应上发送的 Vary 头

### JACKSON (JacksonProperties)

- `spring.jackson.date-format` — 日期格式字符串（例如 `yyyy-MM-dd HH:mm:ss`），或完全限定的日期格式类名（例如 `com.fasterxml.jackson.databind.util.ISO8601DateFormat`）
- `spring.jackson.property-naming-strategy` — Jackson 的 `PropertyNamingStrategy` 上的常量之一（例如 `CAMEL_CASE_TO_LOWER_CASE_WITH_UNDERSCORES`）或 `PropertyNamingStrategy` 子类的完全限定类名
- `spring.jackson.deserialization.*` — 参见 Jackson 的 `DeserializationFeature`
- `spring.jackson.generator.*` — 参见 Jackson 的 `JsonGenerator.Feature`
- `spring.jackson.mapper.*` — 参见 Jackson 的 `MapperFeature`
- `spring.jackson.parser.*` — 参见 Jackson 的 `JsonParser.Feature`
- `spring.jackson.serialization.*` — 参见 Jackson 的 `SerializationFeature`
- `spring.jackson.serialization-inclusion` — 控制序列化期间属性的包含（参见 Jackson 的 `JsonInclude.Include`）

### THYMELEAF (ThymeleafAutoConfiguration)

- `spring.thymeleaf.check-template-location=true`
- `spring.thymeleaf.prefix=classpath:/templates/`
- `spring.thymeleaf.excluded-view-names` — 应从解析中排除的视图名称列表（逗号分隔）
- `spring.thymeleaf.view-names` — 可以解析的视图名称列表（逗号分隔）
- `spring.thymeleaf.suffix=.html`
- `spring.thymeleaf.mode=HTML5`
- `spring.thymeleaf.encoding=UTF-8`
- `spring.thymeleaf.content-type=text/html` — 会添加 `;charset=<encoding>`
- `spring.thymeleaf.cache=true` — 设置为 `false` 以进行热刷新

### FREEMARKER (FreeMarkerAutoConfiguration)

- `spring.freemarker.allow-request-override=false`
- `spring.freemarker.cache=true`
- `spring.freemarker.check-template-location=true`
- `spring.freemarker.charset=UTF-8`
- `spring.freemarker.content-type=text/html`
- `spring.freemarker.expose-request-attributes=false`
- `spring.freemarker.expose-session-attributes=false`
- `spring.freemarker.expose-spring-macro-helpers=false`
- `spring.freemarker.prefix=`
- `spring.freemarker.request-context-attribute=`
- `spring.freemarker.settings.*=`
- `spring.freemarker.suffix=.ftl`
- `spring.freemarker.template-loader-path=classpath:/templates/` — 逗号分隔列表
- `spring.freemarker.view-names=` — 可以解析的视图名称白名单

### GROOVY TEMPLATES (GroovyTemplateAutoConfiguration)

- `spring.groovy.template.cache=true`
- `spring.groovy.template.charset=UTF-8`
- `spring.groovy.template.configuration.*=` — 参见 Groovy 的 `TemplateConfiguration`
- `spring.groovy.template.content-type=text/html`
- `spring.groovy.template.prefix=classpath:/templates/`
- `spring.groovy.template.suffix=.tpl`
- `spring.groovy.template.view-names=` — 可以解析的视图名称白名单

### VELOCITY TEMPLATES (VelocityAutoConfiguration)

- `spring.velocity.allow-request-override=false`
- `spring.velocity.cache=true`
- `spring.velocity.check-template-location=true`
- `spring.velocity.charset=UTF-8`
- `spring.velocity.content-type=text/html`
- `spring.velocity.date-tool-attribute=`
- `spring.velocity.expose-request-attributes=false`
- `spring.velocity.expose-session-attributes=false`
- `spring.velocity.expose-spring-macro-helpers=false`
- `spring.velocity.number-tool-attribute=`
- `spring.velocity.prefer-file-system-access=true` — 模板加载时优先使用文件系统访问
- `spring.velocity.prefix=`
- `spring.velocity.properties.*=`
- `spring.velocity.request-context-attribute=`
- `spring.velocity.resource-loader-path=classpath:/templates/`
- `spring.velocity.suffix=.vm`
- `spring.velocity.toolbox-config-location=` — Velocity Toolbox 配置位置，例如 `/WEB-INF/toolbox.xml`
- `spring.velocity.view-names=` — 可以解析的视图名称白名单

### JERSEY (JerseyProperties)

- `spring.jersey.type=servlet` — `servlet` 或 `filter`
- `spring.jersey.init=` — 初始化参数
- `spring.jersey.filter.order=`

### INTERNATIONALIZATION (MessageSourceAutoConfiguration)

- `spring.messages.basename=messages`
- `spring.messages.cache-seconds=-1`
- `spring.messages.encoding=UTF-8`

### SECURITY (SecurityProperties)

- `security.user.name=user` — 登录用户名
- `security.user.password=` — 登录密码
- `security.user.role=USER` — 分配给用户的角色
- `security.require-ssl=false` — 高级设置...
- `security.enable-csrf=false`
- `security.basic.enabled=true`
- `security.basic.realm=Spring`
- `security.basic.path=` — `/**`
- `security.basic.authorize-mode=` — `ROLE`, `AUTHENTICATED`, `NONE`
- `security.filter-order=0`
- `security.headers.xss=false`
- `security.headers.cache=false`
- `security.headers.frame=false`
- `security.headers.content-type=false`
- `security.headers.hsts=all` — `none` / `domain` / `all`
- `security.sessions=stateless` — `always` / `never` / `if_required` / `stateless`
- `security.ignored=` — 要从默认安全路径中排除的路径列表（逗号分隔）

### DATASOURCE (DataSourceAutoConfiguration & DataSourceProperties)

- `spring.datasource.name=` — 数据源名称
- `spring.datasource.initialize=true` — 使用 `data.sql` 填充
- `spring.datasource.schema=` — 模式（DDL）脚本资源引用
- `spring.datasource.data=` — 数据（DML）脚本资源引用
- `spring.datasource.sql-script-encoding=` — 读取 SQL 脚本的字符集
- `spring.datasource.platform=` — 模式资源中使用的平台（`schema-${platform}.sql`）
- `spring.datasource.continue-on-error=false` — 即使无法初始化也继续
- `spring.datasource.separator=;` — SQL 初始化脚本中的语句分隔符
- `spring.datasource.driver-class-name=` — JDBC 设置...
- `spring.datasource.url=`
- `spring.datasource.username=`
- `spring.datasource.password=`
- `spring.datasource.jndi-name=` — 用于 JNDI 查找（设置后，`class`、`url`、`username` 和 `password` 将被忽略）
- `spring.datasource.max-active=100` — 高级配置...
- `spring.datasource.max-idle=8`
- `spring.datasource.min-idle=8`
- `spring.datasource.initial-size=10`
- `spring.datasource.validation-query=`
- `spring.datasource.test-on-borrow=false`
- `spring.datasource.test-on-return=false`
- `spring.datasource.test-while-idle=`
- `spring.datasource.time-between-eviction-runs-millis=`
- `spring.datasource.min-evictable-idle-time-millis=`
- `spring.datasource.max-wait=`
- `spring.datasource.jmx-enabled=false` — 导出 JMX MBeans（如果支持）

### DAO (PersistenceExceptionTranslationAutoConfiguration)

- `spring.dao.exceptiontranslation.enabled=true`

### MONGODB (MongoProperties)

- `spring.data.mongodb.host=` — 数据库主机
- `spring.data.mongodb.port=27017` — 连接端口（默认为 27107）
- `spring.data.mongodb.uri=mongodb://localhost/test` — 连接 URL
- `spring.data.mongodb.database=`
- `spring.data.mongodb.authentication-database=`
- `spring.data.mongodb.grid-fs-database=`
- `spring.data.mongodb.username=`
- `spring.data.mongodb.password=`
- `spring.data.mongodb.repositories.enabled=true` — 是否启用 Spring Data 仓库支持

### JPA (JpaBaseConfiguration, HibernateJpaAutoConfiguration)

- `spring.jpa.properties.*=` — 在 JPA 连接上设置的属性
- `spring.jpa.open-in-view=true`
- `spring.jpa.show-sql=true`
- `spring.jpa.database-platform=`
- `spring.jpa.database=`
- `spring.jpa.generate-ddl=false` — Hibernate 忽略，可能对其他供应商有用
- `spring.jpa.hibernate.naming-strategy=` — 命名类名
- `spring.jpa.hibernate.ddl-auto=` — 嵌入式数据库默认为 `create-drop`
- `spring.data.jpa.repositories.enabled=true` — 是否启用 Spring Data 仓库支持

### JTA (JtaAutoConfiguration)

- `spring.jta.log-dir=` — 事务日志目录
- `spring.jta.*=` — 技术特定配置

### ATOMIKOS

- `spring.jta.atomikos.connectionfactory.borrow-connection-timeout=30` — 从池中借用连接的超时时间（秒）
- `spring.jta.atomikos.connectionfactory.ignore-session-transacted-flag=true` — 创建会话时是否忽略 transacted 标志
- `spring.jta.atomikos.connectionfactory.local-transaction-mode=false` — 是否需要本地事务
- `spring.jta.atomikos.connectionfactory.maintenance-interval=60` — 池维护线程运行间隔时间（秒）
- `spring.jta.atomikos.connectionfactory.max-idle-time=60` — 连接从池中清理前的空闲时间（秒）
- `spring.jta.atomikos.connectionfactory.max-lifetime=0` — 连接在销毁前可被池化的时间（秒）。`0` 表示无限制。
- `spring.jta.atomikos.connectionfactory.max-pool-size=1` — 池的最大大小
- `spring.jta.atomikos.connectionfactory.min-pool-size=1` — 池的最小大小
- `spring.jta.atomikos.connectionfactory.reap-timeout=0` — 借用连接的重用超时时间（秒）。`0` 表示无限制。
- `spring.jta.atomikos.connectionfactory.unique-resource-name=jmsConnectionFactory` — 恢复期间用于标识资源的唯一名称
- `spring.jta.atomikos.datasource.borrow-connection-timeout=30` — 从池中借用连接的超时时间（秒）
- `spring.jta.atomikos.datasource.default-isolation-level=` — 池提供的连接的默认隔离级别
- `spring.jta.atomikos.datasource.login-timeout=` — 建立数据库连接的超时时间（秒）
- `spring.jta.atomikos.datasource.maintenance-interval=60` — 池维护线程运行间隔时间（秒）
- `spring.jta.atomikos.datasource.max-idle-time=60` — 连接从池中清理前的空闲时间（秒）
- `spring.jta.atomikos.datasource.max-lifetime=0` — 连接在销毁前可被池化的时间（秒）。`0` 表示无限制。
- `spring.jta.atomikos.datasource.max-pool-size=1` — 池的最大大小
- `spring.jta.atomikos.datasource.min-pool-size=1` — 池的最小大小
- `spring.jta.atomikos.datasource.reap-timeout=0` — 借用连接的重用超时时间（秒）。`0` 表示无限制。
- `spring.jta.atomikos.datasource.test-query=` — 用于在返回连接前验证连接的 SQL 查询或语句
- `spring.jta.atomikos.datasource.unique-resource-name=dataSource` — 恢复期间用于标识资源的唯一名称

### BITRONIX

- `spring.jta.bitronix.connectionfactory.acquire-increment=1` — 池增长时创建的连接数
- `spring.jta.bitronix.connectionfactory.acquisition-interval=1` — 获取无效连接后再次尝试获取连接前的等待时间（秒）
- `spring.jta.bitronix.connectionfactory.acquisition-timeout=30` — 从池中获取连接的超时时间（秒）
- `spring.jta.bitronix.connectionfactory.allow-local-transactions=true` — 事务管理器是否允许混合 XA 和非 XA 事务
- `spring.jta.bitronix.connectionfactory.apply-transaction-timeout=false` — 注册 XAResource 时是否设置事务超时
- `spring.jta.bitronix.connectionfactory.automatic-enlisting-enabled=true` — 是否自动注册和注销资源
- `spring.jta.bitronix.connectionfactory.cache-producers-consumers=true` — 是否缓存生产者和消费者
- `spring.jta.bitronix.connectionfactory.defer-connection-release=true` — 提供者是否可以在同一连接上运行多个事务并支持事务交错
- `spring.jta.bitronix.connectionfactory.ignore-recovery-failures=false` — 是否忽略恢复失败
- `spring.jta.bitronix.connectionfactory.max-idle-time=60` — 连接从池中清理前的空闲时间（秒）
- `spring.jta.bitronix.connectionfactory.max-pool-size=10` — 池的最大大小。`0` 表示无限制
- `spring.jta.bitronix.connectionfactory.min-pool-size=0` — 池的最小大小
- `spring.jta.bitronix.connectionfactory.password=` — 连接 JMS 提供者的密码
- `spring.jta.bitronix.connectionfactory.share-transaction-connections=false` — 在事务上下文中是否可以共享 `ACCESSIBLE` 状态的连接
- `spring.jta.bitronix.connectionfactory.test-connections=true` — 从池中获取连接时是否应测试连接
- `spring.jta.bitronix.connectionfactory.two-pc-ordering-position=1` — 两阶段提交期间此资源应占用的位置（始终第一为 `Integer.MIN_VALUE`，始终最后为 `Integer.MAX_VALUE`）
- `spring.jta.bitronix.connectionfactory.unique-name=jmsConnectionFactory` — 恢复期间用于标识资源的唯一名称
- `spring.jta.bitronix.connectionfactory.use-tm-join=true` — 启动 XAResources 时是否应使用 `TMJOIN`
- `spring.jta.bitronix.connectionfactory.user=` — 连接 JMS 提供者的用户
- `spring.jta.bitronix.datasource.acquire-increment=1` — 池增长时创建的连接数
- `spring.jta.bitronix.datasource.acquisition-interval=1` — 获取无效连接后再次尝试获取连接前的等待时间（秒）
- `spring.jta.bitronix.datasource.acquisition-timeout=30` — 从池中获取连接的超时时间（秒）
- `spring.jta.bitronix.datasource.allow-local-transactions=true` — 事务管理器是否允许混合 XA 和非 XA 事务
- `spring.jta.bitronix.datasource.apply-transaction-timeout=false` — 注册 XAResource 时是否设置事务超时
- `spring.jta.bitronix.datasource.automatic-enlisting-enabled=true` — 是否自动注册和注销资源
- `spring.jta.bitronix.datasource.cursor-holdability=` — 连接的默认游标保持能力
- `spring.jta.bitronix.datasource.defer-connection-release=true` — 数据库是否可以在同一连接上运行多个事务并支持事务交错
- `spring.jta.bitronix.datasource.enable-jdbc4-connection-test` — 从池中获取连接时是否调用 `Connection.isValid()`
- `spring.jta.bitronix.datasource.ignore-recovery-failures=false` — 是否忽略恢复失败
- `spring.jta.bitronix.datasource.isolation-level=` — 连接的默认隔离级别
- `spring.jta.bitronix.datasource.local-auto-commit` — 本地事务的默认自动提交模式
- `spring.jta.bitronix.datasource.login-timeout=` — 建立数据库连接的超时时间（秒）
- `spring.jta.bitronix.datasource.max-idle-time=60` — 连接从池中清理前的空闲时间（秒）
- `spring.jta.bitronix.datasource.max-pool-size=10` — 池的最大大小。`0` 表示无限制
- `spring.jta.bitronix.datasource.min-pool-size=0` — 池的最小大小
- `spring.jta.bitronix.datasource.prepared-statement-cache-size=0` — 预处理语句缓存的目标大小。`0` 禁用缓存
- `spring.jta.bitronix.datasource.share-transaction-connections=false` — 在事务上下文中是否可以共享 `ACCESSIBLE` 状态的连接
- `spring.jta.bitronix.datasource.test-query` — 用于在返回连接前验证连接的 SQL 查询或语句
- `spring.jta.bitronix.datasource.two-pc-ordering-position=1` — 两阶段提交期间此资源应占用的位置（始终第一为 `Integer.MIN_VALUE`，始终最后为 `Integer.MAX_VALUE`）
- `spring.jta.bitronix.datasource.unique-name=dataSource` — 恢复期间用于标识资源的唯一名称
- `spring.jta.bitronix.datasource.use-tm-join=true` — 启动 XAResources 时是否应使用 `TMJOIN`

### SOLR (SolrProperties)

- `spring.data.solr.host=http://127.0.0.1:8983/solr`
- `spring.data.solr.zk-host=`
- `spring.data.solr.repositories.enabled=true` — 是否启用 Spring Data 仓库支持

### ELASTICSEARCH (ElasticsearchProperties)

- `spring.data.elasticsearch.cluster-name=` — 集群名称（默认为 `elasticsearch`）
- `spring.data.elasticsearch.cluster-nodes=` — 服务器节点地址（逗号分隔；如果未指定则启动客户端节点）
- `spring.data.elasticsearch.properties.*=` — 用于配置客户端的其他属性
- `spring.data.elasticsearch.repositories.enabled=true` — 是否启用 Spring Data 仓库支持

### DATA REST (RepositoryRestConfiguration)

- `spring.data.rest.base-uri=` — 导出器计算其链接所基于的基础 URI

### FLYWAY (FlywayProperties)

- `flyway.*=` — 自动配置的 `Flyway` 对象上可用的任何公共属性
- `flyway.check-location=false` — 检查迁移脚本位置是否存在
- `flyway.locations=classpath:db/migration` — 迁移脚本的位置
- `flyway.schemas=` — 要更新的模式
- `flyway.init-version= 1` — 开始迁移的版本
- `flyway.init-sqls=` — 获取连接后立即执行以初始化连接的 SQL 语句
- `flyway.sql-migration-prefix=V`
- `flyway.sql-migration-suffix=.sql`
- `flyway.enabled=true`
- `flyway.url=` — 如果希望 Flyway 创建自己的 DataSource，则使用 JDBC URL
- `flyway.user=` — 如果希望 Flyway 创建自己的 DataSource，则使用 JDBC 用户名
- `flyway.password=` — 如果希望 Flyway 创建自己的 DataSource，则使用 JDBC 密码

### LIQUIBASE (LiquibaseProperties)

- `liquibase.change-log=classpath:/db/changelog/db.changelog-master.yaml`
- `liquibase.check-change-log-location=true` — 检查变更日志位置是否存在
- `liquibase.contexts=` — 要使用的运行时上下文
- `liquibase.default-schema=` — 要使用的默认数据库模式
- `liquibase.drop-first=false`
- `liquibase.enabled=true`
- `liquibase.url=` — 特定的 JDBC URL（如果未设置，则使用默认数据源）
- `liquibase.user=` — `liquibase.url` 的用户名
- `liquibase.password=` — `liquibase.url` 的密码

### JMX

- `spring.jmx.enabled=true` — 从 Spring 暴露 MBeans

### RABBIT (RabbitProperties)

- `spring.rabbitmq.host=` — 连接主机
- `spring.rabbitmq.port=` — 连接端口
- `spring.rabbitmq.addresses=` — 连接地址（例如 `myhost:9999,otherhost:1111`）
- `spring.rabbitmq.username=` — 登录用户
- `spring.rabbitmq.password=` — 登录密码
- `spring.rabbitmq.virtual-host=`
- `spring.rabbitmq.dynamic=`

### REDIS (RedisProperties)

- `spring.redis.database=` — 数据库名称
- `spring.redis.host=localhost` — 服务器主机
- `spring.redis.password=` — 服务器密码
- `spring.redis.port=6379` — 连接端口
- `spring.redis.pool.max-idle=8` — 池设置...
- `spring.redis.pool.min-idle=0`
- `spring.redis.pool.max-active=8`
- `spring.redis.pool.max-wait=-1`
- `spring.redis.sentinel.master=` — Redis 服务器名称
- `spring.redis.sentinel.nodes=` — `host:port` 对列表（逗号分隔）

### ACTIVEMQ (ActiveMQProperties)

- `spring.activemq.broker-url=tcp://localhost:61616` — 连接 URL
- `spring.activemq.user=`
- `spring.activemq.password=`
- `spring.activemq.in-memory=true` — 如果未指定 `broker-url`，则创建的代理类型
- `spring.activemq.pooled=false`

### HornetQ (HornetQProperties)

- `spring.hornetq.mode=` — 连接模式（`native`、`embedded`）
- `spring.hornetq.host=localhost` — HornetQ 主机（`native` 模式）
- `spring.hornetq.port=5445` — HornetQ 端口（`native` 模式）
- `spring.hornetq.embedded.enabled=true` — 是否启用嵌入式服务器（需要 `hornetq-jms-server.jar`）
- `spring.hornetq.embedded.server-id=` — 嵌入式服务器的自动生成 ID（整数）
- `spring.hornetq.embedded.persistent=false` — 消息持久化
- `spring.hornetq.embedded.data-directory=` — 数据内容的位置（启用持久化时）
- `spring.hornetq.embedded.queues=` — 启动时创建的队列（逗号分隔）
- `spring.hornetq.embedded.topics=` — 启动时创建的主题（逗号分隔）
- `spring.hornetq.embedded.cluster-password=` — 客户密码（默认随机生成）

### JMS (JmsProperties)

- `spring.jms.jndi-name=` — JMS `ConnectionFactory` 的 JNDI 位置
- `spring.jms.pub-sub-domain=` — `false` 表示队列（默认），`true` 表示主题

### Email (MailProperties)

- `spring.mail.host=smtp.acme.org` — 邮件服务器主机
- `spring.mail.port=` — 邮件服务器端口
- `spring.mail.username=`
- `spring.mail.password=`
- `spring.mail.default-encoding=UTF-8` — 用于 `MimeMessages` 的编码
- `spring.mail.properties.*=` — 在 JavaMail 会话上设置的属性

### SPRING BATCH (BatchDatabaseInitializer)

- `spring.batch.job.names=job1,job2`
- `spring.batch.job.enabled=true`
- `spring.batch.initializer.enabled=true`
- `spring.batch.schema=` — 要加载的批处理模式

### SPRING CACHE (CacheProperties)

- `spring.cache.type=` — `generic`, `ehcache`, `hazelcast`, `jcache`, `redis`, `guava`, `simple`, `none`
- `spring.cache.config=`
- `spring.cache.cache-names=` — 启动时要创建的缓存名称
- `spring.cache.jcache.provider=` — 要使用的 `CachingProvider` 实现的完全限定名称
- `spring.cache.guava.spec=` — Guava 规范

### AOP

- `spring.aop.auto=`
- `spring.aop.proxy-target-class=`

### FILE ENCODING (FileEncodingApplicationListener)

- `spring.mandatory-file-encoding=` — 应用程序必须使用的预期字符编码

### SPRING SOCIAL (SocialWebAutoConfiguration)

- `spring.social.auto-connection-views=true` — 设置为 `true` 以使用默认连接视图，或设置为 `false` 以提供自己的视图

### SPRING SOCIAL FACEBOOK (FacebookAutoConfiguration)

- `spring.social.facebook.app-id=` — 您的应用程序的 Facebook App ID
- `spring.social.facebook.app-secret=` — 您的应用程序的 Facebook App Secret

### SPRING SOCIAL LINKEDIN (LinkedInAutoConfiguration)

- `spring.social.linkedin.app-id=` — 您的应用程序的 LinkedIn App ID
- `spring.social.linkedin.app-secret=` — 您的应用程序的 LinkedIn App Secret

### SPRING SOCIAL TWITTER (TwitterAutoConfiguration)

- `spring.social.twitter.app-id=` — 您的应用程序的 Twitter App ID
- `spring.social.twitter.app-secret=` — 您的应用程序的 Twitter App Secret

### SPRING MOBILE SITE PREFERENCE (SitePreferenceAutoConfiguration)

- `spring.mobile.sitepreference.enabled=true` — 默认启用

### SPRING MOBILE DEVICE VIEWS (DeviceDelegatingViewResolverAutoConfiguration)

- `spring.mobile.devicedelegatingviewresolver.enabled=true` — 默认禁用
- `spring.mobile.devicedelegatingviewresolver.normal-prefix=`
- `spring.mobile.devicedelegatingviewresolver.normal-suffix=`
- `spring.mobile.devicedelegatingviewresolver.mobile-prefix=mobile/`
- `spring.mobile.devicedelegatingviewresolver.mobile-suffix=`
- `spring.mobile.devicedelegatingviewresolver.tablet-prefix=tablet/`
- `spring.mobile.devicedelegatingviewresolver.tablet-suffix=`

## ACTUATOR PROPERTIES

### MANAGEMENT HTTP SERVER (ManagementServerProperties)

- `management.port=` — 默认为 `server.port`
- `management.address=` — 绑定到特定的 NIC
- `management.context-path=` — 默认为 `/`
- `management.add-application-context-header=` — 默认为 `true`
- `management.security.enabled=true` — 启用安全
- `management.security.role=ADMIN` — 访问管理端点所需的角色
- `management.security.sessions=stateless` — 要使用的会话创建策略（`always`, `never`, `if_required`, `stateless`）

### PID FILE (ApplicationPidFileWriter)

- `spring.pidfile=` — 要写入的 PID 文件位置

### ENDPOINTS (AbstractEndpoint subclasses)

- `endpoints.autoconfig.id=autoconfig`
- `endpoints.autoconfig.sensitive=true`
- `endpoints.autoconfig.enabled=true`
- `endpoints.beans.id=beans`
- `endpoints.beans.sensitive=true`
- `endpoints.beans.enabled=true`
- `endpoints.configprops.id=configprops`
- `endpoints.configprops.sensitive=true`
- `endpoints.configprops.enabled=true`
- `endpoints.configprops.keys-to-sanitize=password,secret,key` — 后缀或正则表达式
- `endpoints.dump.id=dump`
- `endpoints.dump.sensitive=true`
- `endpoints.dump.enabled=true`
- `endpoints.env.id=env`
- `endpoints.env.sensitive=true`
- `endpoints.env.enabled=true`
- `endpoints.env.keys-to-sanitize=password,secret,key` — 后缀或正则表达式
- `endpoints.health.id=health`
- `endpoints.health.sensitive=true`
- `endpoints.health.enabled=true`
- `endpoints.health.mapping.*=` — 健康状态到 `HttpStatus` 代码的映射
- `endpoints.health.time-to-live=1000`
- `endpoints.info.id=info`
- `endpoints.info.sensitive=false`
- `endpoints.info.enabled=true`
- `endpoints.mappings.enabled=true`
- `endpoints.mappings.id=mappings`
- `endpoints.mappings.sensitive=true`
- `endpoints.metrics.id=metrics`
- `endpoints.metrics.sensitive=true`
- `endpoints.metrics.enabled=true`
- `endpoints.shutdown.id=shutdown`
- `endpoints.shutdown.sensitive=true`
- `endpoints.shutdown.enabled=false`
- `endpoints.trace.id=trace`
- `endpoints.trace.sensitive=true`
- `endpoints.trace.enabled=true`

### HEALTH INDICATORS (previously health.*)

- `management.health.db.enabled=true`
- `management.health.elasticsearch.enabled=true`
- `management.health.elasticsearch.response-timeout=100` — 等待集群响应的毫秒数
- `management.health.diskspace.enabled=true`
- `management.health.diskspace.path=.`
- `management.health.diskspace.threshold=10485760`
- `management.health.mongo.enabled=true`
- `management.health.rabbit.enabled=true`
- `management.health.redis.enabled=true`
- `management.health.solr.enabled=true`
- `management.health.status.order=DOWN, OUT_OF_SERVICE, UNKNOWN, UP`

### MVC ONLY ENDPOINTS

- `endpoints.jolokia.path=jolokia`
- `endpoints.jolokia.sensitive=true`
- `endpoints.jolokia.enabled=true` — 使用 Jolokia 时

### JMX ENDPOINT (EndpointMBeanExportProperties)

- `endpoints.jmx.enabled=true`
- `endpoints.jmx.domain=` — JMX 域，默认为 `org.springboot`
- `endpoints.jmx.unique-names=false`
- `endpoints.jmx.static-names=`

### JOLOKIA (JolokiaProperties)

- `jolokia.config.*=` — 参见 Jolokia 手册

### REMOTE SHELL

- `shell.auth=simple` — `jaas`, `key`, `simple`, `spring`
- `shell.command-refresh-interval=-1`
- `shell.command-path-patterns=` — `classpath*:/commands/**`, `classpath*:/crash/commands/**`
- `shell.config-path-patterns=` — `classpath*:/crash/*`
- `shell.disabled-commands=jpa*,jdbc*,jndi*` — 要禁用的命令列表（逗号分隔）
- `shell.disabled-plugins=false` — 不暴露插件
- `shell.ssh.enabled=` — SSH 设置...
- `shell.ssh.key-path=`
- `shell.ssh.port=`
- `shell.telnet.enabled=` — Telnet 设置...
- `shell.telnet.port=`
- `shell.auth.jaas.domain=` — 身份验证设置...
- `shell.auth.key.path=`
- `shell.auth.simple.user.name=`
- `shell.auth.simple.user.password=`
- `shell.auth.spring.roles=`

### SENDGRID (SendGridAutoConfiguration)

- `spring.sendgrid.username=` — SendGrid 账户用户名
- `spring.sendgrid.password=` — SendGrid 账户密码
- `spring.sendgrid.proxy.host=` — SendGrid 代理主机
- `spring.sendgrid.proxy.port=` — SendGrid 代理端口

### GIT INFO

- `spring.git.properties=` — 生成的 git info 属性文件的资源引用



# 附录 B. 配置元数据

Spring Boot jars 包含元数据文件，它们提供了所有支持的配置属性详情。这些文件设计用于让 IDE 开发者能够为使用 `application.properties` 或 `application.yml` 文件的用户提供上下文帮助及代码完成功能。

主要的元数据文件是在编译器通过处理所有被`@ConfigurationProperties`注解的节点来自动生成的。

## 附录 B.1. 元数据格式

配置元数据位于 jars 文件中的`META-INF/spring-configuration-metadata.json`，它们使用一个具有"groups"或"properties"分类节点的简单 JSON 格式：

```java
{"groups": [
    {
        "name": "server",
        "type": "org.springframework.boot.autoconfigure.web.ServerProperties",
        "sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
    }
    ...
],"properties": [
    {
        "name": "server.port",
        "type": "java.lang.Integer",
        "sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
    },
    {
        "name": "server.servlet-path",
        "type": "java.lang.String",
        "sourceType": "org.springframework.boot.autoconfigure.web.ServerProperties"
        "defaultValue": "/"
    }
    ...
]} 
```

每个"property"是一个配置节点，用户可以使用特定的值指定它。例如，`server.port`和`server.servlet-path`可能在`application.properties`中如以下定义：

```java
server.port=9090
server.servlet-path=/home 
```

"groups"是高级别的节点，它们本身不指定一个值，但为 properties 提供一个有上下文关联的分组。例如，`server.port`和`server.servlet-path`属性是`server`组的一部分。

**注**：不需要每个"property"都有一个"group"，一些属性可以以自己的形式存在。

### 附录 B.1.1. Group 属性

`groups`数组包含的 JSON 对象可以由以下属性组成：

| 名称 | 类型 | 目的 |
| --- | --- | --- |
| name | String | group 的全名，该属性是强制性的 |
| type | String | group 数据类型的类名。例如，如果 group 是基于一个被`@ConfigurationProperties`注解的类，该属性将包含该类的全限定名。如果基于一个`@Bean`方法，它将是该方法的返回类型。如果该类型未知，则该属性将被忽略 |
| description | String | 一个简短的 group 描述，用于展示给用户。如果没有可用描述，该属性将被忽略。推荐使用一个简短的段落描述，第一行提供一个简洁的总结，最后一行以句号结尾 |
| sourceType | String | 贡献该组的来源类名。例如，如果组基于一个被`@ConfigurationProperties`注解的`@Bean`方法，该属性将包含`@Configuration`类的全限定名，该类包含此方法。如果来源类型未知，则该属性将被忽略 |
| sourceMethod | String | 贡献该组的方法的全名（包含括号及参数类型）。例如，被`@ConfigurationProperties`注解的`@Bean`方法名。如果源方法未知，该属性将被忽略 |

### 附录 B.1.2. Property 属性

`properties`数组中包含的 JSON 对象可由以下属性构成：

| 名称 | 类型 | 目的 |
| --- | --- | --- |
| name | String | property 的全名，格式为小写虚线分割的形式（比如`server.servlet-path`）。该属性是强制性的 |
| type | String | property 数据类型的类名。例如`java.lang.String`。该属性可以用来指导用户他们可以输入值的类型。为了保持一致，原生类型使用它们的包装类代替，比如`boolean`变成了`java.lang.Boolean`。注意，这个类可能是个从一个字符串转换而来的复杂类型。如果类型未知则该属性会被忽略 |
| description | String | 一个简短的组的描述，用于展示给用户。如果没有描述可用则该属性会被忽略。推荐使用一个简短的段落描述，开头提供一个简洁的总结，最后一行以句号结束 |
| sourceType | String | 贡献 property 的来源类名。例如，如果 property 来自一个被`@ConfigurationProperties`注解的类，该属性将包括该类的全限定名。如果来源类型未知则该属性会被忽略 |
| defaultValue | Object | 当 property 没有定义时使用的默认值。如果 property 类型是个数组则该属性也可以是个数组。如果默认值未知则该属性会被忽略 |
| deprecated | boolean | 指定该 property 是否过期。如果该字段没有过期或该信息未知则该属性会被忽略 |

### 附录 B.1.3. 可重复的元数据节点

在同一个元数据文件中出现多次相同名称的"property"和"group"对象是可以接受的。例如，Spring Boot 将`spring.datasource`属性绑定到 Hikari，Tomcat 和 DBCP 类，并且每个都潜在的提供了重复的属性名。这些元数据的消费者需要确保他们支持这样的场景。

## 附录 B.2. 使用注解处理器产生自己的元数据

通过使用`spring-boot-configuration-processor` jar，你可以从被`@ConfigurationProperties`注解的节点轻松的产生自己的配置元数据文件。该 jar 包含一个在你的项目编译时会被调用的 Java 注解处理器。想要使用该处理器，你只需简单添加`spring-boot-configuration-processor`依赖，例如使用 Maven 你需要添加：

```java
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-configuration-processor</artifactId>
    <optional>true</optional>
</dependency> 
```

使用 Gradle 时，你可以使用[propdeps-plugin](https://github.com/spring-projects/gradle-plugins/tree/master/propdeps-plugin)并指定：

```java
dependencies {
        optional "org.springframework.boot:spring-boot-configuration-processor"
    }

    compileJava.dependsOn(processResources)
} 
```

**注**：你需要将`compileJava.dependsOn(processResources)`添加到构建中，以确保资源在代码编译之前处理。如果没有该指令，任何`additional-spring-configuration-metadata.json`文件都不会被处理。

该处理器会处理被`@ConfigurationProperties`注解的类和方法，description 属性用于产生配置类字段值的 Javadoc 说明。

**注**：你应该使用简单的文本来设置`@ConfigurationProperties`字段的 Javadoc，因为在没有被添加到 JSON 之前它们是不被处理的。

属性是通过判断是否存在标准的 getters 和 setters 来发现的，对于集合类型有特殊处理（即使只出现一个 getter）。该注解处理器也支持使用 lombok 的`@Data`, `@Getter`和`@Setter`注解。

### 附录 B.2.1. 内嵌属性

该注解处理器自动将内部类当做内嵌属性处理。例如，下面的类：

```java
@ConfigurationProperties(prefix="server")
public class ServerProperties {

    private String name;

    private Host host;

    // ... getter and setters

    private static class Host {

        private String ip;

        private int port;

        // ... getter and setters

    }

} 
```

### 附录 B.2.2. 添加其他的元数据

## 附录 C. 自动配置类

这里有一个 Spring Boot 提供的所有自动配置类的文档链接和源码列表。也要记着看一下你的应用都开启了哪些自动配置（使用`--debug`或`-Debug`启动应用，或在一个 Actuator 应用中使用`autoconfig`端点）。

### 附录 C.1 来自`spring-boot-autoconfigure`模块

下面的自动配置类来自`spring-boot-autoconfigure`模块：

| 配置类 | 链接 |
| --- | --- |
| [ActiveMQAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/jms/activemq/ActiveMQAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/jms/activemq/ActiveMQAutoConfiguration.html) |
| [AopAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/aop/AopAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/aop/AopAutoConfiguration.html) |
| [BatchAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/batch/BatchAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/batch/BatchAutoConfiguration.html) |
| [CacheAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/cache/CacheAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/cache/CacheAutoConfiguration.html) |
| [CloudAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/cloud/CloudAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/cloud/CloudAutoConfiguration.html) |
| [DataSourceAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/jdbc/DataSourceAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/jdbc/DataSourceAutoConfiguration.html) |
| [DataSourceTransactionManagerAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/jdbc/DataSourceTransactionManagerAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/jdbc/DataSourceTransactionManagerAutoConfiguration.html) |
| [DeviceDelegatingViewResolverAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/mobile/DeviceDelegatingViewResolverAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/mobile/DeviceDelegatingViewResolverAutoConfiguration.html) |



| [DeviceResolverAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/mobile/DeviceResolverAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/mobile/DeviceResolverAutoConfiguration.html) |

| [DispatcherServletAutoConfiguration](http://github.com/spring-projects/spring-boot/tree/master/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/web/DispatcherServletAutoConfiguration.java) | [javadoc](http://docs.spring.io/spring-boot/docs/1.3.0.BUILD-SNAPSHOT/api/org/springframework/boot/autoconfigure/web/DispatcherServletAutoConfiguration.html) |

# 附录 C.2 来自 `spring-boot-actuator` 模块

下列的自动配置类来自于 `spring-boot-actuator` 模块：

# 附录 D. 可执行 jar 格式

`spring-boot-loader` 模块允许 Spring Boot 对可执行 jar 和 war 文件的支持。如果你正在使用 Maven 或 Gradle 插件，可执行 jar 会被自动产生，通常你不需要了解它是如何工作的。

如果你需要从一个不同的构建系统创建可执行 jars，或你只是对底层技术好奇，本章节将提供一些背景资料。

# 附录 D.1 内嵌 JARs

Java 没有提供任何标准的方式来加载内嵌的 jar 文件（也就是 jar 文件自身包含到一个 jar 中）。如果你正分发一个在不解压缩的情况下可以从命令行运行的自包含应用，那这将是个问题。

为了解决这个问题，很多开发者使用"影子" jars。一个影子 jar 只是简单的将所有 jars 的类打包进一个单独的"超级 jar"。使用影子 jars 的问题是它很难分辨在你的应用中实际可以使用的库。在多个 jars 中存在相同的文件名（内容不同）也是一个问题。Spring Boot 另劈稀径，让你能够直接嵌套 jars。

# 附录 D.1.1 可执行 jar 文件结构

Spring Boot Loader 兼容的 jar 文件应该遵循以下结构：

```java
example.jar
 |
 +-META-INF
 |  +-MANIFEST.MF
 +-org
 |  +-springframework
 |     +-boot
 |        +-loader
 |           +-<spring boot loader classes>
 +-com
 |  +-mycompany
 |     + project
 |        +-YouClasses.class
 +-lib
    +-dependency1.jar
    +-dependency2.jar 
```

依赖需要放到内部的 `lib` 目录下。

# 附录 D.1.2 可执行 war 文件结构

Spring Boot Loader 兼容的 war 文件应该遵循以下结构：

```java
example.jar
 |
 +-META-INF
 |  +-MANIFEST.MF
 +-org
 |  +-springframework
 |     +-boot
 |        +-loader
 |           +-<spring boot loader classes>
 +-WEB-INF
    +-classes
    |  +-com
    |     +-mycompany
    |        +-project
    |           +-YouClasses.class
    +-lib
    |  +-dependency1.jar
    |  +-dependency2.jar
    +-lib-provided
       +-servlet-api.jar
       +-dependency3.jar 
```

依赖需要放到内嵌的 `WEB-INF/lib` 目录下。任何运行时需要但部署到普通 web 容器不需要的依赖应该放到 `WEB-INF/lib-provided` 目录下。

# 附录 D.2 Spring Boot 的 "JarFile" 类

Spring Boot 用于支持加载内嵌 jars 的核心类是 `org.springframework.boot.loader.jar.JarFile`。它允许你从一个标准的 jar 文件或内嵌的子 jar 数据中加载 jar 内容。当首次加载的时候，每个 `JarEntry` 的位置被映射到一个偏移于外部 jar 的物理文件：

```java
myapp.jar
+---------+---------------------+
|         | /lib/mylib.jar      |
| A.class |+---------+---------+|
|         || B.class | B.class ||
|         |+---------+---------+|
+---------+---------------------+
^          ^          ^
0063       3452       3980 
```

上面的示例展示了如何在 `myapp.jar` 的 0063 处找到 `A.class`。来自于内嵌 jar 的 `B.class` 实际可以在 `myapp.jar` 的 3452 处找到，`B.class` 可以在 3980 处找到（图有问题？）。

有了这些信息，我们就可以通过简单的寻找外部 jar 的合适部分来加载指定的内嵌实体。我们不需要解压存档，也不需要将所有实体读取到内存中。

# 附录 D.2.1 对标准 Java "JarFile" 的兼容性

Spring Boot Loader 努力保持对已有代码和库的兼容。`org.springframework.boot.loader.jar.JarFile` 继承自 `java.util.jar.JarFile`，可以作为降级替换。

# 附录 D.3 启动可执行 jars

`org.springframework.boot.loader.Launcher` 类是个特殊的启动类，用于一个可执行 jars 的主要入口。它实际上就是你 jar 文件的 `Main-Class`，并用来设置一个合适的 `URLClassLoader`，最后调用你的 `main()` 方法。

这里有３个启动器子类，`JarLauncher`，`WarLauncher` 和 `PropertiesLauncher`。它们的作用是从嵌套的 jar 或 war 文件目录中（相对于显示的从 classpath）加载资源（`.class` 文件等）。在 `[Jar|War]Launcher` 情况下，嵌套路径是固定的（`lib/*.jar` 和 war 的 `lib-provided/*.jar`），所以如果你需要很多其他 jars 只需添加到那些位置即可。`PropertiesLauncher` 默认查找你应用存档的 `lib/` 目录，但你可以通过设置环境变量 `LOADER_PATH` 或 `application.properties` 中的 `loader.path` 来添加其他的位置（逗号分割的目录或存档列表）。

# 附录 D.3.1 Launcher manifest

你需要指定一个合适的 Launcher 作为 `META-INF/MANIFEST.MF` 的 `Main-Class` 属性。你实际想要启动的类（也就是你编写的包含 `main` 方法的类）需要在 `Start-Class` 属性中定义。

例如，这里有个典型的可执行 jar 文件的 `MANIFEST.MF`：

```java
Main-Class: org.springframework.boot.loader.JarLauncher
Start-Class: com.mycompany.project.MyApplication 
```

对于一个 war 文件，它可能是这样的：

```java
Main-Class: org.springframework.boot.loader.WarLauncher
Start-Class: com.mycompany.project.MyApplication 
```

**注**：你不需要在 manifest 文件中指定 `Class-Path` 实体，classpath 会从嵌套的 jars 中被推导出来。

# 附录 D.3.2 暴露的存档

一些 PaaS 实现可能选择在运行前先解压存档。例如，Cloud Foundry 就是这样操作的。你可以运行一个解压的存档，只需简单的启动合适的启动器：

```java
$ unzip -q myapp.jar
$ java org.springframework.boot.loader.JarLaunche 
```

# 附录 D.4 PropertiesLauncher 特性

`PropertiesLauncher` 有一些特殊的性质，它们可以通过外部属性来启用（系统属性，环境变量，manifest 实体或 `application.properties`）。

| Key | 作用 |

| --- | --- |

| `loader.path` | 逗号分割的 classpath，比如 `lib:${HOME}/app/lib` |

| `loader.home` | 其他属性文件的位置，比如 `/opt/app`（默认为 `${user.dir}`） |

| `loader.args` | `main` 方法的默认参数（以空格分割） |

| `loader.main` | 要启动的 main 类名称，比如 `com.app.Application` |

| `loader.config.name` | 属性文件名，比如 `loader`（默认为 `application`） |

| `loader.config.location` | 属性文件路径，比如 `classpath:loader.properties`（默认为 `application.properties`） |

| `loader.system` | 布尔标识，表明所有的属性都应该添加到系统属性中（默认为 `false`） |

Manifest 实体 keys 通过大写单词首字母及将分隔符从 "." 改为 "-"（比如 `Loader-Path`）来进行格式化。`loader.main` 是个特例，它是通过查找 manifest 的 `Start-Class`，这样也兼容 `JarLauncher`。

环境变量可以大写字母并且用下划线代替句号。

* `loader.home` 是其他属性文件（覆盖默认）的目录位置，只要没有指定 `loader.config.location`。

* `loader.path` 可以包含目录（递归地扫描 jar 和 zip 文件），存档路径或通配符模式（针对默认的 JVM 行为）。

* 占位符在使用前会被系统和环境变量加上属性文件本身的值替换掉。

# 附录 D.5 可执行 jar 的限制

当使用 Spring Boot Loader 打包的应用时有一些你需要考虑的限制。

# 附录 D.5.1 Zip 实体压缩

对于一个嵌套 jar 的 `ZipEntry` 必须使用 `ZipEntry.STORED` 方法保存。这是需要的，这样我们可以直接查找嵌套 jar 中的个别内容。嵌套 jar 的内容本身可以仍旧被压缩，正如外部 jar 的其他任何实体。

# 附录 D.5.2 系统 ClassLoader

启动的应用在加载类时应该使用 `Thread.getContextClassLoader()`（多数库和框架都默认这样做）。尝试通过 `ClassLoader.getSystemClassLoader()` 加载嵌套的类将失败。请注意 `java.util.Logging` 总是使用系统类加载器，由于这个原因你需要考虑一个不同的日志实现。

# 附录 D.6 可替代的单一 jar 解决方案

如果以上限制造成你不能使用 Spring Boot Loader，那可以考虑以下的替代方案：

* [Maven Shade Plugin](http://maven.apache.org/plugins/maven-shade-plugin/)

* [JarClassLoader](http://www.jdotsoft.com/JarClassLoader.php)

* [OneJar](http://one-jar.sourceforge.net/)

# 附录 E. 依赖版本

下面的表格提供了详尽的依赖版本信息，这些版本由 Spring Boot 自身的 CLI，Maven 的依赖管理（dependency management）和 Gradle 插件提供。当你声明一个对以下 artifacts 的依赖而没有声明版本时，将使用下面表格中列出的版本。
