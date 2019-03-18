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


 </br></br>
 
 **Running the project locally**
 

