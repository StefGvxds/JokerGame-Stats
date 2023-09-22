JokerGame-Stats
-------
JokerGame-Stats is a user-friendly GUI application that utilizes data from the Greek lottery OPAP (https://www.opap.gr/web-services). It allows users to manage and display statistics, among other features. The application is characterized by its easy navigation and expandability.

The primary goal of the project is to develop a modern GUI application that is not only functional but also intuitive for users, including beginners. Through the use of appropriate icons, users should receive the necessary guidance to access the information they're interested in. Moreover, users should have the capability to navigate back to the main menu from any location within the program.

For significant actions, such as data deletion, a confirmation message should always be presented. Another key objective is to design the application in a manner that accommodates future expansion should new requirements emerge.



Features and Functions of the JokerGame-Stats Application
-------

The features and functions of the JokerGame-Stats application are outlined as follows:

**Main Menu**<br>
Upon launching the program, the main menu opens, allowing the user to select certain basic actions or exit the application, terminating the program. Each basic action opens a separate panel with appropriate functionalities.

The menu includes the following basic options:
<ul>
  <li>Management of JOKER data</li>
  <li>Viewing JOKER data</li>
  <li>Viewing JOKER statistics</li>
  <li>Viewing drawing statistics in graphical format</li>
  <li>Exit</li>
</ul>

**Management of JOKER Data**<br>
Displays a screen with the following options:
<ul>
  <li>Input field for the GameID (GameID) and a search button for the user to retrieve data from the API</li>
  <li>If the user does not enter a valid GameID or leaves the input field empty and presses the search button, the application displays the message "Enter a valid GAME ID!" Otherwise, if the user enters a valid GameID and clicks "Search," a message appears stating that the "search was successful," and the corresponding drawing is displayed in the table</li>
  <li>Two input fields for entering dates "From" and "To" and a search button to retrieve data for a specific date range from the API.</li>
  <li>If the user does not enter dates and clicks the "Search" button, the application returns a message to the user: "You must enter dates!" The same message appears if the user fills in only the "From" date field and not the "To" field (and vice versa).</li>
  <li>If the user enters a "From" date later than the "To" date (e.g., 03/02/2022 - 03/01/2022), the program displays the message "The 'From' date must not be greater than the 'To' date."</li>
  <li>If the user enters a date in any date field that is greater than the current date, the program displays the message "The selected date is greater than today."</li>
  <li>If the user enters a valid date range, the program returns the message: "The search was successful," and all drawings that took place during that period are displayed if they exist.</li>
  <li>A button to save all drawing data from the table to the database (Button Name: "Save Data").</li>
  <li>If there is no data in the table, and the user presses "Save Data," the program displays the message: "Search for the data you want to save."</li>
  <li>If the user presses the "Save Data" button and there are entries in the table, the program displays the message: "The save was successful" if the data was not already in the database. If the data already exists in the database, the program displays the message: "The save was NOT successful; the data already exists in the database."</li>
  <li>A button to delete the selected drawing from the database (Button Name: "Delete Game Data").</li>
  <li>If the user does not select an item from the table and presses the "Delete Game Data" button, the program displays the message: "Select a drawing from the table that you want to delete."</li>
  <li>If the user selects a drawing from the table to delete, a confirmation window appears, asking the user to confirm deletion.</li>
  <li>If the data exists in the database, the program deletes the drawing from the database and the table, displaying the message: "Deletion was successful!"</li>
  <li>If the drawing was not stored in the database, the selected drawing is deleted only from the table, and the program displays the message: "The data did not exist in the database, so it could not be deleted."</li>
  <li>A button to delete all drawings within a date range from the database (Button Name: "Delete Game Data within Date Range").</li>
  <li>All drawings in the table (provided they are stored in the database) are deleted, and the message "Deletion was successful!" is displayed.</li>
  <li>In the case where there are no drawings in the table, and the button is pressed, the program displays the message: "There is no data in the table to delete!"</li>
  <li>A button to return to the main menu.</li>
</ul>

Whether by entering the GameID of a JOKER game or by entering a date range and clicking the search button, a table is updated with the drawing or drawings selected. The user can then select the drawing of interest from the table. The following data is automatically displayed: winning numbers (winning column) and basic success categories (number and winnings per success).

**Specification Viewing JOKER Data**<br>
With the option "View JOKER Data," a screen appears that contains the following:
<ul>
  <li>A list of available years (displaying all years that have JOKER draws in the database) where the user can select one.</li>
  <li>A table with the 12 months, where if the user clicks on one of the months, a new window appears showing:</li>
  <ul>
    <li>How many games were played,</li>
    <li>How much money was distributed, and</li>
    <li>How many Jackpots were won for the selected year and month. (Only data from the database is displayed here)</li>
  </ul>
  <li>A return button to the main menu</li>
</ul>

**Specification Viewing JOKER Statistics Data**<br>
With the option "View JOKER Statistics Data," a screen appears that contains the following:
<ul>
  <li>Five tables (the first three for viewing statistics of drawn numbers, and the last two for viewing statistics of JOKER numbers drawn).</li>
  <li>A button for viewing statistics where, when pressed, makes use of the API CALL https://api.opap.gr/games/v1.0/%7bgameId%7d/statistics. The data retrieved is then populated into the five tables.</li>
  <li>A button to export the statistics table to PDF.</li>
  <li>A return button to the main menu.</li>
</ul>


**Specification Viewing Draw Statistics in Graphical Form**<br>
With the option "View Draw Statistics in Graphical Form," a screen appears that contains the following:
<ul>
  <li>Two fields for entering From - To dates (where the same date rules as in R2 apply, with the difference that the search is performed in the database and not through an API).</li>
  <li>Three tables where:</li>
  <ul>
    <li>The first table shows the frequency of appearance of numbers (the 5 most frequently drawn numbers).</li>
    <li>The second table shows the frequency of appearance of JOKER numbers (the 5 most frequently drawn JOKER numbers).</li>
    <li>The third table shows the average winnings per category.</li>
  </ul>
  All the above data is retrieved by the program from the database.

  <li>By pressing the "View Statistics" button, the program populates the three tables with data and displays the information graphically.</li>
  <li>A return button to the main menu.</li>
</ul>


Functionalities
-------
It utilizes the web service (https://www.opap.gr/web-services), which contains REST-type web services and returns data in JSON format by making calls to the appropriate API.
The system provides the following options:
<ul>
<li>Management of JOKER data,</li>
<li>Viewing JOKER data per month for a specific year,</li>
<li>Viewing JOKER statistics and printing them as PDF files,</li>
<li>Displaying drawing statistics in graphical form, and</li>
<li>Exiting the application.</li>
</ul>

**Specifically, the data displayed by the application includes:**<br>
<ul>
<li>The winning numbers (winning column),</li>  
<li>The basic prize categories,</li>
  <ul>
    <li>Number of wins, and</li>
    <li>Winnings per win</li>
  </ul>
<li>Statistics of numbers drawn within a given date range in a tabular format, with the option to print these details to a PDF file.</li>
</ul>
The application gives the user the ability to retrieve and view data (within a specific date range or by entering a game ID), store data, and delete data from the database.

Data Retrieval Features in the Application
-------
<ul>
  <li>For each month:</li>
    <ul>
      <li>How many games were played,</li>
      <li>How much money was distributed, and</li>
      <li>How many JACKPOTs were won.</li>
    </ul>  
<li>Frequency of number appearances (the top 5 most frequently drawn numbers),</li>
<li>Frequency of Joker number appearances (the top 5 most frequently drawn Joker numbers), and</li>
<li>Average winnings per category.</li>
</ul>

Requirements
-------
<ul>
  <li>Internet access</li>
  <li>The use of specific libraries provided as requirements by the Hellenic Open University (HOU) in Netbeans, integrated into a 3GE library located in the project folder 2022_PLH24_OMADA_6\libraries.</li>
  <li>Apache Derby 10.11.1.2 Release</li>
</ul>

Development Tools and Environment
-------
<ul>
  <li>Java jdk1.8.0_111</li>
  <li>Development environment for Java Netbeans IDE 8.2</li>
  <li>ApacheDerby DB</li>
  <li>Microsoft Teams (team communication)</li>
  <li>Gantt Project for project planning and Gantt charts</li>
  <li>Planning poker - http://www.planningpoker.com/</li>
  <li>Priority poker http://www.uxforthemasses.com/priority-poker/</li>
  <li>Visual Paradigm for UML</li>
  <li>Trello https://trello.com</li>
  <li>Microsoft Word for writing the project report</li>
  <li>Microsoft Excel for fulfilling the project requirements as requested in the project description.</li>
</ul>

Instructions for installing and launching the application
-------

**1) Database Installation**<br>
Extract the compressed database file: omada6db_DerbyDatabase.zip wherever desired.
After extracting the file, copy the omada6db folder to the location where NetBeans stores Derby databases, usually:
C:\Users\%username%\AppData\Roaming\NetBeans\Derby
The database contains complete data for the years 2021 and 2022.

**2) Installation of the Application Source Code**<br>
Extract the compressed source code file: 2022_PLH24_OMADA_6.zip wherever desired (NOTE: files 2022_PLH24_OMADA_6.z01, 2022_PLH24_OMADA_6.z02, and 2022_PLH24_OMADA_6.zip should be in the same folder).
Open NetBeans and add the Project that you just saved (folder 2022_PLH24_OMADA_6).

