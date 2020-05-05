# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
1. Include the **AS** keyword for creating aliases: the first letter of each word in the object’s name
2. Use uppercase for the reserved keywords like **SELECT** and **WHERE**.
3. Indentation: can really help the readability
4. Try to use only standard SQL functions
5. Only use letters, numbers and underscores in names.
#### What layers can you name in a simple web application?
* Presentation layer (UI layer, view layer, presentation tier)
* Business layer (business logic: determines how data can be created, stored, and changed. )
* Data access layer (persistence layer, logging, managing a database and other services which are required to support
 a particular business layer)
***

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
* IndexOutOfRangeException
#### What is the “finally” block, and how would you use it?
* **finally** block is always executed after leaving the **try** statement
* **finally** block is used to deallocate the system resources.
#### Why should we catch special exception types?
* In Python, we use special exception types for control-flow, for pulling error-handling outside loops and can simplify
 code quite a bit in common situations where the ability to handle an issue is far removed from where the issue arose.
* The use of exceptions in Python does not slow the surrounding code and calling code.
***

### Security
#### What is SQL injection? How to protect an application against it?
* A SQL injection (SQLi) is a type of security exploit in which the attacker adds Structured Query Language (SQL) code
 to a Web form input box in order to gain access to unauthorized resources or make changes to sensitive data.
* The only sure way to prevent SQL Injection attacks is input validation and parametrized queries including prepared 
statements. The application code should never use the input directly. 
* The developer must sanitize all input, not only 
web form inputs such as login forms.
#### What is XSS? How to protect an application against it?
* Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise 
benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, 
generally in the form of a browser side script, to a different end user.
* For example, the attacker could send the victim a misleading email with a link containing malicious JavaScript. If 
the victim clicks on the link, the HTTP request is initiated from the victim's browser and sent to the vulnerable web 
application.
* How to prevent XSS attacks: 
    * Filter input on arrival. At the point where user input is received, filter as strictly as possible based on what 
    is expected or valid input.
    * Encode data on output. At the point where user-controllable data is output in HTTP responses, encode the output 
    to prevent it from being interpreted as active content.
    * Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended to contain any HTML or 
    JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the 
    responses in the way you intend.
#### How to properly store passwords?
* The best way to protect passwords is to employ salted password hashing. 
* To Store a Password:
    1. Generate a long random salt using a CSPRNG.
    2. Prepend the salt to the password and hash it with a standard password hashing function like Argon2, bcrypt
    , scrypt, or PBKDF2.
    3. Save both the salt and the hash in the user's database record.
* To Validate a Password:
    1. Retrieve the user's salt and hash from the database.
    2. Prepend the salt to the given password and hash it using the same hash function.
    3. Compare the hash of the given password with the hash from the database. If they match, the password is correct. 
    Otherwise, the password is incorrect.
#### What is HTTPS?
* Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). It is used for 
secure communication over a computer network, and is widely used on the Internet.
* HTTPS takes the HTTP protocol, and simply layers a SSL/TLS encryption layer on top of it. Servers and clients still 
speak exactly the same HTTP to each other, but over a secure SSL connection that encrypts and decrypts their requests 
and responses.
#### What is encryption and decryption?
* **Encryption** is the process of translating plain text data (plaintext) into something that appears to be random and 
meaningless (cipher text).
* **Decryption** is the process of converting cipher text back to plaintext.
#### What is hashing?
* A method of generating from a data collection a fixed length string.
#### What is the difference between encryption and hashing? When would you use which?
* Encryption is reversible, while hashing is one way.
#### What encryption methods do you know?
* Symmetric:
    * encrypter, and decrypter — need access to the same key.
    * make the key available only to the software that needs it.
* Asymmetric:
    * known as public key cryptography, uses public and private keys to encrypt and decrypt data.
    * Either of the keys can be used to encrypt a message; the opposite key from the one used to encrypt the message 
    is used for decryption.
* Hash:
    * used only to verify data
    * the same input will always produce the same output
    * impossible to reverse it back to the original data
