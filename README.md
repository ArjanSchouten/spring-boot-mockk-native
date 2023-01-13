# Spring boot 3.0.x with MockkExtension fails

```bash
./gradlew clean nativeTest                                        

> Task :processTestAot
18:00:45.399 [main] INFO org.springframework.test.context.aot.TestClassScanner - Scanning for Spring test classes in all packages in classpath roots [/mypath/spring-boot-mockk-native/build/classes/kotlin/test]
18:00:45.569 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.web.ServletTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [jakarta/servlet/ServletContext]
18:00:45.571 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.transaction.TransactionalTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [org/springframework/transaction/interceptor/TransactionAttributeSource]
18:00:45.572 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.jdbc.SqlScriptsTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [org/springframework/transaction/interceptor/TransactionAttribute]
18:00:45.573 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Using TestExecutionListeners for test class [DemoApplicationTests]: [DirtiesContextBeforeModesTestExecutionListener, ApplicationEventsTestExecutionListener, MockitoTestExecutionListener, DependencyInjectionTestExecutionListener, DirtiesContextTestExecutionListener, EventPublishingTestExecutionListener, RestDocsTestExecutionListener, MockRestServiceServerResetTestExecutionListener, MockMvcPrintOnlyOnFailureTestExecutionListener, WebDriverTestExecutionListener, MockWebServiceServerTestExecutionListener, ResetMocksTestExecutionListener]
18:00:45.576 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Neither @ContextConfiguration nor @ContextHierarchy found for test class [DemoApplicationTests]: using SpringBootContextLoader
18:00:45.577 [main] DEBUG org.springframework.test.context.support.AbstractContextLoader - Could not detect default resource locations for test class [com.example.demo.DemoApplicationTests]: no resource found for suffixes {-context.xml, Context.groovy}.
18:00:45.577 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils - Could not detect default configuration classes for test class [com.example.demo.DemoApplicationTests]: DemoApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
18:00:45.588 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Using ContextCustomizers for test class [DemoApplicationTests]: [DisableObservabilityContextCustomizer, PropertyMappingContextCustomizer, Customizer, ExcludeFilterContextCustomizer, DuplicateJsonObjectContextCustomizer, MockitoContextCustomizer, TestRestTemplateContextCustomizer]
18:00:45.614 [main] DEBUG org.springframework.context.annotation.ClassPathScanningCandidateComponentProvider - Identified candidate component class: file [/mypath/spring-boot-mockk-native/build/classes/kotlin/main/com/example/demo/DemoApplication.class]
18:00:45.627 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Found @SpringBootConfiguration com.example.demo.DemoApplication for test class com.example.demo.DemoApplicationTests
18:00:45.661 [main] DEBUG org.springframework.test.context.aot.TestContextAotGenerator - Generating AOT artifacts for test classes [com.example.demo.DemoApplicationTests]

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.0.1)

2023-01-13T18:00:45.786+01:00  INFO 20254 --- [           main] com.example.demo.DemoApplicationTests    : Starting DemoApplicationTests using Java 17.0.5 with PID 20254 (/mypath/spring-boot-mockk-native/build/classes/kotlin/test started by  in /mypath/spring-boot-mockk-native)
2023-01-13T18:00:45.786+01:00  INFO 20254 --- [           main] com.example.demo.DemoApplicationTests    : No active profile set, falling back to 1 default profile: "default"

> Task :test
OpenJDK 64-Bit Server VM warning: Sharing is only supported for boot loader classes because bootstrap classpath has been appended

> Task :generateTestResourcesConfigFile
[native-image-plugin] Resources configuration written into /mypath/spring-boot-mockk-native/build/native/generated/generateTestResourcesConfigFile/resource-config.json

> Task :nativeTestCompile
[native-image-plugin] GraalVM Toolchain detection is disabled
[native-image-plugin] GraalVM location read from environment variable: JAVA_HOME
[native-image-plugin] Native Image executable path: /Users//.sdkman/candidates/java/22.3.r17-grl/lib/svm/bin/native-image
========================================================================================================================
GraalVM Native Image: Generating 'demo-tests' (executable)...
========================================================================================================================
[1/7] Initializing...                                                                                    (5,4s @ 0,29GB)
 Version info: 'GraalVM 22.3.0 Java 17 CE'
 Java version info: '17.0.5+8-jvmci-22.3-b08'
 C compiler: cc (apple, arm64, 14.0.0)
 Garbage collector: Serial GC
 2 user-specific feature(s)
 - org.graalvm.junit.platform.JUnitPlatformFeature
 - org.springframework.aot.nativex.feature.PreComputeFieldFeature
[junit-platform-native] Running in 'test listener' mode using files matching pattern [junit-platform-unique-ids*] found in folder [/mypath/spring-boot-mockk-native/build/test-results/test/testlist] and its subfolders.
Field org.springframework.test.context.web.socket.MockServerContainerContextCustomizerFactory#webSocketPresent set to false at build time
Field org.apache.commons.logging.LogAdapter#log4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#log4jSlf4jProviderPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jSpiPresent set to true at build time
Field org.apache.commons.logging.LogAdapter#slf4jApiPresent set to true at build time
Field org.springframework.boot.logging.log4j2.Log4J2LoggingSystem$Factory#PRESENT set to false at build time
Field org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener#MOCKITO_IS_PRESENT set to false at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#reactorClientPresent set to false at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#jettyClientPresent set to false at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#httpComponentsClientPresent set to false at build time
Field org.springframework.boot.test.web.reactive.server.WebTestClientContextCustomizerFactory#webClientPresent set to false at build time
Field org.springframework.boot.logging.java.JavaLoggingSystem$Factory#PRESENT set to true at build time
Field org.springframework.core.NativeDetector#imageCode set to true at build time
Field org.springframework.core.KotlinDetector#kotlinPresent set to true at build time
Field org.springframework.core.KotlinDetector#kotlinReflectPresent set to true at build time
Field org.springframework.format.support.DefaultFormattingConversionService#jsr354Present set to false at build time
Field org.springframework.cglib.core.AbstractClassGenerator#imageCode set to true at build time
Field org.springframework.boot.logging.logback.LogbackLoggingSystemProperties#JBOSS_LOGGING_PRESENT set to false at build time
Field org.springframework.context.event.ApplicationListenerMethodAdapter#reactiveStreamsPresent set to false at build time
[2/7] Performing analysis...  [******]                                                                  (25,4s @ 3,28GB)
  15.458 (92,29%) of 16.750 classes reachable
  22.474 (69,27%) of 32.445 fields reachable
  67.918 (59,95%) of 113.288 methods reachable
     530 classes,   140 fields, and 2.076 methods registered for reflection
      64 classes,    71 fields, and    55 methods registered for JNI access
       5 native libraries: -framework CoreServices, -framework Foundation, dl, pthread, z
[3/7] Building universe...                                                                               (3,1s @ 1,91GB)
[4/7] Parsing methods...      [**]                                                                       (2,7s @ 1,60GB)
[5/7] Inlining methods...     [***]                                                                      (0,9s @ 3,55GB)
[6/7] Compiling methods...    [****]                                                                    (12,6s @ 1,46GB)
[7/7] Creating image...                                                                                  (4,5s @ 3,62GB)
  27,56MB (48,66%) for code area:    43.065 compilation units
  28,38MB (50,10%) for image heap:  321.235 objects and 98 resources
 718,29KB ( 1,24%) for other data
  56,64MB in total
------------------------------------------------------------------------------------------------------------------------
Top 10 packages in code area:                               Top 10 object types in image heap:
   1,00MB java.util                                            5,84MB byte[] for code metadata
 683,68KB java.lang.invoke                                     3,76MB java.lang.Class
 618,96KB kotlin.reflect.jvm.internal.impl.metadata            3,21MB byte[] for java.lang.String
 528,86KB java.lang                                            3,14MB java.lang.String
 474,24KB c.s.org.apache.xerces.internal.impl.xs.traversers    2,32MB byte[] for general heap data
 426,72KB com.sun.crypto.provider                              1,30MB com.oracle.svm.core.hub.DynamicHubCompanion
 419,13KB com.sun.org.apache.xerces.internal.impl            824,89KB byte[] for embedded resources
 401,90KB java.util.concurrent                               817,34KB byte[] for reflection metadata
 395,48KB java.io                                            626,41KB java.lang.String[]
 388,51KB jdk.proxy4                                         614,20KB java.util.HashMap$Node
  22,07MB for 621 more packages                                4,99MB for 3035 more object types
------------------------------------------------------------------------------------------------------------------------
                        3,0s (5,0% of total time) in 33 GCs | Peak RSS: 6,25GB | CPU load: 4,58
------------------------------------------------------------------------------------------------------------------------
Produced artifacts:
 /mypath/spring-boot-mockk-native/build/native/nativeTestCompile/demo-tests (executable)
 /mypath/spring-boot-mockk-native/build/native/nativeTestCompile/demo-tests.build_artifacts.txt (txt)
========================================================================================================================
Finished generating 'demo-tests' in 58,3s.
    [native-image-plugin] Native Image written to: /mypath/spring-boot-mockk-native/build/native/nativeTestCompile

> Task :nativeTest
JUnit Platform on Native Image - report
----------------------------------------

18:01:47.118 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Neither @ContextConfiguration nor @ContextHierarchy found for test class [DemoApplicationTests]: using SpringBootContextLoader
18:01:47.119 [main] DEBUG org.springframework.test.context.support.AbstractContextLoader - Could not detect default resource locations for test class [com.example.demo.DemoApplicationTests]: no resource found for suffixes {-context.xml, Context.groovy}.
18:01:47.119 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils - Could not detect default configuration classes for test class [com.example.demo.DemoApplicationTests]: DemoApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
18:01:47.121 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Using ContextCustomizers for test class [DemoApplicationTests]: [DisableObservabilityContextCustomizer, PropertyMappingContextCustomizer, Customizer, ExcludeFilterContextCustomizer, DuplicateJsonObjectContextCustomizer, MockitoContextCustomizer, TestRestTemplateContextCustomizer]
18:01:47.121 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Found @SpringBootConfiguration com.example.demo.DemoApplication for test class com.example.demo.DemoApplicationTests
18:01:47.124 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.web.ServletTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [org.springframework.test.context.web.ServletTestExecutionListener]
18:01:47.124 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.transaction.TransactionalTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [org.springframework.test.context.transaction.TransactionalTestExecutionListener]
18:01:47.124 [main] DEBUG org.springframework.test.context.util.TestContextSpringFactoriesUtils - Skipping candidate TestExecutionListener [org.springframework.test.context.jdbc.SqlScriptsTestExecutionListener] due to a missing dependency. Specify custom TestExecutionListener classes or make the default TestExecutionListener classes and their required dependencies available. Offending class: [org.springframework.test.context.jdbc.SqlScriptsTestExecutionListener]
18:01:47.124 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Using TestExecutionListeners for test class [DemoApplicationTests]: [DirtiesContextBeforeModesTestExecutionListener, ApplicationEventsTestExecutionListener, MockitoTestExecutionListener, DependencyInjectionTestExecutionListener, DirtiesContextTestExecutionListener, EventPublishingTestExecutionListener, RestDocsTestExecutionListener, MockRestServiceServerResetTestExecutionListener, MockMvcPrintOnlyOnFailureTestExecutionListener, WebDriverTestExecutionListener, MockWebServiceServerTestExecutionListener, ResetMocksTestExecutionListener]
18:01:47.124 [main] DEBUG org.springframework.test.context.support.AbstractDirtiesContextTestExecutionListener - Before test class: class [DemoApplicationTests], class annotated with @DirtiesContext [false] with mode [null]
18:01:47.127 [main] DEBUG org.springframework.test.context.support.AbstractDirtiesContextTestExecutionListener - After test class: class [DemoApplicationTests], class annotated with @DirtiesContext [false] with mode [null]
com.example.demo.DemoApplicationTests > contextLoads() FAILED


Failures (2):
  JUnit Jupiter:DemoApplicationTests:contextLoads()
    MethodSource [className = 'com.example.demo.DemoApplicationTests', methodName = 'contextLoads', methodParameterTypes = '']
    => java.lang.ExceptionInInitializerError
       io.mockk.junit5.MockKExtension.postProcessTestInstance(MockKExtension.kt:177)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$10(ClassBasedTestDescriptor.java:377)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.executeAndMaskThrowable(ClassBasedTestDescriptor.java:382)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$11(ClassBasedTestDescriptor.java:377)
       java.base@17.0.5/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
       [...]
     Caused by: java.lang.IllegalStateException: Cannot locate class file for Byte Buddy installer
       net.bytebuddy.agent.ByteBuddyAgent$AgentProvider$ForByteBuddyAgent.createJarFile(ByteBuddyAgent.java:1501)
       net.bytebuddy.agent.ByteBuddyAgent$AgentProvider$ForByteBuddyAgent.resolve(ByteBuddyAgent.java:1540)
       net.bytebuddy.agent.ByteBuddyAgent.install(ByteBuddyAgent.java:631)
       net.bytebuddy.agent.ByteBuddyAgent.install(ByteBuddyAgent.java:611)
       net.bytebuddy.agent.ByteBuddyAgent.install(ByteBuddyAgent.java:563)
       [...]
  JUnit Jupiter:DemoApplicationTests
    ClassSource [className = 'com.example.demo.DemoApplicationTests', filePosition = null]
    => java.lang.NoClassDefFoundError: Could not initialize class io.mockk.impl.JvmMockKGateway
       io.mockk.junit5.MockKExtension.afterAll(MockKExtension.kt:189)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeAfterAllCallbacks$18(ClassBasedTestDescriptor.java:461)
       org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeAfterAllCallbacks$19(ClassBasedTestDescriptor.java:461)
       java.base@17.0.5/java.util.ArrayList.forEach(ArrayList.java:1511)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.invokeAfterAllCallbacks(ClassBasedTestDescriptor.java:461)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.after(ClassBasedTestDescriptor.java:235)
       org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.after(ClassBasedTestDescriptor.java:84)
       org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:161)
       org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
       [...]

Test run finished after 5039 ms
[         2 containers found      ]
[         0 containers skipped    ]
[         2 containers started    ]
[         0 containers aborted    ]
[         1 containers successful ]
[         1 containers failed     ]
[         1 tests found           ]
[         0 tests skipped         ]
[         1 tests started         ]
[         0 tests aborted         ]
[         0 tests successful      ]
[         1 tests failed          ]


> Task :nativeTest FAILED

FAILURE: Build failed with an exception.
```