**3) Launching the Application Source Code**<br>
Open NetBeans, go to Services, and start the Java DB database service (Start Server).
Select the Project 2022_PLH24_OMADA_6 and press Run -> Run Project or press the F6 key.

Execution of the Application
-------

At program startup, the main menu opens.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/ce7952e7-90d4-421e-8496-1ef70ea99b7a" width="400" height="400" /><br><br>


By pressing the 'Exit' button, the program terminates. 

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/433ea45c-ad7f-4d8b-962d-7ce762bfa40a" width="100" height="50" /><br><br>
<br>

When pressing the 'Manage JOKER Data' button from the main menu ,

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/2c733a5d-6d9b-4668-93e8-37e7ebf2f60c" width="400" height="100" /><br><br>

the 'Manage JOKER Data' screen opens.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/580b8972-04cf-470d-a8da-117ddd2dc5a0" width="600" height="400" /><br><br>

When pressing button (1) for searching without entering the Game ID, the program displays the message: (2) 'Please provide a valid GAME ID!'

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/42e52c5e-217a-41b0-937c-052ee95b94ae" width="600" height="400" /><br><br>

Entering a valid (1) Game ID and pressing (2) search displays the message: (4) 'Search successful,' and (3) selecting the draw from the table fills in the tables with the information: (5) Number of wins for each category, (6) Winnings per win per category, (7) Draw number, (8) Draw date, (9) Lucky draw numbers, and (10) Joker draw.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fa90f6e5-a7c0-454d-84eb-25d25780c4e8" width="600" height="400" /><br><br>

