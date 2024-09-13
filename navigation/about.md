---
layout: page
title: About Me
permalink: /about/
hide: true
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Profile</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f9;
            color: #333;
            margin: 0;
            padding: 0;
        }
        h2 {
            color: #2c3e50;
            text-align: center;
            margin-top: 20px;
        }
        ul {
            list-style-type: none;
            padding: 0;
            text-align: center;
        }
        li {
            background: #000080;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            display: inline-block;
            width: 180px;
            text-align: center;
        }
        p {
            text-align: center;
            font-size: 1.1em;
        }
        img {
            display: block;
            margin: 20px auto;
            border-radius: 10px;
        }
        #guess-container {
            text-align: center;
            margin: 40px auto;
            padding: 20px;
            background-color: #000080;
            border-radius: 10px;
            width: 80%;
            max-width: 500px;
        }
        #guess-container h3 {
            color: white;
        }
        input[type="text"] {
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #bdc3c7;
            width: 80%;
            max-width: 300px;
            margin-bottom: 10px;
        }
        button {
            background-color: #2980b9;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #3498db;
        }
        #hint {
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <h2>Sports:</h2>
    <ul>
        <li>Water Polo</li>
        <li>Swimming</li>
    </ul>

    <img width="269" alt="Screenshot 2024-09-13 at 9 15 36 AM" src="https://github.com/user-attachments/assets/a5018f45-7433-4ace-8eae-be1d076831cc">
    <img width="263" alt="Screenshot 2024-09-13 at 9 16 31 AM" src="https://github.com/user-attachments/assets/3a0e043e-d8b7-4f09-b108-c8eaf02fe562">


    <h2>Freetime:</h2>
    <p>Hanging out with friends or watching movies</p>

    <h2>My favorite things:</h2>
    <ul>
        <li>Mountain biking</li>
        <li>Surfing</li>
        <li>Researching about cars</li>
    </ul>

    <h2>Favorite top 3 movies:</h2>
    <ul>
        <li>Tron</li>
        <li>Cars</li>
        <li>Surf's Up</li>
    </ul>
    
    <img width="218" alt="Screenshot 2024-09-13 at 8 35 08 AM" src="https://github.com/user-attachments/assets/36ab2bfa-3686-439e-8873-783f7b6ad2f3">
    <img width="226" alt="Screenshot 2024-09-13 at 8 36 12 AM" src="https://github.com/user-attachments/assets/949d2d9e-0dec-40f0-9fd8-ab846cd13db7">
    <img width="218" alt="Screenshot 2024-09-13 at 8 36 43 AM" src="https://github.com/user-attachments/assets/62def3ff-2745-49a3-aa2b-9bd3d025d61d">

    <h2>Culture and background:</h2>
    <p>I'm Vietnamese and I've lived in Vietnam and Boston</p>

    <img width="554" alt="Screenshot 2024-09-13 at 8 48 20 AM" src="https://github.com/user-attachments/assets/f31839ee-5899-4d7c-b8d9-b10472b2bdb0">

    <h2>Guess My Favorite Beach</h2>

    <div id="guess-container">
        <h3>Guess My Favorite Beach in San Diego</h3>
        <input type="text" id="beach-guess" placeholder="Enter your guess here">
        <button id="submit-guess">Submit Guess</button>
        <p id="hint"></p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const correctBeach = 'Scripps';
            const submitButton = document.getElementById('submit-guess');
            const hintParagraph = document.getElementById('hint');

            submitButton.addEventListener('click', function() {
                const userGuess = document.getElementById('beach-guess').value.trim().toLowerCase();

                if (userGuess === correctBeach.toLowerCase()) {
                    hintParagraph.textContent = 'Congratulations! You guessed it right!';
                    hintParagraph.style.color = 'green';
                } else {
                    hintParagraph.textContent = getHint(userGuess);
                    hintParagraph.style.color = '#d9534f';
                }
            });

            function getHint(guess) {
                const hints = [
                    'It is a beach near La Jolla.',
                    'It has a pier.',
                    'It is below the Birch Aquarium.',
                    'It’s next to a research facility.',
                    'It’s next to Blacks beach.'
                ];

                return hints[Math.floor(Math.random() * hints.length)];
            }
        });
    </script>
</body>
</html>
