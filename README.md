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




