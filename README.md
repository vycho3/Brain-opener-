<div id="secret-trigger" onclick="unlockSecretLevel()"></div>
#secret-trigger {
    width: 4px;
    height: 4px;
    background: #39ff14;
    position: absolute;
    top: 10px;
    right: 10px;
    opacity: 0.2; /* Nearly invisible */
    cursor: crosshair;
    border-radius: 50%;
    transition: opacity 0.5s;
}

#secret-trigger:hover {
    opacity: 1; /* It glows when they hover over it! */
    box-shadow: 0 0 10px #39ff14;
}

/* Styling for the Secret Level look */
.secret-mode {
    background-color: #1a0000 !important; /* Changes background to dark red */
    color: #ff0000 !important; /* Changes text to red */
    border-color: #ff0000 !important;
}

.secret-mode .ninja-star {
    background: #ff0000 !important;
    box-shadow: 0 0 20px #ff0000 !important;
}
0puzzles.length<div class="game-container">
    <div class="logo-area">
        <div class="ninja-star"></div>
    </div>

    <div id="intro-screen">
        <div class="mission-section">
            <h3>The Mission</h3>
            <p>Intelligence is the ability to adapt. Our trials are designed to open your mind, one logic layer at a time. No ego, no logins—just pure thought.</p>
        </div>
        <button onclick="startGame()" class="btn-glow">Begin the Trial</button>
    </div>

    <div id="game-screen" class="hidden">
        <div class="quiz-box">
            <h2 id="level-title">Level 1</h2>
            <p id="question"></p>
            <input type="text" id="answer-input" placeholder="Type your answer...">
            <br><br>
            <button onclick="checkAnswer()" class="btn-glow">Submit</button>
            
            <div class="hint-section">
                <button id="hint-btn" onclick="showHint()">Get a Hint</button>
                <p id="hint-text" class="hidden"></p>
            </div>
        </div>
    </div>
</div>
function unlockSecretLevel() {
    // Change the theme to Red
    document.body.classList.add("secret-mode");
    document.querySelector(".game-container").classList.add("secret-mode");
    
    // Change the content
    document.getElementById("intro-screen").classList.add("hidden");
    document.getElementById("game-screen").classList.remove("hidden");
    
    // Set a specialized Impossible Riddle
    document.getElementById("level-title").innerText = "ERROR: SECRET LEVEL UNLOCKED";
    document.getElementById("question").innerText = "I am the beginning of everything, and the end of everywhere. I'm the beginning of eternity, the end of time and space. What am I?";
    
    // Update the answer logic for the secret level
    puzzles.push({a: "e"}); // The answer is the letter 'e'
    currentLevel = puzzles.length - 1;
    
    document.getElementById("hint-text").innerText = "Look closely at the words... not their meaning.";
}