#### What hashing methods do you know?
* SHA-1: This is the second version of the Secure Hash Algorithm standard, SHA-0 being the first. 
SHA-1 creates 160-bit outputs.
* SHA-2: This is actually a suite of hashing algorithms. The suite contains SHA-224, SHA-256, SHA-384, and SHA-512. 
Each algorithm is represented by the length of its output. SHA-2 algorithms are more secure than SHA-1 algorithms
#### How/where would you store sensitive data (like db password, API key, ...) of your application?
* Sensitive data should never be used or stored in non-production systems, and access passwords should be stored in a 
password manager rather than entrusted to individuals.
***

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
* The main differences between stack and queue are that **Stack** uses LIFO (last in first out) method to access and
 add data elements whereas **Queue** uses FIFO (First in first out) method to access and add data elements.
#### What is BubbleSort? Describe the main logic of this sorting algorithm.
* A sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if 
they are in the wrong order. The pass through the list is repeated until the list is sorted.
#### Explain the process of finding the maximum and minimum value in a list of numbers!
* Declare two variables max and min to store maximum and minimum. Assume first array element as maximum and minimum 
both, say max = arr[0] and min = arr[0] . 
* Iterate through array to find maximum and minimum element in array.
#### Explain the process of calculating the average value in an array of numbers!
* Collect integer values in an array A of size N. Add all values of A. Divide the output with N. Display the
 output as average.
#### What is Big O complexity? Explain time and space complexity!
* Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. 
* Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the 
space used (e.g. in memory or on disk) by an algorithm:
    * Different steps get added: 
        * O(a + b)
    * Drop constants: 
        * <del>O(2n)</del> &rarr; O(n)
    * Different inputs &rarr; different variables: 
        * <del>O(n<sup>2</sup>)</del> &rarr; O(a * b)
    * Drop non-dominate terms: 
        * <del>O(n + n<sup>2</sup>)</del> &rarr; O(n<sup>2</sup>)
#### Explain the process of calculating the average value in a linked list of numbers!
* Start traversing the linked list using a loop until all the nodes get traversed. Add the value of current node to 
the sum i.e. sum += ptr -> data. 
* Increment the pointer to the next node of linked list i.e. ptr = ptr ->next . Divide sum by total number of node 
and Return the average.
***

### Procedural
#### How the CASE condition works in SQL?
* CASE expression is the same as IF/ELSE statement in other programming languages:
```
SELECT name, continent, indep_year,
    CASE WHEN indep_year < 1900 THEN 'before 1900'
    WHEN indep_year <= 1930 THEN 'between 1900 and 1930'
    ELSE 'after 1930' 
    END AS indep_year_group
FROM countries
ORDER BY indep_year_group;
```
#### How the switch-case condition works in JavaScript?
```
let a = 2 + 2;
switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too large' );
    break;
  default:
    alert( "I don't know such values" );
}
```
#### How to achieve a switch-case-like structure in Python?
```
def week(i):
    switcher={
            0:'Sunday',
            1:'Monday',
            2:'Tuesday',
            3:'Wednesday',
            4:'Thursday',
            5:'Friday',
            6:'Saturday'
         }
    return switcher.get(i, "Invalid day of week")
```
#### Explain variable scoping in Python!
* A variable created inside a function is available inside that function
* The local variable can be accessed from a function within the function
* A variable created outside of a function is global and can be used by anyone
#### What’s the difference between const and var in JavaScript?
* var: The scope of a variable defined with the keyword “var” is limited to the “function” within which it is defined. 
If it is defined outside any function, the scope of the variable is global.
* var is “function scoped”.
* let: The scope of a variable defined with the keyword “let” or “const” is limited to the “block” defined by curly
 braces i.e. {}.
* “let” and “const” are“block scoped”.
* const: The scope of a variable defined with the keyword “const” is limited to the block defined by curly braces.
* “const” cannot be re-assigned to a new value.
* value of the variable defined within the "const" keyword is mutable
#### How the list comprehension looks like in Python?
```
new_list = [expression for member in iterable (if conditional)]
sentence = 'the rocket came back from mars'
vowels = [i for i in sentence if i in 'aeiou']
```
#### How the “ternary expression” looks like in Python?
```
a if a > b else b
'yes' if ('qux' in ['foo', 'bar', 'baz']) else 'no'
```
#### How the ternary expression looks like in JavaScript?
```
var age = 19;
var canDrive = age > 16 ? 'yes' : 'no';
```
#### How to import a function from another module in Python?
```
import mod
from mod import s, foo
```
#### How to import a function from another module in JavaScript?
```
models/course.js
export function Course() {
    this.id = '';
    this.name = '';
};
models/student.js
import { Course } from './course.js';
```
***

