<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bible Study - 2026</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@400;600;700&family=DM+Sans:wght@400;500;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #2C5F2D;
            --primary-light: #97BC62;
            --accent: #D4A574;
            --background: #FEFAF6;
            --surface: #FFFFFF;
            --text: #2C3E50;
            --text-light: #6B7280;
            --border: #E5E7EB;
            --success: #10B981;
            --streak: #F59E0B;
        }
        
        body {
            font-family: 'DM Sans', sans-serif;
            background: linear-gradient(135deg, #FEFAF6 0%, #F8F4EF 100%);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        header {
            text-align: center;
            padding: 3rem 0 2rem;
            position: relative;
        }
        
        h1 {
            font-family: 'Crimson Pro', serif;
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
            letter-spacing: -0.02em;
        }
        
        .subtitle {
            font-size: 1.1rem;
            color: var(--text-light);
            margin-bottom: 2rem;
        }
        
        .accountability-section {
            background: var(--surface);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05), 0 10px 20px rgba(0,0,0,0.03);
            border: 1px solid var(--border);
        }
        
        .partner-setup {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .partner-card {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            border-radius: 16px;
            padding: 2rem;
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .partner-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(-20px, -20px); }
        }
        
        .partner-card h3 {
            font-family: 'Crimson Pro', serif;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            position: relative;
        }
        
        .partner-card input {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 8px;
            background: rgba(255,255,255,0.2);
            color: white;
            font-size: 1rem;
            position: relative;
        }
        
        .partner-card input::placeholder {
            color: rgba(255,255,255,0.7);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .stat-card {
            background: var(--surface);
            border: 2px solid var(--border);
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
            border-color: var(--primary);
        }
        
        .stat-value {
            font-family: 'Crimson Pro', serif;
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            display: block;
            margin-bottom: 0.25rem;
        }
        
        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        
        .streak-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        
        .calendar-container {
            background: var(--surface);
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            margin-bottom: 2rem;
        }
        
        .month-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 2px solid var(--border);
        }
        
        .month-title {
            font-family: 'Crimson Pro', serif;
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .month-nav {
            display: flex;
            gap: 0.5rem;
        }
        
        .month-nav button {
            padding: 0.5rem 1rem;
            border: 2px solid var(--primary);
            background: var(--surface);
            color: var(--primary);
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s;
        }
        
        .month-nav button:hover {
            background: var(--primary);
            color: white;
        }
        
        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 0.75rem;
        }
        
        .day-header {
            text-align: center;
            font-weight: 700;
            color: var(--primary);
            padding: 0.75rem;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        
        .day-cell {
            aspect-ratio: 1;
            border: 2px solid var(--border);
            border-radius: 12px;
            padding: 0.75rem;
            background: var(--surface);
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            display: flex;
            flex-direction: column;
            min-height: 120px;
        }
        
        .day-cell:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            border-color: var(--primary-light);
        }
        
        .day-cell.empty {
            background: transparent;
            border: none;
            cursor: default;
        }
        
        .day-cell.empty:hover {
            transform: none;
            box-shadow: none;
        }
        
        .day-cell.past {
            opacity: 0.5;
        }
        
        .day-cell.today {
            border-color: var(--accent);
            background: linear-gradient(135deg, #FFF9F0 0%, #FFFFFF 100%);
            border-width: 3px;
        }
        
        .day-cell.both-checked {
            background: linear-gradient(135deg, #E8F5E9 0%, #C8E6C9 100%);
            border-color: var(--success);
        }
        
        .day-cell.partner1-checked {
            background: linear-gradient(135deg, #E3F2FD 0%, #BBDEFB 100%);
        }
        
        .day-cell.partner2-checked {
            background: linear-gradient(135deg, #FCE4EC 0%, #F8BBD0 100%);
        }
        
        .day-number {
            font-weight: 700;
            font-size: 1rem;
            color: var(--text);
            margin-bottom: 0.25rem;
        }
        
        .reading-text {
            font-size: 0.7rem;
            color: var(--text-light);
            line-height: 1.3;
            flex-grow: 1;
            overflow: hidden;
        }
        
        .check-indicators {
            display: flex;
            gap: 0.25rem;
            margin-top: 0.5rem;
        }
        
        .check-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--border);
        }
        
        .check-dot.checked-partner1 {
            background: #2196F3;
        }
        
        .check-dot.checked-partner2 {
            background: #E91E63;
        }
        
        .check-buttons {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
        }
        
        .check-btn {
            flex: 1;
            padding: 0.75rem;
            border: 2px solid;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            background: white;
        }
        
        .check-btn.partner1 {
            border-color: #2196F3;
            color: #2196F3;
        }
        
        .check-btn.partner1:hover, .check-btn.partner1.active {
            background: #2196F3;
            color: white;
        }
        
        .check-btn.partner2 {
            border-color: #E91E63;
            color: #E91E63;
        }
        
        .check-btn.partner2:hover, .check-btn.partner2.active {
            background: #E91E63;
            color: white;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(4px);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .modal.active {
            display: flex;
        }
        
        .modal-content {
            background: var(--surface);
            border-radius: 20px;
            padding: 2rem;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            animation: slideUp 0.3s ease;
        }
        
        @keyframes slideUp {
            from { 
                opacity: 0;
                transform: translateY(20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .modal-header {
            font-family: 'Crimson Pro', serif;
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        .modal-reading {
            background: #F5F5F5;
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 1.5rem;
            font-size: 1rem;
            color: var(--text);
        }
        
        .close-modal {
            width: 100%;
            padding: 0.75rem;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .close-modal:hover {
            background: var(--primary-light);
            transform: translateY(-2px);
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .partner-setup {
                grid-template-columns: 1fr;
            }
            
            .calendar-grid {
                gap: 0.5rem;
            }
            
            .day-cell {
                min-height: 100px;
                padding: 0.5rem;
            }
            
            .reading-text {
                font-size: 0.65rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>📖 Bible Study</h1>
            <p class="subtitle">2026 Reading Plan • Feb 3 - Dec 31</p>
        </header>
        
        <div class="accountability-section">
            <div class="partner-setup">
                <div class="partner-card">
                    <h3>👤 Partner 1</h3>
                    <input type="text" id="partner1Name" placeholder="Enter your name" />
                </div>
                <div class="partner-card">
                    <h3>👤 Partner 2</h3>
                    <input type="text" id="partner2Name" placeholder="Enter partner's name" />
                </div>
            </div>
            
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="streak-icon">🔥</div>
                    <span class="stat-value" id="currentStreak">0</span>
                    <span class="stat-label">Current Streak</span>
                </div>
                <div class="stat-card">
                    <div class="streak-icon">⭐</div>
                    <span class="stat-value" id="longestStreak">0</span>
                    <span class="stat-label">Longest Streak</span>
                </div>
                <div class="stat-card">
                    <div class="streak-icon">✅</div>
                    <span class="stat-value" id="totalDays">0</span>
                    <span class="stat-label">Days Completed</span>
                </div>
                <div class="stat-card">
                    <div class="streak-icon">📚</div>
                    <span class="stat-value" id="chaptersRead">0</span>
                    <span class="stat-label">Chapters Read</span>
                </div>
            </div>
        </div>
        
        <div class="calendar-container">
            <div class="month-header">
                <h2 class="month-title" id="monthTitle">February 2026</h2>
                <div class="month-nav">
                    <button onclick="previousMonth()">← Prev</button>
                    <button onclick="nextMonth()">Next →</button>
                </div>
            </div>
            <div class="calendar-grid" id="calendar"></div>
        </div>
    </div>
    
    <div class="modal" id="dayModal">
        <div class="modal-content">
            <h3 class="modal-header" id="modalDate"></h3>
            <div class="modal-reading" id="modalReading"></div>
            <div class="check-buttons">
                <button class="check-btn partner1" id="checkPartner1">
                    <span id="partner1BtnText">✓ Partner 1</span>
                </button>
                <button class="check-btn partner2" id="checkPartner2">
                    <span id="partner2BtnText">✓ Partner 2</span>
                </button>
            </div>
            <button class="close-modal" onclick="closeModal()">Close</button>
        </div>
    </div>

    <script>
        const readingPlan = [{"date":"2026-02-03","day":3,"month":2,"reading":"Genesis 1-4"},{"date":"2026-02-04","day":4,"month":2,"reading":"Genesis 5-8"},{"date":"2026-02-05","day":5,"month":2,"reading":"Genesis 9-12"},{"date":"2026-02-06","day":6,"month":2,"reading":"Genesis 13-16"},{"date":"2026-02-07","day":7,"month":2,"reading":"Genesis 17-20"},{"date":"2026-02-08","day":8,"month":2,"reading":"Genesis 21-24"},{"date":"2026-02-09","day":9,"month":2,"reading":"Genesis 25-28"},{"date":"2026-02-10","day":10,"month":2,"reading":"Genesis 29-32"},{"date":"2026-02-11","day":11,"month":2,"reading":"Genesis 33-36"},{"date":"2026-02-12","day":12,"month":2,"reading":"Genesis 37-40"},{"date":"2026-02-13","day":13,"month":2,"reading":"Genesis 41-44"},{"date":"2026-02-14","day":14,"month":2,"reading":"Genesis 45-48"},{"date":"2026-02-15","day":15,"month":2,"reading":"Genesis 49-50; Exodus 1-2"},{"date":"2026-02-16","day":16,"month":2,"reading":"Exodus 3-6"},{"date":"2026-02-17","day":17,"month":2,"reading":"Exodus 7-10"},{"date":"2026-02-18","day":18,"month":2,"reading":"Exodus 11-14"},{"date":"2026-02-19","day":19,"month":2,"reading":"Exodus 15-18"},{"date":"2026-02-20","day":20,"month":2,"reading":"Exodus 19-22"},{"date":"2026-02-21","day":21,"month":2,"reading":"Exodus 23-26"},{"date":"2026-02-22","day":22,"month":2,"reading":"Exodus 27-30"},{"date":"2026-02-23","day":23,"month":2,"reading":"Exodus 31-34"},{"date":"2026-02-24","day":24,"month":2,"reading":"Exodus 35-38"},{"date":"2026-02-25","day":25,"month":2,"reading":"Exodus 39-40; Leviticus 1-2"},{"date":"2026-02-26","day":26,"month":2,"reading":"Leviticus 3-6"},{"date":"2026-02-27","day":27,"month":2,"reading":"Leviticus 7-10"},{"date":"2026-02-28","day":28,"month":2,"reading":"Leviticus 11-14"},{"date":"2026-03-01","day":1,"month":3,"reading":"Leviticus 15-18"},{"date":"2026-03-02","day":2,"month":3,"reading":"Leviticus 19-22"},{"date":"2026-03-03","day":3,"month":3,"reading":"Leviticus 23-26"},{"date":"2026-03-04","day":4,"month":3,"reading":"Leviticus 27; Numbers 1-3"},{"date":"2026-03-05","day":5,"month":3,"reading":"Numbers 4-6"},{"date":"2026-03-06","day":6,"month":3,"reading":"Numbers 7-9"},{"date":"2026-03-07","day":7,"month":3,"reading":"Numbers 10-13"},{"date":"2026-03-08","day":8,"month":3,"reading":"Numbers 14-16"},{"date":"2026-03-09","day":9,"month":3,"reading":"Numbers 17-20"},{"date":"2026-03-10","day":10,"month":3,"reading":"Numbers 21-24"},{"date":"2026-03-11","day":11,"month":3,"reading":"Numbers 25-27"},{"date":"2026-03-12","day":12,"month":3,"reading":"Numbers 28-31"},{"date":"2026-03-13","day":13,"month":3,"reading":"Numbers 32-34"},{"date":"2026-03-14","day":14,"month":3,"reading":"Numbers 35-36; Deuteronomy 1-2"},{"date":"2026-03-15","day":15,"month":3,"reading":"Deuteronomy 3-6"},{"date":"2026-03-16","day":16,"month":3,"reading":"Deuteronomy 7-10"},{"date":"2026-03-17","day":17,"month":3,"reading":"Deuteronomy 11-14"},{"date":"2026-03-18","day":18,"month":3,"reading":"Deuteronomy 15-18"},{"date":"2026-03-19","day":19,"month":3,"reading":"Deuteronomy 19-22"},{"date":"2026-03-20","day":20,"month":3,"reading":"Deuteronomy 23-26"},{"date":"2026-03-21","day":21,"month":3,"reading":"Deuteronomy 27-30"},{"date":"2026-03-22","day":22,"month":3,"reading":"Deuteronomy 31-34"},{"date":"2026-03-23","day":23,"month":3,"reading":"Joshua 1-4"},{"date":"2026-03-24","day":24,"month":3,"reading":"Joshua 5-8"},{"date":"2026-03-25","day":25,"month":3,"reading":"Joshua 9-12"},{"date":"2026-03-26","day":26,"month":3,"reading":"Joshua 13-16"},{"date":"2026-03-27","day":27,"month":3,"reading":"Joshua 17-20"},{"date":"2026-03-28","day":28,"month":3,"reading":"Joshua 21-24"},{"date":"2026-03-29","day":29,"month":3,"reading":"Judges 1-3"},{"date":"2026-03-30","day":30,"month":3,"reading":"Judges 4-7"},{"date":"2026-03-31","day":31,"month":3,"reading":"Judges 8-11"},{"date":"2026-04-01","day":1,"month":4,"reading":"Judges 12-15"},{"date":"2026-04-02","day":2,"month":4,"reading":"Judges 16-18"},{"date":"2026-04-03","day":3,"month":4,"reading":"Judges 19-21"},{"date":"2026-04-04","day":4,"month":4,"reading":"Ruth 1-4"},{"date":"2026-04-05","day":5,"month":4,"reading":"1 Samuel 1-3"},{"date":"2026-04-06","day":6,"month":4,"reading":"1 Samuel 4-7"},{"date":"2026-04-07","day":7,"month":4,"reading":"1 Samuel 8-11"},{"date":"2026-04-08","day":8,"month":4,"reading":"1 Samuel 12-15"},{"date":"2026-04-09","day":9,"month":4,"reading":"1 Samuel 16-19"},{"date":"2026-04-10","day":10,"month":4,"reading":"1 Samuel 20-23"},{"date":"2026-04-11","day":11,"month":4,"reading":"1 Samuel 24-27"},{"date":"2026-04-12","day":12,"month":4,"reading":"1 Samuel 28-31"},{"date":"2026-04-13","day":13,"month":4,"reading":"2 Samuel 1-4"},{"date":"2026-04-14","day":14,"month":4,"reading":"2 Samuel 5-8"},{"date":"2026-04-15","day":15,"month":4,"reading":"2 Samuel 9-12"},{"date":"2026-04-16","day":16,"month":4,"reading":"2 Samuel 13-16"},{"date":"2026-04-17","day":17,"month":4,"reading":"2 Samuel 17-20"},{"date":"2026-04-18","day":18,"month":4,"reading":"2 Samuel 21-24"},{"date":"2026-04-19","day":19,"month":4,"reading":"1 Kings 1-3"},{"date":"2026-04-20","day":20,"month":4,"reading":"1 Kings 4-7"},{"date":"2026-04-21","day":21,"month":4,"reading":"1 Kings 8-11"},{"date":"2026-04-22","day":22,"month":4,"reading":"1 Kings 12-15"},{"date":"2026-04-23","day":23,"month":4,"reading":"1 Kings 16-19"},{"date":"2026-04-24","day":24,"month":4,"reading":"1 Kings 20-22"},{"date":"2026-04-25","day":25,"month":4,"reading":"2 Kings 1-4"},{"date":"2026-04-26","day":26,"month":4,"reading":"2 Kings 5-8"},{"date":"2026-04-27","day":27,"month":4,"reading":"2 Kings 9-12"},{"date":"2026-04-28","day":28,"month":4,"reading":"2 Kings 13-16"},{"date":"2026-04-29","day":29,"month":4,"reading":"2 Kings 17-20"},{"date":"2026-04-30","day":30,"month":4,"reading":"2 Kings 21-25"},{"date":"2026-05-01","day":1,"month":5,"reading":"1 Chronicles 1-3"},{"date":"2026-05-02","day":2,"month":5,"reading":"1 Chronicles 4-6"},{"date":"2026-05-03","day":3,"month":5,"reading":"1 Chronicles 7-10"},{"date":"2026-05-04","day":4,"month":5,"reading":"1 Chronicles 11-14"},{"date":"2026-05-05","day":5,"month":5,"reading":"1 Chronicles 15-18"},{"date":"2026-05-06","day":6,"month":5,"reading":"1 Chronicles 19-22"},{"date":"2026-05-07","day":7,"month":5,"reading":"1 Chronicles 23-26"},{"date":"2026-05-08","day":8,"month":5,"reading":"1 Chronicles 27-29"},{"date":"2026-05-09","day":9,"month":5,"reading":"2 Chronicles 1-4"},{"date":"2026-05-10","day":10,"month":5,"reading":"2 Chronicles 5-8"},{"date":"2026-05-11","day":11,"month":5,"reading":"2 Chronicles 9-12"},{"date":"2026-05-12","day":12,"month":5,"reading":"2 Chronicles 13-16"},{"date":"2026-05-13","day":13,"month":5,"reading":"2 Chronicles 17-20"},{"date":"2026-05-14","day":14,"month":5,"reading":"2 Chronicles 21-24"},{"date":"2026-05-15","day":15,"month":5,"reading":"2 Chronicles 25-28"},{"date":"2026-05-16","day":16,"month":5,"reading":"2 Chronicles 29-32"},{"date":"2026-05-17","day":17,"month":5,"reading":"2 Chronicles 33-36"},{"date":"2026-05-18","day":18,"month":5,"reading":"Ezra 1-4"},{"date":"2026-05-19","day":19,"month":5,"reading":"Ezra 5-7"},{"date":"2026-05-20","day":20,"month":5,"reading":"Ezra 8-10"},{"date":"2026-05-21","day":21,"month":5,"reading":"Nehemiah 1-4"},{"date":"2026-05-22","day":22,"month":5,"reading":"Nehemiah 5-7"},{"date":"2026-05-23","day":23,"month":5,"reading":"Nehemiah 8-10"},{"date":"2026-05-24","day":24,"month":5,"reading":"Nehemiah 11-13"},{"date":"2026-05-25","day":25,"month":5,"reading":"Esther 1-4"},{"date":"2026-05-26","day":26,"month":5,"reading":"Esther 5-7"},{"date":"2026-05-27","day":27,"month":5,"reading":"Esther 8-10"},{"date":"2026-05-28","day":28,"month":5,"reading":"Job 1-4"},{"date":"2026-05-29","day":29,"month":5,"reading":"Job 5-8"},{"date":"2026-05-30","day":30,"month":5,"reading":"Job 9-12"},{"date":"2026-05-31","day":31,"month":5,"reading":"Job 13-16"},{"date":"2026-06-01","day":1,"month":6,"reading":"Job 17-20"},{"date":"2026-06-02","day":2,"month":6,"reading":"Job 21-24"},{"date":"2026-06-03","day":3,"month":6,"reading":"Job 25-28"},{"date":"2026-06-04","day":4,"month":6,"reading":"Job 29-32"},{"date":"2026-06-05","day":5,"month":6,"reading":"Job 33-36"},{"date":"2026-06-06","day":6,"month":6,"reading":"Job 37-40"},{"date":"2026-06-07","day":7,"month":6,"reading":"Job 41-42; Psalms 1-3"},{"date":"2026-06-08","day":8,"month":6,"reading":"Psalms 4-7"},{"date":"2026-06-09","day":9,"month":6,"reading":"Psalms 8-11"},{"date":"2026-06-10","day":10,"month":6,"reading":"Psalms 12-15"},{"date":"2026-06-11","day":11,"month":6,"reading":"Psalms 16-19"},{"date":"2026-06-12","day":12,"month":6,"reading":"Psalms 20-23"},{"date":"2026-06-13","day":13,"month":6,"reading":"Psalms 24-27"},{"date":"2026-06-14","day":14,"month":6,"reading":"Psalms 28-31"},{"date":"2026-06-15","day":15,"month":6,"reading":"Psalms 32-35"},{"date":"2026-06-16","day":16,"month":6,"reading":"Psalms 36-39"},{"date":"2026-06-17","day":17,"month":6,"reading":"Psalms 40-43"},{"date":"2026-06-18","day":18,"month":6,"reading":"Psalms 44-47"},{"date":"2026-06-19","day":19,"month":6,"reading":"Psalms 48-51"},{"date":"2026-06-20","day":20,"month":6,"reading":"Psalms 52-55"},{"date":"2026-06-21","day":21,"month":6,"reading":"Psalms 56-59"},{"date":"2026-06-22","day":22,"month":6,"reading":"Psalms 60-63"},{"date":"2026-06-23","day":23,"month":6,"reading":"Psalms 64-67"},{"date":"2026-06-24","day":24,"month":6,"reading":"Psalms 68-71"},{"date":"2026-06-25","day":25,"month":6,"reading":"Psalms 72-75"},{"date":"2026-06-26","day":26,"month":6,"reading":"Psalms 76-79"},{"date":"2026-06-27","day":27,"month":6,"reading":"Psalms 80-83"},{"date":"2026-06-28","day":28,"month":6,"reading":"Psalms 84-87"},{"date":"2026-06-29","day":29,"month":6,"reading":"Psalms 88-91"},{"date":"2026-06-30","day":30,"month":6,"reading":"Psalms 92-95"},{"date":"2026-07-01","day":1,"month":7,"reading":"Psalms 96-99"},{"date":"2026-07-02","day":2,"month":7,"reading":"Psalms 100-103"},{"date":"2026-07-03","day":3,"month":7,"reading":"Psalms 104-106"},{"date":"2026-07-04","day":4,"month":7,"reading":"Psalms 107-109"},{"date":"2026-07-05","day":5,"month":7,"reading":"Psalms 110-113"},{"date":"2026-07-06","day":6,"month":7,"reading":"Psalms 114-117"},{"date":"2026-07-07","day":7,"month":7,"reading":"Psalms 118-119"},{"date":"2026-07-08","day":8,"month":7,"reading":"Psalms 120-123"},{"date":"2026-07-09","day":9,"month":7,"reading":"Psalms 124-127"},{"date":"2026-07-10","day":10,"month":7,"reading":"Psalms 128-131"},{"date":"2026-07-11","day":11,"month":7,"reading":"Psalms 132-135"},{"date":"2026-07-12","day":12,"month":7,"reading":"Psalms 136-139"},{"date":"2026-07-13","day":13,"month":7,"reading":"Psalms 140-143"},{"date":"2026-07-14","day":14,"month":7,"reading":"Psalms 144-147"},{"date":"2026-07-15","day":15,"month":7,"reading":"Psalms 148-150; Proverbs 1"},{"date":"2026-07-16","day":16,"month":7,"reading":"Proverbs 2-5"},{"date":"2026-07-17","day":17,"month":7,"reading":"Proverbs 6-9"},{"date":"2026-07-18","day":18,"month":7,"reading":"Proverbs 10-13"},{"date":"2026-07-19","day":19,"month":7,"reading":"Proverbs 14-17"},{"date":"2026-07-20","day":20,"month":7,"reading":"Proverbs 18-21"},{"date":"2026-07-21","day":21,"month":7,"reading":"Proverbs 22-25"},{"date":"2026-07-22","day":22,"month":7,"reading":"Proverbs 26-29"},{"date":"2026-07-23","day":23,"month":7,"reading":"Proverbs 30-31; Ecclesiastes 1"},{"date":"2026-07-24","day":24,"month":7,"reading":"Ecclesiastes 2-5"},{"date":"2026-07-25","day":25,"month":7,"reading":"Ecclesiastes 6-9"},{"date":"2026-07-26","day":26,"month":7,"reading":"Ecclesiastes 10-12; Song of Solomon 1"},{"date":"2026-07-27","day":27,"month":7,"reading":"Song of Solomon 2-5"},{"date":"2026-07-28","day":28,"month":7,"reading":"Song of Solomon 6-8; Isaiah 1"},{"date":"2026-07-29","day":29,"month":7,"reading":"Isaiah 2-5"},{"date":"2026-07-30","day":30,"month":7,"reading":"Isaiah 6-9"},{"date":"2026-07-31","day":31,"month":7,"reading":"Isaiah 10-13"},{"date":"2026-08-01","day":1,"month":8,"reading":"Isaiah 14-17"},{"date":"2026-08-02","day":2,"month":8,"reading":"Isaiah 18-21"},{"date":"2026-08-03","day":3,"month":8,"reading":"Isaiah 22-25"},{"date":"2026-08-04","day":4,"month":8,"reading":"Isaiah 26-29"},{"date":"2026-08-05","day":5,"month":8,"reading":"Isaiah 30-33"},{"date":"2026-08-06","day":6,"month":8,"reading":"Isaiah 34-37"},{"date":"2026-08-07","day":7,"month":8,"reading":"Isaiah 38-41"},{"date":"2026-08-08","day":8,"month":8,"reading":"Isaiah 42-45"},{"date":"2026-08-09","day":9,"month":8,"reading":"Isaiah 46-49"},{"date":"2026-08-10","day":10,"month":8,"reading":"Isaiah 50-53"},{"date":"2026-08-11","day":11,"month":8,"reading":"Isaiah 54-57"},{"date":"2026-08-12","day":12,"month":8,"reading":"Isaiah 58-61"},{"date":"2026-08-13","day":13,"month":8,"reading":"Isaiah 62-66"},{"date":"2026-08-14","day":14,"month":8,"reading":"Jeremiah 1-3"},{"date":"2026-08-15","day":15,"month":8,"reading":"Jeremiah 4-7"},{"date":"2026-08-16","day":16,"month":8,"reading":"Jeremiah 8-11"},{"date":"2026-08-17","day":17,"month":8,"reading":"Jeremiah 12-15"},{"date":"2026-08-18","day":18,"month":8,"reading":"Jeremiah 16-19"},{"date":"2026-08-19","day":19,"month":8,"reading":"Jeremiah 20-23"},{"date":"2026-08-20","day":20,"month":8,"reading":"Jeremiah 24-27"},{"date":"2026-08-21","day":21,"month":8,"reading":"Jeremiah 28-31"},{"date":"2026-08-22","day":22,"month":8,"reading":"Jeremiah 32-35"},{"date":"2026-08-23","day":23,"month":8,"reading":"Jeremiah 36-39"},{"date":"2026-08-24","day":24,"month":8,"reading":"Jeremiah 40-43"},{"date":"2026-08-25","day":25,"month":8,"reading":"Jeremiah 44-47"},{"date":"2026-08-26","day":26,"month":8,"reading":"Jeremiah 48-51"},{"date":"2026-08-27","day":27,"month":8,"reading":"Jeremiah 52; Lamentations 1-2"},{"date":"2026-08-28","day":28,"month":8,"reading":"Lamentations 3-5"},{"date":"2026-08-29","day":29,"month":8,"reading":"Ezekiel 1-4"},{"date":"2026-08-30","day":30,"month":8,"reading":"Ezekiel 5-8"},{"date":"2026-08-31","day":31,"month":8,"reading":"Ezekiel 9-12"},{"date":"2026-09-01","day":1,"month":9,"reading":"Ezekiel 13-16"},{"date":"2026-09-02","day":2,"month":9,"reading":"Ezekiel 17-20"},{"date":"2026-09-03","day":3,"month":9,"reading":"Ezekiel 21-24"},{"date":"2026-09-04","day":4,"month":9,"reading":"Ezekiel 25-28"},{"date":"2026-09-05","day":5,"month":9,"reading":"Ezekiel 29-32"},{"date":"2026-09-06","day":6,"month":9,"reading":"Ezekiel 33-36"},{"date":"2026-09-07","day":7,"month":9,"reading":"Ezekiel 37-40"},{"date":"2026-09-08","day":8,"month":9,"reading":"Ezekiel 41-44"},{"date":"2026-09-09","day":9,"month":9,"reading":"Ezekiel 45-48"},{"date":"2026-09-10","day":10,"month":9,"reading":"Daniel 1-4"},{"date":"2026-09-11","day":11,"month":9,"reading":"Daniel 5-8"},{"date":"2026-09-12","day":12,"month":9,"reading":"Daniel 9-12"},{"date":"2026-09-13","day":13,"month":9,"reading":"Hosea 1-4"},{"date":"2026-09-14","day":14,"month":9,"reading":"Hosea 5-8"},{"date":"2026-09-15","day":15,"month":9,"reading":"Hosea 9-11"},{"date":"2026-09-16","day":16,"month":9,"reading":"Hosea 12-14; Joel 1"},{"date":"2026-09-17","day":17,"month":9,"reading":"Joel 2-3; Amos 1-2"},{"date":"2026-09-18","day":18,"month":9,"reading":"Amos 3-6"},{"date":"2026-09-19","day":19,"month":9,"reading":"Amos 7-9; Obadiah 1"},{"date":"2026-09-20","day":20,"month":9,"reading":"Jonah 1-4"},{"date":"2026-09-21","day":21,"month":9,"reading":"Micah 1-4"},{"date":"2026-09-22","day":22,"month":9,"reading":"Micah 5-7; Nahum 1"},{"date":"2026-09-23","day":23,"month":9,"reading":"Nahum 2-3; Habakkuk 1-2"},{"date":"2026-09-24","day":24,"month":9,"reading":"Habakkuk 3; Zephaniah 1-3"},{"date":"2026-09-25","day":25,"month":9,"reading":"Haggai 1-2; Zechariah 1-2"},{"date":"2026-09-26","day":26,"month":9,"reading":"Zechariah 3-6"},{"date":"2026-09-27","day":27,"month":9,"reading":"Zechariah 7-10"},{"date":"2026-09-28","day":28,"month":9,"reading":"Zechariah 11-14"},{"date":"2026-09-29","day":29,"month":9,"reading":"Malachi 1-4"},{"date":"2026-09-30","day":30,"month":9,"reading":"Matthew 1-4"},{"date":"2026-10-01","day":1,"month":10,"reading":"Matthew 5-7"},{"date":"2026-10-02","day":2,"month":10,"reading":"Matthew 8-11"},{"date":"2026-10-03","day":3,"month":10,"reading":"Matthew 12-15"},{"date":"2026-10-04","day":4,"month":10,"reading":"Matthew 16-19"},{"date":"2026-10-05","day":5,"month":10,"reading":"Matthew 20-23"},{"date":"2026-10-06","day":6,"month":10,"reading":"Matthew 24-26"},{"date":"2026-10-07","day":7,"month":10,"reading":"Matthew 27-28; Mark 1"},{"date":"2026-10-08","day":8,"month":10,"reading":"Mark 2-5"},{"date":"2026-10-09","day":9,"month":10,"reading":"Mark 6-9"},{"date":"2026-10-10","day":10,"month":10,"reading":"Mark 10-13"},{"date":"2026-10-11","day":11,"month":10,"reading":"Mark 14-16"},{"date":"2026-10-12","day":12,"month":10,"reading":"Luke 1-3"},{"date":"2026-10-13","day":13,"month":10,"reading":"Luke 4-6"},{"date":"2026-10-14","day":14,"month":10,"reading":"Luke 7-10"},{"date":"2026-10-15","day":15,"month":10,"reading":"Luke 11-14"},{"date":"2026-10-16","day":16,"month":10,"reading":"Luke 15-18"},{"date":"2026-10-17","day":17,"month":10,"reading":"Luke 19-22"},{"date":"2026-10-18","day":18,"month":10,"reading":"Luke 23-24; John 1"},{"date":"2026-10-19","day":19,"month":10,"reading":"John 2-5"},{"date":"2026-10-20","day":20,"month":10,"reading":"John 6-9"},{"date":"2026-10-21","day":21,"month":10,"reading":"John 10-13"},{"date":"2026-10-22","day":22,"month":10,"reading":"John 14-17"},{"date":"2026-10-23","day":23,"month":10,"reading":"John 18-21"},{"date":"2026-10-24","day":24,"month":10,"reading":"Acts 1-4"},{"date":"2026-10-25","day":25,"month":10,"reading":"Acts 5-8"},{"date":"2026-10-26","day":26,"month":10,"reading":"Acts 9-12"},{"date":"2026-10-27","day":27,"month":10,"reading":"Acts 13-16"},{"date":"2026-10-28","day":28,"month":10,"reading":"Acts 17-20"},{"date":"2026-10-29","day":29,"month":10,"reading":"Acts 21-24"},{"date":"2026-10-30","day":30,"month":10,"reading":"Acts 25-28"},{"date":"2026-10-31","day":31,"month":10,"reading":"Romans 1-4"},{"date":"2026-11-01","day":1,"month":11,"reading":"Romans 5-8"},{"date":"2026-11-02","day":2,"month":11,"reading":"Romans 9-12"},{"date":"2026-11-03","day":3,"month":11,"reading":"Romans 13-16"},{"date":"2026-11-04","day":4,"month":11,"reading":"1 Corinthians 1-4"},{"date":"2026-11-05","day":5,"month":11,"reading":"1 Corinthians 5-8"},{"date":"2026-11-06","day":6,"month":11,"reading":"1 Corinthians 9-12"},{"date":"2026-11-07","day":7,"month":11,"reading":"1 Corinthians 13-16"},{"date":"2026-11-08","day":8,"month":11,"reading":"2 Corinthians 1-4"},{"date":"2026-11-09","day":9,"month":11,"reading":"2 Corinthians 5-9"},{"date":"2026-11-10","day":10,"month":11,"reading":"2 Corinthians 10-13"},{"date":"2026-11-11","day":11,"month":11,"reading":"Galatians 1-3"},{"date":"2026-11-12","day":12,"month":11,"reading":"Galatians 4-6; Ephesians 1"},{"date":"2026-11-13","day":13,"month":11,"reading":"Ephesians 2-5"},{"date":"2026-11-14","day":14,"month":11,"reading":"Ephesians 6; Philippians 1-3"},{"date":"2026-11-15","day":15,"month":11,"reading":"Philippians 4; Colossians 1-3"},{"date":"2026-11-16","day":16,"month":11,"reading":"Colossians 4; 1 Thessalonians 1-4"},{"date":"2026-11-17","day":17,"month":11,"reading":"1 Thessalonians 5; 2 Thessalonians 1-3"},{"date":"2026-11-18","day":18,"month":11,"reading":"1 Timothy 1-4"},{"date":"2026-11-19","day":19,"month":11,"reading":"1 Timothy 5-6; 2 Timothy 1-2"},{"date":"2026-11-20","day":20,"month":11,"reading":"2 Timothy 3-4; Titus 1-3"},{"date":"2026-11-21","day":21,"month":11,"reading":"Philemon 1; Hebrews 1-4"},{"date":"2026-11-22","day":22,"month":11,"reading":"Hebrews 5-9"},{"date":"2026-11-23","day":23,"month":11,"reading":"Hebrews 10-13"},{"date":"2026-11-24","day":24,"month":11,"reading":"James 1-5"},{"date":"2026-11-25","day":25,"month":11,"reading":"1 Peter 1-4"},{"date":"2026-11-26","day":26,"month":11,"reading":"1 Peter 5; 2 Peter 1-3"},{"date":"2026-11-27","day":27,"month":11,"reading":"1 John 1-5"},{"date":"2026-11-28","day":28,"month":11,"reading":"2 John 1; 3 John 1; Jude 1"},{"date":"2026-11-29","day":29,"month":11,"reading":"Revelation 1-4"},{"date":"2026-11-30","day":30,"month":11,"reading":"Revelation 5-8"},{"date":"2026-12-01","day":1,"month":12,"reading":"Revelation 9-12"},{"date":"2026-12-02","day":2,"month":12,"reading":"Revelation 13-16"},{"date":"2026-12-03","day":3,"month":12,"reading":"Revelation 17-18"},{"date":"2026-12-04","day":4,"month":12,"reading":"Revelation 19-22"}];
        
        let currentMonth = 2;
        let selectedDay = null;
        let checkIns = JSON.parse(localStorage.getItem('bibleCheckIns')) || {};
        let partner1Name = localStorage.getItem('partner1Name') || '';
        let partner2Name = localStorage.getItem('partner2Name') || '';
        
        document.getElementById('partner1Name').value = partner1Name;
        document.getElementById('partner2Name').value = partner2Name;
        
        document.getElementById('partner1Name').addEventListener('change', (e) => {
            partner1Name = e.target.value;
            localStorage.setItem('partner1Name', partner1Name);
            updateButtonLabels();
        });
        
        document.getElementById('partner2Name').addEventListener('change', (e) => {
            partner2Name = e.target.value;
            localStorage.setItem('partner2Name', partner2Name);
            updateButtonLabels();
        });
        
        function updateButtonLabels() {
            document.getElementById('partner1BtnText').textContent = partner1Name ? `✓ ${partner1Name}` : '✓ Partner 1';
            document.getElementById('partner2BtnText').textContent = partner2Name ? `✓ ${partner2Name}` : '✓ Partner 2';
        }
        
        function renderCalendar() {
            const calendar = document.getElementById('calendar');
            calendar.innerHTML = '';
            
            const monthNames = ['', 'January', 'February', 'March', 'April', 'May', 'June', 
                              'July', 'August', 'September', 'October', 'November', 'December'];
            document.getElementById('monthTitle').textContent = `${monthNames[currentMonth]} 2026`;
            
            const days = ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];
            days.forEach(day => {
                const header = document.createElement('div');
                header.className = 'day-header';
                header.textContent = day;
                calendar.appendChild(header);
            });
            
            const firstDay = new Date(2026, currentMonth - 1, 1).getDay();
            const daysInMonth = new Date(2026, currentMonth, 0).getDate();
            
            for (let i = 0; i < firstDay; i++) {
                const emptyCell = document.createElement('div');
                emptyCell.className = 'day-cell empty';
                calendar.appendChild(emptyCell);
            }
            
            const monthReadings = {};
            readingPlan.forEach(entry => {
                if (entry.month === currentMonth) {
                    monthReadings[entry.day] = entry.reading;
                }
            });
            
            const today = new Date();
            for (let day = 1; day <= daysInMonth; day++) {
                const cell = document.createElement('div');
                cell.className = 'day-cell';
                
                const currentDate = new Date(2026, currentMonth - 1, day);
                const dateKey = `2026-${String(currentMonth).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
                
                if (currentDate.toDateString() === today.toDateString()) {
                    cell.classList.add('today');
                }
                
                if (currentDate < today) {
                    cell.classList.add('past');
                }
                
                const checks = checkIns[dateKey] || {};
                if (checks.partner1 && checks.partner2) {
                    cell.classList.add('both-checked');
                } else if (checks.partner1) {
                    cell.classList.add('partner1-checked');
                } else if (checks.partner2) {
                    cell.classList.add('partner2-checked');
                }
                
                const dayNumber = document.createElement('div');
                dayNumber.className = 'day-number';
                dayNumber.textContent = day;
                cell.appendChild(dayNumber);
                
                if (monthReadings[day]) {
                    const reading = document.createElement('div');
                    reading.className = 'reading-text';
                    reading.textContent = monthReadings[day];
                    cell.appendChild(reading);
                    
                    const indicators = document.createElement('div');
                    indicators.className = 'check-indicators';
                    
                    const dot1 = document.createElement('div');
                    dot1.className = 'check-dot' + (checks.partner1 ? ' checked-partner1' : '');
                    indicators.appendChild(dot1);
                    
                    const dot2 = document.createElement('div');
                    dot2.className = 'check-dot' + (checks.partner2 ? ' checked-partner2' : '');
                    indicators.appendChild(dot2);
                    
                    cell.appendChild(indicators);
                    
                    cell.onclick = () => openModal(dateKey, monthReadings[day], day);
                }
                
                calendar.appendChild(cell);
            }
            
            updateStats();
        }
        
        function openModal(dateKey, reading, day) {
            selectedDay = dateKey;
            const modal = document.getElementById('dayModal');
            document.getElementById('modalDate').textContent = `${new Date(dateKey).toLocaleDateString('en-US', {weekday: 'long', month: 'long', day: 'numeric', year: 'numeric'})}`;
            document.getElementById('modalReading').textContent = reading;
            
            const checks = checkIns[dateKey] || {};
            
            const btn1 = document.getElementById('checkPartner1');
            const btn2 = document.getElementById('checkPartner2');
            
            btn1.classList.toggle('active', checks.partner1);
            btn2.classList.toggle('active', checks.partner2);
            
            updateButtonLabels();
            
            modal.classList.add('active');
        }
        
        function closeModal() {
            document.getElementById('dayModal').classList.remove('active');
        }
        
        document.getElementById('checkPartner1').onclick = function() {
            if (!selectedDay) return;
            if (!checkIns[selectedDay]) checkIns[selectedDay] = {};
            checkIns[selectedDay].partner1 = !checkIns[selectedDay].partner1;
            this.classList.toggle('active');
            saveCheckIns();
            renderCalendar();
        };
        
        document.getElementById('checkPartner2').onclick = function() {
            if (!selectedDay) return;
            if (!checkIns[selectedDay]) checkIns[selectedDay] = {};
            checkIns[selectedDay].partner2 = !checkIns[selectedDay].partner2;
            this.classList.toggle('active');
            saveCheckIns();
            renderCalendar();
        };
        
        function saveCheckIns() {
            localStorage.setItem('bibleCheckIns', JSON.stringify(checkIns));
        }
        
        function updateStats() {
            let totalDays = 0;
            let currentStreak = 0;
            let longestStreak = 0;
            let tempStreak = 0;
            let totalChapters = 0;
            
            const sortedDates = Object.keys(checkIns).sort();
            const today = new Date().toISOString().split('T')[0];
            
            sortedDates.forEach(date => {
                const checks = checkIns[date];
                if (checks.partner1 && checks.partner2) {
                    totalDays++;
                    tempStreak++;
                    
                    const entry = readingPlan.find(e => e.date === date);
                    if (entry) {
                        const matches = entry.reading.match(/(\d+)-(\d+)|(\d+)/g);
                        if (matches) {
                            matches.forEach(match => {
                                if (match.includes('-')) {
                                    const [start, end] = match.split('-').map(Number);
                                    totalChapters += (end - start + 1);
                                } else {
                                    totalChapters += 1;
                                }
                            });
                        }
                    }
                    
                    if (tempStreak > longestStreak) {
                        longestStreak = tempStreak;
                    }
                } else {
                    tempStreak = 0;
                }
            });
            
            let checkDate = new Date(today);
            while (true) {
                const dateKey = checkDate.toISOString().split('T')[0];
                const checks = checkIns[dateKey];
                if (checks && checks.partner1 && checks.partner2) {
                    currentStreak++;
                    checkDate.setDate(checkDate.getDate() - 1);
                } else {
                    break;
                }
            }
            
            document.getElementById('currentStreak').textContent = currentStreak;
            document.getElementById('longestStreak').textContent = longestStreak;
            document.getElementById('totalDays').textContent = totalDays;
            document.getElementById('chaptersRead').textContent = totalChapters;
        }
        
        function previousMonth() {
            if (currentMonth > 2) {
                currentMonth--;
                renderCalendar();
            }
        }
        
        function nextMonth() {
            if (currentMonth < 12) {
                currentMonth++;
                renderCalendar();
            }
        }
        
        renderCalendar();
        
        document.getElementById('dayModal').onclick = function(e) {
            if (e.target === this) {
                closeModal();
            }
        };
    </script>
</body>
</html>
