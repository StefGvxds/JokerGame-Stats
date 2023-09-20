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
