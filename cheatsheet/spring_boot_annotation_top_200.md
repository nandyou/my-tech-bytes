
Top 200 Spring Boot Annotations with Categories

1. Core Spring Framework Annotations
------------------------------------
1. @Component – Marks a Java class as a Spring component.
2. @Service – Indicates that a class is a service.
3. @Repository – Indicates that a class is a data repository.
4. @Controller – Marks a class as a Spring MVC controller.
5. @RestController – Combines @Controller and @ResponseBody.
6. @RequestMapping – Maps HTTP requests to handler methods.
7. @GetMapping – Shortcut for GET method mapping.
8. @PostMapping – Shortcut for POST method mapping.
9. @PutMapping – Shortcut for PUT method mapping.
10. @DeleteMapping – Shortcut for DELETE method mapping.
11. @PatchMapping – Shortcut for PATCH method mapping.
12. @RequestParam – Extracts query parameters from a request.
13. @PathVariable – Extracts path parameters.
14. @RequestBody – Binds the request body to an object.
15. @ResponseBody – Binds method return value to response.
16. @RequestHeader – Binds request headers to parameters.
17. @CookieValue – Binds cookie values.
18. @SessionAttributes – Stores model attributes in session.
19. @ModelAttribute – Binds data to model attributes.
20. @InitBinder – Initializes web data binder.

2. Configuration & Bootstrapping
-------------------------------
21. @Configuration – Declares configuration class.
22. @Bean – Declares a bean.
23. @ComponentScan – Enables component scanning.
24. @PropertySource – Loads external properties.
25. @Import – Imports additional configurations.
26. @ImportResource – Imports XML configuration.
27. @EnableAutoConfiguration – Enables auto-configuration.
28. @SpringBootApplication – Composite annotation.
29. @Profile – Enables bean based on profile.
30. @Conditional – Conditional bean registration.
31. @ConditionalOnProperty – Conditional on property value.
32. @ConditionalOnClass – Conditional on class presence.
33. @ConditionalOnMissingClass – Conditional on class absence.
34. @ConditionalOnBean – Conditional on bean presence.
35. @ConditionalOnMissingBean – Conditional on missing bean.
36. @ConditionalOnExpression – Conditional on SpEL.

3. Dependency Injection & Lifecycle
-----------------------------------
37. @Autowired – Auto-wires dependencies.
38. @Qualifier – Specifies bean to inject.
39. @Primary – Primary bean candidate.
40. @Value – Injects property values.
41. @PostConstruct – Executes after injection.
42. @PreDestroy – Executes before destruction.
43. @Lazy – Delays bean initialization.
44. @Scope – Defines bean scope.
45. @DependsOn – Declares bean dependencies.
46. @Lookup – Returns runtime bean.
47. @Resource – Injects by name (JSR-250).
48. @Inject – Injects dependencies (JSR-330).
49. @Named – Named bean (JSR-330).

4. Persistence & Data Access
----------------------------
50. @Entity – Declares a JPA entity.
51. @Table – Table mapping.
52. @Id – Primary key.
53. @GeneratedValue – Auto-generates keys.
54. @Column – Field-column mapping.
55. @JoinColumn – Foreign key mapping.
56. @ManyToOne – Many-to-one mapping.
57. @OneToMany – One-to-many mapping.
58. @OneToOne – One-to-one mapping.
59. @ManyToMany – Many-to-many mapping.
60. @Lob – Large object type.
61. @Transient – Non-persistent field.
62. @DataJpaTest – JPA test configuration.
63. @EnableJpaRepositories – Enables repositories.
64. @Query – Custom repository query.
65. @Modifying – Modifies data query.
66. @Transactional – Declares transaction.

5. Validation
-------------
67. @Valid – Activates validation.
68. @Validated – Group-based validation.
69. @NotNull – Field must not be null.
70. @NotEmpty – Field must not be empty.
71. @NotBlank – Field must not be blank.
72. @Size – Size constraints.
73. @Min – Minimum value.
74. @Max – Maximum value.
75. @Pattern – Regex pattern.
76. @Email – Email format.

6. Testing
----------
77. @SpringBootTest – Loads full context.
78. @WebMvcTest – Tests web layer.
79. @DataJpaTest – Tests JPA layer.
80. @MockBean – Adds mock bean.
81. @SpyBean – Adds spy bean.
82. @TestConfiguration – Test-specific config.
83. @TestPropertySource – Loads test properties.
84. @ContextConfiguration – Context for tests.
85. @ActiveProfiles – Activates profile in tests.
86. @Sql – Executes SQL scripts.
87. @SqlGroup – Groups SQL annotations.
88. @Rollback – Rolls back transactions.
89. @Commit – Commits transaction.
90. @WebAppConfiguration – Web test context.

7. AOP (Aspect Oriented Programming)
------------------------------------
91. @EnableAspectJAutoProxy – Enables AOP.
92. @Aspect – Declares aspect class.
93. @Before – Pre-method advice.
94. @After – Post-method advice.
95. @AfterReturning – Advice on success.
96. @AfterThrowing – Advice on exception.
97. @Around – Surrounds method.

8. Scheduling
-------------
98. @EnableScheduling – Enables scheduling.
99. @Scheduled – Schedules method execution.

9. Asynchronous Execution
-------------------------
100. @EnableAsync – Enables async support.
101. @Async – Executes method asynchronously.

10. Events
----------
102. @EventListener – Listens for events.
103. @TransactionalEventListener – Listens in transaction.

