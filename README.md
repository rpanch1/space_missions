# Space Missions Application
1) Database + instructions for installation and loading the data:

This is a mobile application made in android studio that displays information about every space mission by running querys to a local database. This is the link to the original source of the dataset used in this project (https://www.kaggle.com/agirlcoding/all-space-missions-from-1957). However, I have done some preprocessing on the data by removing unwanted columns so the dataset used in the project is slightly different. Also, you do NOT need to download or load any data. The project already contains a csv file and the application will automatically create the database and read the data into a table from the file when you first launch the application.  


2) Application + instructions for installing the application software:

The app is made in android studio so technically you could run it on your android device but I think it is simpler to run it on the android emulator in android studio. If you already have android studio and a virtual device installed in android studio then you can skip the steps and just run the app in android studio.

Steps to run the android emulator in android studio:
- download/install android studio and open the project
- To create a virtual device, click on the AVD manager icon on the top right bar.
- click create virtual device which will show the select hardware menu
- for the phone type, I recommend choosing pixel 3 XL and hit next to go to system image menu
- In the recommended tab select R (API 30, Android 11)
- In the x86 Images tab select Pie, API 28, x86_64 ABI, Android 9.0 (Google APIs). You will need to download the APIs if you don't have it yet by clicking 'download'.
- Click next and then finish to install the virtual device. It should be displayed in AVD manager.
- Click the play icon on the top bar that says run 'app'. This should lauch the android emulator if you have a virtual device installed and launch the app on the emulator. 

3) Navigating the Application

When the app launches it should display the main screen with a button that says continue. Clicking continue will open the another activity that displays a list of every single space company and agency that has launched a space mission. Clicking any of the names on the list will open another activity which gives specific information about every space mission from that space organization. This includes the total number of space missions they have launched. Each space mission displays information such as the location of launch, date of launch, rocket name and the status of the mission. Going back and selecting another space agency will also display specific informaton about the space missions that agency has launched. 

All information that is displayed in each activity is queryed from the SQLite database when that activity opens. There is a MyDatabaseHelper class which extends the SQLiteOpenHelper class that is specific to android studio. This class is responsible for creating the database (if there is none) and the table when the app is launched. The database and the table are created using a specific SQL query displayed in the onCreate method of the class. If the table is initially empty then the main activity will load the data from the csv file. The MyDatabaseHelper class also has functions for calling specific queries on the databse so when certain activities are opened those function will run queries on the database and the data that is retrived will be returned and displayed on the screen.