### Functional
#### What is recursion?
* Recursion is the process which comes into existence when a function calls a copy of itself to work on a smaller 
problem. Any function which calls itself is called recursive function, and such function calls are called recursive 
calls.
#### Write a recursive function which calculates the Fibonacci numbers!
```
def fib(n):
    if n < 0:
        return "Incorrect input"
    elif n == 1:
        return 0
    elif n == 2:
        return 1
    else:
        return fib(n - 1) + fib(n - 2)
def fib_seq(n):
    result = []
    for i in range(1, n + 1):
        temp = fib(i)
        result.append(temp)
    return result
```
#### How to store a function in a variable in Python?
```
def greet(name):
    def get_message():
        return "Hello "

    result = get_message() + name
    return result
```
#### List the ways of defining a callable logical unit in JavaScript!
* Function expression:
```
const square = function(number) { 
    return number * number 
}
```
* Function declaration:
```
function square(number) {
  return number * number;
}
```
* IIFE (Immediately Invoked Function Expression):
```
(function(number) { 
    return number * number 
})();
```
#### What is an event listener? How to attach one?
* A function that is called whenever an event of the specified type occurs:
```
const buttonElement = document.getElementById('btn');
buttonElement.addEventListener('click', function (event) {
  alert('Element clicked through function!');
});
```
#### How to trigger an event in JavaScript?
```
var el = document.querySelector('input[type="text"]');
el.click(); // for any element
el.focus(); // for inputs and textareas
el.blur();
var my_form = document.querySelector('form'); // for form elements
my_form.submit();
my_form.reset();
```
#### What is a callback function? Tell some examples of its usage.
* A **callback function** is a function passed into another function as an argument.
```
function greeting(name) {
  alert('Hello ' + name);
}
function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}
processUserInput(greeting);
```
#### What is a Python decorator? How does it work? Tell some examples of its usage.
* **Decorators** wrap functions, modifying the behavior of the code before and after a target function execution, 
without the need to modify the function itself:
```
def decorator(func):
    def func_wrapper(name):
        print("Wrapper function first part")
        print(func(name))
        print("Wrapper function last part")
    return func_wrapper
@decorator
def function_to_wrap(text_parameter):
   return "Wrapped function. Its parameter: " + text_parameter
```
#### What is the difference between synchronous and asynchronous execution?
* When you execute something synchronously, you wait for it to finish before moving on to another task. When you 
execute something asynchronously, you can move on to another task before it finishes.
***

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
* In order to connect to the database, we create a connection to it. Any queries and operations are performed 
using the connection, which is closed after the work is finished.
* Use environment variables to save personal data, like database password, database name, host and user name.
#### When do you use the DISTINCT keyword in SQL?
* The SQL DISTINCT keyword is used in conjunction with the SELECT statement to eliminate all the duplicate records and 
fetching only unique records.
#### What are aggregate functions in SQL? Give 3 examples.
* Aggregate expressions (or functions) allow you to summarize information about a group of rows of data:
* i.e. ARRAY_AGG function is used to concatenate the input values including null into an array.
```
SELECT COUNT(*) FROM table WHERE name='Paul';
SELECT name, AVG(salary) FROM table GROUP BY name;
SELECT ARRAY_AGG(salary) FROM table;
```
#### What kind of JOIN types do you know in SQL? Could you give examples?
* INNER JOIN is a process that matches rows from the first table and the second table which have the same key (as 
defined by the ON constraint) to create a result row with the combined columns from both tables.
* When joining table A to table B, a LEFT JOIN simply includes rows from A regardless of whether a matching row is 
found in B.
* The RIGHT JOIN is the same, but reversed, keeping rows in B regardless of whether a match is found in A. 
* FULL OUTER JOIN simply means that rows from both tables are kept, regardless of whether a matching row exists in 
the other table.
#### What are the constraints in sql?
* Constraints are the rules enforced on data columns on table.
* Defining a data type for a column is a constraint in itself.
```
CREATE TABLE department1(
   id INT PRIMARY KEY      NOT NULL,
   dept           CHAR(50) NOT NULL,
   emp_id         INT      references company6(id)
);
```
#### What is a cursor in SQL? Why would you use one?
* The major function of a cursor is to retrieve data, one row at a time, from a result set, unlike the SQL commands
which operate on all the rows in the result set at one time.
* Cursors are used when the user needs to update records in a singleton fashion or in a row by row manner, in a
database table.
#### What are database indexes? When to use?
* Indexes are special lookup tables that the database search engine can use to speed up data retrieval.
* An index is a pointer to data in a table. An index in a database is very similar to an index in the back of a book.
* An index helps to speed up SELECT queries and WHERE clauses; however, it slows down data input, with UPDATE and
 INSERT statements. 
