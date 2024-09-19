---
layout: page
title: Typing Game
search_exclude: true
permalink: /typing/
---

<html lang="en">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }

        #text-container {
            margin-bottom: 20px;
        }

        #user-input {
            width: 80%;
            height: 100px;
            font-size: 16px;
            padding: 10px;
        }

        #results {
            margin-top: 20px;
        }
    </style>

    <h1>Typing Game</h1>
    <div id="text-container">
        <p id="text-to-type">The quick brown fox jumps over the lazy dog.</p>
    </div>
    <textarea id="user-input" placeholder="Start typing here..." autofocus></textarea>
    <button id="start-button">Start</button>
    <div id="results">
        <p id="time">Time: <span id="time-display">0</span> seconds</p>
        <p id="accuracy">Accuracy: <span id="accuracy-display">0%</span></p>
    </div>
    <script>
        let startButton = document.getElementById('start-button');
        let userInput = document.getElementById('user-input');
        let textToType = document.getElementById('text-to-type').innerText;
        let timeDisplay = document.getElementById('time-display');
        let accuracyDisplay = document.getElementById('accuracy-display');

        let startTime, endTime, timer, isTyping = false;

        function startTypingTest() {
            if (isTyping) return;
            
            isTyping = true;
            userInput.value = '';
            userInput.disabled = false;
            userInput.focus();
            
            startTime = new Date().getTime();
            timer = setInterval(updateTime, 100);
        }

        function updateTime() {
            let currentTime = new Date().getTime();
            let elapsedTime = (currentTime - startTime) / 1000;
            timeDisplay.textContent = elapsedTime.toFixed(2);
        }

        function endTypingTest() {
            clearInterval(timer);
            isTyping = false;
            
            let typedText = userInput.value;
            let correctChars = 0;
            
            for (let i = 0; i < typedText.length; i++) {
                if (typedText[i] === textToType[i]) {
                    correctChars++;
                }
            }
            
            let accuracy = (correctChars / textToType.length) * 100;
            accuracyDisplay.textContent = accuracy.toFixed(2) + '%';
            
            userInput.disabled = true;
        }

        startButton.addEventListener('click', startTypingTest);
        userInput.addEventListener('input', function() {
            if (userInput.value.length >= textToType.length) {
                endTypingTest();
            }
        });
    </script>
