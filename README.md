# webd-concepts

## CORS (Cross origin resource sharing) :
No 'Access=control-allow-origin' header is present in request. Every request has header with it . When we try to access resources from different domains (origins) .. accessing resources of domain A.com in domain 
B.com. Header has info about HOST , Method etc .. 

PreFLight Request :  Not the actual request , it is a request sent by browser to server with origin and method (All the things related to cors take place in pre flight request).Actual request is sent
after pre flight request.

Access-control-allow-origin (method) : We can specify the methods allowed to access our domain.Like only GET , POST methods or DELETE, PUT methods etc

How to fix this : allow origin of different domain in the back end of application. 

Access-allow-origin-control : If we specify a particular domain , only that domain can access the resources of our server. 
  
POSTMAN : It doesnt have any pre-flight request .. we can access directly to the server. (CORs wagere ki bt nahi)


## REACT Class Components and LifeCycle Methods

## React Functional components and react HOOKS
React hooks provide lifecycle methods functionality to functional components.


  ### useRef()
`useRef()` : creates mutable variable which will not re render the component and directly accessing the DOM. It returns an object. `.current` is property of useRef returned object
```
const count = useRef(0);

useEffect(()=>{
count.current = count.current + 1; 
});

```
If we will not useRef .. it will be send into a infinte loop by useEffect() ; 

#### Accessing input data field using useRef() :
```
const inp = useRef("");

<Input ref={inp} />
```


## react-router-dom and routes and route
For eg navbar is same for all pages .. so instead of loading navbar again and again for diff pages .. we switching only the required component keeping other components same.
react-router is used for this. Angular has routing built in , but in react we have to npm install react-router-dom package. 
Routing within the components 

Browser-router : Parent tag 

Route : Route tag with path as parameter .

Link : Tag which works as <a> tag for react components

**PARAMS ** : https://www.worldometers.info/coronavirus/**country/us/**  .. this is the parameter passed in url and data on page is realted to this parameter. This is dynamic so we dont need to write 
components for each param. 

`<Route path="/user/**:name**" element={<User/>} > ` and now in  User compoenent `const params = useParams() ` and `const {name} = params` and use this name as variable in div etc.

`useNavigate()` **:** For redirecting to page , go back to prev page functionality etc . `const navigate = useNavigate()` . For redirecting to contact page use this function `navigate('/contact')`.

Go back feature in navigate : `navigate(-1)` 


## REST API ( REST : Representational State Transfer )
RESTful web service : Service that uses REST API. REST is just a convention of writing APIs.

REST API are stateless and supports caching. It uses `URI : Uniform resource identifier` . `api/v1/icecreams` here `icecreams` is a resource.
### Request : 
GET , POST , PUT , DELETE methods. Each request has `endpoint , header , body , operation and parameters` . 

### Response :
Response body according to request method.It has `status code`.
```
2xx : success
4xx : client side error
5xx : server side error
```



## Spring Boot 

### Bean and IOC container
Bean can be considered as an object. Spring IOC container contains all the beans.
 
### Basic back end : 
Models of items (class ) -> DAO layer (interface + class implementing it .. CRUD operations on DB ) -> service layer ( Business logic ) -> API layer (contains GET , POST , PUT methods)

### Annotation
Supply extra info to compiler without looking into the class/method . `@RestController` will tell that below class is a REST API  class. `@GetMapping` will tell that below method uses GET request. 

`@SpringBootApplication` : tells compiler that the annotated class is the spring boot application entry point . This class need to have a `static void main (String[] args)` 

* `@SpringBootConfiguration` : Uses `@Configuration` .. 3 configs XML based , Java based and Annotation based . For JAVA @Configuration is used . 

* `@EnableAutoConfiguration` : Enables auto configs for classes 

* `@ComponentScan` : Scan spring components within every subpackages and in base package.




`@Component` : Tells spring container that highlighted class is spring bean/ component.

`@Autowired` : Inject dependency using contructor injection ,setter injection and field injection. Here Pizza is an interface.
```
// (constructor injection)

private Vegpizza vegpizza;

@Autowired
public PizzaController(){
this.vegpizza = vegpizza;
}
// This tells to inject Vegpizza instance through this constructor 
```

```
// (field injection)

@Autowired
private Vegpizza vegpizza;

```

`@Qualifier` : Used with @Autowired to avoid confusion when we have two or more beans configured. Suppose Pizza interface has two implementation classes vegPizza and nonvegPizza and we want to initiliase Pizza
then for injecting nonveg pizza implementation.
```
private Pizza pizza;
@Autowired
public PizzaController(@Qualifier("nonvegPizza") Pizza pizza){
this.pizza = pizza;
}
```
`@Primary` : give higher prioirty to a bean when multiple beans are present. Like Pizza interface has two implementations veg and nonveg so if we make veg as `@Primary` , then by default Pizza will use 
vegPizza implementation.

`@Configuration` : to decalre a configuration class to create spring bean definitions.

`@Bean` : to create a spring bean class.
```

```

`@Repository` : create spring bean at DAO layer.

`@Service` : create spring bean at service layer.

`@Controller` : create spring bean at controller layer.

`@RestController` : for creating RESTful web serivces.

`@Scope` : different types of scopes like : singleton , prototype , request , session , application and websocket. Singleton : only one bean is created and used everywhere .. this is the default scope. Prototype : new instance is created every time it is requested.
```
@Scope(value="singleton")
public class SingletonBean{
}
```

`@ResponseBody` : convert response to json format.

 `@RequestMapping` : to map web requests to spring controller methods. We can specify our API URI's . URI for class `/api/v1` and URI for methods `/user` so API URI will be `/api/v1/user` .

`@GetMapping` : Maps HTTP GET requests to handler methods.It is just requestMapping's GET method. We can specify API URI here also.

`@PostMapping` : Maps HTTP POST request to handler method

`@RequestBody` : for retrivieng HTTP request body (JSON) and convert it to JAVA Object.

`@ResponseStatus` : to get the status code of response from server.

`@PutMapping(value = "/api/v1/{user}")` here user is URI template variable. Helps in creating dynamic URI with variables included.

`@PathVariable` : binds a method argument to URI template variable. `@PathVariable int user` is passed as an argument in mapping handler method. **Path variable and URI template variable should have same name to be binded otherwise it gives error**

`@RequestParam` : to extract query parameters from request and bind them to method arguments. `/api/v1/q?user=ramesh` here user is a query parameter .. anything followed by ? is query parameter.


### ResponseEntity class
Used in getting response from server. `ResponseEntity<Book>` means we will get a book object as a response. 