* Indexes can be created or dropped with no effect on the data.
#### What are database transactions? When to use?
* A transaction is a unit of work that is performed against a database.
* For example, if you are creating a record, updating a record, or deleting a record from the table, then you are 
performing transaction on the table.
*  It is important to control transactions to ensure data integrity and to handle database errors. Practically, you
 will club many SQL queries into a group and you will execute all of them together as a part of a transaction:
 ```
BEGIN;
...
COMMIT;
[ROLLBACK;]
```
#### What kind of database relations do you know? How to define them?
* There are three specific types of relationships that can exist between a pair of tables: 
    * one-to-one = when a single record in the first table is related to only one record in the second table, and a
    single record in the second table is related to only one record in the first table.
    * one-to-many = when a single record in the first table can be related to one or more records in the second table,
    but a single record in the second table can be related to only one record in the first table.
    * many-to-many = when a single record in the first table can be related to one or more records in the second table
    and a single record in the second table can be related to one or more records in the first table.
#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
```
SELECT * FROM table WHERE address LIKE '%Miskolc%';
```
#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
* Call a stored procedure on your database server to write a log of the database changes.
* To track those changes made to tables in PostgreSQL you can write a generic changelog trigger.
***

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
* XML is abbreviation for Extensible Markup Language whereas HTML stands for Hypertext Markup Language.
* XML is a markup language that defines a set of rules for encoding documents in a format that is both 
human-readable and machine-readable.
* XML is strict for closing tag while HTML is not strict. XML tags are extensible whereas HTML has limited tags.
* XML tags are not predefined whereas HTML has predefined tags.
* XHTML stands for EXtensible HyperText Markup Language and is a stricter, more XML-based version of HTML.
* XHTML is HTML defined as an XML application and is supported by all major browsers.
#### How to include a JavaScript file in a webpage?
* Internal:
```
<script>
    alert("Hello, world.");
</script>
```
* External:
```
<script src="script.js"></script>
```
#### How to include a CSS file in a webpage?
* Inline:
```
<p style="color: red">text</p>
```
* Internal:
```
<head>
    <title>CSS Example</title>
    <style>
        p {
            color: red;
        }
        a {
            color: blue;
        }
    </style>
</head>
```
* External (separate CSS file):
```
p {
    color: red;
}

a {
    color: blue;
}
```
#### How to select an element using its id in CSS?
```
#top {
    background-color: #ccc;
    padding: 20px
}
```
#### How to select elements using their class in CSS?
```
.intro {
    color: red;
    font-weight: bold;
}
```
#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
```
.alpha.beta {
    color: red;
    font-weight: bold;
}
```
#### How to select all list items in all ordered lists on the page in CSS?
```
ol li {
    color: red;
    font-weight: bold;
}
```
#### How to select elements using their attributes in CSS?
```
input[type=text] { width: 200px; }
```
#### What are UX and UI?
* UX deals with the purpose and functionality of the product.
* UI deals with the quality of the interaction that the end-user has with the product.
* UI design has an artistic component as it relates to the design and interface with the product.
#### Please list some points that an application should fulfill to have good UX.
* Contrast - make the font bright not the background
* Font size
* Precise positioning
* Make it work with keyboard
* Cover all visual info with textual
#### What is XML, XSLT, DTD?
* XSLT (eXtensible Stylesheet Language Transformations) is the recommended style sheet language for XML. XSLT is far 
more sophisticated than CSS. 
* With XSLT you can add/remove elements and attributes to or from the output file.
* A document type definition (DTD) is a set of markup declarations that define a document type for an SGML-family 
markup language (GML, SGML, XML, HTML).
* The purpose of a DTD (Document Type Definition) is to define the legal building blocks of an XML document
#### What is the difference between HTML and XML?
* Hypertext Markup Language (HTML) is the standard markup language for documents designed to be displayed in a 
web browser.
* XML stands for Extensible Markup Language. It is a text-based markup language derived from Standard Generalized 
Markup Language (SGML).
* HTML is used for the data presentation whereas the main purpose of XML was to store and transfer the data.
* HTML is a simple, predefined language while XML is the standard markup language to define other languages. 
***

