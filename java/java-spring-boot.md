# Java Spring Boot

## Getting Started with Spring Boot

To create a new project run command

```
spring init myapp
```

## Annotations for Models

- @Entity : tells that class is an instance that will be stored in a database
- @Table(name="name") : defines a custom name for a table
- @Id : tells which field is to be set as the primary key
- @GeneratedValue(startegy=GenerationType.IDENTITY) : Used with id tells how values are to be generated
- @Column(name="column_name") : optional but can define what name a column in the database will have

## Annotations for URLs in controllers

- @GetMapping("/url"): define a GET route
- @GetMapping("/url/{id}"): define a GET route and take in an id 
	- public Stuff getStuff(@PathVariable("id") Interger id) : also need to pass in @PathVariable Annotation with id as a variable
- @PostMapping("/url") : define a POST route
	- public Stuff createStuff(@RequestBody Stuff stuff) : also need to include request body and assign to an variable
- @PutMapping("/url") : define a PUT route
	- public Stuff updateStuff(@PathVariable("id") Integer id, @RequestBody Stuff stuff)
- @DeleteMapping("/url") : define a DELETE route
	- public Stuff deleteStuff(@PathVariable("id") Integer id)


## Setup connection to models with CrudRepository

Start by defining an interface and extend CrudRepository to that interface

```
public interface StuffRepository extends CrudRepository<Stuff, Long>

```

Controllers needed to be injected with with the repository in order to use them

```
@RestController
public class StuffController {
	private final StuffRepository stuffRepository;
	
	public StuffController(StuffRepository stuffRepository) {
		this.stuffRepository = stuffRepository;
	}

}

```

## Setup database connection

In application.properties file set up the driver, database location, and credentials to connect to the database

```
spring.datasource.url=jbdc:postressql://url:port
spring.datasource.username=name
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
```

## database seeding

create a data.sql file in the src/main/resources using H2.  This can be used for development and testing

```
insert INTO STUFF(column) VALUES (values comma seperated)
```

In the application.properties

```
spring.jpa.defer-datasource-initialization=true # Ensures tables exsit before queries run
```

## JPA Queries

- findAll() : returns an iterable collection of all records
- findById(id) : takes an integer and returns an Optional type that helps check if record exists
- save(stuff) : takes the body of creation and creates or updates a record in the that database
- delete(stuff) : takes the record to be deleted and deletes it

Can be used like

```
stuffRepository.findAll();
```

### Named Query

Allows for the dynamic queries based on names. 

Like used by findBy...() like findByName(String name)

Automatically generates a SQL query for you

### Boolean & Null checks

Also create queries for True, false, Null, or NotNull

```
List<Stuff> findByActiveTrue();
List<Stuff> findByEmailNull();
List<Stuff> findByEmailNotNull();
List<Stuff> findByActiveFalse();
// can combine queries
List<Stuff> findByActiveFalseAndAgeNotNull();
```

### Comparison Modifiers

Also GreaterThan, LessThan, LessThanEqual, GreaterThanEqual, and Between

```
List<Stuff> findByAgeLessThan(Integer age);
List<Stuff> findByAgeBetween(Integer startAge, Ingeter EndAge);
```

### Multi-Condition Queries

Combine Queries with And and Or

```
List<Stuff> findByFirstNameAndLastName(String firstName, String lastName);
```


### Named Query Annotation

Use annotation @NamedQuery on the entity class to defined your own queries to run

```
@Entity
@NamedQuery(name = "User.findByNameAndState",
	query = "SELECT u FROM User u WHERE u.name = ?1 AND u.state = ?2")
public class User {}

//in interface defined it
List <User> findByNameAndState(String name, String city);

```


### Query

Use query annotation on repository method to defined a custom query

```
@Query("SELECT u FROM User u WHERE u.status = ?1 AND u.lastLogin > ?2")
List<User> findActiveUsersWithRecentLogin(String status, Date date);
```


