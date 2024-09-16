---
layout: base
title: Kayden Home
description: Home Page
hide: true
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dropdown Menu to game file</title>
</head>
<body>

    <label for="md-files">Choose a file:</label>
    <select id="md-files" onchange="navigateToFile()">
        <option value="">--Select an option--</option>
        <option value="{{ '/tron/' | relative_url }}">Tron</option> <!-- Updated to use the correct path -->
        <option value="{{ '/typing/' | relative_url }}">Typing Game</option> <!-- Adjusted for possible .html output -->
        <option value="{{ '/pair/' | relative_url }}">Pair Programming</option> <!-- Adjusted for possible .html output -->
    </select>

    <script>
        function navigateToFile() {
            var file = document.getElementById("md-files").value;
            if (file) {
                window.location.href = file; // Redirects to the selected file
            }
        }
    </script>

</body>
</html>
