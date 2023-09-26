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

### Basic back end : 
Models of items (class ) -> DAO layer (interface + class implementing it .. CRUD operations on DB ) -> service layer ( Business logic ) -> API layer (contains GET , POST , PUT methods)

### Annotation
Supply extra info to compiler without looking into the class/method . `@RestController` will tell that below class is a REST API  class. `@GetMapping` will tell that below method uses GET request. 

`@SpringBootApplication` : tells compiler that the highlighted class is the spring boot application entry point . This class need to have a `static void main (String[] args)` 

`@Component` : Tells spring container that highlighted class is spring bean/ component.

`@Autowired` : Inject dependency using contructor injection ,setter injection and field injection. 
```
// (constructor injection)

private Vegpizza vegpizza;

@Autowired
public Pizza(){
this.vegpizza = vegpizza;
}
// This tells to inject Vegpizza instance through this constructor 
```

```
// (field injection)

@Autowired
private Vegpizza vegpizza;

```