### Javascript

#### What is javascript?
* JavaScript is a lightweight, interpreted programming language. It is designed for creating network-centric 
applications.
* It is easy to implement because it is integrated with HTML. It is open and cross-platform.
* While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, 
such as Node.js, Apache CouchDB and Adobe Acrobat.
#### When to use AJAX? Bring examples of its usage.
* AJAX = Asynchronous JavaScript and XML. AJAX is a technique for creating fast and dynamic web pages. 
* AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the 
scenes.
* Almost all sites that pull in new content without a page reload (like Facebook, Gmail, Google Maps etc) use this 
same technique:
```
async function getUsersAsync(count) {
    let response = await fetch(`https://randomuser.me/api/?results=${count}`);
    let data = await response.json()
    let results = data.results;
    for (let result of results) {
        list.innerHTML += populateCard(result);
    }
}
getUsersAsync(5);
```
#### What is DOM and how to manipulate it from Javascript?
* DOM is the Document Object Model. It is the API in HTML and XML document.
* JavaScript Methods For DOM Manipulation:
    * querySelector() The querySelector() method returns the first element that matches one or more CSS selectors
    * querySelectorAll()
    * addEventListener()
    * removeEventListener()
    * createElement()
    * appendChild()
    * removeChild()
    * replaceChild()
    * cloneNode() When you have to create a new element that needs to be the same as an already existing element on 
    the web page
    * insertBefore() method adds a specified child element before another child element. 
    * createDocumentFragment() method insert multiple elements in bulk, such as adding multiple rows to a table.
    * getComputedStyle() returns the read-only computed values of all the CSS properties of a specified HTML element.
    * setAttribute()
    * getAttribute() 
    * removeAttribute()
#### What are events and how/why to use them in Javascript?
* JavaScript's interaction with HTML is handled through events that occur when the user or the browser manipulates 
a page.
* When the page loads, it is called an event. When the user clicks a button, that click too is an event. Other 
examples include events like pressing any key, closing a window, resizing a window, etc.
* Events are a part of the Document Object Model (DOM) Level 3 and every HTML element contains a set of events 
which can trigger JavaScript Code.
* These events are used to execute JavaScript coded responses, which cause buttons to close windows, 
messages to be displayed to users, data to be validated, and virtually any other type of response imaginable.
#### What is event bubbling/capturing? How would you use it?
* Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an 
element inside another element, and both elements have registered a handle for that event.
* bubbling = the event is first captured and handled by the innermost element and then propagated to outer elements.
* capturing = the event is first captured by the outermost element and propagated to the inner elements.
* We can use the **addEventListener(type, listener, useCapture)** to register event handlers for in either 
bubbling (default, useCapture=false) or capturing mode.
* To use the capturing model pass the third argument as true.
#### What is JSON and how do we use it?
* JSON is JavaScript Object Notation = format is often used for serializing and transmitting structured data over 
a network connection.
* It is used primarily to transmit data between a server and web application, serving as an alternative to XML. 
***

## Software engineering

### Version control

#### What type of branching strategy would you use?
1. Centralized Workflow:
    * uses a central repository to serve as the single point-of-entry for all changes to the project.
    * the default development branch is called master and all changes are committed into this branch.
    *  This workflow doesn’t require any other branches besides master.
2. Feature branching:
    * all feature development should take place in a dedicated branch instead of the master branch.
    * the master branch should never contain broken code.
3. Forking Workflow:
    * gives every developer a server-side repository.
    * each contributor has not one, but two Git repositories: a private local one and a public server-side one.
    *  does not use a single server-side repository to act as the “central” codebase.
#### What would you do if you find a bug on the production code (master branch)?
* Create a hotfix branch from your "production" commit, fix bug, and merge it to master and develop.
#### How can you move changes from one branch to another in GIT?
* You can create a new branch pointing to the current commit using "git branch branchname"
(or "git checkout -b branchname" if you want to check it out directly).
* This will basically duplicate your master branch, so you can continue working on there.
#### How does a VCS help with code reviews?
* Because VCS keeps track of:
    * a complete long-term change history of every file. This means every change made by many individuals over time. 
    * the ability to work on independent streams of changes.
    * each change made to the software and connects it to project management and bug tracking software such as 
    Jira, and being able to annotate each change with a message describing the purpose and intent of the change
#### What is your favorite git command? Why?
```
git log --graph --decorate --oneline
```
* It will draw a text based graph of the commits on the left hand side of the commit messages, with the names of
 branches or tags of the commits on a single line.
#### What does remote/local mean in Git?
* **git remote** = lists the remote connections you have to other repositories.
* **git remote -v** = same including the URL of each connection.
* **git remote -v** = create a new connection to a remote repository. 
* **git remote rm <name>** = remove the connection to the remote repository called <name>.
***

### DevOps

#### Why is it good to use a package manager software?
* A package manager software is a programming language’s tool to create project environments and easily import external 
dependencies.
* **pip** allows you to add dependencies to your projects for your given Python instalments.
#### Why is it good to use a virtual environment for a project?
* **virtualenv** is a tool to create isolated Python environments. It solves a very specific problem: it allows
 multiple Python projects that have different (and often conflicting ) requirements, to coexist on the same computer.
***

### Networks

#### What kind of HTTP status codes do you know?
* 1xx Informational
    * Request received, continuing process.
* 2xx Success
    * action requested by the client was received, understood, accepted and processed successfully.
* 3xx Redirection
    * client must take additional action to complete the request.
* 4xx Client Error
    * client seems to have erred.
* 5xx Server Error
    * server failed to fulfill an apparently valid request.
#### What is a API?
* is a gate (interface) in a software, that allows connectivity for the outside word. Usually one API endpoint lets 
you interact with one certain part of the given software.
#### What is REST API?
* Representational state transfer (REST) or RESTful is an architectural style used for web development, aiming for fast
 performance, reliability and the ability to scale (to grow and easily support extra users). 
* RESTful API ensures other developers can understand the structure easily compared to creating endpoints without a
 standard.
#### What is JSON? When to use?
* JSON or JavaScript Object Notation is a lightweight text-based open standard designed for human-readable data
 interchange. 
* JSON format is used for serializing and transmitting structured data over network connection.
* It is primarily used to transmit data between a server and web applications.
* Web services and APIs use JSON format to provide public data.
#### What is TCP/IP? What layers does it define, what are they responsible for?
* The Internet works by using a protocol called TCP/IP, or Transmission Control Protocol/Internet Protocol.
* TCP/IP allows one computer to talk to another computer via the Internet through compiling packets of data and
 sending them to right location.
* TCP/IP model is practical model and is used in the Internet, which combines the two layers (Physical and Data link
 layer) into one layer i.e. Host-to-Network layer:
    * Application Layer
        * provides different services such as manipulation of information, retransferring the files
         of information, distributing the results etc.
        * functions such as LOGIN or password checking are also performed by the application layer.
        * Protocols used in this layer: TELNET, FTP, SMTP, DN, HTTP, NNTP 
    * Transport Layer
        * uses TCP and UDP protocols for end to end transmission.
        * TCP is reliable and connection oriented protocol, that also handles flow control.
    * Internet Layer
        * allows the host to insert packets into network and then make them travel independently to the destination.
        * the order of receiving the packet can be different from the sequence they were sent.
        * Protocols used in this layer: Internet Protocol (IP).
    * Host-to-Network Layer
        * the host has to connect to network using some protocol, so that it can send IP packets over it.
        * Protocols used in this layer: ARPANET, SATNET, LAN, packet radio
#### What’s the difference between TCP and UDP?
* User Datagram Protocol is used for broadcast and multicast type of network transmission.
* UDP protocol works almost similar to TCP, but it throws all the error-checking out.
* TCP is a connection-oriented protocol, whereas UDP is a connectionless protocol.
* TCP reads data as streams of bytes, and the message is transmitted to segment boundaries. TCP rearranges data
 packets in the specific order.
* UDP messages contain packets that were sent one by one. It also checks for integrity at the arrival time. UDP
 protocol has no fixed order because all packets are independent of each other.
* The speed for TCP is slower while the speed of UDP is faster.
*  UDP is used if both client and server may separately send packets, and occasional delay is also not acceptable. (e.g
. multiplayer games).
#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
* HTTP header fields provide required information about the request or response, or about the object sent in the
  message body. There are four types of HTTP message headers:
    * General-header: These header fields have general applicability for both request and response messages.
        * Connection
    * Client Request-header: These header fields have applicability only for request messages.
        * Accept-Language
        * Accept-Encoding
    * Server Response-header: These header fields have applicability only for response messages.
        * Location : absoluteURI
        * Set-Cookie: NAME=VALUE; OPTIONS
    * Entity-header: These header fields define meta information about the entity-body or, if no body is present
    , about the resource identified by the request.
        * Allow: GET, HEAD, PUT, POST
        * Content-Length
        * Content-Type
* **GET** request
```
GET /hello.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.tutorialspoint.com

