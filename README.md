# JokerGame-Stats
JokerGame-Stats: User-friendly GUI app using OPAP's Greek lottery data (https://www.opap.gr/web-services). Manage, display stats, and more. Easy navigation, expandable.

# Instructions for installing and launching the application

1) Database Installation
Extract the compressed database file: omada6db_DerbyDatabase.zip wherever desired.
After extracting the file, copy the omada6db folder to the location where NetBeans stores Derby databases, usually:
C:\Users\%username%\AppData\Roaming\NetBeans\Derby
The database contains complete data for the years 2021 and 2022.

2) Installation of the Application Source Code
Extract the compressed source code file: 2022_PLH24_OMADA_6.zip wherever desired (NOTE: files 2022_PLH24_OMADA_6.z01, 2022_PLH24_OMADA_6.z02, and 2022_PLH24_OMADA_6.zip should be in the same folder).
Open NetBeans and add the Project that you just saved (folder 2022_PLH24_OMADA_6).

3) Launching the Application Source Code
Open NetBeans, go to Services, and start the Java DB database service (Start Server).
Select the Project 2022_PLH24_OMADA_6 and press Run -> Run Project or press the F6 key.

# The JokerGame-Stats application offers the following functionalities:
It utilizes the web service (https://www.opap.gr/web-services), which contains REST-type web services and returns data in JSON format by making calls to the appropriate API.
The system provides the following options:
• Management of JOKER data,
• Viewing JOKER data per month for a specific year,
• Viewing JOKER statistics and printing them as PDF files,
• Displaying drawing statistics in graphical form, and
• Exiting the application.
Specifically, the data displayed by the application includes:
• The winning numbers (winning column),
• The basic prize categories,
  o  Number of wins, and
  o Winnings per win.
• Statistics of numbers drawn within a given date range in a tabular format, with the option to print these details to a PDF file.
The application gives the user the ability to retrieve and view data (within a specific date range or by entering a game ID), store data, and delete data from the database.

#The application also allows the user to retrieve the following information from the data stored in the database:
• For each month:
  o How many games were played,
  o How much money was distributed, and
  o How many JACKPOTs were won.
• Frequency of number appearances (the top 5 most frequently drawn numbers),
• Frequency of Joker number appearances (the top 5 most frequently drawn Joker numbers), and
• Average winnings per category.

Project Objective

The primary objective of the project is to create a modern GUI application that is not only functional but also user-friendly. It is essential that users can use it easily without the need for explanations.

The application should have a user-friendly graphical interface, even for beginners. With the help of appropriate icons, users should have the guidance they need to access the information they are interested in. Additionally, users should have the ability to return to the main menu from anywhere in the program.

For significant actions, such as data deletion, there should always be a confirmation message. Another important goal is to design the application in a way that allows for future expansion in case new requirements arise.

Translation into English:

**Features and Functions of the JokerGame-Stats Application**

The features and functions of the JokerGame-Stats application are outlined as follows:

**Specification R1: Main Menu**
Upon launching the program, the main menu opens, allowing the user to select certain basic actions or exit the application, terminating the program. Each basic action opens a separate panel with appropriate functionalities.

The menu includes the following basic options:
1. Management of JOKER data
2. Viewing JOKER data
3. Viewing JOKER statistics
4. Viewing drawing statistics in graphical format
5. Exit

At this point, the team decided to add the "View drawing statistics in graphical format" button to the Main Menu.

**Specification R2: Management of JOKER Data**
Selecting "Management of JOKER data" displays a screen with the following options:
- Input field for the GameID (GameID) and a search button for the user to retrieve data from the API.
  - If the user does not enter a valid GameID or leaves the input field empty and presses the search button, the application displays the message "Enter a valid GAME ID!" Otherwise, if the user enters a valid GameID and clicks "Search," a message appears stating that the "search was successful," and the corresponding drawing is displayed in the table.
- Two input fields for entering dates "From" and "To" and a search button to retrieve data for a specific date range from the API.
  - If the user does not enter dates and clicks the "Search" button, the application returns a message to the user: "You must enter dates!" The same message appears if the user fills in only the "From" date field and not the "To" field (and vice versa).
  - If the user enters a "From" date later than the "To" date (e.g., 03/02/2022 - 03/01/2022), the program displays the message "The 'From' date must not be greater than the 'To' date."
  - If the user enters a date in any date field that is greater than the current date, the program displays the message "The selected date is greater than today."
  - If the user enters a valid date range, the program returns the message: "The search was successful," and all drawings that took place during that period are displayed if they exist.
- A button to save all drawing data from the table to the database (Button Name: "Save Data").
  - If there is no data in the table, and the user presses "Save Data," the program displays the message: "Search for the data you want to save."
  - If the user presses the "Save Data" button and there are entries in the table, the program displays the message: "The save was successful" if the data was not already in the database. If the data already exists in the database, the program displays the message: "The save was NOT successful; the data already exists in the database."
- A button to delete the selected drawing from the database (Button Name: "Delete Game Data").
  - If the user does not select an item from the table and presses the "Delete Game Data" button, the program displays the message: "Select a drawing from the table that you want to delete."
  - If the user selects a drawing from the table to delete, a confirmation window appears, asking the user to confirm deletion.
    - If the data exists in the database, the program deletes the drawing from the database and the table, displaying the message: "Deletion was successful!"
    - If the drawing was not stored in the database, the selected drawing is deleted only from the table, and the program displays the message: "The data did not exist in the database, so it could not be deleted."
- A button to delete all drawings within a date range from the database (Button Name: "Delete Game Data within Date Range").
  - All drawings in the table (provided they are stored in the database) are deleted, and the message "Deletion was successful!" is displayed.
  - In the case where there are no drawings in the table, and the button is pressed, the program displays the message: "There is no data in the table to delete!"
- A button to return to the main menu.

Whether by entering the GameID of a JOKER game or by entering a date range and clicking the search button, a table is updated with the drawing or drawings selected. The user can then select the drawing of interest from the table. The following data is automatically displayed: winning numbers (winning column) and basic success categories (number and winnings per success).

Specification R3: Viewing JOKER Data
With the option "View JOKER Data," a screen appears that contains the following:
• A list of available years (displaying all years that have JOKER draws in the database) where the user can select one.
• A table with the 12 months, where if the user clicks on one of the months, a new window appears showing:
   o How many games were played,
   o How much money was distributed, and
   o How many Jackpots were won for the selected year and month. (Only data from the database is displayed here)
• A return button to the main menu

Specification R4: Viewing JOKER Statistics Data
With the option "View JOKER Statistics Data," a screen appears that contains the following:
• Five tables (the first three for viewing statistics of drawn numbers, and the last two for viewing statistics of JOKER numbers drawn).
• A button for viewing statistics where, when pressed, makes use of the API CALL https://api.opap.gr/games/v1.0/%7bgameId%7d/statistics. The data retrieved is then populated into the five tables.
• A button to export the statistics table to PDF.
• A return button to the main menu.

Specification R5: Viewing Draw Statistics in Graphical Form
With the option "View Draw Statistics in Graphical Form," a screen appears that contains the following:
• Two fields for entering From - To dates (where the same date rules as in R2 apply, with the difference that the search is performed in the database and not through an API).
• Three tables where:
   o The first table shows the frequency of appearance of numbers (the 5 most frequently drawn numbers).
   o The second table shows the frequency of appearance of JOKER numbers (the 5 most frequently drawn JOKER numbers).
   o The third table shows the average winnings per category.
All the above data is retrieved by the program from the database.
• By pressing the "View Statistics" button, the program populates the three tables with data and displays the information graphically.
• A return button to the main menu.

Information Regarding the Implementation of the JokerGame-Stats Application
The team that developed this project consists of three members and is composed of the following students:
1. Stefanos Gavoukhidis (A.M: 138044)
2. Savvas Philippidis (A.M: 045401)
3. Polydoros Tsigris (A.M: 119403)
Supervised by Professor Panagiotis Fitsilis.

For the operation of the application, the following is required:
• Internet access
• The use of specific libraries provided as requirements by the Hellenic Open University (HOU) in Netbeans, integrated into a 3GE library located in the project folder 2022_PLH24_OMADA_6\libraries.
• Apache Derby 10.11.1.2 Release

The application was developed in the Java programming language, and the following tools were used for the completion of the project:
• Java jdk1.8.0_111
• Development environment for Java Netbeans IDE 8.2
• ApacheDerby DB
• Microsoft Teams (team communication)
• Gantt Project for project planning and Gantt charts
• Planning poker - http://www.planningpoker.com/
• Priority poker http://www.uxforthemasses.com/priority-poker/
• Visual Paradigm for UML
• Trello https://trello.com
• Microsoft Word for writing the project report
• Microsoft Excel for fulfilling the project requirements as requested in the project description.

**Execution of the Application**


At program startup, the main menu opens.

![Execution of the Application 1](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/ce7952e7-90d4-421e-8496-1ef70ea99b7a)

By pressing the 'Exit' button, the program terminates. ![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/433ea45c-ad7f-4d8b-962d-7ce762bfa40a)

When pressing the 'Manage JOKER Data' button from the main menu (R1),

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/2c733a5d-6d9b-4668-93e8-37e7ebf2f60c)

