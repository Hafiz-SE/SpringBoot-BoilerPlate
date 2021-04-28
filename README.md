# SpringBoot-BoilerPlate-Microservice

Java Spring Boot based boilerplate code with Spring Security (JWT), Swagger and Logging and many more. 

## How To Use

Step 1 : Go to ```/src/main/resources/application.properties``` select a profile by uncommenting.

Step 2 : Go to corresponding profile and set ```port```, ```datasource-url```,```username``` and  ```password``` . If you to send mail from your application please set ```smtp``` configurations also.

Step 3 : Go to corresponding ```logback-file``` and set logfile address to the property called ```directory``` value.

Step 4 : Go to ```/src/main/resources/com/disl/boilerplate/AppConstants.java``` and set logfile directory as per profile. Check for static variables and replace ```BoilerPlate``` with ```your-project-name```. Don't forget to set Super Admin ```username``` and ```password``` from here.

Step 5 : Go to ```/src/main/resources/com/disl/boilerplate/config/SwaggerConfig.java``` and replace ```Boilerplate``` with ```your-project-name```.

Step 6 : Go to ```pom.xml``` and set ```groupId```,```artifactId```,```version```, ```name``` and ```description``` as per your project. Also refactor the project as per your requirement.

Step 7 : Go to ```/src/main/resources/templates``` edit all the html and replace the text ```boilerplate``` with ```your-project-name```.

Step - 8 : Re-write README.md and write documentation as per your project also switch git head.

Step - 9 : Run the Eureka Server application first. Check your port and test if Eureka Client is opening.

Step - 10 : Run the Zuul-Auth Server. Check port and check if signin is working (EntryController). 

## Adding your own service

Step - 1 : set this  ```spring.application.name=your-service-name``` in application properties (based on your need)

Step - 2  : ```eureka.client.service-url.default-zone=http://localhost:{eurekaport}/eureka``` set this in application properties too.

Step - 3 :   Add this ```		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
		</dependency>``` dependency in your pom.xml file.
    
Step - 4 : Add this lines in application.properties of the Zuul-Auth application ```zuul.routes.your-service.path=/your-service/**
zuul.routes.your-service.service-id=your-service```

Run Eureka Application first. Then Zuul-Auth then all your microservices. 

Please make sure to update tests as appropriate. Now run the application using ```mvn spring-boot:run```. 🤞 If everything is done properly the application will start at your desired port. 

## License
[MIT](https://choosealicense.com/licenses/mit/)