Pressing (1) search without entering dates will display the program message (2) 'You must enter dates!' (the same message will appear if only one of the two date fields is filled in).

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/accbeae9-189b-4c2c-bf1c-9c8fd3199690" width="600" height="400" /><br><br>

If the date in the (1) From field is later than the date in the (2) To field, and you press search, the program will display the message: (3) "The From date must be greater than the To date."

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/48b2650d-71af-4e9c-ac68-60d7ece5218f" width="600" height="400" /><br><br>

If a date later than today is entered in one of the two date input fields (1) and a search is pressed, the program displays the message: (2) "The selected date is greater than today."

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fbf203bd-12d9-48e7-b0a1-505095242c83" width="600" height="400" /><br><br>

If valid dates are entered in the date fields (1) From - To and the search button is pressed, the program displays all the draws that took place during that period in the (2) table, and the program displays the message: (3) "The search was successful!"

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/207abceb-414c-40aa-9222-8aaad2be9b29" width="600" height="400" /><br><br>

When the (1) Save Data button is pressed (provided there are draws in the table), all the draws in the table are stored in the database, and the message (2) "The save was successful!" is displayed.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/602fff43-d20a-4932-bb3a-bcf891b35c86" width="600" height="400" /><br><br>

If the data already exists in the database and the (1) Save Data button is pressed, the program will display the message: (2) "The save was NOT successful, the data already exists in the Database!"

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/bf3f23a2-6fc8-468a-bead-fdcd1fa0b447" width="600" height="400" /><br><br>

