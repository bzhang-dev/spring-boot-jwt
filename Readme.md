
### JwtTokenUtil
The **JwtTokenUtil** is responsible for performing JWT operations like creation and validation. It makes use of the io.jsonwebtoken.Jwts for achieving this.

### JwtAuthenticationController

Expose a POST API /authenticate using the **JwtAuthenticationController**. The POST API gets the username and password in the body. Using the Spring Authentication Manager, we authenticate the username and password. If the credentials are valid, a JWT token is created using the **JWTTokenUtil** and is provided to the client.

### JwtRequest

This class is required for storing the username and password we received from the client.

### JwtResponse

This class is required for creating a response containing the JWT to be returned to the user.

### JwtRequestFilter

The **JwtRequestFilter** extends the Spring Web Filter **OncePerRequestFilter** class. For any incoming request, this **Filter** class gets executed. It checks if the request has a valid JWT token. If it has a valid JWT Token, then it sets the authentication in context to specify that the current user is authenticated.

### JwtAuthenticationEntryPoint

This class will extend Spring's **AuthenticationEntryPoint** class and override its method to commence. It rejects every unauthenticated request and sends error code 401.

### WebSecurityConfig

This class extends the **WebSecurityConfigurerAdapter**. This is a convenience class that allows customization to both **WebSecurity** and **HttpSecurity**.




### reference

https://dzone.com/articles/spring-boot-security-json-web-tokenjwt-hello-world 