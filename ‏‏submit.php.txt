<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "patient";

// Connect to database
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Get form data
$first_name = $_POST['first_name'];
$last_name = $_POST['last_name'];
$age = $_POST['age'];

// Insert data into the table
if (!empty($first_name) && !empty($last_name) && !empty($age)) {
    $sql = "INSERT INTO info (first_name, last_name, age)
            VALUES ('$first_name', '$last_name', $age)";

    if ($conn->query($sql) === TRUE) {
        echo "<h3 style='color: green;'>✅ Data inserted successfully!</h3>";
    } else {
        echo "<h3 style='color: red;'>❌ Error: " . $sql . "<br>" . $conn->error . "</h3>";
    }
} else {
    echo "<h3 style='color: orange;'>⚠️ Please fill in all the fields!</h3>";
}

// Fetch all records from the table
$result = $conn->query("SELECT * FROM info");

// Display data in an HTML table
if ($result->num_rows > 0) {
    echo "<h3>📋 All Records:</h3>";
    echo "<table border='1' cellpadding='10' style='border-collapse: collapse;'>
            <tr style='background-color: #f2f2f2;'>
                <th>ID</th>
                <th>First Name</th>
                <th>Last Name</th>
                <th>Age</th>
            </tr>";

    while ($row = $result->fetch_assoc()) {
        echo "<tr>
                <td>" . htmlspecialchars($row['id']) . "</td>
                <td>" . htmlspecialchars($row['first_name']) . "</td>
                <td>" . htmlspecialchars($row['last_name']) . "</td>
                <td>" . htmlspecialchars($row['age']) . "</td>
              </tr>";
    }

    echo "</table>";
} else {
    echo "<p>No records found.</p>";
}

$conn->close();
?>