If the (1) Save Data button is pressed without any draws in the table, the program will display the message: (2) "Search for the data you want to save."

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/0aa20ac7-3512-49ae-9d57-6bf82bde4cee" width="600" height="400" /><br><br>

If (1) a draw is selected from the table, and it is stored in the database, and the (2) Delete Game Data button is pressed, a confirmation message appears: (3) "Are you sure you want to delete the data?" (Note: The Yes or No buttons appear in the same language as the system; in this case, they are in German, displaying the option Ja for Yes and Nein for No).

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/fb77bc52-4fda-4ccd-ad3b-d3ee2c903fe7" width="600" height="400" /><br><br>

If the selected draw is not stored in the database, and the (1) Delete Game Data button is pressed, then the program will display the message: (2) "The data did not exist in the database and cannot be deleted."

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/ea8233ec-a500-4bb1-9afb-8db3ec1a0326" width="600" height="400" /><br><br>

If the (1) Delete Game Data button is pressed while there are no draws in the (2) table, then the program will display the message: (3) "First, search for the data you want to delete!"

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/cf2d7672-9bcc-4a0f-846e-654618838d5a" width="600" height="400" /><br><br>

If the (1) Delete Game Data button is pressed within a date range while there are no draws in the (2) table, then the program will display the message: (3) "There is no data in the table to be deleted!"

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/36630a5d-6f18-4566-a6db-bb068587387e" width="600" height="400" /><br><br>

If the (1) Delete Game Data button is pressed within a date range, and there are draws in the database, then a confirmation message for deletion appears. If Yes is selected (i.e., to delete), the program deletes the draws in the table and displays the message: (2) "Deletion was successful."

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/e44571e5-99ef-42a0-90db-71a8d889400a" width="600" height="400" /><br><br>

If the (1) Delete Game Data button is pressed within a date range, a confirmation message appears: "Are you sure you want to delete the data?" (The confirmation message is not shown in the screenshot, but it's the same one that appears when the Delete Game Data button is pressed). If the confirmation is confirmed and the draws in the table are not stored in the database, the program displays the message: (2) "The data did not exist in the database to be deleted," and the draws are deleted from the table.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/3266230e-7601-4681-8470-39238393ce88" width="600" height="400" /><br><br>

If the Menu button is pressed, the program returns to the main menu.


<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/28aa21e2-ba27-44fb-8ca6-826a1ea14d5a" width="120" height="70" /><br><br>

Pressing the View Joker Data button on the main menu displays the Joker Data View screen. The program provides the option to select (1) a year (only from the years containing data in the database) and (2) a month. By clicking on the month, a new screen appears with the following information: Total games, Total money, and Total JACKPOT (these data are for the selected year and month in the database. In case there are no draws for the selected month, the values are displayed as zeros).


<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/be3a4183-db67-410a-b691-8b3a2cafcbf8" width="600" height="400" /><br><br>

With the Close button on the second screen, the screen terminates. 


<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/0c0fa19e-3121-4e55-8d74-810e3a4d72a0" width="130" height="50" /><br><br>

Using the Menu button on the Joker Data View screen returns the program to the main menu.

<img src="https://github.com/StefGvxds/JokerGame-Stats/assets/129869539/28aa21e2-ba27-44fb-8ca6-826a1ea14d5a" width="120" height="70" /><br><br>

By clicking on the View Joker Statistics button on the main menu, the Joker Statistics Data View screen appears.

Developed by
-------
<ul>
<li>Professor Panagiotis Fitsilis (Product Owner)</li>
<li>Student Stefanos Gavouchidis (Scrum Master & Developer)</li>
<li>Student Savvas Philippidis (Developer)</li>
<li>Student Polydoros Tsigris (Developer)</li>
</ul>










































