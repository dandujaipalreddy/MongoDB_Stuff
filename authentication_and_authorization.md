# Authentication and Authorization in MongoDB
* _Authentication verifies the user’s identity, and authorization determines the level of actions that the user can
perform on the authenticated database_
* _Both authentication and authorization exist at a per-database level. The users exist in the context of a
single logical database_
* _The information on the users is maintained in a collection named system.users , which exists in the
admin database. This collection maintains the credentials needed for authenticating the user wherein
it stores the user id, password, and the database against which it is created, plus privileges needed for
authorizing the user_
* _MongoDB uses a role-based approach for authorization_
* _Authentication is disabled by default, so use --auth to enable authentication while starting mongod_

## Authentication Mechanisms
* _MongoDB supports a number of authentication mechanisms that clients can use to verify their identity._
* _These mechanisms allow MongoDB to integrate into your existing authentication system.The following are some of the authentication mechanisms supported by MongoDb._
* _**1)SCRAM-SHA-1 [Default from version 3.0]**_
* _**2).MongoDB Challenge and Response (MONGODB-CR)**_
* _**3).x.509 Certificate Authentication**_

## Users
* _To authenticate a client in MongoDB, you must add a corresponding user to MongoDB._
* _*creating user : *_  `use admin;db.createUser({user: "AdminUser", pwd: "password", roles:["userAdminAnyDatabase"]}) ` 
* _*Authenticating  user : *_  `use admin;db.auth("AdminUser","password") `
*  [Follow this for more information](https://docs.mongodb.com/manual/tutorial/enable-authentication/)
*  [Role-Based Access Control](https://docs.mongodb.com/manual/core/authorization/)

## Use Firewalls
* _Firewalls are used to control access within a network. They can be used to allow access from a specific IP address to specific IP ports, or to stop any access from any untrusted hosts. They can be used to create a trusted environment for your mongod instance where you can specify what IP addresses or hosts can connect to which ports or interfaces of the mongod_


