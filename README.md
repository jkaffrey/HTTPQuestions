## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.
```
protocol: How the website goes about connecting via it be http, https, ftp, sftp, ssh, etc.
port: the port that is connected through. Basically, the apartment within the building.
domain: the web address (masked ip address) that you are attempting to connect to
path: the location of the files on the server.
query: the information that is being passed to the GET, POST, etc requets.
anchor: where on the page you want to quick travel to.
```
* Name the pieces of the following urls:
	* `https://www.google.com/`
	```
	  domain: google.com
	```
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	```
	  domain: galvanize.com
	  path: cohorts/41/learning_experiences/367
	```
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
	```
	  domain: localhost
	  port: 5000
	  path: animals/puppies
	  query: onlycute=1&size=medium
	  anchor: firstPuppy
	```
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
	```
	  domain: wikipedia
	  path: wiki/List_of_HTTP_status_codes
	  anchor: 4xx_Client_error
	```
* Can a server use more than 1 port?
```
Yes
```
* Why is https different than http?
```
HTTPS is a secure connection encrypted and secured through an SSL
```
* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
puppies: [ fido, max, moxie ]
JSON data structure of an array of values
```

__HTTP Request/Response__

* Name at least 4 http verbs
```
GET: when we want to get some information such as a web page.
POST: for sending information such as a query.
DELETE: to communicate with a server in order to remove a resource.
PUT: updaing information
```
* What is each verb useful for in your own words
```
See above
```
* What does idempotent mean?
```
Meaning no matter how many times we call this 'thing' it will always return the same.
```
* Name the 5 http status code ranges.  What are they used for in general?
```
5--: errors
4--: no information or error
3--: not available here
2--: success
1--: processing
```
* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?
```
navigates to google.com permanently
```
* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept ``` response ```
	* Content-type ``` request ```
	* User-agent ``` request ```
	* Set-cookies ``` both ```
	* Cache-control ``` request ```
	* Cookie ``` both ```
* Is the following a http request or response?  How do you know for each?

```
--- A request. It is returning information

HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
-- response, providing information
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.
```
A file format for storing information in a readable way. 
```
* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}

var info = {
	company: "Github",
	age: 7,
	categories: [ "Services", "Internet", "Software" ]
};

console.log(info.age);
```
* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}

var objectMap = {
	company: [ "Github", "Airbnb", "Square", "Dropbox" ],
	age: [ 7, 6, 7, 11 ],
	categories: [ ["Service", "Internet", Software"], ["Hotel", "Travel"], ["FinTech", "Hardware + Software", "Finance"] , ["Cloud Date Services", "Storage", "Web Hosting"]]
}

for (var name in objectMap.company) {

    console.log(name);
}
```
* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

--- JSON.stringify(myObj);
```
__MISC__

* Describe what DNS is.
```
Domain Name Service - a domain name manager
```
* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).
```
-v: be more verbose with output
-X: use a custom request method
```
* What is TCP/IP?  How does it interact with HTTP?
```
It's the building blocks of HTTP and allows lower level computer to computer communication
```
* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?
```
Yes, IP
```
