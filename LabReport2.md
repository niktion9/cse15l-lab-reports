# Lab Report 2

## Part 1:
### Code for Server:
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/33de48db-e347-4dd6-bdbd-797e5f3f09e3)


### Screenshot of First Message:
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/7abffdb3-cc45-475b-86bd-b1c47a8acb6f)


Explantion: 
To acheive the desired outcome, the ```handleRequest``` method takes in the URL as an argumet and it breaks down the entry into the 2 needed parameters that are to be displayed, name and the respective message. This method belongs to the ```handler``` class, which has a field called ```finalMessage``` which consists of the final output that will be presented on the server and it gets updated everytime there is a new entry to the url, and is returned at the end of the method. Within the ```handleRequest()``` method, String array fields like ```splitRequest```, ```stringParameter```, and ```nameParameter``` are used to store and split up different component of the entry, which helps us to get down to the main phrases used for display. The final phrases are the stored in ```String userMessage``` and ```String userName```, which are combined into ```finalMessage```. ```finalMessage``` starts off as an empty list, once the query gets split up into portion, it is then concatenated in the specific order the format of the final output in required to be in, and the final string is stored as the final message.


### Screenshot of Second Message:
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/2747b6a2-8629-42b6-a437-ba6d5d494770)

Explanation:
The second message has more words and spaces for the message parameter, and it has to be stored along with the first message. So, the value of ```finalMessage``` changes as new parameters get added on to the next line (thanks to the ```/n```). The new string of message get added onto a new line The same method is used and the all the other values play the same role with the second input as well.


## Part 2:
### Screenshot of login without key
![image](https://github.com/niktion9/cse15l-lab-reports/assets/150311091/b76c6733-113a-4384-8158-b9d7b63efef9)


### Screenshot of public key absolute path
<img width="616" alt="Screen Shot 2024-01-30 at 4 52 43 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/bf4caa74-1ce6-49c1-b632-c606d602621c"/>

### Screenshot of private key absolute path
<img width="661" alt="Screen Shot 2024-01-30 at 5 02 13 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/175da808-1f66-4fdb-9db4-9e0dd7628777"/>

## Part 3
I have only heard of private and public key as terminology in a one-day class topic of cryptography. With this lab report I have learned about the difference and encryption that lies within each of the keys, and their purpose of keep details safe while still allowing us to inderact to external services. Also, I have taken this course with little to no knowledge on how to use a terminal. So, the past two weeks of instruction have been filled with new concepts and lots of learning. A highlight would be learning about cat and curl commands. I think these two commands make everyone's lives so much more easier!
