---
layout: page
title: About Me
permalink: /about/
---
## Sports:
Water Polo and Swimming

## Freetime:
Hanging out with friends or watching movies

## Favorite top 3 movies:
Tron, Cars, Surf up

## My favorite things:
Mountain biking and surfing

## Culture and background
Im Vietnamese and I've lived in Vietnam and Boston


# Guess My favorite beach

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess My Favorite Beach</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #234b75;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        #guess-container {
            text-align: center;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        input[type="text"] {
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            width: 300px;
            margin-bottom: 10px;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            background-color: #007bff;
            color: #fff;
            border-radius: 4px;
        }

        button:hover {
            background-color: #0056b3;
        }

        #hint {
            margin-top: 15px;
            font-size: 18px;
            color: #d9534f;
        }
    </style>
</head>
<body>
    <div id="guess-container">
        <h1>Guess My Favorite Beach in San Diego</h1>
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

                if (userGuess === correctBeach) {
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
                    'Its next to a research facility.',
                    'Its next to Blacks beach.',
                ];

                return hints[Math.floor(Math.random() * hints.length)];
            }
        });
    </script>
</body>
</html>


