# Spring Boot Authentication

Spring Security annotations

- @PreAuthorize
- @Secured
- @PostAuthorize
- @DenyAll
- @PermitAll
- @RolesAllowed

Sprint Security Configuration on class

- @Configuration : signifies that class has @Bean definitions
- @EnableWebSecurity : Provides Web security support

Configure authenticated routes

HttpSecurity has a method authorizeHttpRequest() to create an AuthorizationManagerRequestMatcherRegistry object.  You can define security rules for specific paths using method requestMatchers followed by permitAll or authenticated

```
@Bean SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
	http.authorizeHttpRequest(auth -> auth
		.requestMatchers("/login").permitAll()
		.requestMatchers(HttpMethod.GET, "/math/*").permitAll()
		.requestMatchers("/public/**").permitAll()
		.anyRequest().authenticated()
		);
		
		return http.build();
}
```

Customize the login process with formLogin().  Able to set a custom login page and configure form parameters

```
public SecurityFilterChain securityFilterChain(HttpSecurity http) {
	http.formLogin(login -> login
		.loginPage("/login")
		.usernameParameter("FirstName")
		.passwordParameter("secret")
		.defaultSuccessUrl("/home", true)
		.failureUrl("/failed-screen")
		);


}
```

Customize the logout property

```
public SecurityFilterChain securityFilterChain(HttpSecurity http) {
	http.logout(logout -> logout
		.logoutUrl("/logout")
		.logoutSuccessUrl("/logout")
		);
		
		return http.build();
}
```

Spring PasswordEncoder

Use to encode passwords security

```
@Bean
public PasswordEncoder passwordEncoder() {
	return Argon2PasswordEncoder.defaultsForSpringSecurity_v5_8();
}

@PostMappging
public String register(PasswordEncoder encoder) {
	String hashedPassword = encoder.encode(password);
}
```

Store credentials in a database with UserDetailsManager bean

```
@Bean
public UserDetailsService userDetailsService() {
	return new InMemoryUserDetailsManager(
		User.withDefaultPasswordEncoder()
			.username("user")
			.password("password")
			.roles("USER")
			.build()
		);
	}
}


```


User session persistant

```
@GetMapping
public String getHomePage() {
	User auth = (User) SecurityContextHolder.getContext().getAuthentication().getPrincipal();
	String username = auth.getUserName();

}
```

