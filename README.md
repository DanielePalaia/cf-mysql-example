# cf-mysql-example
Sample of an application using cloud foundry with a mysql instance bounded. </br></br>

The program is implementing a Todo List throught a set of rest api </br>
You can get the collection of Todo to do, you can insert, update or delete a new todo item following this curl commands:</br>

You can test with curl the various rest api, for instance</br>

curl http://localhost:8080/todos</br>

will do get to the collection showing all the collection elements</br>

this one will create a new element to the collection</br>
curl -H "Content-Type: application/json" -d '{"Topic":"New TodoElem", "Completed":0}' -X POST http://localhost:8080/todos</br>

this one will get an element:</br>
curl http://localhost:8080/todos/1</br>

this one will update an existing element of the collection</br>
curl -H "Content-Type: application/json" -d '{"Id":0,"name":"New TodoElem Updated"}' -X PUT http://localhost:8080/todos</br>

this one will delete a resource</br>
curl -X DELETE http://localhost/todos/1</br>

this one will delete all the collection</br>
curl -X DELETE http://localhost/todos</br>

 </br>
 
 **Running the project locally**</br>
 You need an instance of mysql to run. Create a database and the simple table as defined in the file datastore.sql</br> 
 In the file conf specify the dbms parameters (user, password, host, port and database)</br> 
 
 Run /bin/project</br>  
 
 The server will start listening to port 8080 ready to listen to the curl command as specified above</br>
 </br>  
**Running on Cloud Foundry**</br>
1. Download and install cf-dev https://docs.pivotal.io/pcf-dev/usage.html or create and account at Pivotal Web Service https://run.pivotal.io/</br>
2. Download and install the cf client</br>
3. Login with cf </br>
   cf login -a https://api.dev.cfdev.sh --skip-ssl-validation </br>
4. cf push on the current project path </br>
5. Open the apps manager and login with: admin, admin </br> 
   https://login.dev.cfdev.sh/home   </br> 
6. in services section create a new mysql service and bind it to the current app (todos)</br> 
8. Do an cf mysql your_mysel_service_name in order to enter to the mysql prompt of the mysq instance now created</br>
9. Create database and table as specified in datastore.sql </br>
10. Create a binding key, once created have a look at it in order to look to the username/password and host to use</br> 
11. Replace the info in the conf file of the project and cf push again</br> 
12. Use https://todos.dev.cfdev.sh/todos and the commands specified before to test teh application using the rest-api </br> 13. Do and cf ssh todos in order to enter the container app and go to /app/logs/mylogger.log in order to debug and see the log of the application if necessary.