the 'Manage JOKER Data' screen opens.
![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/580b8972-04cf-470d-a8da-117ddd2dc5a0)

When pressing button (1) for searching without entering the Game ID, the program displays the message: (2) 'Please provide a valid GAME ID!'

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/42e52c5e-217a-41b0-937c-052ee95b94ae)

Entering a valid (1) Game ID and pressing (2) search displays the message: (4) 'Search successful,' and (3) selecting the draw from the table fills in the tables with the information: (5) Number of wins for each category, (6) Winnings per win per category, (7) Draw number, (8) Draw date, (9) Lucky draw numbers, and (10) Joker draw.

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fa90f6e5-a7c0-454d-84eb-25d25780c4e8)

Pressing (1) search without entering dates will display the program message (2) 'You must enter dates!' (the same message will appear if only one of the two date fields is filled in).

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/accbeae9-189b-4c2c-bf1c-9c8fd3199690)

If the date in the (1) From field is later than the date in the (2) To field, and you press search, the program will display the message: (3) "The From date must be greater than the To date."

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/48b2650d-71af-4e9c-ac68-60d7ece5218f)

If a date later than today is entered in one of the two date input fields (1) and a search is pressed, the program displays the message: (2) "The selected date is greater than today."

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fbf203bd-12d9-48e7-b0a1-505095242c83)

