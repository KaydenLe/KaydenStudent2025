---
layout: page
title: Pair Programming
search_exclude: true
permalink: /pair/
---

    <h1>Typing Game</h1>
    <div id="text-container">
        <p id="text-to-type">The quick brown fox jumps over the lazy dog.</p>
    </div>
    <textarea id="user-input" placeholder="Start typing here..." autofocus disabled></textarea>
    <br>
    <button id="start-button">Start</button>
    <div id="results">
        <p id="time">Time: <span id="time-display">0</span> seconds</p>
        <p id="accuracy">Accuracy: <span id="accuracy-display">0%</span></p>
    </div>

    <script>
        // DOM elements
        const startButton = document.getElementById('start-button');
        const userInput = document.getElementById('user-input');
        const textToType = document.getElementById('text-to-type').innerText;
        const timeDisplay = document.getElementById('time-display');
        const accuracyDisplay = document.getElementById('accuracy-display');

        let startTime, timer, isTyping = false;

        // Start the typing test
        function startTypingTest() {
            if (isTyping) return; // Prevent restarting while in progress
            
            isTyping = true;
            userInput.value = ''; // Reset input field
            userInput.disabled = false; // Enable typing
            userInput.focus(); // Focus on the input area

            // Start the timer
            startTime = new Date().getTime();
            timer = setInterval(updateTime, 100);
        }

        // Update the time display
        function updateTime() {
            const currentTime = new Date().getTime();
            const elapsedTime = (currentTime - startTime) / 1000; // Seconds
            timeDisplay.textContent = elapsedTime.toFixed(2); // Display time with two decimals
        }

        // End the typing test
        function endTypingTest() {
            clearInterval(timer); // Stop the timer
            isTyping = false; // Reset typing state
            userInput.disabled = true; // Disable typing after finishing

            const typedText = userInput.value;
            let correctChars = 0;

            // Calculate accuracy by comparing input to the text
            for (let i = 0; i < typedText.length; i++) {
                if (typedText[i] === textToType[i]) {
                    correctChars++;
                }
            }

            // Display accuracy
            const accuracy = (correctChars / textToType.length) * 100;
            accuracyDisplay.textContent = accuracy.toFixed(2) + '%';
        }

        // Event listener for the start button
        startButton.addEventListener('click', startTypingTest);

        // Check if the typing test is finished
        userInput.addEventListener('input', function () {
            if (userInput.value.length >= textToType.length) {
                endTypingTest(); // End test when the length of input matches the given text
            }
        });
    </script>