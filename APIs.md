#Application Programming interfaces (APIs)
Out for a walk one day, a woman came across a construction site and saw three men working. She asked the first man, “What are you doing?” Annoyed by the question, the first man barked, “Can’t you see that I’m laying bricks?” Not satisfied with the answer, she asked the second man what he was doing. The second man answered, “I’m building a brick wall.” Then, turning his attention to the first man, he said, “Hey, you just passed the end of the wall. You need to take off that last brick.” Again not satisfied with the answer, she asked the third man what he was doing. And the man said to her while looking up in the sky, “I am building the biggest cathedral this world has ever known.” While he was standing there and looking up in the sky the other two men started arguing about the errant brick. The man turned to the first two men and said, “Hey guys, don’t worry about that brick. It’s an inside wall, it will get plastered over and no one will ever see that brick. Just move on to another layer.”
So the moral of the story is if you want to know how things work, you will know how they are made/created. Because there is no way you will think of a good solution if you don’t know what criteria to use to solve that particular problem.

#So what Are APIs?
A simple explanation is, an API is an abstraction of a particular piece of software or hardware with code, like in terms of computer hardware the sockets API is an implementation of a networking card, they create an endpoint for communication between two machines without the need to write a communication tool between your network card and the script you are writing, making it easy for you to concentrate on just writing code that does the communication you wanted rather than having to write extra code to achieve that communication, so an API is nothing more than just a bunch of classes that have methods, properties and events that “do things for you”.
To keep it short an API is just a class in Object Oriented Programming or a routine in functional programming that accomplishes a specific task or are allows interaction with a specific software component, like communication in the example above.

#WEB APIs
APIs are commonly used in enterprise development to give software engineers access to data that is hosted in the cloud, an example could be the TMDB API that allows one to access movie & t.v information stored by TMDB, with this you can create applications that make use of the API, like by writing an application that requests for a list of TV shows and any data associated with it. The API gives you access to get that data via endpoints using HTTP to return JSON or whatever response is availabe like XML and text.

##HTTP and REST
Hypertext Transfer Protocol (HTTP) is the life of the web. It's used every time you transfer a document, or make a request for resources, HTTP can be used in any programming language which makes it ideal for communicating with web APIs to request for or send resources.
###REST
Rest is a simple way of organizing interactions between independent systems, and is what TMDB API uses for those interactions. This is due to the fact that REST allows you to interact with minimal overhead with clients as diverse as mobile phones and other websites. In theory, REST is not tied to the web, but it's almost always implemented as such, and was inspired by HTTP. As a result, REST can be used wherever HTTP can.

###URLs
we can't talk of any of the above without talking a look at URLs. URL stands for Unified Resource Locator, an example of a url is http://video.google.com:80/videoplay?docid=496999690949&hl=en#00h02m30s, will analyze each part to understand the parts that make up a url bellow:
1. http:// => protocol, this declares the protocol to be used and thus http is used.
2. video => subdomain namem, this is a subdivision of the main domain name.
3. google.com => domain name, this is the main domain name.
4. :80 => port, this is the addressing port to be used, port 80 is amongst the main ones.
5. /videoplay => path, this is a path to to a resource in the webserver.
6. ? => query, this tell the server that it should get a particular resource that matches the parameters.
7. docid=496999690949&hl=en => parameters, this are the parameters that  describe the requrired resource.
8. #00h02m30st => fragment,this part requests specific part of the resource, commonly it describes a section of a resource
Now that we understand urls lets delve int how it all comes together,but first we will have to understand some common http verbs by showing how they are used to work with data stored somewhere in the cloud or even locally.
####GET 
Like the name suggests ```GET``` is used to get/fetch data, for example in the TMDB example we would do
                        ```GET https://api.themoviedb.org/3/movie/now_playing?api_key=your_api_key```
supposing you have the right api key a list of now playing movies is returned in json format.
GET is basically used for getting data.
####PUT/PATCH
```PUT``` and ```PATCH``` are mostly used to elter data for example when updating your username or password like
                     ```PUT/PATCH https://themoviedb.org/accounts/mine?username=####&password=######```
the exmple above would not work but just demontstrate how put could be used.
####DELETE
Is used to delete resource, for example if you have a list of favorite movies and for some reason you no longer consider one a favirite you can use
                    ```DELETE https://themoviedb.org/account/mine/favorites?movie=2012```
that would remove 2012 from a list of your favorite movies.
####POST
Is used to save data to the database like for example we would use it to add a movie to our favorites list like
                    ```POST https://themoviedb.org/accounts/mine/favorites/movie=2012```
that would add 2012 to our favorites again.

When we do all of the above we will get response code,below we discuss the and what they mean.
####200 0k
This response code indicates that the request was successful.

####201 Created
this message is usually returned when a resource has been added using ```POST``` or updated using ```PATCH/PUT```, usually indicates resource was created successfully. 

####400 Bad Request
The request was malformed. This happens especially with ```POST``` and ```PUT/PATCH``` requests, when the data does not pass validation, or is in the wrong format.

####404 Not Found
This response indicates that the required resource could not be found. This is generally returned to all requests which point to a URL with no corresponding resource.

####401 Unauthorized
This error indicates that you need to perform authentication before accessing the resource.

####405 Method Not Allowed
The ```HTTP``` method used is not supported for this resource.

####409 Conflict
This indicates a conflict. For instance, you are using a ```PUT``` request to create the same resource twice.

####500 Internal Server Error
When all else fails; generally, a 500 response is used when processing fails due to unanticipated circumstances on the server side, which causes the server to error out.

#Conclusion
you now have a basic understanding of how APIs work and now you are ready to start building an api, in the next article we will build a simple api that communicates with our database and retrieves resources.
See yuo in two weeks, until the Happy hacking.











