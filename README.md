# nexus

## nexus란?

> Nexus는 JavaScript 패키지를 저장, 관리 및 공유하기 위한 오픈소스 프로젝트 관리 도구입니다.
> 
> Nexus는 npm, Docker, Bower, Maven, RubyGems 등 다양한 패키지 매니저를 지원하며, 이를 통해 패키지 저장소를 관리할 수 있습니다. Nexus는 패키지 저장소에 패키지를 업로드하고 검색할 수 있는 웹 인터페이스를 제공하며, 이를 통해 팀 내에서 패키지를 공유하고 재사용할 수 있습니다.
> 
> 또한, Nexus는 팀 내에서 공유하는 패키지를 관리할 수 있도록 보안 기능도 제공합니다. Nexus는 패키지 업로드 및 다운로드에 대한 권한을 지정할 수 있으며, 패키지 저장소에 업로드된 패키지의 무결성을 검증할 수도 있습니다.
> @chatGPT

## 설치하기

```bash
docker-compose up -d
```

설치를 완료하고 http://localhost:8081로 접속합니다. `sign in` 클릭

- id: admin
- passwd: 커맨드라인에서 `make passwd`

## nexus 설정하기

npm 배포를 위해서 로그인하기 https://help.sonatype.com/repomanager3/nexus-repository-administration/user-authentication/realms#Realms-npmBearerTokenRealm

```
npm adduser --auth-type=legacy --registry=http://localhost:8081/repository/npm-internal/
```

## next error

