# CS9163 - Application Security 
## Assignment 5

Repo URL: //github.com/joelbcastillo/CS-GY9163_AppSec_Assignment_5

Student: Joel Castillo (jc5383)

Vulnerabilities
- settings.setAllowFileAccessFromFileURLs(true) - There is no reason to allow the embedded browser to access local javascript files. This could introduce vulnerabilities. 
- settings.setAllowUniversalAccessFromFileURLs(true) - Since we don't need to access file urls for javascript we also shouldn't need to allow universal access from files.

Permission Changes
- Since the application only needs to access the internet, I removed all permissions except for the Internet access permission. 
  - Location Access was used to support multiple languages within the application. Since the backend service only supports English there is no need to support this functionality. 
  - It looks like the application was attempting to use SMS to automatically spell check received text messages. I see this as a vulnerability because it means that received messages would be sent automatically to an external service, which could be a major breach of privacy. I've removed all instances of SMSReceiver from the application.