<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <meta name="description" content="Use our Random Name Picker to fairly and quickly choose a name from a list. Perfect for giveaways, team selections, classroom use, and more." />
  <meta name="keywords" content="Random Name Picker, name selector, name chooser tool, random picker, draw winner tool" />
 
  <title>Random Name Picker – Instantly Pick a Name from a List</title>
    <style>
        /* Modern CSS Reset with Custom Variables */
        :root {
            --primary-purple: #7e57c2;
            --secondary-pink: #ec407a;
            --accent-teal: #26a69a;
            --light-bg: #f8f9fa;
            --dark-text: #2c3e50;
            --light-text: #f5f7fa;
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.1);
            --shadow-md: 0 4px 12px rgba(0,0,0,0.15);
            --transition-fast: all 0.2s ease;
            --border-radius: 8px;
            --highlight-color: #fff176;
        } 
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', sans-serif;
        }
        body {
            background-color: var(--light-bg);
            color: var(--dark-text);
            line-height: 1.6;
            padding: 0.5rem;
        }
        .namepick-container-main {
            max-width: 800px;
            margin: 0 auto;
            padding: 0.8rem;
            background: white;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
        }
        .namepick-header-section {
            text-align: center;
            margin-bottom: 1.5rem;
            padding: 0.8rem;
            background: linear-gradient(135deg, var(--primary-purple), var(--secondary-pink));
            color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-md);
        }
        .namepick-title-heading {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.2);
        .namepick-subtitle-text {
            font-size: 1rem;
            opacity: 0.9;
        }
        .namepick-input-section {
            display: grid;
            grid-template-columns: 1fr auto;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        .namepick-input-group {
            position: relative;
        }
        .namepick-input-label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--primary-purple);
        }
        .namepick-textarea {
            width: 100%;
            min-height: 120px;
            padding: 0.8rem;
            border: 2px solid #e0e0e0;
            border-radius: var(--border-radius);
            font-size: 1rem;
            transition: var(--transition-fast);
            background-color: #f8f9fa;
            resize: vertical;
        }
        .namepick-textarea:focus {
            outline: none;
            border-color: var(--primary-purple);
            background-color: white;
            box-shadow: 0 0 0 3px rgba(126, 87, 194, 0.2);
        }
        .namepick-button-group {
            display: flex;
            flex-direction: column;
            gap: 0.8rem;
            justify-content: flex-end;
        }
        .namepick-button {
            padding: 0.8rem 1.2rem;
            border: none;
            border-radius: var(--border-radius);
            background-color: var(--primary-purple);
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition-fast);
            box-shadow: var(--shadow-sm);
            white-space: nowrap;
        }
                .namepick-button:hover {
            background-color: var(--secondary-pink);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }
        .namepick-button:active {
            transform: translateY(0);
        }
                .namepick-button-secondary {
            background-color: var(--accent-teal);
        }
        .namepick-result-container {
            margin-bottom: 2rem;
            text-align: center;
        }
        .namepick-result-card {
            padding: 2rem;
            border-radius: var(--border-radius);
            background: white;
            box-shadow: var(--shadow-sm);
            border-top: 4px solid var(--primary-purple);
            margin-bottom: 1rem;
            transition: all 0.3s ease;
        }
        .namepick-result-card.highlight {
            animation: highlight 1.5s ease;
            background-color: var(--highlight-color);
        }
                @keyframes highlight {
            0% { background-color: var(--highlight-color); }
            100% { background-color: white; }
        }
        .namepick-result-value {
            font-size: 3rem;
            font-weight: 700;
            margin: 0.5rem 0;
            color: var(--secondary-pink);
            min-height: 4rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .namepick-result-label {
            font-size: 1rem;
            color: var(--dark-text);
            opacity: 0.8;
        }
        .namepick-history-container {
            margin-bottom: 2rem;
        }
        .namepick-history-title {
            font-weight: 600;
            color: var(--primary-purple);
            margin-bottom: 0.8rem;
        }
        .namepick-history-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        .namepick-history-item {
            padding: 0.5rem 1rem;
            background-color: var(--light-bg);
            border-radius: 20px;
            font-size: 0.9rem;
        }
        .namepick-history-item.current {
            background-color: var(--secondary-pink);
            color: white;
        }
        .namepick-settings-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }
        .namepick-setting-group {
            padding: 1rem;
            border-radius: var(--border-radius);
            background: white;
            box-shadow: var(--shadow-sm);
            border-left: 4px solid var(--accent-teal);
        }
        .namepick-setting-title {
            font-weight: 600;
            color: var(--primary-purple);
            margin-bottom: 0.5rem;
        }
        .namepick-checkbox-group {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-top: 0.5rem;
        }
        .namepick-checkbox {
            accent-color: var(--primary-purple);
        }
        .namepick-table-responsive {
            width: 100%;
            overflow-x: auto;
            margin-bottom: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
        }
        .namepick-data-table {
            width: 100%;
            border-collapse: collapse;
            min-width: 500px;
        }
        .namepick-data-table th, .namepick-data-table td {
            padding: 0.8rem;
            text-align: left;
            border-bottom: 1px solid #e0e0e0;
        }
        .namepick-data-table th {
            background-color: var(--primary-purple);
            color: white;
            font-weight: 600;
        }
        .namepick-data-table tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        .namepick-data-table tr:hover {
            background-color: #f3e5f5;
        }
        @media (max-width: 768px) {
            .namepick-input-section {
                grid-template-columns: 1fr;
            }
            .namepick-button-group {
                flex-direction: row;
                justify-content: flex-start;
            }
            .namepick-title-heading {
                font-size: 1.5rem;
            }
            .namepick-result-value {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <div class="namepick-container-main">
        <div class="namepick-header-section">
            <h1 class="namepick-title-heading">Random Name Picker</h1>
            <p class="namepick-subtitle-text">Fair and fun selection for any occasion</p>
        </div>
                <div class="namepick-input-section">
            <div class="namepick-input-group">
                <label for="nameList" class="namepick-input-label">Enter Names (one per line or comma separated)</label>
                <textarea id="nameList" class="namepick-textarea" placeholder="John, Jane, Mike, Sarah"></textarea>
            </div>
            <div class="namepick-button-group">
                <button id="pickRandom" class="namepick-button">Pick Random</button>
                <button id="resetList" class="namepick-button namepick-button-secondary">Reset</button>
                <button id="removeSelected" class="namepick-button">Remove Selected</button>
                <button id="shuffleList" class="namepick-button">Shuffle All</button>
            </div>
        </div>      
        <div class="namepick-result-container">
            <div class="namepick-result-card" id="resultCard">
                <div class="namepick-result-label">Selected Name</div>
                <div id="selectedName" class="namepick-result-value">?</div>
                <div class="namepick-result-label" id="selectionStats">No names entered yet</div>
            </div>
        </div>
        <div class="namepick-settings-container">
            <div class="namepick-setting-group">
                <div class="namepick-setting-title">Selection Options</div>
                <div class="namepick-checkbox-group">
                    <input type="checkbox" id="allowDuplicates" class="namepick-checkbox" checked>
                    <label for="allowDuplicates">Allow duplicate picks</label>
                </div>
                <div class="namepick-checkbox-group">
                    <input type="checkbox" id="autoRemove" class="namepick-checkbox">
                    <label for="autoRemove">Auto-remove selected names</label>
                </div>
            </div>
            <div class="namepick-setting-group">
                <div class="namepick-setting-title">Animation Effects</div>
                <div class="namepick-checkbox-group">
                    <input type="checkbox" id="enableAnimation" class="namepick-checkbox" checked>
                    <label for="enableAnimation">Enable selection animation</label>
                </div>
                <div class="namepick-checkbox-group">
                    <input type="checkbox" id="showCountdown" class="namepick-checkbox" checked>
                    <label for="showCountdown">Show countdown</label>
                </div>
            </div>
        </div>
                <div class="namepick-history-container">
            <div class="namepick-history-title">Recently Picked Names</div>
            <div class="namepick-history-list" id="historyList">
                <!-- History items will be added here dynamically -->
            </div>
        </div>
        <div class="namepick-table-responsive">
            <table class="namepick-data-table">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Times Picked</th>
                        <th>Last Picked</th>
                        <th>Percentage</th>
                    </tr>
                </thead>
                <tbody id="nameStatsTable">
                    <!-- Name stats will be added here dynamically -->
                </tbody>
            </table>
        </div>
    </div>
    <script>
        // DOM Elements
        const nameListInput = document.getElementById('nameList');
        const pickRandomBtn = document.getElementById('pickRandom');
        const resetListBtn = document.getElementById('resetList');
        const removeSelectedBtn = document.getElementById('removeSelected');
        const shuffleListBtn = document.getElementById('shuffleList');
        const selectedNameElement = document.getElementById('selectedName');
        const selectionStatsElement = document.getElementById('selectionStats');
        const resultCard = document.getElementById('resultCard');
        const historyList = document.getElementById('historyList');
        const nameStatsTable = document.getElementById('nameStatsTable');
        // Settings elements
        const allowDuplicatesCheckbox = document.getElementById('allowDuplicates');
        const autoRemoveCheckbox = document.getElementById('autoRemove');
        const enableAnimationCheckbox = document.getElementById('enableAnimation');
        const showCountdownCheckbox = document.getElementById('showCountdown');
        // Data storage
        let names = [];
        let originalNames = [];
        let pickedNames = [];
        let nameStats = {};
        let isPicking = false;
        // Initialize
        function initialize() {
            parseNames();
            updateUI();
        }
        // Parse names from textarea
        function parseNames() {
            const text = nameListInput.value.trim();
            if (text.includes(',')) {
                names = text.split(',').map(name => name.trim()).filter(name => name);
            } else {
                names = text.split('\n').map(name => name.trim()).filter(name => name);
            }
            originalNames = [...names];
            initializeNameStats();
        }
        // Initialize name statistics
        function initializeNameStats() {
            nameStats = {};
            originalNames.forEach(name => {
                nameStats[name] = {
                    count: 0,
                    lastPicked: null,
                    percentage: 0
                };
            });
        }
        // Update name statistics
        function updateNameStats(name) {
            if (!nameStats[name]) {
                nameStats[name] = {
                    count: 0,
                    lastPicked: null,
                    percentage: 0
                };
            }
            nameStats[name].count++;
            nameStats[name].lastPicked = new Date().toLocaleTimeString();
            // Update percentages
            const totalPicks = pickedNames.length;
            Object.keys(nameStats).forEach(n => {
                nameStats[n].percentage = totalPicks > 0 
                    ? Math.round((nameStats[n].count / totalPicks) * 100) 
                    : 0;
            });
        }
        // Pick a random name
        function pickRandomName() {
            if (isPicking) return;
            if (names.length === 0) {
                selectedNameElement.textContent = "No names left!";
                selectionStatsElement.textContent = "Reset or add more names to continue";
                return;
            }
            isPicking = true;
            if (enableAnimationCheckbox.checked && showCountdownCheckbox.checked) {
                animateSelection();
            } else {
                completeSelection();
            }
        }
        // Animate the selection process
        function animateSelection() {
            let iterations = 0;
            const maxIterations = 20;
            const speedDecreaseFactor = 1.2;
            let delay = 100;
            const animate = () => {
                if (iterations >= maxIterations) {
                    completeSelection();
                    return;
                } 
                // Pick a temporary random name
                const tempIndex = Math.floor(Math.random() * names.length);
                selectedNameElement.textContent = names[tempIndex];
                // Increase delay to slow down animation
                delay *= speedDecreaseFactor;
                iterations++;
                setTimeout(animate, delay);
            };
            animate();
        }
        // Complete the selection process
        function completeSelection() {
            const randomIndex = Math.floor(Math.random() * names.length);
            const selectedName = names[randomIndex];
            // Update selected name display
            selectedNameElement.textContent = selectedName;
            // Highlight the result
            if (enableAnimationCheckbox.checked) {
                resultCard.classList.add('highlight');
                setTimeout(() => {
                    resultCard.classList.remove('highlight');
                }, 1500);
            }
            // Update picked names
            pickedNames.push(selectedName);
            updateNameStats(selectedName);
            // Remove name if auto-remove is enabled
            if (autoRemoveCheckbox.checked) {
                names.splice(randomIndex, 1);
            } else if (!allowDuplicatesCheckbox.checked) {
                names.splice(randomIndex, 1);
            }
            // Reset names if empty and duplicates not allowed
            if (names.length === 0 && !allowDuplicatesCheckbox.checked) {
                names = [...originalNames];
            }
            isPicking = false;
            updateUI();
        }
        // Reset the name list
        function resetList() {
            names = [...originalNames];
            pickedNames = [];
            initializeNameStats();
            selectedNameElement.textContent = "?";
            selectionStatsElement.textContent = `Ready to pick from ${names.length} names`;
            updateUI();
        }
        // Remove the currently selected name
        function removeSelected() {
            const currentName = selectedNameElement.textContent;
            if (currentName && currentName !== "?" && currentName !== "No names left!") {
                const index = names.indexOf(currentName);
                if (index !== -1) {
                    names.splice(index, 1);
                }
                updateUI();
            }
        }
        // Shuffle all names
        function shuffleList() {
            for (let i = names.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [names[i], names[j]] = [names[j], names[i]];
            }
            updateUI();
        }
        // Update the UI
        function updateUI() {
            // Update selection stats
            selectionStatsElement.textContent = pickedNames.length > 0
                ? `Picked ${pickedNames.length} of ${originalNames.length} names (${names.length} remaining)`
                : `Ready to pick from ${names.length} names`;
            // Update history list
            historyList.innerHTML = '';
            const uniquePickedNames = [...new Set(pickedNames)].reverse().slice(0, 10);
            uniquePickedNames.forEach(name => {
                const count = pickedNames.filter(n => n === name).length;
                const historyItem = document.createElement('div');
                historyItem.className = 'namepick-history-item';
                if (name === selectedNameElement.textContent) {
                    historyItem.classList.add('current');
                }
                historyItem.textContent = `${name}${count > 1 ? ` (${count})` : ''}`;
                historyList.appendChild(historyItem);
            });
            // Update stats table
            nameStatsTable.innerHTML = '';
            originalNames.forEach(name => {
                const row = document.createElement('tr');
                const nameCell = document.createElement('td');
                nameCell.textContent = name;
                row.appendChild(nameCell);
                const countCell = document.createElement('td');
                countCell.textContent = nameStats[name]?.count || 0;
                row.appendChild(countCell);
                                const lastPickedCell = document.createElement('td');
                lastPickedCell.textContent = nameStats[name]?.lastPicked || 'Never';
                row.appendChild(lastPickedCell);
                const percentageCell = document.createElement('td');
                percentageCell.textContent = nameStats[name]?.percentage ? `${nameStats[name].percentage}%` : '0%';
                row.appendChild(percentageCell);
                nameStatsTable.appendChild(row);
            });
        }
        // Event listeners
        nameListInput.addEventListener('input', initialize);
        pickRandomBtn.addEventListener('click', pickRandomName);
        resetListBtn.addEventListener('click', resetList);
        removeSelectedBtn.addEventListener('click', removeSelected);
        shuffleListBtn.addEventListener('click', shuffleList);
        // Initialize on load
        initialize();
    </script>
</body>
</html>

<br>
 <p>The <strong>Random Name Picker</strong> is a fast and fair tool for choosing names from a list. Whether you're running a giveaway, choosing team members, or making a classroom activity more fun, this tool makes random selections easy and exciting.</p>

  <h2>What Is a Random Name Picker?</h2>
  <p>It’s a simple online tool where you enter a list of names, and it randomly selects one or more from the list. It helps avoid bias, saves time, and makes the selection process feel fair to everyone involved.</p>

  <h2>How to Use the Tool</h2>
  <div class="info-box">
    <ul>
      <li>Type or paste all the names into the box, one name per line.</li>
      <li>Click the “Pick a Name” button.</li>
      <li>The tool will randomly select a name from your list and display it on the screen.</li>
    </ul>
  </div>

  <h2>Where Can You Use It?</h2>
  <ul>
    <li><strong>Giveaways:</strong> Fairly choose a winner from all entries.</li>
    <li><strong>Classrooms:</strong> Pick a student to answer a question or lead an activity.</li>
    <li><strong>Teams:</strong> Randomly assign members to groups or roles.</li>
    <li><strong>Events:</strong> Draw names for prizes, volunteers, or activities.</li>
  </ul>

  <h2>Benefits of a Random Name Picker</h2>
  <ul>
    <li>Eliminates human bias</li>
    <li>Saves time when managing large groups</li>
    <li>Easy to use on any device</li>
    <li>Fun and engaging experience for all users</li>
  </ul>

  <h2>Example</h2>
  <p>Imagine you’re hosting a $50 giveaway. You have 10 names. Instead of writing them on paper and drawing randomly, you use the Random Name Picker. In one click, it fairly picks a winner for you — saving time and adding fun!</p>

  <h2>Conclusion</h2>
  <p>The <strong>Random Name Picker</strong> is a smart solution for any situation where names need to be selected at random. Whether for fun or function, this tool is simple, quick, and always fair. Try it today and make your random selections easier than ever.</p>