```log
nexus3_1  | 2023-05-10 06:56:57,213+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder - Properties:
nexus3_1  | 2023-05-10 06:56:57,214+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   application-conf='/sonatype-work/conf'
nexus3_1  | 2023-05-10 06:56:57,214+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   application-host='0.0.0.0'
nexus3_1  | 2023-05-10 06:56:57,214+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   application-port='8081'
nexus3_1  | 2023-05-10 06:56:57,214+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   bundleBasedir='/opt/sonatype/nexus'
nexus3_1  | 2023-05-10 06:56:57,214+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   java.awt.headless='true'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   networkaddress.cache.ttl='3600'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   nexus-app='/opt/sonatype/nexus/nexus/WEB-INF'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   nexus-webapp='/opt/sonatype/nexus/nexus'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   nexus-webapp-context-path='/nexus'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   nexus-work='/sonatype-work'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   org.eclipse.ecf.provider.filetransfer.retrieve.readTimeout='30000'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   runtime='/opt/sonatype/nexus/nexus/WEB-INF'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   security-xml-file='/sonatype-work/conf/security.xml'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.ConfigurationBuilder -   storage.diskCache.bufferSize='4096'
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.Launcher - Java: 1.8.0_322, OpenJDK 64-Bit Server VM, Red Hat, Inc., 25.322-b06
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.Launcher - OS: Linux, 5.15.74-1-pve, amd64
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.Launcher - User: nexus, en, /sonatype-work
nexus3_1  | 2023-05-10 06:56:57,215+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.Launcher - CWD: /opt/sonatype/nexus
nexus3_1  | 2023-05-10 06:56:57,224+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.Launcher - TMP: /tmp
nexus3_1  | 2023-05-10 06:56:57,225+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.jetty.JettyServer - Starting
nexus3_1  | 2023-05-10 06:56:57,231+0000 INFO  [main] *SYSTEM org.eclipse.jetty.util.log - Logging initialized @215ms to org.eclipse.jetty.util.log.Slf4jLog
nexus3_1  | 2023-05-10 06:56:57,235+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.jetty.JettyServer - Applying configuration: file:/opt/sonatype/nexus/conf/jetty.xml
nexus3_1  | 2023-05-10 06:56:57,373+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.jetty.JettyServer - Applying configuration: file:/opt/sonatype/nexus/conf/jetty-requestlog.xml
nexus3_1  | 2023-05-10 06:56:57,380+0000 INFO  [main] *SYSTEM org.sonatype.nexus.bootstrap.jetty.JettyServer - Applying configuration: file:/opt/sonatype/nexus/conf/jetty-http.xml
nexus3_1  | 2023-05-10 06:56:57,405+0000 INFO  [jetty-main-1]  org.sonatype.nexus.bootstrap.jetty.JettyServer - Starting: Server@17baae6e{STOPPED}[9.4.45.v20220203]
nexus3_1  | 2023-05-10 06:56:57,408+0000 INFO  [jetty-main-1]  org.eclipse.jetty.server.Server - jetty-9.4.45.v20220203; built: 2022-02-03T09:14:34.105Z; git: 4a0c91c0be53805e3fcffdcdcc9587d5301863db; jvm 1.8.0_322-b06
nexus3_1  | 2023-05-10 06:56:57,617+0000 INFO  [jetty-main-1]  org.eclipse.jetty.server.session - DefaultSessionIdManager workerName=node0
nexus3_1  | 2023-05-10 06:56:57,617+0000 INFO  [jetty-main-1]  org.eclipse.jetty.server.session - No SessionScavenger set, using defaults
nexus3_1  | 2023-05-10 06:56:57,619+0000 INFO  [jetty-main-1]  org.eclipse.jetty.server.session - node0 Scavenging every 660000ms
nexus3_1  | 2023-05-10 06:56:57,625+0000 INFO  [jetty-main-1]  org.sonatype.nexus.webapp.WebappBootstrap - Initializing
nexus3_1  | 2023-05-10 06:56:57,625+0000 INFO  [jetty-main-1]  org.sonatype.nexus.webapp.WebappBootstrap - Using bootstrap launcher configuration
nexus3_1  | 2023-05-10 06:56:57,631+0000 WARN  [jetty-main-1]  org.sonatype.nexus.util.LockFile - Failed to write lock file
nexus3_1  | java.io.FileNotFoundException: /sonatype-work/nexus.lock (Permission denied)
nexus3_1  |     at java.io.RandomAccessFile.open0(Native Method)
nexus3_1  |     at java.io.RandomAccessFile.open(RandomAccessFile.java:316)
nexus3_1  |     at java.io.RandomAccessFile.<init>(RandomAccessFile.java:243)
nexus3_1  |     at org.sonatype.nexus.util.LockFile.lock(LockFile.java:92)
nexus3_1  |     at org.sonatype.nexus.webapp.WebappBootstrap.contextInitialized(WebappBootstrap.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.callContextInitialized(ContextHandler.java:1073)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.callContextInitialized(ServletContextHandler.java:572)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.contextInitialized(ContextHandler.java:1002)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletHandler.initialize(ServletHandler.java:746)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.startContext(ServletContextHandler.java:379)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startWebapp(WebAppContext.java:1449)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startContext(WebAppContext.java:1414)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.doStart(ContextHandler.java:916)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.doStart(ServletContextHandler.java:288)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.doStart(WebAppContext.java:524)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at com.codahale.metrics.jetty9.InstrumentedHandler.doStart(InstrumentedHandler.java:92)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.server.Server.start(Server.java:423)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.server.Server.doStart(Server.java:387)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.sonatype.nexus.bootstrap.jetty.JettyServer$JettyMainThread.run(JettyServer.java:247)
nexus3_1  | 2023-05-10 06:56:57,631+0000 ERROR [jetty-main-1]  org.sonatype.nexus.webapp.WebappBootstrap - Failed to initialize
nexus3_1  | java.lang.IllegalStateException: Nexus work directory already in use: /sonatype-work
nexus3_1  |     at com.google.common.base.Preconditions.checkState(Preconditions.java:200)
nexus3_1  |     at org.sonatype.nexus.webapp.WebappBootstrap.contextInitialized(WebappBootstrap.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.callContextInitialized(ContextHandler.java:1073)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.callContextInitialized(ServletContextHandler.java:572)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.contextInitialized(ContextHandler.java:1002)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletHandler.initialize(ServletHandler.java:746)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.startContext(ServletContextHandler.java:379)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startWebapp(WebAppContext.java:1449)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startContext(WebAppContext.java:1414)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.doStart(ContextHandler.java:916)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.doStart(ServletContextHandler.java:288)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.doStart(WebAppContext.java:524)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at com.codahale.metrics.jetty9.InstrumentedHandler.doStart(InstrumentedHandler.java:92)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.server.Server.start(Server.java:423)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.server.Server.doStart(Server.java:387)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.sonatype.nexus.bootstrap.jetty.JettyServer$JettyMainThread.run(JettyServer.java:247)
nexus3_1  | 2023-05-10 06:56:57,632+0000 WARN  [jetty-main-1]  org.eclipse.jetty.webapp.WebAppContext - Failed startup of context o.e.j.w.WebAppContext@220c2549{Nexus Repository Manager 2.15.1-02,/nexus,file:///opt/sonatype/nexus/nexus/,UNAVAILABLE}{/opt/sonatype/nexus/nexus}
nexus3_1  | java.lang.IllegalStateException: Nexus work directory already in use: /sonatype-work
nexus3_1  |     at com.google.common.base.Preconditions.checkState(Preconditions.java:200)
nexus3_1  |     at org.sonatype.nexus.webapp.WebappBootstrap.contextInitialized(WebappBootstrap.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.callContextInitialized(ContextHandler.java:1073)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.callContextInitialized(ServletContextHandler.java:572)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.contextInitialized(ContextHandler.java:1002)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletHandler.initialize(ServletHandler.java:746)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.startContext(ServletContextHandler.java:379)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startWebapp(WebAppContext.java:1449)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startContext(WebAppContext.java:1414)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.doStart(ContextHandler.java:916)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.doStart(ServletContextHandler.java:288)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.doStart(WebAppContext.java:524)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at com.codahale.metrics.jetty9.InstrumentedHandler.doStart(InstrumentedHandler.java:92)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.server.Server.start(Server.java:423)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.server.Server.doStart(Server.java:387)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.sonatype.nexus.bootstrap.jetty.JettyServer$JettyMainThread.run(JettyServer.java:247)
nexus3_1  | 2023-05-10 06:56:57,633+0000 INFO  [jetty-main-1]  org.eclipse.jetty.server.session - node0 Stopped scavenging
nexus3_1  | 2023-05-10 06:56:57,634+0000 INFO  [jetty-main-1]  org.sonatype.nexus.bootstrap.jetty.JettyServer - Running
nexus3_1  | 2023-05-10 06:56:57,634+0000 ERROR [main] *SYSTEM org.sonatype.nexus.bootstrap.jetty.JettyServer - Start failed
nexus3_1  | java.lang.IllegalStateException: Nexus work directory already in use: /sonatype-work
nexus3_1  |     at com.google.common.base.Preconditions.checkState(Preconditions.java:200)
nexus3_1  |     at org.sonatype.nexus.webapp.WebappBootstrap.contextInitialized(WebappBootstrap.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.callContextInitialized(ContextHandler.java:1073)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.callContextInitialized(ServletContextHandler.java:572)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.contextInitialized(ContextHandler.java:1002)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletHandler.initialize(ServletHandler.java:746)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.startContext(ServletContextHandler.java:379)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startWebapp(WebAppContext.java:1449)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startContext(WebAppContext.java:1414)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.doStart(ContextHandler.java:916)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.doStart(ServletContextHandler.java:288)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.doStart(WebAppContext.java:524)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at com.codahale.metrics.jetty9.InstrumentedHandler.doStart(InstrumentedHandler.java:92)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.server.Server.start(Server.java:423)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.server.Server.doStart(Server.java:387)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.sonatype.nexus.bootstrap.jetty.JettyServer$JettyMainThread.run(JettyServer.java:247)
nexus3_1  | Exception in thread "main" java.lang.IllegalStateException: Nexus work directory already in use: /sonatype-work
nexus3_1  |     at com.google.common.base.Preconditions.checkState(Preconditions.java:200)
nexus3_1  |     at org.sonatype.nexus.webapp.WebappBootstrap.contextInitialized(WebappBootstrap.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.callContextInitialized(ContextHandler.java:1073)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.callContextInitialized(ServletContextHandler.java:572)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.contextInitialized(ContextHandler.java:1002)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletHandler.initialize(ServletHandler.java:746)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.startContext(ServletContextHandler.java:379)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startWebapp(WebAppContext.java:1449)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.startContext(WebAppContext.java:1414)
nexus3_1  |     at org.eclipse.jetty.server.handler.ContextHandler.doStart(ContextHandler.java:916)
nexus3_1  |     at org.eclipse.jetty.servlet.ServletContextHandler.doStart(ServletContextHandler.java:288)
nexus3_1  |     at org.eclipse.jetty.webapp.WebAppContext.doStart(WebAppContext.java:524)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at com.codahale.metrics.jetty9.InstrumentedHandler.doStart(InstrumentedHandler.java:92)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:117)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.start(ContainerLifeCycle.java:169)
nexus3_1  |     at org.eclipse.jetty.server.Server.start(Server.java:423)
nexus3_1  |     at org.eclipse.jetty.util.component.ContainerLifeCycle.doStart(ContainerLifeCycle.java:110)
nexus3_1  |     at org.eclipse.jetty.server.handler.AbstractHandler.doStart(AbstractHandler.java:97)
nexus3_1  |     at org.eclipse.jetty.server.Server.doStart(Server.java:387)
nexus3_1  |     at org.eclipse.jetty.util.component.AbstractLifeCycle.start(AbstractLifeCycle.java:73)
nexus3_1  |     at org.sonatype.nexus.bootstrap.jetty.JettyServer$JettyMainThread.run(JettyServer.java:247)
```

바인딩된 폴더의 유저권한문재 - 참고 https://www.programmersought.com/article/42391018475/

```
chown -R 200:200 nexus-data
```
