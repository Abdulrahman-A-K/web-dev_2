# web-dev_2
## second tasks  
* **overview**
    * This task builds upon the previous one by focusing on retrieving and displaying the robot's most recent movement from the database. The web interface allows users to view the last recorded movement of the robot.

* **Dependencies**
     *XAMPP: Local server environment including Apache, PHP, and MySQL.
     *PHP 7.x or higher: Server-side scripting language for processing requests.
     *MySQL: Database system to store and retrieve robot movement data.

* **files we have**
    * first file we have is index.html is holding the interface structure   
            * a form to retreive the robot's last move from database and its link to last-move.php that gets the data from database and prints the last

    * second file we have is The design.css file defines the visual styling and layout of the index.html page 

    * last file we have is last-move.php is print out the last-move of the robot using  this commnad and then redirecting to index.html after 3 seconds
    ``` php
        $sql = 'SELECT direction FROM robotmove ORDER BY id DESC LIMIT 1';
        $result = mysqli_query($conn, $sql);

    // Fetch the result
        if(mysqli_num_rows($result) == 0){
            echo "the robot has not moved".'<br>';
        }
        else{
            $row = mysqli_fetch_assoc($result);
            echo $row['direction'];   
        }
        header("Refresh: 3; url=index.html");
    ```