Accept-Language: en-us
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
```
* **POST** request
```
POST /cgi-bin/process.cgi HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.tutorialspoint.com

Content-Type: application/x-www-form-urlencoded
Content-Length: length

Accept-Language: en-us
Accept-Encoding: gzip, deflate
Connection: Keep-Alive

licenseID=string&content=string&/paramsXML=string
```
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
* The request method indicates the method to be performed on the resource identified by the given Request-URI. 
* Most relevant request methods:
    * GET method is used to retrieve information from the given server using a given URI. Requests using GET
     should only retrieve data and should have no other effect on the data.
     * 	POST request is used to send data to the server, for example, customer information, file upload, etc
     . using HTML forms.
     * 	PUT Replaces all the current representations of the target resource with the uploaded content.
     * DELETE Removes all the current representations of the target resource given by URI.
* HTTP Response example:
```
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
Content-Length: 88
Content-Type: text/html
Connection: Closed
```
#### What is DNS? How does it work?
* DNS (Domain Name Server) is a host name to IP address translation service. It is a distributed database
 implemented in a hierarchy of name servers. It is an application layer protocol for message exchange between clients
  and servers.
* Domain name system comprises of: 
    * Domain Name
        * a symbolic string associated with an IP address. 
        * there are several domain names available; some of them are generic such as com, edu, gov, net etc,
        * some country level domain names such as au, in, za, us etc.
    * Domain Name Space
        * refers a hierarchy in the internet naming structure, which has multiple levels (from 0 to 127), with a 
        root at the top: edu &rarr; colorado &rarr; cs &rarr; kim
        * each domain can be partitioned into sub domains and these can be further partitioned and so on.
    * Name Server
        * contains the DNS database, that comprises of various names and their corresponding IP addresses. 
        * it is not possible for a single server to maintain entire DNS database, the information is distributed
         among many DNS servers.
        * The entire name space is divided into the zones
    * Zones
        * a collection of nodes (sub domains) under the main domain. The server maintains a database called zone file
         for every zone.
#### What is a web server?
* It is a computer where the web content is stored. Basically web server is used to host the web sites but there exists
 other web servers also such as gaming, storage, FTP, email etc.
#### Explain the client-server architecture.
* works with a system of request and response. The client sends a request to the server and the server responds with
  the desired information.
* The client and server follow a common communication protocol so they can easily interact with each other. All the
 communication protocols are available at the application layer.
* A server can only accommodate a limited number of client requests at a time. So it uses a system based to priority
  to respond to the requests.
* A web server is a client server computing system. It returns the web pages to the clients that requested them.
#### What would you use a session for?
* A session creates a file in a temporary directory on the server where registered session variables and their
  values are stored. This data will be available to all pages on the site during that visit.
* A session ends when the user closes the browser or after leaving the site, the server will terminate the session
  after a predetermined period of time, commonly 30 minutes duration.
#### What would you use a cookie for?
* Cookies are text files stored on the client computer and they are kept for tracking purposes. Server script
  sends a set of cookies to the browser.
* For example name, age, or identification number etc. The browser stores this information on a local machine for
 future use.
* When next time browser sends any request to web server then it sends those cookies information to the server and
  server uses that information to identify the user.
***

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
* Waterfall Model
    * Requirement Gathering and analysis
    * System Design
    * Implementation
    * Integration and Testing
    * Deployment of system
    * Maintenance
* Agile Model
    * User Stories &rarr; features customers might one day like to see in their software.
    * Estimation &rarr; make some really accurate predictions about the future while based on what was done in the past.
    * Iterations &rarr; a short one to two week period where a team takes a couple of their customers most important
     user stories and builds them completely as running-tested-software.
    * Planning &rarr; measuring the speed a team can turn user stories into working, production-ready software and
      then using that to figure out when they’ll be done.
    * Unit Testing &rarr; snippets of test code developers write to prove to themselves that what they are developing
     actually works.
    * Refactoring &rarr; maintaining order in the design
    * Burndown Charts &rarr; a chart that shows how quickly the customer's user stories are burned. It shows the total
     effort against the amount of work delivered for each iteration.
#### What are the SCRUM roles?
* Scrum is an efficient framework within which you can develop software with teamwork. It is based on agile principles.
* The Scrum Team consists of three roles, namely a ScrumMaster, a Product Owner, and the Team:
    * ScrumMaster &rarr; the keeper of the scrum process. He/she is responsible for:
        * making the process run smoothly
        * removing obstacles that impact productivity
        * organizing and facilitating the critical meetings
    * Product Owner &rarr; is the sole person responsible for managing the Product Backlog. Product Backlog
     management includes:
        * Expressing Product Backlog items clearly.
        * Ordering the Product Backlog items to best achieve goals and missions.
        * Optimizing the value of the work the Team performs.
        * Ensuring that the Product Backlog is visible, transparent, and clear to all, and shows what the Team will
         work on further.
         * Ensuring that the Team understands items in the Product Backlog to the level needed.
     * The Team &rarr; comprises of analysts, designers, developers, testers, etc. as appropriate and as relevant to
      the project.
        * The Team size should be kept in the range from five to nine people, if possible.
#### What are the SCRUM ceremonies?
* Sprint Planning Meeting &rarr; discuss and estimate the high priority user stories, and forecast the work which
  can be consummate in the current sprint.
* Daily Stand-up Meeting &rarr; enhances the team communications, increases visibility of the work, allows quick
 decisions making abilities, identifying and removing the obstacles.
* Sprint Review Meeting &rarr; also called as Demo or Showcase meeting held at the end of the sprint to demonstrate
  the actual working software to review and get the feedback.
* Sprint Retrospective Meeting &rarr; collect the feedback on how the team worked in the just concluded sprint. And
  based on those input the team identify the improvements for the next sprints.
#### What are the SCRUM artifacts?
* Scrum Artifacts provide key information that the Scrum Team and the stakeholders need to be aware of for
  understanding the product under development, the activities done, and the activities being planned in the project:
    * Product Backlog &rarr; list of items that have the attributes of a description, order, estimate, and value. These
     items are normally termed as User Stories.
    * Sprint Backlog &rarr; set of Product Backlog items selected for the Sprint, plus a plan for delivering the
     product Increment and realizing the Sprint Goal.
    * Increment &rarr; the sum of all the Product Backlog items completed during a Sprint combined with the
      increments of all previous Sprints.
    * Sprint Burn-Down Chart &rarr; the total work remaining in the Sprint Backlog.
#### What is the main goal of a retrospective meeting?
*  A lesson learned discussions to improve the way of work for the betterment of the team and the project.
#### Explain, when would you recommend to use the waterfall methodology?
* Waterfall methodology is recommended when:
    * Requirements are very clear and fixed. 
    * There are no ambiguous requirements. 
    * Ample resources with required expertise are available freely. 
    * The client has high confidence in the organization.
***