11. Caching
-----------
104. @EnableCaching – Enables caching.
105. @Cacheable – Caches method result.
106. @CachePut – Updates cache.
107. @CacheEvict – Evicts from cache.

12. WebSocket
-------------
108. @EnableWebSocket – Enables WebSocket.
109. @ServerEndpoint – WebSocket endpoint.
110. @MessageMapping – Maps messages.
111. @SendTo – Broadcasts messages.
112. @SendToUser – Sends to specific user.
113. @SubscribeMapping – Mapping on subscribe.

13. Security
------------
114. @EnableWebSecurity – Enables web security.
115. @EnableMethodSecurity – Method-level security.
116. @Secured – Secured by role.
117. @PreAuthorize – Pre-execution auth.
118. @PostAuthorize – Post-execution auth.
119. @EnableOAuth2Client – Enables OAuth2 client.
120. @EnableOAuth2Sso – Enables OAuth2 SSO.
121. @EnableAuthorizationServer – Auth server.
122. @EnableResourceServer – Resource server.
123. @AuthenticationPrincipal – Current principal.

14. Spring Cloud & Microservices
-------------------------------
124. @EnableDiscoveryClient – Enables service discovery.
125. @EnableEurekaClient – Registers with Eureka server.
126. @EnableFeignClients – Enables Feign clients.
127. @FeignClient – Declares a Feign client.
128. @LoadBalanced – Adds client-side load balancing.
129. @EnableZuulProxy – Enables Zuul API gateway.
130. @EnableCircuitBreaker – Enables circuit breaker.
131. @HystrixCommand – Wraps method in circuit breaker.
132. @EnableConfigServer – Enables config server.
133. @RefreshScope – Refreshes beans on config changes.
134. @EnableHystrixDashboard – Enables Hystrix dashboard.
135. @EnableTurbine – Aggregates Hystrix metrics.
136. @EnableOAuth2Resource – Enables OAuth2 in microservices.
137. @EnableGlobalMethodSecurity – Global method security.
138. @EnableBinding – Binds messaging channels.
139. @StreamListener – Listens for message stream.
140. @SendTo – Sends output to stream.

15. Spring Messaging
--------------------
141. @EnableJms – Enables JMS support.
142. @JmsListener – JMS message listener.
143. @EnableRabbit – Enables RabbitMQ support.
144. @RabbitListener – RabbitMQ message listener.
145. @KafkaListener – Kafka message listener.
146. @EnableKafka – Enables Kafka support.

16. DevTools & Actuator
-----------------------
147. @EnableAutoConfiguration – Auto-config support.
148. @EnableConfigurationProperties – Binds properties.
149. @ConfigurationProperties – Maps properties to beans.
150. @Endpoint – Custom actuator endpoint.
151. @ReadOperation – Read-only operation.
152. @WriteOperation – Write operation.
153. @DeleteOperation – Delete operation.

17. Web & Servlet
-----------------
154. @ServletComponentScan – Enables servlet scanning.
155. @WebFilter – Declares a filter.
156. @WebServlet – Declares a servlet.
157. @WebListener – Declares a listener.
158. @MultipartConfig – Enables multipart support.

18. Others & Miscellaneous
--------------------------
159. @CrossOrigin – Enables CORS.
160. @SessionScope – Defines session scope.
161. @RequestScope – Defines request scope.
162. @ApplicationScope – Application-wide scope.
163. @ControllerAdvice – Global controller exception handler.
164. @ExceptionHandler – Handles exceptions in controller.
165. @RestControllerAdvice – REST-style global exception handler.
166. @MatrixVariable – Binds matrix variable.
167. @EnableTransactionManagement – Enables transactions.
168. @EnableWebFlux – Enables WebFlux support.
169. @EnableReactiveMongoRepositories – Reactive Mongo repos.
170. @EnableMongoRepositories – Enables MongoDB repositories.
171. @EnableR2dbcRepositories – Enables R2DBC repositories.
172. @EnableElasticsearchRepositories – Enables Elasticsearch.
173. @EnableJpaAuditing – Enables auditing.
174. @CreatedDate – Auditing created date.
175. @LastModifiedDate – Auditing last modified date.
176. @CreatedBy – Auditing created by.
177. @LastModifiedBy – Auditing modified by.
178. @Order – Orders configuration or aspect.
179. @AliasFor – Meta-annotation alias.
180. @EnableMBeanExport – Exports JMX MBeans.
181. @ManagedResource – Marks resource as manageable.
182. @ManagedAttribute – Exposes attribute to JMX.
183. @ManagedOperation – Exposes operation to JMX.
184. @ProfileValueSourceConfiguration – Profile testing.
185. @Timed – Times execution duration.
186. @ImportAutoConfiguration – Imports autoconfig classes.
187. @Indexed – Spring index support.
188. @EventListenerFactory – Custom event listener factory.
189. @BootstrapWith – Bootstraps test class.
190. @ConditionalOnJava – Conditional on Java version.
191. @RestClientTest – Test REST clients.
192. @WebFluxTest – Test reactive web layer.
193. @JsonComponent – Registers Jackson components.
194. @JsonDeserialize – Custom deserialization.
195. @JsonSerialize – Custom serialization.
196. @EnableGlobalMethodSecurity – Global method security.
197. @DynamicPropertySource – Dynamic test properties.
198. @RegisterExtension – JUnit 5 extension.
199. @ParameterizedTest – JUnit parameterized test.
200. @CsvSource – Supplies CSV data to test.

