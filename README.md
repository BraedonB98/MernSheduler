# MernSheduler
A remake of the uiScheduler but while using the MERN stack


MVP:

Data Structures 
---------------------------
Users:
    -Name
    -Job Position
    -PayRate
    -UserName
    -PhotoURL
    -Password
    -Schedules

Schedules:
    -ID
    -StartDate
    -EndDate
    -Day = [Sunday:{Employee id,[Start Time, End Time] }, Monday....] //should be able to calculate total hours based on start time and end time difference, Then summing together all of them in an array in case of a split shift
    -Labor Cost(Total)
    -Per Employee Hours



Front End Pages
---------------------------
DashBoard
    -Should display logo of store user is assigned 
    -Have a google maps view of the store
    -If not signed in it will show generic information about program
Schedule
    -Employees can see their schedules
    -Managers can Add schedules, edit,view,  and remove schedules
Contacts/Employee list
    -Normal employees should be able to see the contact information for other employees (get)
    -Managers can edit Employees, add, and remove (post, Delete, patch)
Login/Sign Up
    -Should be able to create an account and enter a store number


Backend Requests(Get, Post, Delete, Patch)
--------------------------------------------
GET: /api/users/ 
    -returns array of user objects with all the users for the store (requires admin login)
POST: /api/users/
    -adds user to db (Body: Name, Position = employee, Payrate = null,UserName,PhotoURL, Password)
GET /api/users/:uid
    -returns user with uid
PATCH /api/users/:uid
    -edits user in db (Body: Name, Position , Payrate ,UserName,PhotoURL, Password)
DELETE /api/users/:uid
    -deletes user in db

GET /api/schedule/:sid
    -returns schedule with id for specific start date(Sunday-Saturday)
POST /api/schedule/:sid
    -adds schedule
PATCH /api/schedule/:sid
    -updates schedule
DELETE /api/schedule/:sid
    -deletes schedule

Get /api/schedule/:sid/:uid
    -returns specific users schedules
DELETE /api/schedule/:sid/:uid
    -deletes person from schedule
PATCH /api/schedule/:sid/:uid
    -deletes person from schedule
POST /api/schedule/:sid/:uid
    -adds person to schedule




------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Data Structures 
---------------------------
Users:
    -Name
    -Job Position
    -Store/Division
        -Schedules object link 
    -PayRate
    -UserName
    -Profile Photo
    -Password

Store:
    -ID
    -Name
    -Employees
    -Profile Photo
    -Manager(s)
Schedules:
    -StartDate
    -EndDate
    -Day = []{Employee id,[Start Time, End Time] } //should be able to calculate total hours based on start time and end time difference, Then summing together all of them in an array in case of a split shift
    -Labor Cost(Total)
    -Per Employee Hours



Front End Pages
---------------------------
DashBoard
    -Should display logo of store user is assigned 
    -Have a google maps view of the store
    -If not signed in it will show generic information about program
Schedule
    -Employees can see their schedules(that havnt already been completed/once date is past it will be removed)
    -Managers can Add schedules, edit,view,  and remove schedules
Announcements
    -Employees can see current announcements
    -Managers can add an announcement
Contacts/Employee list
    -Normal employees should be able to see the contact information for other employees (get)
    -Managers can edit Employees, add, and remove (post, Delete, patch)
Login/Sign Up
    -Should be able to create an account and enter a store number(then manager accept or declines them into store on contacts page)
New Store
    -only Visable to highest level users


Backend Requests(Get, Post, Delete, Patch)
--------------------------------------------
GET: /api/:storeId/
    -returns store object
POST:/api/newStore/
    -adds a new store to the server (body:Name, profileUrl, Manager(s))

GET: /api/:storeId/users/ 
    -returns array of user objects with all the users for the store (requires admin login)



GET: 