If valid dates are entered in the date fields (1) From - To and the search button is pressed, the program displays all the draws that took place during that period in the (2) table, and the program displays the message: (3) "The search was successful!"

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/207abceb-414c-40aa-9222-8aaad2be9b29)

When the (1) Save Data button is pressed (provided there are draws in the table), all the draws in the table are stored in the database, and the message (2) "The save was successful!" is displayed.

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/602fff43-d20a-4932-bb3a-bcf891b35c86)

If the data already exists in the database and the (1) Save Data button is pressed, the program will display the message: (2) "The save was NOT successful, the data already exists in the Database!"

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/bf3f23a2-6fc8-468a-bead-fdcd1fa0b447)

If the (1) Save Data button is pressed without any draws in the table, the program will display the message: (2) "Search for the data you want to save."

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/0aa20ac7-3512-49ae-9d57-6bf82bde4cee)

If (1) a draw is selected from the table, and it is stored in the database, and the (2) Delete Game Data button is pressed, a confirmation message appears: (3) "Are you sure you want to delete the data?" (Note: The Yes or No buttons appear in the same language as the system; in this case, they are in German, displaying the option Ja for Yes and Nein for No).

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fb77bc52-4fda-4ccd-ad3b-d3ee2c903fe7)

If the selected draw is not stored in the database, and the (1) Delete Game Data button is pressed, then the program will display the message: (2) "The data did not exist in the database and cannot be deleted."

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/ea8233ec-a500-4bb1-9afb-8db3ec1a0326)

If the (1) Delete Game Data button is pressed while there are no draws in the (2) table, then the program will display the message: (3) "First, search for the data you want to delete!"

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/cf2d7672-9bcc-4a0f-846e-654618838d5a)

If the (1) Delete Game Data button is pressed within a date range while there are no draws in the (2) table, then the program will display the message: (3) "There is no data in the table to be deleted!"

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/36630a5d-6f18-4566-a6db-bb068587387e)

If the (1) Delete Game Data button is pressed within a date range, and there are draws in the database, then a confirmation message for deletion appears. If Yes is selected (i.e., to delete), the program deletes the draws in the table and displays the message: (2) "Deletion was successful."

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/e44571e5-99ef-42a0-90db-71a8d889400a)

If the (1) Delete Game Data button is pressed within a date range, a confirmation message appears: "Are you sure you want to delete the data?" (The confirmation message is not shown in the screenshot, but it's the same one that appears when the Delete Game Data button is pressed). If the confirmation is confirmed and the draws in the table are not stored in the database, the program displays the message: (2) "The data did not exist in the database to be deleted," and the draws are deleted from the table.

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/3266230e-7601-4681-8470-39238393ce88)

If the Menu button is pressed, the program returns to the main menu.

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/28aa21e2-ba27-44fb-8ca6-826a1ea14d5a)

Pressing the View Joker Data button on the main menu displays the Joker Data View screen. The program provides the option to select (1) a year (only from the years containing data in the database) and (2) a month. By clicking on the month, a new screen appears with the following information: Total games, Total money, and Total JACKPOT (these data are for the selected year and month in the database. In case there are no draws for the selected month, the values are displayed as zeros).

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/be3a4183-db67-410a-b691-8b3a2cafcbf8)

With the Close button on the second screen, the screen terminates. 

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/0c0fa19e-3121-4e55-8d74-810e3a4d72a0)

Using the Menu button on the Joker Data View screen returns the program to the main menu.

![image](https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/1c7cab5a-016b-4987-8117-64c323b9cefa)

By clicking on the View Joker Statistics button on the main menu, the Joker Statistics Data View screen appears.
















































