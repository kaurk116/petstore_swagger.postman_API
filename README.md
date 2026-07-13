npx newman run /home/karam/Downloads/petstore_swagger.postman_collection.json   when collection  on local workspace
npx newman run petstore_swagger.postman_collection.json  when collection  on github


commands run collection and report report
newman run petstore_swagger.postman_collection.json -r html
npx newman run petstore_swagger.postman_collection.json -r cli,html --reporter-html-export report.html

commands run selenium grid server

java -jar selenium-server-4.40.0.jar standalone

run jenkins:

java -jar jenkins.war --httpPort=9090
http://localhost:9090   Admin admin@123





postman code
**********************
pre request:

const randomNumber = Math.floor(Math.random()*100+1)

var randomString = Math.random().toString(36).substring(2, 8);

//var emailid = "karam"+randomString+"@gmail.com";

pm.environment.set("id" , randomNumber)

pm.collectionVariables.set("username", randomString)

pm.collectionVariables.set("firstName", randomString)

pm.collectionVariables.set("lastName", randomString)

pm.collectionVariables.set("email" , "karam"+randomString+"@gmail.com")

pm.collectionVariables.set("password", randomString)

pm.collectionVariables.set("phone", "8872682291")

pm.collectionVariables.set("userStatus", 0);
********************
post request:
pm.test("Status code is 200", function () {

    pm.response.to.have.status(200);
});
console.log(pm.collectionVariables.get("username"));

*****************
  body
  
{
  "id": "{{id}}",

  "username": "{{username}}",
  
  "firstName": "{{firstName}}",
  
  "lastName": "{{lastName}}",
  
  "email": "{{email}}",
  
  "password": "{{password}}",
  
  "phone": "{{phone}}",
  
  "userStatus": {{userStatus}}
}
