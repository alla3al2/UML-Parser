# UMLParser
The UML Parser is a web-based application that receives Java source codes as input, analyzes the Java source codes, and finally produces UML Class and Sequence Diagrams. This application uses Tomcat and MySQL database, I have created a simple database (this application purpose was Reverse Engineering NOT a Complex database :D )      

# UML Parser Flow 
The below Figure, it represents the main flow and architecture of UML Parser. In the beginning, the user enters the site then the system will prepare the UI to the user. After that, the user enters his username and password, the system will perform the Login Process by taking the user input and map and compare it with the database. If the Login Process succeeded, UML Parser Menu will appear to the user. At this point, an input and output path will appear to the user in the UML parser menu, then the user must put the java source code which needs to be reversed in the input path. In addition, the user has two option to choose, either Class diagram, or Sequence diagram, the system will take that input information to prepare it and send it to UML Parser Engine. UML Parser Engine will handle this request then start parsing and creating the needed diagram to send it to yUML if it is a class diagram or to create pUML notation to draw a sequence diagram. When the parsing is complete, an image will be created according to the selected diagram. Furthermore, UML Parser Engine will store the data as text and image in the database and generate a traceability report which the user can find it in output path given by the UML Parser. This image will appear to the user in the UML Parser menu and saved to the output path.

![](nbproject/Flow.png)

# UML Parser Database
the below are the database tables 

images :
        ImageID         int  | 
        ImagePath       Varchar(2500)   |
        ImageType       Varchar(5)    |
        Sequence        int   |
        ImageBinary     BLOB    |
        Date            datetime    |
        CreatedByUserID int   |
        ReleaseVersion  Varchar(5)    
        
users : 
        UserID          int
        UserName        Varchar(15)
        Password        Varchar(20)
        UserTypeID      int
        UserStatusID    int
        LastLoginTime   datetime
        
userstatus:  
        UserStatusID    int   |
        UserStatusDescription   varchar(45) 
        
usertype:  
        UserTypeID    int   |
        UserTypeDescription   varchar(45) 

        
imagetype:  
        ImageTypeID    int   |
        ImageTypeDescription   varchar(45) 
        
note that you have to create user manually in the data base 

MySQL download link : https://dev.mysql.com/downloads/installer/ 

# User Interface of UML Parser



