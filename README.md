# Age-calculator-codealpha-project-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Age Calculator</title>
</head>
<body>
  <div class="calculator">
    <label for="dob">Date of Birth:</label>
    <input type="date" id="dob" required>
    <button onclick="calculateAge()">Calculate Age</button>
    <p id="result"></p>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.calculator {
  text-align: center;
  max-width: 400px;
  margin: auto;
}

button {
  margin-top: 10px;
}
function calculateAge() {
  const dobInput = document.getElementById("dob").value;
  const dob = new Date(dobInput);
  const currentDate = new Date();

  const age = currentDate.getFullYear() - dob.getFullYear();
  const monthDiff = currentDate.getMonth() - dob.getMonth();

  if (monthDiff < 0 || (monthDiff === 0 && currentDate.getDate() < dob.getDate())) {
    // Adjust age if birthday hasn't occurred yet this year
    document.getElementById("result").innerText = `Your age is ${age - 1} years.`;
  } else {
    document.getElementById("result").innerText = `Your age is ${age} years.`;
  }
}
