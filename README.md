# Interview

## Question 1
#### What is the most influential book or blog post you’ve read regarding web development?

https://www.w3schools.com/ , this website has been the best help for most of my doubts related to web development and 
definitely inspired me to learn more about new web technologies.

---

## Question 2
#### Tell me about a web application you have built. Why did you choose to build it? What did you learn? What challenges did you face and how did you overcome them?

I built an API for a job interview where I had to create an API for flight search, they just give some requirements but, they expect extra features. I started to research about designing guidelines, RESTful API architecture, concepts and technical aspects. After all the research I decided to implement pagination and memcached. I decided to use Tornado (Python web framework) because they used Tornado to build their API’s, this was a big challenge because I had limited time and I had to learn from scratch, but at the end, I was able to learn the basics and build the API.


---

## Question 3
#### Write a function that takes a list of strings and returns a single string that is an HTML unordered list `(<ul>...</ul>)` of those strings. You should include a brief explanation of your code. Then, what would you have to consider if the original list was provided by user input?

```python
def htmlUnorderedList(listStr):
    ul = "\n \
    <ul>\n"
    for string in listStr:
        ul += "\
          <li>"+string+"</li>\n"  # for each string in list create a list item
    ul += "\
    </ul>"
    # HTML structure
    html_format = """<html>
    <head>
    </head>
    <body>%s
    </body>
    </html>"""
    html_msg = html_format % (ul) # HTML message
    return html_msg

```

If the list is given by user input, the function should check if the input is a list, and if the list contains strings.

---

## Question 4
#### List 2-3 attacks that web applications are vulnerable to. How do these attacks work? How can we prevent those attacks?

### Cross-Site Scripting (XSS) 
	This attack involves injecting malicious code into a website, but the website itself is not being attacked. Instead, the malicious code the attacker has injected only runs in the user's browser when they visit the attacked website, and it goes after the visitor directly, not the website. For example, they could embed a link to a malicious JavaScript in a comment on a blog. 

How to Prevent Cross-Site Scripting Attacks
1. Sanitize user input:
	1.1 Validate to catch potentially malicious user-provided input.
	2.2 Encode output to prevent potentially malicious user-provided data from triggering automatic load-and-execute behavior by a browser.

2. Limit use of user-provided data.

3. Regularly use a web vulnerability scanning tool to identify XSS vulnerabilities in your software.
 

### SQL Injection Attack 
	An SQL injection attack works by exploiting any one of the known SQL vulnerabilities that allow the SQL server to run malicious code. For example, if a SQL server is vulnerable to an injection attack, it may be possible for an attacker to go to a website's search box and type in code that would force the site's SQL server to dump all of its stored usernames and passwords for the site. 

How to Prevent SQL Injection Attacks
	1. Don’t use dynamic SQL
		Avoid placing user-provided input directly into SQL statements.
		Prefer prepared statements and parameterized queries
		Stored procedures are also usually safer than dynamic SQL.
	2. Sanitize user-provided inputs
		Properly escape those characters which should be escaped.
		Verify that the type of data submitted matches the type expected.
	3. Don’t leave sensitive data in plaintext
		Encrypt private/confidential data being stored in the database.

	4. Limit database permissions and privileges
		Set the capabilities of the database user to the bare minimum required.
		This will limit what an attacker can do if they manage to gain access.
	5. Avoid displaying database errors directly to the user

	6. Use a Web Application Firewall (WAF) for web applications that access databases
		This provides protection to web-facing applications.
		It can help identify SQL injection attempts.
		
	7. Use a web application security testing solution to routinely test web apps that 	interact with databases
	
	8. Keep databases updated to the latest available patches

---

## Question 5
#### Here is some starter code for a Flask Web Application. Expand on that and include a route that simulates rolling two dice and returns the result in JSON. You should include a brief explanation of your code.

```python
import random
from flask import Flask, jsonify
app = Flask(__name__)

import json
import random

@app.route('/')
def hello_world():
 return 'Hello World!'

# Rolling two dice function
@app.route('/dice', methods=['GET'])
def rolling_dice():
    dice01 = random.randint(1,6) # use of random to simulate a rolling dice
    dice02 = random.randint(1,6)
    sum = dice01 + dice02 # sum of two random values
    return jsonify({'value': sum, 'num_dice': 2}) # generate json response

if __name__ == '__main__':
 app.debug = True
 app.run()


```

The '/dice' enpoint has the funcionality to roll two dice and return the result as a json string. 
The result of each die roll is add and assigned to sum variable. 

---

## Question 6
#### If you were to start your full-stack developer position today, what would be your goals a year from now? 

One year from now, I will have learned and created React web applications, and for that I have to improve my javascript skills and learn other libraries that complete React like for example, Redux or Relay.




