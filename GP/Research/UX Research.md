# UX Research

## Introduction

```
Mediaan is an international IT company, founded in Heerlen, the Netherlands, in 1969. We are in Heerlen, Amsterdam, Düsseldorf, München and Brussel. We believe that technology can make a difference in every company. Using smart processes and the newest technologies, companies can connect, inspire and grow.  
We deliver technology ranging from mobile apps to back-end services. Quality is of the utmost importance to us and our designs are unique. As soon as customers are interested in collaborating with Mediaan, but aren't sure of the feasibility of a project, Mediaan will offer a Proof of Concept. Currently, Mediaan has an idea for restaurants. However, this can only be realised with limited budget. Therefor Mediaan turns to students.  
Case 
The process in a restaurant is usually the same. Customers get seated, are hand over the menu, order drinks and food, consume the drinks and food and finally have dessert. A restaurant has a new idea to convert the above process to a digital experience. You will be developing the requested proof of concept in an agile fashion. Initially you'll focus on the MVP (the most important features) and then continue to flesh out the application.  
Milestone 1 (the MVP) 
After being welcomed by the staff, a customer takes seat at a table in the restaurant. On each table in the restaurant, a QR-code is placed. When a customer scans the QR-code, they will be presented with the digital menu of the restaurant. By scanning the QR-code and opening the application, the system should register their table and open a new session for the duration of the customer's stay.  
The customer should then be able to order from the digital menu. When the customer submits their order, it should be sent in real-time to the kitchen staff, who must then process the order. They will receive the order in a 'live-view'-screen in the kitchen. The system should aid the kitchen staff in organizing their work. A way to see which orders are new, processing and completed is preferred. 
Milestone 2 
The digital menu has a certain structure. Maybe there are categories of dishes, the dishes themselves, ingredients of the dishes and their nutritional information. The restaurant owner or the chef can administrate the products of the digital menu, in order to keep it up to date.  
Milestone 3 
The restaurant wants to have an inventory management system. This system should be able to be updated from the customer (when ordering something) or the kitchen (when creating waste or getting new inventory). This system needs to make sure that customers are not able to order a meal when this is not available. 
Bonus 
Create a white label application. Create or refactor the application in such a manner that it can be deployed at other restaurants. That means not only should the restaurant be able to create their digital menu. They should also be able to upload their logo and create their colour scheme. The digital menu application will then always render in the style of the restaurant.  
Bonus 
Integrate a food review system. A customer should be able to rate their meal in the menu. Other customers can directly see scores and reviews for each meal. They can also react to the reviews by for example simple down or upvoting the review. The restaurant is also able to react to these reviews. 
Technologies 
You will touch upon the following technologies:  
•	Webservices / back-end systems 
•	WebSockets for real-time communication 
•	Front-end development 
•	Databases  
```

## Context

This research involves the login page and the kitchen dashboard. As a kitchen staff you need to authenticate yourself before accessing the admin page. When an order is placed the incoming order needs to be visible for the kitchen staff and can be labeled as done when the order is completed.

## Designs

I have made the designs in Adobe XD. Below are the designs to be tested by our target audience. The designs include the Login page and the Dashboard Kitchen.

### Login

To access the admin panel an user must be authenticated. To authenticate we use this login page.

<img width="700" alt="login page" src="https://user-images.githubusercontent.com/33750291/144591002-f5182908-a844-4979-b0ab-666a8c8f9ed1.png">

### Kitchen Dashboard

The kitchen dashboard as designed below is connected to two user-stories “As a kitchen staff member I want to be able to see all incoming orders” and “As a kitchen staff member I want to label incoming orders as “done” when they are finished”.

<img width="700" alt="login page" src="https://user-images.githubusercontent.com/33750291/144594745-9063eb62-1603-4c9b-ad65-637087be1d17.png">

## Target Audience

Our target audience is the catering industry. I have assembled 3 different age types that work in the catering industry. One young, one middle aged and one aged employee.

Name: Nick Reijnders\
Gender: Male\
Age: 20

Name: Monica Berman\
Gender: Female\
Age: 35

Name: Carsten Simons\
Gender: Male\
Age: 59

## Tasks

For the login page I asked the testers to try to login. 

```
Nick:
-	Result: Nick successfully logged in with no problems.
-	Feedback Nick: “It is simple and common design”.
```

```
Monica:
-	Result: Monica successfully logged in after reading the placeholder text.
-	Feedback Monica: “Nice and simple design, should be no problem with people my age”.
```

```
Carsten:
-	Result: Carsten successfully logged in after taking time to read the placeholder’s text.
-	Feedback Carsten: “Without the placeholder’s text I would not know what to do”.
```

For the Dashboard page I asked the testers to try to set “Incoming orders”(Grey card) to “In progress”(Orange card), set “In progress”(Orange card) to “Done”(Green card) and finally Delete “Done”(Green card) cards.

```
Nick:
-	Result: Nick went through all the card stages successfully and fast.
-	Feedback Nick: “No problem just a couple clicks, not a complex system”.
```

```
Monica:
-	Result: Monica successfully went through all the card changes.
-	Feedback Monica: “Super nice that the status is colored, you can see the status of the card immediately”.
```

```
Carsten:
-	Result: Carsten successfully logged in after taking time to read the placeholder’s text.
-	Feedback Carsten: “If the card could get more of the status color in it. It could the card make stand out more therefore, it is better and faster to see the status of it”.
```

## Conclusion

The tests passed successfully. There were no big problems every tester could easily use the current designs. Although there was feedback to use more of the status color in the card. I will change that to make the card better visible for employees with possible vision problems.

