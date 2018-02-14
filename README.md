
 <?php
$servername = "localhost";
$username = "****";
$password = "******";
$database = "****";
$FirstName=$_POST["FirstName"];
$LastName=$_POST["LastName"];
$email = $_POST["email"];
$pasword = $_POST["pasword"];
$confirmpasword = $_POST["confirmpasword"];
if  ($_SERVER["REQUEST_METHOD"] == "POST") {
if ($confirmpasword == $pasword)
	{	
	$conn = new mysqli( $servername, $username, $password, $database);
	if ($conn->connect_error) {
	    die("Connection failed: " . $conn->connect_error);
	}
	$sql = "INSERT INTO signups(first,last,email,password)
	VALUES ($FirstName,$LastName,$email,$pasword)";
	$conn->close();
	echo "Account created successfully,Happy shopping !";
	}

else {
	echo "password doesn't match";
	}
}
?>
