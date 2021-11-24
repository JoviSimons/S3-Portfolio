
# Welcome to my Learning Outcomes!

## Table of Contents
1. [Web Application](#Web-Application)
2. [Software Quality](#Software-Quality)
3. [CI/CD](#CI/CD)
4. [Professional](#Professional)


## Web Application

### Applications
1. [MyDrugs Front-end](#MyDrugs-Front-end)
2. [ProductService](#ProductService)
3. [CartService](#CartService)

### MyDrugs Front-end
Repository: [MyDrugs](https://bitbucket.org/studentjovi-admin/mydrugs/src)

### ProductService
Repository: [ProductService](https://bitbucket.org/studentjovi-admin/productservice/src)

### CartService
Repository: [CartService](https://bitbucket.org/studentjovi-admin/mydrugs/src/master/)


## Software Quality

For this learning outcome I wrote and automated tests for my [ProductService](https://bitbucket.org/studentjovi-admin/productservice/src). I have used Unit and Integration tests for this.

### 1. Unit Testing

Unit Testing is done during the development (coding phase) of an application by the developers. Unit Tests isolate a section of code and verify its correctness. A unit may be an individual function, method, procedure, module, or object. That is why Unit tests are so important, they test an individual component of your application and run fast.

I have made two Unit Tests. One tests Unit tests my CategoryService and the other tests my CategoryRepository.

| Repository Tests | Service Tests |
| --- | ----------- |
| <img width="501" alt="Repo Test" src="https://user-images.githubusercontent.com/33750291/143297753-ed394e8b-9275-47c3-be75-cfa678c6b816.png">   | <img width="414" alt="Service" src="https://user-images.githubusercontent.com/33750291/143297986-0b1c01e8-15c0-48e1-87af-aa14d06e4ea9.png"> |
| <img width="324" alt="Succesful repo test" src="https://user-images.githubusercontent.com/33750291/143291249-9a823594-beb8-453c-9b7c-d4a6d3f4042b.png"> | <img width="179" alt="Succesful service test" src="https://user-images.githubusercontent.com/33750291/143291275-c24f93c8-92c7-4077-bbbc-2b7e1fcd179f.png"> |

Sources:
- <a href="https://www.youtube.com/watch?v=TJcshrJOnsE&list=PL6gx4Cwl9DGDPsneZWaOFg0H2wsundyGrMockMvc">thenewboston</a>
- <a href="https://www.youtube.com/watch?v=Geq60OVyBPg&t=2283s">AmigosCode</a>


### 2. Integration Testing

Integration tests verify that different modules or services used by your application work well together.
I made 2 types of Integration. The MockMvc is used for Server side testing and the testRestTemplate is used for Client side testing. I chose to do this because of learning purposes.

| MockMvc tests | testRestTemplate tests |
| --- | ----------- |
| <img width="819" alt="MockMvc Test 1" src="https://user-images.githubusercontent.com/33750291/143293422-68e46bf9-9020-471f-a651-73f989a84304.png">
<img width="903" alt="MockMvc Test 2" src="https://user-images.githubusercontent.com/33750291/143293427-55d356cd-595f-4f32-9a13-67b872614448.png"> | <img width="969" alt="testRestTemplate test" src="https://user-images.githubusercontent.com/33750291/143293471-f2445164-60e5-4aee-82e1-c0f2e246c0ba.png"> |
| <img width="482" alt="MockMvc succesful tests" src="https://user-images.githubusercontent.com/33750291/143291328-67233d17-55c5-47d4-a896-37b0852475f9.png">  | <img width="371" alt="testRestTemplate succesful tests" src="https://user-images.githubusercontent.com/33750291/143291323-85337a85-ac11-41c7-8ce6-780ff3f59cef.png"> |

They both test the same functionalities. They test the GET, POST, PUT and DELETE with their exceptions.
I personally think the MockMvc tests are better but the testRestTemplates are easier to understand and use less code. Another difference is the code, the code from MockMvc looks cleaner thus easier to read.

Sources:
- <a href="https://www.baeldung.com/spring-resttemplate-post-json">Baeldung</a> (testRestTemplate)
- <a href="https://www.youtube.com/watch?v=TJcshrJOnsE&list=PL6gx4Cwl9DGDPsneZWaOFg0H2wsundyGrMockMvc">thenewboston</a> (MockMvc)

## CI/CD

Below you can see my first yaml file that uses sonarcloud too check the quality of my code.

<img width="550" alt="first yaml file" src="https://user-images.githubusercontent.com/33750291/137206448-23be4f60-1635-486e-ac1d-bc0ba8be1c1e.png">

The pictures below shows a yaml file that builds, tests and deploys my ProductService.

<p>
<img width="400" alt="second yaml file" src="https://user-images.githubusercontent.com/33750291/140995446-68fda41e-74c4-4466-9f9f-c43abe11d37e.png">
<img width="450" alt="yaml file result" src="https://user-images.githubusercontent.com/33750291/140995456-948ffca8-ff36-45a4-86ba-9c07f8c36258.png">
 </p>
 
 Left picture: in the left picture you can see the yaml file. By default on every push it builds and test the service. When pushing to master branch it will build test and deploy the service to my dockerhub online.
 
 Right picture: in the right picture you can see the result of my yaml file. As seen in the picture it succesfully builds, tests and deploys the service.
 

## Professional

### 1. Jira and Bitbucket

| Jira | Bitbucket|
| --- | ----------- |
| <img width="1377" alt="Schermafbeelding 2021-11-24 om 20 13 54" src="https://user-images.githubusercontent.com/33750291/143300214-2c2a2062-a4e8-44d3-ac16-aad1ab095a0c.png"> | <img width="1211" alt="Schermafbeelding 2021-11-24 om 20 12 57" src="https://user-images.githubusercontent.com/33750291/143300222-1744b2c4-ab27-4af5-8287-cf96eea44503.png"> |




<img width="428" alt="Schermafbeelding 2021-11-19 om 00 16 40" src="https://user-images.githubusercontent.com/33750291/143299920-8734abf2-c897-4654-a26e-40a39c7b8da0.png">

<img width="1136" alt="Schermafbeelding 2021-11-18 om 23 05 11" src="https://user-images.githubusercontent.com/33750291/143299908-5f15c2f0-0597-4a57-b845-90c2e33557e3.png">

