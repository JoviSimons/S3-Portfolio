
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

#### Single page

In front-end application we can call the API services as seen in the picture below. We get all the products from our Product-Service.

<img width="700" alt="Front-end products" src="https://user-images.githubusercontent.com/33750291/144400269-ce55435c-b449-428b-9b73-f5a26cdb1bd4.png"> 


#### Auth0

For the Aunthentication we use an external service called Auth0. You don't have to make your own authentication system that saves a lot of time. Below you see the button to login when clicked you go to the login/registration page provided by Auth0.

|||
|-|-|
|![login](https://user-images.githubusercontent.com/33750291/144405745-9fd1b457-7010-469b-8628-f5f9a37e0f99.png)|<img width="200" alt="Auth0 login" src="https://user-images.githubusercontent.com/33750291/144401915-de9113f7-0083-431d-a631-7838388a9470.png"> |

When you are logged in you can access your profile page and the possiblity to log-out as seen below.

<img width="700" alt="Auth0 profile" src="https://user-images.githubusercontent.com/33750291/144405393-ea6a42d7-4e03-44e9-9c01-1e61645ae8ae.png"> 

### MyDrugs ProductService

Repository: [ProductService](https://bitbucket.org/studentjovi-admin/productservice/src)

<img width="700" alt="ProductService" src="https://user-images.githubusercontent.com/33750291/144393702-53fcdc8f-7f2e-4482-85b4-1427a86039be.png"> 

<img width="700" alt="ProductSwagger" src="https://user-images.githubusercontent.com/33750291/143325286-b120e303-282b-4bdb-be44-1b67e4721fd5.png"> 

For Documentation I use Swagger UI as seen in the picture above. I have customized swagger so you can see my details instead of the details that are there per default.



### CartService

Repository: [CartService](https://bitbucket.org/studentjovi-admin/mydrugs/src/master/)


## Software Quality

For this learning outcome I wrote and automated tests for my [ProductService](https://bitbucket.org/studentjovi-admin/productservice/src). I have used the in-memory H2 Database as my test database to test my Unit and Integration tests.

### 1. H2 Database

H2 Database is an in-memery database that I use for testing purposes. It's configured so that before I run my tests it will create a database based of my Entities in the service. To do that I have an application.properties file in my test package with this code:

```properties
spring.datasource.url=jdbc:h2:mem:db;DB_CLOSE_DELAY=-1
spring.datasource.username=sa
spring.datasource.password=sa
spring.datasource.driver-class-name=org.h2.Driver
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.h2.console.enabled=true
spring.jpa.defer-datasource-initialization=true
```

To populate the in-memory database with test values I have made a data.sql file in my test package that will be executed after the database is created:

```sql
INSERT INTO Category (id, name, description) VALUES (1, 'Cat', 'description'), (2, 'Category', 'description');
```
Sources:
- <a href="https://www.baeldung.com/spring-boot-h2-database">Baeldung</a>

### 2. Unit Testing

Unit Testing is done during the development (coding phase) of an application by the developers. Unit Tests isolate a section of code and verify its correctness. A unit may be an individual function, method, procedure, module, or object. That is why Unit tests are so important, they test an individual component of your application and run fast.

I have made two Unit Tests. One tests Unit tests my CategoryService and the other tests my CategoryRepository.

| Repository Tests | Service Tests |
| --- | ----------- |
| <img width="501" alt="Repo Test" src="https://user-images.githubusercontent.com/33750291/143297753-ed394e8b-9275-47c3-be75-cfa678c6b816.png">   | <img width="414" alt="Service" src="https://user-images.githubusercontent.com/33750291/143297986-0b1c01e8-15c0-48e1-87af-aa14d06e4ea9.png"> |
| <img width="324" alt="Succesful repo test" src="https://user-images.githubusercontent.com/33750291/143291249-9a823594-beb8-453c-9b7c-d4a6d3f4042b.png"> | <img width="179" alt="Succesful service test" src="https://user-images.githubusercontent.com/33750291/143291275-c24f93c8-92c7-4077-bbbc-2b7e1fcd179f.png"> |

Sources:
- <a href="https://www.youtube.com/watch?v=TJcshrJOnsE&list=PL6gx4Cwl9DGDPsneZWaOFg0H2wsundyGrMockMvc">thenewboston</a>
- <a href="https://www.youtube.com/watch?v=Geq60OVyBPg&t=2283s">AmigosCode</a>


### 3. Integration Testing

Integration tests verify that different modules or services used by your application work well together.
I made 2 types of Integration. The MockMvc is used for Server side testing and the testRestTemplate is used for Client side testing. I chose to do this because of learning purposes.

Below I have two different tests but they test the same functionality. They test the PUT request and check on duplicate entry. 

| MockMvc tests | testRestTemplate tests |
| --- | ----------- |
| <img width="819" alt="MockMvc Test 1" src="https://user-images.githubusercontent.com/33750291/143293422-68e46bf9-9020-471f-a651-73f989a84304.png">
<img width="903" alt="MockMvc Test 2" src="https://user-images.githubusercontent.com/33750291/143293427-55d356cd-595f-4f32-9a13-67b872614448.png"> | <img width="969" alt="testRestTemplate test" src="https://user-images.githubusercontent.com/33750291/143293471-f2445164-60e5-4aee-82e1-c0f2e246c0ba.png"> |
| <img width="482" alt="MockMvc succesful tests" src="https://user-images.githubusercontent.com/33750291/143291328-67233d17-55c5-47d4-a896-37b0852475f9.png">  | <img width="371" alt="testRestTemplate succesful tests" src="https://user-images.githubusercontent.com/33750291/143291323-85337a85-ac11-41c7-8ce6-780ff3f59cef.png"> |

Both files test the same functionalities. They test the GET, POST, PUT and DELETE with their exceptions.
I personally think the MockMvc tests are better but the testRestTemplates are easier to understand and use less code. Another difference is the code, the code from MockMvc looks cleaner thus easier to read.

Sources:
- <a href="https://www.baeldung.com/spring-resttemplate-post-json">Baeldung</a> (testRestTemplate)
- <a href="https://www.youtube.com/watch?v=TJcshrJOnsE&list=PL6gx4Cwl9DGDPsneZWaOFg0H2wsundyGrMockMvc">thenewboston</a> (MockMvc)

### 4. Automated testing

Below you can see the script that runs by default on every push and tests. So with every little change in the code that I push it will be tested to make sure nothing breaks when adding new features.

```yaml
image: maven:3.8.3-jdk-11

pipelines:
  default:
    - parallel:
        - step:
            name: Build and Test
            script:
              - mvn test
```

Below is the result of the yaml. You can see that 22 tests passed! Ready for pull request.

<img width="400" alt="second yaml file" src="https://user-images.githubusercontent.com/33750291/143413735-ca638e8b-a364-40d4-bef6-fddd1a9cd00d.png">

Sources:
- <a href="https://support.atlassian.com/bitbucket-cloud/docs/configure-bitbucket-pipelinesyml/"> Pipeline docs</a>

### 5. SonarCloud
|BitBucket|SonarCloud|
|-|-|
|<img width="858" alt="" src="https://user-images.githubusercontent.com/33750291/143471014-8e3e3069-3ec8-4857-9ec1-449c7412026b.png">|<img width="1153" alt="Schermafbeelding 2021-11-25 om 16 47 25" src="https://user-images.githubusercontent.com/33750291/143471023-aaa6b5b9-ef8a-4852-8bb0-8c7d3d525cc1.png">|


### 6. Merge checks


If you want to merge development into main you cannot to that without a Pull Request. 
There are a couple merge checks before merging in main:
- No failing builds
- Has one or more succesfull builds
- It must be reviewed by one person. 

If all those checks are marked you can merge the dev branch into main as seen below.

<img width="550" alt="Pull Request" src="https://user-images.githubusercontent.com/33750291/143471167-bc3136f5-cbca-47ea-bcb0-2a3cb5ded038.png">

## CI/CD

Below you can see my first yaml file that uses sonarcloud too check the quality of my code.

<img width="550" alt="first yaml file" src="https://user-images.githubusercontent.com/33750291/137206448-23be4f60-1635-486e-ac1d-bc0ba8be1c1e.png">

The pictures below shows a yaml file that builds, tests and deploys my ProductService.

```yaml
branches:
    master:
      - step:
          name: Build and Test
          script:
            - mvn clean install
            - IMAGE_NAME=product-service-docker
            - docker build . --file Dockerfile --tag ${IMAGE_NAME}
            - docker save ${IMAGE_NAME} --output "${IMAGE_NAME}.tar"
          services:
            - docker
          caches:
            - docker
          artifacts:
            - "*.tar"
      - step:
          name: Deploy to Production
          deployment: Production
          script:
            - echo ${DOCKERHUB_PASSWORD} | docker login --username "$DOCKERHUB_USERNAME" --password-stdin
            - IMAGE_NAME=product-service-docker
            - docker load --input "${IMAGE_NAME}.tar"
            - VERSION="prod-0.1.${BITBUCKET_BUILD_NUMBER}"
            - IMAGE=${DOCKERHUB_USERNAME}/${IMAGE_NAME}
            - docker tag "${IMAGE_NAME}" "${IMAGE}:latest"
            - docker push "${IMAGE}:latest"
          services:
            - docker
```

| Bitbucket | Dockerhub|
| --- | ----------- |
| <img width="450" alt="dockerhub result" src="https://user-images.githubusercontent.com/33750291/140995456-948ffca8-ff36-45a4-86ba-9c07f8c36258.png"> |<img width="450" alt="bitbucket result" src="https://user-images.githubusercontent.com/33750291/143414091-472c49d2-4f6e-48db-9b6e-a6152ceffdc8.png"> |
 
 Left picture: in the left picture you can see result of yaml file in bitbucket. By default on every push it builds and test the service. When pushing to master branch it will build test and deploy the service to my dockerhub online.
 
 Right picture: in the right picture you can see the result of the yaml that is pushed to dockerhub and online.
 

Sources:
- <a href="https://support.atlassian.com/bitbucket-cloud/docs/configure-bitbucket-pipelinesyml/"> Pipeline docs</a>


## Professional

### 1. Git Flow

In my project I use the git flow in my source control. The workflow is great for a release-based software workflow.

Branches:

- A main branch is created
- A develop branch is created from main
- Feature branches are created from develop
- When a feature is complete it is merged into the develop branch using Pull Request
- Closing the used feature branch
- When the development branch is done it is merged into main using Pull Request


<img width="428" alt="GitFlow" src="https://miro.medium.com/max/823/1*uUpzVOpdFw5V-tJ_YvgFmA.png">

The reason why I chose this workflow because it makes working with branches much easier and more clear too see what is going on. It's also a common flow used on the workfloor.

Sources:
- <a href="https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow"> Bitbucket docs</a>

### 2. Jira and Bitbucket

I Use Jira for my KanBan board and Bitbucket as my online SourceControl. The Reason why I chose this is because Jira and Bitbucket are from the same organization called Atlassian. This means that there is a great integration between these two web applications. 

| Jira | Bitbucket|
| --- | ----------- |
| <img width="1211" alt="Jira board" src="https://user-images.githubusercontent.com/33750291/143300222-1744b2c4-ab27-4af5-8287-cf96eea44503.png"> | <img width="1377" alt="Bitbucket board" src="https://user-images.githubusercontent.com/33750291/143300214-2c2a2062-a4e8-44d3-ac16-aad1ab095a0c.png"> |

As seen in the pictures above all the issues made in Jira(left picture) or Bitbucket(right picture) are shared with each other.



![image](https://user-images.githubusercontent.com/33750291/143448146-a330701b-0e09-4478-b130-1c5ad7d017d5.png)

In Jira when clicked on a user story, bug, feature etc. You can see the the branch it's on if it has a branch attached to it, the pull request if made one and the pipeline results linked to it. As seen in the picture below.

<img width="550" alt="Jira ticket" src="https://user-images.githubusercontent.com/33750291/143307587-6140b944-6627-4b41-a2e7-8ca92530b27b.png">





