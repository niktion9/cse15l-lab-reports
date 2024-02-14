# Lab Report 2

## Part 1:
### Code for Server:
<img alt = "Lab2code.png" src = "https://github.com/niktion9/cse15l-lab-reports/blob/main/Lab2code.png?raw=true">

### Screenshot of First Message:
<img width="867" alt="Screen Shot 2024-01-30 at 5 23 55 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/d4129384-f24f-46c4-bb0d-4aba38ad177f"/>


Explantion: 
To acheive the desired outcome, the ```handleRequest``` method takes in the URL as an argumet and it breaks down the entry into the 2 needed parameters that are to be displayed, name and the respective message. This method belongs to the ```handler``` class, which has a field called ```finalMessage``` which consists of the final output that will be presented on the server and it gets updated everytime there is a new entry to the url, and is returned at the end of the method. Within the ```handleRequest()``` method, String array fields like ```splitRequest```, ```stringParameter```, and ```nameParameter``` are used to store and split up different component of the entry, which helps us to get down to the main phrases used for display. The final phrases are the stored in ```String message``` and ```String userName```, which are combined into ```finalMessage```. ```finalMessage``` starts off as an empty list, once the query gets split up into portion, it is then concatenated in the specific order the format of the final output in required to be in, and the final string is stored as the final message.


### Screenshot of Second Message:
<img width="1224" alt="Screen Shot 2024-01-30 at 5 23 01 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/15ab52c8-9ca8-4372-ac86-e3a2f7fb4810">
Explanation:
The second message has more words and spaces for the message parameter, and it has to be stored along with the first message. So, the value of ```finalMessage``` changes as new parameters get added on to the next line (thanks to the ```/n```). The new string of message get added onto a new line The same method is used and the all the other values play the same role with the second input as well.


## Part 2:
### Screenshot of login without key
<img width="799" alt="Screen Shot 2024-01-30 at 4 34 39 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/ae85f74d-1717-4a58-9185-5f791496c5a7"/>

### Screenshot of public key absolute path
<img width="616" alt="Screen Shot 2024-01-30 at 4 52 43 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/bf4caa74-1ce6-49c1-b632-c606d602621c"/>

### Screenshot of private key absolute path
<img width="661" alt="Screen Shot 2024-01-30 at 5 02 13 PM" src="https://github.com/niktion9/cse15l-lab-reports/assets/150311091/175da808-1f66-4fdb-9db4-9e0dd7628777"/>

## Part 3
I have taken this course with zero prior knowledge on how to use a terminal. So, the past two weeks of instruction have been filled with new concepts and lots of learning. A highlight would be learning about cat and curl commands. Personally, I think these two commands make everyone's lives so much more easier!
