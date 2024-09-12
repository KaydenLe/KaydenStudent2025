---
layout: base
title: Kayden Home
description: Home Page
hide: true
---

## About Me:
 Growing up I never liked staying inside cause to me it’s just too boring and by going outside it created a great escape. I like hiking and mountain biking in my freetime and exploring nature. Mountain biking was a big part of my life growing up as I was a sponsored athlete until 2021 and an accident. I still occasionally go mountain biking and hiking at least a couple times a month because the planet is literally a playground and it depends what you are capable of doing which is represented by the 1 and second and 4 pictures. The first picture represents my love for going to the beach. As I have lived in San Diego for most of my life, I have always loved the beach. I’m on the swim team and so sometimes at the beach I swim and surf. I also like fishing as I will fish occasionally and sometimes if I catch a good fish I will eat but most fish I throw back into the water and this is represented through the 5th photo. The last picture represents how I like going sightseeing with my friends. I will drive and walk anywhere just for the view even though I will be there for a couple minutes. Mainly I like hanging out with my friends as they have helped me in my life a lot and they are the people that have helped me become the person I am today.

My Schedule:
1st Period: AP CSA
2nd Period: AP GOV.
3rd Period: EXPOS
4th Period: Business Law
5th Period: Off Roll

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

