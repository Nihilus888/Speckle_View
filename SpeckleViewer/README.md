# Speckle Viewer
This project aims to replicate parts of speckle for CAD-BIM integration that requires 3D rendering and API Integrations with Speckle

## Tech Stack
One of the most important considerations is choosing your tech stack as it is a software architectural design decision and I decided to go with these tech stack based on various considerations that I have identified

1. React.js/Three.js 

    I chose React.js as there is a specific library called React Three Fiber which is a good React renderer that integrates well with Three.js. Another consideration is that I'm personally more familiar with React compared with other popular frontend frameworks like
Vue or Angular

2. Node.js

    Node.js integrates very well with React.js and MongoDB 
which was my choice of my database. This tech stack is 
quite popular as it is the MERN stack which is versatile, 
easy to scale and scaffold. 

3. MongoDB

    After testing their REST API with their various endpoints via Postman, it looks like they have a lot of unstructured data that is in a 
JSON format. My rationale is using a relational database like MySQL or PostgreSQL will not be appropriate due to how there is a lot of 
metadata and unstructured data for the 3D rendering. 

## API Integration

I first started this project by reading the documentation 
particularly the API integration so that I can understand 
the different 
endpoints that I can pull from. After reading the API 
documentation, I used Postman to test the API after being 
granted the necessary 
permissions to call the necessary information. As I was using REST API and not GraphQL to call the JSON data, there were times where the data was quite large and it crashed my Postman while I was doing data exploration. 

After exploring the data, I integrated with their API using Node.js where I called their API and integrated the data and stored those data into my database which was MongoDB. I had to structure the data in such a way where all the object Ids for a particular model would be kept into an array with a unique id where I can do a for loop and iterate through the object Ids to generate the 3D rendering via Speckle Viewer. 

## Frontend

On the frontend, I used React-Routers for routing of my pages and had to do a lot of research on Speckle Viewer library after researching on their documentation to find out how to use it as they have integrated three.js to display the 3D models. There were two main things that I noticed after reading through the documentation which was:

1. The Speckle Viewer

This is where the main camera is where we can download the objectIds from the model and display it. Furthermore, we can interact with the camera and do panning, zooming in and zooming out and various rotations.

2. Add-ons

There are certain features that can be added to the main speckle viewer with many examples that was shown however many of them were written in typescript which I'm not familiar with and a lot of the methods that were in the documentation have been deprecated according to the migration document update. So I have to choose those that are not deprecated and have no issues.