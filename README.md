## About 

### Project technical traget
The aim of this project is to create a web-based dashboard that displays data visualizations and allows for interactive exploration of a dataset. The dashboard is built using the Dash framework in Python, and the data is stored in a MongoDB database. 

### Animal Shelter Project Motivation
The main motivation of this project is to create an interactive interface for project user to interact with the animal collection in the AAC database. The user will read and create documents in the database. Creating, Reading, Updating, and deleting objects/files are essential for interacting with databases. Following the project motivation, it is aslo important to automate accessibility and queries within the Mongo Database using Python mongo driver (Pymongo). 

### Getting started
If you wish to run the code on a local machine follow these steps:
Prerequisite:
- Get a copy/install MongoDB
- Perform local system configuration and make sure mongodb is running...
1. Start the MongoDB service
    
    ```zsh
    mongod
    ```
2. Import the “aac_shelter_outcomes.csv” dataset using the following command
    ```zsh
    mongoimport --port <PORT#> --db AAC --collection animals --type=csv --headerline  <PATH_TO_CSV>aac_shelter_outcomes.csv
    ```
3. Launch the Mongo shell and create the admin and aacuser

    ```zsh
    mongosh
    db.createUser({user:’admin’,pwd:passwordPrompt(),roles:[{role:’userAdminAnyDatabase’,db:’admin’},’readWriteAnyDatabase’]})
    db.createUser({user:’aacuser’,pwd:passwordPrompt(),roles:[{role:’readWrite’,db:’AAC’ }]})
    ```
4. Restart MongoDB service with auth
    ```zsh
    mongod --shutdown
    mongod
    ```
5.  Now you can install the Animal Shelter package and create a new instance to connect to the database.
    ```python
    client = AnimalShelter (<USER>, <PASSWORD>, <PORT>, <AUTH_SRC>)
    ```


# CS 340 Portfolio

## Development Reflection

###### How do you write programs that are maintainable, readable, and adaptable? Especially consider your work on the CRUD Python module from Project One, which you used to connect the dashboard widgets to the database in Project Two. What were the advantages of working in this way? How else could you use this CRUD Python module in the future?

Maintaining a program can be achieved by making it modular and reusable, which allows for easy addition of functionality and keeping it current. In addition to modularity, writing comments that provide clear guidance on code functionality helps improve code readability. Adaptability is another crucial aspect, where modular code can be easily adapted to different incoming or outgoing data types, making it flexible and adjustable to meet different requirements. By following these practices, a programmer can build programs that are maintainable, readable, and adaptable.

###### How do you approach a problem as a computer scientist? Consider how you approached the database or dashboard requirements that Grazioso Salvare requested. How did your approach to this project differ from previous assignments in other courses? What techniques or strategies would you use in the future to create databases to meet other client requests?

As a computer scientist, my problem-solving approach begins by identifying the desired outcome and selecting the necessary tools to achieve it. I prioritize building the foundational tools before proceeding with higher-level functions. This project presented a unique challenge as it was my first time working with databases. To tackle this task, I built the database, created the CRUD module, and used it to construct the interactive dashboard. Previously, I relied on arrays, vectors, and objects to store data, which proved to be inefficient for handling large amounts of data. This project provided an opportunity to expand my skillset and introduced me to valuable techniques, such as the CRUD module. I am already considering how to incorporate it into the SQL database I am building for my website project. Additionally, I recognize the importance of aggregation when working with vast amounts of data and limited search time.

###### What do computer scientists do, and why does it matter? How would your work on this type of project help a company, like Grazioso Salvare, to do their work better?

Computer scientists play a crucial role in problem-solving by developing software that processes data at a faster rate than human manual labor can achieve, making calculations that are more accurate and precise, and creating technology that simplifies people's lives and businesses. The importance of computer scientists and their work is clear since computers have revolutionized the world. Without computer scientists, we wouldn't have advanced 3D graphics films, video games, or even something as simple as quickly adding up the number of employees for various companies throughout states. Projects like this are vital to companies, as they can locate and retrieve information quickly and with minimal effort. For instance, this project helped Grazioso Salvare find the desired dog records with a specific age range and breed, saving them hours of manual research among the 10,000 records. This project is expandable, so it can accommodate any additional records added in the future, making it a one-time effort for Grazioso Salvare.
