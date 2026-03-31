<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Instrução Militar - FAL 7.62mm | Plataforma de Treinamento</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #d4af37;
            --secondary-color: #8b6b2a;
            --accent-color: #4a6a2a;
            --danger-color: #8b3a3a;
            --success-color: #4caf50;
            --warning-color: #ff9800;
            --bg-primary: #1a2a1a;
            --bg-secondary: #2a3a2a;
            --bg-tertiary: #0f2a0f;
            --text-primary: #ffffff;
            --text-secondary: #d4c9a6;
            --text-muted: #9aa88a;
            --border-color: rgba(212, 175, 55, 0.3);
            --glass-bg: rgba(26, 42, 26, 0.7);
            --error-color: #ff4757;
        }

        [data-theme="light"] {
            --bg-primary: #f5f0e6;
            --bg-secondary: #e8e0d0;
            --bg-tertiary: #fff8e8;
            --text-primary: #2d2a1a;
            --text-secondary: #5a4a2a;
            --text-muted: #8b7a5a;
            --glass-bg: rgba(245, 240, 230, 0.8);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Arial', sans-serif;
            color: var(--text-primary);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            background: linear-gradient(135deg, var(--bg-primary) 0%, var(--bg-secondary) 50%, var(--bg-tertiary) 100%);
            position: relative;
            overflow-x: hidden;
            transition: all 0.3s ease;
        }

        .tech-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 80%, rgba(212, 175, 55, 0.08) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(139, 107, 42, 0.08) 0%, transparent 50%);
            z-index: -1;
            pointer-events: none;
        }

        .grid-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: linear-gradient(rgba(212, 175, 55, 0.1) 1px, transparent 1px),
                              linear-gradient(90deg, rgba(212, 175, 55, 0.1) 1px, transparent 1px);
            background-size: 40px 40px;
            z-index: -1;
            opacity: 0.3;
            pointer-events: none;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 40px;
            background: rgba(26, 42, 26, 0.9);
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(15px);
            border-bottom: 2px solid var(--primary-color);
            flex-wrap: wrap;
            gap: 15px;
        }

        [data-theme="light"] header {
            background: rgba(245, 240, 230, 0.95);
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            text-decoration: none;
            font-family: 'Courier New', monospace;
            color: var(--primary-color);
        }

        @supports (background-clip: text) or (-webkit-background-clip: text) {
            .logo {
                background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
            }
            
            .logo span {
                background: linear-gradient(135deg, #ffd700, #b8860b);
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
            }
        }

        header nav {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        header nav a {
            color: var(--text-secondary);
            text-decoration: none;
            text-transform: uppercase;
            font-weight: 600;
            font-size: 12px;
            padding: 8px 12px;
            border-radius: 8px;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        header nav a:hover,
        header nav a.active {
            background: rgba(212, 175, 55, 0.2);
            border-color: var(--primary-color);
            transform: translateY(-2px);
            color: var(--primary-color);
        }

        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .login-btn {
            padding: 8px 20px;
            border: 2px solid var(--primary-color);
            background: transparent;
            color: var(--primary-color);
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .login-btn:hover {
            background: rgba(212, 175, 55, 0.2);
            transform: translateY(-2px);
        }

        .theme-toggle {
            background: var(--glass-bg);
            border: 1px solid var(--border-color);
            color: var(--text-primary);
            padding: 8px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 36px;
            height: 36px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .main-content {
            flex: 1;
            padding: 20px;
            max-width: 1400px;
            margin: 0 auto;
            width: 100%;
        }

        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero-section {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, rgba(0,0,0,0.5), rgba(0,0,0,0.3));
            border-radius: 30px;
            margin-bottom: 40px;
        }

        .hero-section h1 {
            font-size: clamp(3rem, 10vw, 5rem);
            margin: 0;
            font-weight: 800;
            letter-spacing: 3px;
            background: linear-gradient(135deg, var(--primary-color), #ffd700, var(--secondary-color));
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero-section p {
            max-width: 600px;
            margin: 20px auto;
            font-size: 18px;
            line-height: 1.6;
            color: var(--text-secondary);
        }

        .hero-subtitle {
            font-size: 14px !important;
            color: var(--text-muted) !important;
        }

        .hero-section button {
            margin-top: 30px;
            padding: 15px 40px;
            border: 2px solid var(--primary-color);
            background: transparent;
            color: var(--primary-color);
            cursor: pointer;
            font-size: 16px;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            border-radius: 30px;
        }

        .hero-section button:hover {
            background: rgba(212, 175, 55, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(212, 175, 55, 0.3);
        }

        .stats-section {
            margin: 40px 0;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .stat-item {
            text-align: center;
            padding: 25px;
            background: var(--glass-bg);
            border-radius: 15px;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(10px);
        }

        .stat-item h3 {
            font-size: 2rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            margin-bottom: 10px;
        }

        .stat-item p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .quick-access {
            margin-top: 40px;
            text-align: center;
        }

        .quick-access h3 {
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .quick-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        .quick-card {
            background: var(--glass-bg);
            padding: 25px;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
        }

        .quick-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
            background: rgba(212, 175, 55, 0.1);
        }

        .quick-card i {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 10px;
            display: block;
        }

        .quick-card span {
            color: var(--text-primary);
            font-weight: 600;
        }

        .tab-header {
            text-align: center;
            margin-bottom: 40px;
            padding: 20px;
        }

        .tab-header h2 {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            font-size: 2rem;
            margin-bottom: 10px;
        }

        .tab-header p {
            color: var(--text-secondary);
        }

        .specs-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .specs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .spec-card {
            background: var(--glass-bg);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }

        .spec-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
        }

        .spec-card i {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .spec-card h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        .spec-card p {
            color: var(--text-secondary);
            font-size: 1.1rem;
            font-weight: bold;
        }

        .disassembly-container, .assembly-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .simulator-area {
            display: grid;
            grid-template-columns: 1fr 280px;
            gap: 30px;
            margin-bottom: 30px;
        }

        @media (max-width: 768px) {
            .simulator-area {
                grid-template-columns: 1fr;
            }
        }

        .weapon-schema {
            background: var(--glass-bg);
            border-radius: 20px;
            padding: 40px;
            min-height: 400px;
            border: 2px solid var(--border-color);
            display: flex;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .weapon-part {
            background: rgba(212, 175, 55, 0.15);
            border: 2px solid var(--primary-color);
            border-radius: 12px;
            padding: 15px 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            min-width: 120px;
        }

        .weapon-part:hover {
            background: rgba(212, 175, 55, 0.3);
            transform: scale(1.05);
        }

        .weapon-part.completed {
            background: var(--success-color);
            border-color: var(--success-color);
            opacity: 0.7;
            cursor: default;
            transform: none;
        }

        .weapon-part.completed i,
        .weapon-part.completed span {
            color: white;
        }

        .weapon-part i {
            font-size: 1.5rem;
            color: var(--primary-color);
            display: block;
            margin-bottom: 8px;
        }

        .weapon-part span {
            font-size: 0.8rem;
            font-weight: 600;
        }

        .sequence-panel {
            background: var(--glass-bg);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid var(--border-color);
        }

        .sequence-panel h3 {
            color: var(--primary-color);
            margin-bottom: 15px;
            font-size: 1rem;
            text-align: center;
        }

        .sequence-list {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .sequence-item {
            padding: 8px 12px;
            background: rgba(0,0,0,0.3);
            border-radius: 8px;
            font-size: 0.85rem;
            border-left: 3px solid var(--primary-color);
        }

        .sequence-item.completed {
            background: rgba(76, 175, 80, 0.3);
            border-left-color: var(--success-color);
        }

        .progress-area {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .progress-bar-container {
            flex: 1;
            background: rgba(0,0,0,0.3);
            border-radius: 10px;
            padding: 10px;
        }

        .progress-label {
            font-size: 0.8rem;
            margin-bottom: 5px;
            color: var(--text-secondary);
        }

        .progress-bar {
            background: rgba(255,255,255,0.2);
            border-radius: 10px;
            height: 10px;
            overflow: hidden;
        }

        .progress-fill {
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            height: 100%;
            transition: width 0.3s ease;
            width: 0%;
        }

        .action-btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .reset-btn {
            background: var(--warning-color);
            color: #1a2a1a;
        }

        .check-btn {
            background: var(--success-color);
            color: white;
        }

        .feedback-area {
            background: var(--glass-bg);
            border-radius: 10px;
            padding: 15px;
            margin-top: 20px;
        }

        .feedback-message {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-secondary);
        }

        .feedback-message.success { color: var(--success-color); }
        .feedback-message.error { color: var(--error-color); }
        .feedback-message.warning { color: var(--warning-color); }

        .shooting-simulator {
            display: grid;
            grid-template-columns: 1fr 350px;
            gap: 30px;
        }

        @media (max-width: 768px) {
            .shooting-simulator {
                grid-template-columns: 1fr;
            }
        }

        .target-area {
            background: var(--glass-bg);
            border-radius: 20px;
            padding: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            min-height: 500px;
            border: 2px solid var(--border-color);
        }

        .target {
            position: relative;
            width: 300px;
            height: 300px;
            cursor: crosshair;
            transition: transform 0.1s ease;
        }

        .target:active { transform: scale(0.98); }

        .target-ring {
            position: absolute;
            border-radius: 50%;
            border: 3px solid;
        }

        .ring-10 {
            width: 60px;
            height: 60px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-color: #ffd700;
            background: radial-gradient(circle, #ffd700, #b8860b);
        }
        .ring-9 { width: 100px; height: 100px; top: 50%; left: 50%; transform: translate(-50%, -50%); border-color: #ffaa00; }
        .ring-8 { width: 140px; height: 140px; top: 50%; left: 50%; transform: translate(-50%, -50%); border-color: #ff7700; }
        .ring-7 { width: 180px; height: 180px; top: 50%; left: 50%; transform: translate(-50%, -50%); border-color: #ff4400; }
        .target-center {
            position: absolute;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 10;
        }

        .hit-marker {
            position: absolute;
            font-size: 2rem;
            pointer-events: none;
            animation: hitPulse 0.3s ease;
            transform: translate(-50%, -50%);
        }

        @keyframes hitPulse {
            0% { transform: scale(0.5); opacity: 1; }
            100% { transform: scale(1.5); opacity: 0; }
        }

        .shooting-controls {
            background: var(--glass-bg);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid var(--border-color);
        }

        .weapon-status {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 25px;
        }

        .status-item {
            background: rgba(0,0,0,0.3);
            padding: 12px;
            border-radius: 10px;
            text-align: center;
        }

        .status-item i { color: var(--primary-color); margin-right: 8px; }
        .status-item strong { color: var(--primary-color); font-size: 1.2rem; }

        .breathing-exercise {
            text-align: center;
            margin-bottom: 25px;
            padding: 15px;
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
        }

        .breathing-exercise h4 { color: var(--primary-color); margin-bottom: 15px; }

        .breathing-circle {
            width: 80px;
            height: 80px;
            background: rgba(212, 175, 55, 0.3);
            border-radius: 50%;
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.1s linear;
            border: 2px solid var(--primary-color);
            cursor: pointer;
        }

        .breathing-circle.inhale { transform: scale(1.3); background: rgba(76, 175, 80, 0.3); }
        .breathing-circle.exhale { transform: scale(0.8); background: rgba(255, 71, 87, 0.3); }

        .shooting-buttons {
            display: flex;
            gap: 15px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }

        .shoot-btn, .reload-btn, .reset-shooting-btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .shoot-btn { background: var(--danger-color); color: white; }
        .shoot-btn:disabled { opacity: 0.5; cursor: not-allowed; }
        .reload-btn { background: var(--primary-color); color: #1a2a1a; }
        .reset-shooting-btn { background: var(--warning-color); color: #1a2a1a; }

        .shooting-tips ul {
            list-style: none;
            padding-left: 0;
        }

        .shooting-tips li {
            padding: 8px 0;
            color: var(--text-secondary);
            font-size: 0.85rem;
            border-bottom: 1px solid var(--border-color);
        }

        .shooting-tips li::before {
            content: "•";
            color: var(--primary-color);
            font-weight: bold;
            margin-right: 10px;
        }

        .shooting-history {
            grid-column: 1 / -1;
            background: var(--glass-bg);
            border-radius: 20px;
            padding: 20px;
            margin-top: 20px;
        }

        .history-list {
            max-height: 150px;
            overflow-y: auto;
        }

        .history-empty {
            text-align: center;
            color: var(--text-muted);
            padding: 20px;
        }

        .history-item {
            display: flex;
            justify-content: space-between;
            padding: 8px;
            border-bottom: 1px solid var(--border-color);
            font-size: 0.85rem;
        }

        .history-item .score-10 { color: #ffd700; font-weight: bold; }
        .history-item .score-9 { color: #ffaa00; }
        .history-item .score-8 { color: #ff7700; }
        .history-item .score-7 { color: #ff4400; }
        .history-item .miss { color: var(--error-color); }

        .safety-container { max-width: 1000px; margin: 0 auto; }

        .safety-rules-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .rule-card {
            background: var(--glass-bg);
            padding: 25px;
            border-radius: 15px;
            border-left: 5px solid;
            position: relative;
            transition: all 0.3s ease;
        }

        .rule-card:hover { transform: translateY(-5px); }
        .rule-1 { border-left-color: #ff4757; }
        .rule-2 { border-left-color: #ffa502; }
        .rule-3 { border-left-color: #ff6348; }
        .rule-4 { border-left-color: #2ed573; }
        .rule-5 { border-left-color: #1e90ff; }
        .rule-6 { border-left-color: #ff6b81; }

        .rule-number {
            position: absolute;
            top: -10px;
            left: 20px;
            background: var(--primary-color);
            color: #1a2a1a;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .rule-card h3 {
            margin: 15px 0 10px;
            color: var(--primary-color);
            font-size: 1.1rem;
        }

        .rule-card p {
            color: var(--text-secondary);
            line-height: 1.5;
            font-size: 0.9rem;
        }

        .quiz-container {
            max-width: 800px;
            margin: 0 auto;
            background: var(--glass-bg);
            border-radius: 20px;
            padding: 30px;
        }

        .quiz-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--border-color);
            flex-wrap: wrap;
            gap: 15px;
        }

        .quiz-info {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .quiz-info span {
            color: var(--text-secondary);
            font-size: 0.85rem;
        }

        .quiz-info i {
            color: var(--primary-color);
            margin-right: 5px;
        }

        .quiz-timer {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
            font-family: monospace;
        }

        .quiz-questions { margin-bottom: 30px; }
        .quiz-question {
            margin-bottom: 25px;
            padding: 20px;
            background: rgba(0,0,0,0.2);
            border-radius: 12px;
        }

        .question-text {
            font-weight: bold;
            margin-bottom: 15px;
            color: var(--text-primary);
        }

        .question-options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .quiz-option {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px;
            background: rgba(255,255,255,0.05);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .quiz-option:hover { background: rgba(212, 175, 55, 0.2); }
        .quiz-option input { cursor: pointer; }
        .quiz-option.correct { background: rgba(76, 175, 80, 0.3); border: 1px solid var(--success-color); }
        .quiz-option.wrong { background: rgba(255, 71, 87, 0.3); border: 1px solid var(--error-color); }

        .quiz-actions {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .submit-quiz-btn { background: var(--success-color); color: white; }
        .reset-quiz-btn { background: var(--warning-color); color: #1a2a1a; }

        .quiz-result { margin-top: 30px; }
        .result-card {
            text-align: center;
            padding: 30px;
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
        }

        .result-card i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .result-card h3 { color: var(--primary-color); margin-bottom: 10px; }
        .result-score { margin: 20px 0; }
        .result-score strong { font-size: 2rem; color: var(--primary-color); }
        .certificate-btn { background: var(--primary-color); color: #1a2a1a; }

        .ranking-container { max-width: 800px; margin: 0 auto; }
        .ranking-filters {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .filter-btn {
            padding: 8px 20px;
            background: var(--glass-bg);
            border: 1px solid var(--border-color);
            color: var(--text-secondary);
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .filter-btn.active,
        .filter-btn:hover {
            background: rgba(212, 175, 55, 0.2);
            color: var(--primary-color);
            border-color: var(--primary-color);
        }

        .ranking-list {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 30px;
        }

        .ranking-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            background: var(--glass-bg);
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .ranking-item:hover { transform: translateX(5px); }
        .rank {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--primary-color);
            min-width: 50px;
        }

        .user-avatar { font-size: 1.5rem; }
        .user-info { flex: 1; }
        .user-info strong { display: block; margin-bottom: 5px; }
        .user-info span { color: var(--text-secondary); font-size: 0.85rem; }
        .user-score strong { color: var(--primary-color); }
        .ranking-empty { text-align: center; padding: 40px; color: var(--text-secondary); }

        .user-position {
            background: var(--glass-bg);
            padding: 20px;
            border-radius: 15px;
            border: 2px solid var(--primary-color);
        }

        .position-card { display: flex; align-items: center; gap: 15px; }

        .profile-container { max-width: 1000px; margin: 0 auto; }
        .profile-header {
            background: var(--glass-bg);
            padding: 30px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            gap: 30px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        @media (max-width: 768px) {
            .profile-header { flex-direction: column; text-align: center; }
            .profile-stats { justify-content: center; }
        }

        .profile-avatar { position: relative; }
        .avatar-circle {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: #1a2a1a;
        }

        .edit-avatar-btn {
            position: absolute;
            bottom: 0;
            right: 0;
            background: var(--primary-color);
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .profile-info { flex: 1; }
        .profile-info h3 {
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-bottom: 5px;
        }

        .profile-badges {
            display: flex;
            gap: 10px;
            margin-top: 10px;
            flex-wrap: wrap;
        }

        .badge {
            background: rgba(212, 175, 55, 0.2);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            color: var(--primary-color);
        }

        .profile-stats {
            display: flex;
            gap: 30px;
            flex-wrap: wrap;
        }

        .stat { text-align: center; }
        .stat-number {
            display: block;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }
        .stat-label { font-size: 0.8rem; color: var(--text-secondary); }

        .profile-section {
            background: var(--glass-bg);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 20px;
        }

        .profile-section h3 {
            color: var(--primary-color);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .stat-card {
            background: rgba(0,0,0,0.2);
            padding: 15px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .stat-card i {
            font-size: 2rem;
            color: var(--primary-color);
        }

        .stat-info h4 {
            font-size: 1.2rem;
            color: var(--primary-color);
        }
        .stat-info p { font-size: 0.8rem; color: var(--text-secondary); }

        .certifications-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .cert-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 12px;
            background: rgba(0,0,0,0.2);
            border-radius: 10px;
        }

        .cert-item i {
            font-size: 1.5rem;
            color: var(--primary-color);
        }
        .cert-empty { text-align: center; padding: 20px; color: var(--text-secondary); }

        .settings-grid {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .setting-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background: rgba(0,0,0,0.2);
            border-radius: 10px;
            flex-wrap: wrap;
            gap: 15px;
        }

        .setting-info h4 { margin-bottom: 5px; }
        .setting-info p { font-size: 0.8rem; color: var(--text-secondary); }

        .switch {
            position: relative;
            display: inline-block;
            width: 50px;
            height: 24px;
        }

        .switch input { opacity: 0; width: 0; height: 0; }
        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider { background-color: var(--primary-color); }
        input:checked + .slider:before { transform: translateX(26px); }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: linear-gradient(135deg, var(--bg-secondary), var(--bg-tertiary));
            padding: 30px;
            border-radius: 20px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            border: 1px solid var(--primary-color);
            position: relative;
        }

        .modal-content.certificate-modal { max-width: 800px; }
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 24px;
            cursor: pointer;
            color: var(--primary-color);
            background: none;
            border: none;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .close-modal:hover { transform: scale(1.1); }
        .modal-title {
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .profile-options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 20px;
        }

        .profile-option {
            background: rgba(212, 175, 55, 0.1);
            padding: 20px;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
        }

        .profile-option:hover {
            background: rgba(212, 175, 55, 0.2);
            transform: translateY(-3px);
        }

        .profile-option i {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .profile-option h3 {
            color: var(--primary-color);
            margin-bottom: 5px;
        }
        .profile-option p { color: var(--text-secondary); font-size: 0.85rem; }

        .login-page {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .login-content {
            background: linear-gradient(135deg, var(--bg-secondary), var(--bg-tertiary));
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 400px;
            border: 1px solid var(--primary-color);
            position: relative;
        }

        .login-title {
            color: var(--primary-color);
            margin-bottom: 10px;
            font-size: 1.5rem;
        }
        .login-subtitle {
            color: var(--text-secondary);
            margin-bottom: 20px;
            font-size: 0.9rem;
        }

        .login-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .form-group { text-align: left; }
        .form-group label {
            display: block;
            margin-bottom: 5px;
            color: var(--primary-color);
            font-size: 0.9rem;
        }

        .form-group input {
            width: 100%;
            padding: 10px;
            background: rgba(255,255,255,0.1);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            color: var(--text-primary);
        }

        .form-group input:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        .login-button {
            background: var(--primary-color);
            color: #1a2a1a;
            padding: 12px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 10px;
            transition: all 0.3s ease;
        }

        .login-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.3);
        }

        .toggle-form, .back-button {
            background: none;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            margin-top: 15px;
            font-size: 0.85rem;
            transition: color 0.3s ease;
        }

        .toggle-form:hover, .back-button:hover { color: var(--primary-color); }
        .back-button { color: var(--primary-color); display: block; width: 100%; text-align: center; }

        footer {
            background: rgba(26, 42, 26, 0.9);
            padding: 20px;
            text-align: center;
            font-size: 0.8rem;
            color: var(--text-muted);
            border-top: 1px solid var(--primary-color);
            margin-top: 40px;
        }

        .footer-links {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 10px;
        }

        .footer-links a {
            color: var(--text-muted);
            transition: color 0.3s ease;
            font-size: 1.2rem;
        }
        .footer-links a:hover { color: var(--primary-color); }

        .custom-alert { animation: slideInRight 0.3s ease; }
        @keyframes slideInRight {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .user-menu {
            position: absolute;
            top: 70px;
            right: 20px;
            background: var(--bg-secondary);
            border: 1px solid var(--primary-color);
            border-radius: 10px;
            padding: 10px 0;
            min-width: 180px;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .user-menu-item {
            padding: 10px 20px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: background 0.3s ease;
            color: var(--text-primary);
        }
        .user-menu-item:hover { background: rgba(212, 175, 55, 0.2); }

        .glow { animation: glow 2s ease-in-out infinite alternate; }
        @keyframes glow {
            from { text-shadow: 0 0 10px rgba(212, 175, 55, 0.3); }
            to { text-shadow: 0 0 20px rgba(212, 175, 55, 0.5); }
        }

        .pulse { animation: pulse 2s infinite; }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        ::-webkit-scrollbar { width: 8px; height: 8px; }
        ::-webkit-scrollbar-track { background: var(--bg-secondary); border-radius: 4px; }
        ::-webkit-scrollbar-thumb { background: var(--primary-color); border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--secondary-color); }

        @media (max-width: 1024px) {
            .specs-grid { grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); }
        }

        @media (max-width: 768px) {
            header { flex-direction: column; padding: 15px; }
            header nav { justify-content: center; }
            .header-actions { display: none; }
            .hero-section { padding: 40px 20px; }
            .stats-container { grid-template-columns: 1fr 1fr; }
            .quiz-header { flex-direction: column; text-align: center; }
            .quiz-info { justify-content: center; }
            .weapon-schema { padding: 20px; }
            .weapon-part { min-width: 100px; padding: 10px 15px; }
        }

        @media (max-width: 480px) {
            .stats-container { grid-template-columns: 1fr; }
            .quick-grid { grid-template-columns: 1fr; }
            .specs-grid { grid-template-columns: 1fr; }
            .weapon-part { width: 100%; }
            .ranking-item { flex-wrap: wrap; }
        }
    </style>
</head>
<body data-theme="dark">
    <div class="tech-bg"></div>
    <div class="grid-pattern"></div>

    <header>
        <a href="#" class="logo">FAL <span>7.62mm</span></a>
        <nav>
            <a href="#inicio" class="nav-link active" data-tab="inicio"><i class="fas fa-home"></i> INÍCIO</a>
            <a href="#especificacoes" class="nav-link" data-tab="especificacoes"><i class="fas fa-microchip"></i> ESPECIFICAÇÕES</a>
            <a href="#desmontagem" class="nav-link" data-tab="desmontagem"><i class="fas fa-tools"></i> DESMONTAGEM</a>
            <a href="#montagem" class="nav-link" data-tab="montagem"><i class="fas fa-cogs"></i> MONTAGEM</a>
            <a href="#simulador" class="nav-link" data-tab="simulador"><i class="fas fa-crosshairs"></i> SIMULADOR</a>
            <a href="#seguranca" class="nav-link" data-tab="seguranca"><i class="fas fa-shield-alt"></i> SEGURANÇA</a>
            <a href="#quiz" class="nav-link" data-tab="quiz"><i class="fas fa-question-circle"></i> AVALIAÇÃO</a>
            <a href="#ranking" class="nav-link" data-tab="ranking"><i class="fas fa-trophy"></i> RANKING</a>
            <a href="#perfil" class="nav-link" data-tab="perfil"><i class="fas fa-user"></i> PERFIL</a>
        </nav>
        <div class="header-actions">
            <button class="login-btn" id="headerLoginBtn"><i class="fas fa-sign-in-alt"></i> ENTRAR</button>
            <button class="theme-toggle" id="themeToggle">☀️</button>
        </div>
    </header>

    <main class="main-content">
        <!-- Aba Início -->
        <section id="inicio" class="tab-content active">
            <div class="hero-section">
                <h1 class="glow">FAL 7.62mm</h1>
                <p>Fuzil Automático Leve - Plataforma de Instrução Militar</p>
                <p class="hero-subtitle">Sistema interativo de treinamento para montagem, desmontagem, simulação de disparos e avaliação teórica</p>
                <button id="startTrainingBtn" class="pulse">INICIAR TREINAMENTO</button>
            </div>

            <div class="stats-section">
                <div class="stats-container">
                    <div class="stat-item"><h3 id="totalSoldiers">0</h3><p>Militares Treinados</p></div>
                    <div class="stat-item"><h3 id="avgScore">0%</h3><p>Média de Aproveitamento</p></div>
                    <div class="stat-item"><h3 id="totalShots">0</h3><p>Simulações Realizadas</p></div>
                    <div class="stat-item"><h3 id="certifiedCount">0</h3><p>Certificados Emitidos</p></div>
                </div>
            </div>

            <div class="quick-access">
                <h3><i class="fas fa-bolt"></i> Acesso Rápido</h3>
                <div class="quick-grid">
                    <div class="quick-card" onclick="app.switchTab('desmontagem')"><i class="fas fa-tools"></i><span>Desmontagem</span></div>
                    <div class="quick-card" onclick="app.switchTab('montagem')"><i class="fas fa-cogs"></i><span>Montagem</span></div>
                    <div class="quick-card" onclick="app.switchTab('simulador')"><i class="fas fa-crosshairs"></i><span>Simulador de Tiro</span></div>
                    <div class="quick-card" onclick="app.switchTab('quiz')"><i class="fas fa-question-circle"></i><span>Avaliação Teórica</span></div>
                </div>
            </div>
        </section>

        <!-- Aba Especificações -->
        <section id="especificacoes" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-microchip"></i> Especificações Técnicas</h2><p>Dados completos do FAL 7.62mm</p></div>
            <div class="specs-container"><div class="specs-grid">
                <div class="spec-card"><i class="fas fa-bullseye"></i><h3>Calibre</h3><p>7,62 x 51mm NATO</p></div>
                <div class="spec-card"><i class="fas fa-weight-hanging"></i><h3>Peso (descarregado)</h3><p>4,25 kg</p></div>
                <div class="spec-card"><i class="fas fa-weight-hanging"></i><h3>Peso (carregado)</h3><p>≈ 4,85 kg</p></div>
                <div class="spec-card"><i class="fas fa-ruler"></i><h3>Comprimento Total</h3><p>1.090 mm</p></div>
                <div class="spec-card"><i class="fas fa-ruler"></i><h3>Comprimento do Cano</h3><p>533 mm</p></div>
                <div class="spec-card"><i class="fas fa-gauge-high"></i><h3>Cadência de Tiro</h3><p>650-700 tiros/min</p></div>
                <div class="spec-card"><i class="fas fa-map-marker-alt"></i><h3>Alcance Efetivo</h3><p>600 metros</p></div>
                <div class="spec-card"><i class="fas fa-map-marker-alt"></i><h3>Alcance Máximo</h3><p>3.200 metros</p></div>
                <div class="spec-card"><i class="fas fa-magazine"></i><h3>Capacidade Carregador</h3><p>20 munições</p></div>
                <div class="spec-card"><i class="fas fa-tachometer-alt"></i><h3>Velocidade Inicial</h3><p>830 m/s</p></div>
                <div class="spec-card"><i class="fas fa-cogs"></i><h3>Sistema de Funcionamento</h3><p>Por gases, ferrolho rotativo</p></div>
                <div class="spec-card"><i class="fas fa-eye"></i><h3>Alça de Mira</h3><p>Aferível de 200 a 600m</p></div>
            </div></div>
        </section>

        <!-- Aba Desmontagem -->
        <section id="desmontagem" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-tools"></i> Desmontagem do FAL 7.62mm</h2><p>Siga a sequência correta</p></div>
            <div class="disassembly-container">
                <div class="simulator-area">
                    <div class="weapon-schema" id="weaponSchemaDisassembly">
                        <div class="weapon-part" data-part="carregador" data-order="1"><i class="fas fa-magazine"></i><span>Carregador</span></div>
                        <div class="weapon-part" data-part="guarda-mao" data-order="2"><i class="fas fa-hand-paper"></i><span>Guarda-mão</span></div>
                        <div class="weapon-part" data-part="cano" data-order="3"><i class="fas fa-gun"></i><span>Cano</span></div>
                        <div class="weapon-part" data-part="corpo" data-order="4"><i class="fas fa-cube"></i><span>Corpo/Receptor</span></div>
                        <div class="weapon-part" data-part="culatra" data-order="5"><i class="fas fa-microchip"></i><span>Culatrá/Ferrolho</span></div>
                        <div class="weapon-part" data-part="coice" data-order="6"><i class="fas fa-chair"></i><span>Coice/Coronha</span></div>
                    </div>
                    <div class="sequence-panel"><h3>Sequência Correta</h3><div class="sequence-list" id="sequenceListDisassembly"><div class="sequence-item" data-step="1">1. Carregador</div><div class="sequence-item" data-step="2">2. Guarda-mão</div><div class="sequence-item" data-step="3">3. Cano</div><div class="sequence-item" data-step="4">4. Corpo/Receptor</div><div class="sequence-item" data-step="5">5. Culatrá/Ferrolho</div><div class="sequence-item" data-step="6">6. Coice/Coronha</div></div></div>
                </div>
                <div class="progress-area"><div class="progress-bar-container"><div class="progress-label">Progresso</div><div class="progress-bar"><div class="progress-fill" id="disassemblyProgressFill"></div></div><span id="disassemblyProgressText">0/6 peças</span></div><button class="action-btn reset-btn" id="resetDisassemblyBtn"><i class="fas fa-redo"></i> Reiniciar</button><button class="action-btn check-btn" id="checkDisassemblyBtn"><i class="fas fa-check-circle"></i> Verificar</button></div>
                <div class="feedback-area" id="disassemblyFeedback"><div class="feedback-message"><i class="fas fa-info-circle"></i><span>Clique nas peças na ordem correta</span></div></div>
            </div>
        </section>

        <!-- Aba Montagem -->
        <section id="montagem" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-cogs"></i> Montagem do FAL 7.62mm</h2><p>Siga a sequência correta</p></div>
            <div class="assembly-container">
                <div class="simulator-area">
                    <div class="weapon-schema" id="weaponSchemaAssembly">
                        <div class="weapon-part" data-part="coice" data-order="1"><i class="fas fa-chair"></i><span>Coice/Coronha</span></div>
                        <div class="weapon-part" data-part="culatra" data-order="2"><i class="fas fa-microchip"></i><span>Culatrá/Ferrolho</span></div>
                        <div class="weapon-part" data-part="corpo" data-order="3"><i class="fas fa-cube"></i><span>Corpo/Receptor</span></div>
                        <div class="weapon-part" data-part="cano" data-order="4"><i class="fas fa-gun"></i><span>Cano</span></div>
                        <div class="weapon-part" data-part="guarda-mao" data-order="5"><i class="fas fa-hand-paper"></i><span>Guarda-mão</span></div>
                        <div class="weapon-part" data-part="carregador" data-order="6"><i class="fas fa-magazine"></i><span>Carregador</span></div>
                    </div>
                    <div class="sequence-panel"><h3>Sequência Correta</h3><div class="sequence-list" id="sequenceListAssembly"><div class="sequence-item" data-step="1">1. Coice/Coronha</div><div class="sequence-item" data-step="2">2. Culatrá/Ferrolho</div><div class="sequence-item" data-step="3">3. Corpo/Receptor</div><div class="sequence-item" data-step="4">4. Cano</div><div class="sequence-item" data-step="5">5. Guarda-mão</div><div class="sequence-item" data-step="6">6. Carregador</div></div></div>
                </div>
                <div class="progress-area"><div class="progress-bar-container"><div class="progress-label">Progresso</div><div class="progress-bar"><div class="progress-fill" id="assemblyProgressFill"></div></div><span id="assemblyProgressText">0/6 peças</span></div><button class="action-btn reset-btn" id="resetAssemblyBtn"><i class="fas fa-redo"></i> Reiniciar</button><button class="action-btn check-btn" id="checkAssemblyBtn"><i class="fas fa-check-circle"></i> Verificar</button></div>
                <div class="feedback-area" id="assemblyFeedback"><div class="feedback-message"><i class="fas fa-info-circle"></i><span>Clique nas peças na ordem correta</span></div></div>
            </div>
        </section>

        <!-- Aba Simulador -->
        <section id="simulador" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-crosshairs"></i> Simulador de Tiro</h2><p>Pratique sua pontaria</p></div>
            <div class="shooting-simulator">
                <div class="target-area"><div class="target" id="target"><div class="target-ring ring-10"></div><div class="target-ring ring-9"></div><div class="target-ring ring-8"></div><div class="target-ring ring-7"></div><div class="target-center"></div></div><div class="hit-marker" id="hitMarker" style="display:none;">🎯</div></div>
                <div class="shooting-controls">
                    <div class="weapon-status"><div class="status-item"><i class="fas fa-battery-full"></i><span>Munição: <strong id="ammoCount">20</strong>/20</span></div><div class="status-item"><i class="fas fa-chart-line"></i><span>Pontuação: <strong id="scoreCount">0</strong></span></div><div class="status-item"><i class="fas fa-bullseye"></i><span>Acertos: <strong id="hitCount">0</strong></span></div><div class="status-item"><i class="fas fa-times-circle"></i><span>Erros: <strong id="missCount">0</strong></span></div></div>
                    <div class="breathing-exercise"><h4><i class="fas fa-lungs"></i> Respiração</h4><div class="breathing-circle" id="breathingCircle"><span>Inspire</span></div><p>Controle a respiração</p></div>
                    <div class="shooting-buttons"><button class="shoot-btn" id="shootBtn"><i class="fas fa-crosshairs"></i> DISPARAR</button><button class="reload-btn" id="reloadBtn"><i class="fas fa-sync-alt"></i> RECARREGAR</button><button class="reset-shooting-btn" id="resetShootingBtn"><i class="fas fa-redo"></i> REINICIAR</button></div>
                    <div class="shooting-tips"><h4><i class="fas fa-lightbulb"></i> Dicas</h4><ul><li>Controle a respiração</li><li>Pressione suavemente</li><li>Mire no centro</li></ul></div>
                </div>
                <div class="shooting-history"><h4><i class="fas fa-history"></i> Histórico</h4><div class="history-list" id="shootingHistory"><div class="history-empty">Nenhum disparo</div></div></div>
            </div>
        </section>

        <!-- Aba Segurança -->
        <section id="seguranca" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-shield-alt"></i> Regras de Segurança</h2><p>Normas fundamentais</p></div>
            <div class="safety-container"><div class="safety-rules-grid">
                <div class="rule-card rule-1"><div class="rule-number">01</div><h3>Arma descarregada</h3><p>Trate toda arma como carregada até verificar.</p></div>
                <div class="rule-card rule-2"><div class="rule-number">02</div><h3>Dedo fora do gatilho</h3><p>Mantenha o dedo estendido sobre o corpo.</p></div>
                <div class="rule-card rule-3"><div class="rule-number">03</div><h3>Nunca aponte</h3><p>Não aponte para o que não quer destruir.</p></div>
                <div class="rule-card rule-4"><div class="rule-number">04</div><h3>Conheça seu alvo</h3><p>Saiba o que há atrás do alvo.</p></div>
                <div class="rule-card rule-5"><div class="rule-number">05</div><h3>Inspeção visual</h3><p>Verifique câmara e carregador.</p></div>
                <div class="rule-card rule-6"><div class="rule-number">06</div><h3>Use EPIs</h3><p>Protetor auricular e óculos.</p></div>
            </div></div>
        </section>

        <!-- Aba Quiz -->
        <section id="quiz" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-question-circle"></i> Avaliação Teórica</h2><p>Teste seus conhecimentos</p></div>
            <div class="quiz-container"><div class="quiz-header"><div class="quiz-info"><span><i class="fas fa-question"></i> 15 questões</span><span><i class="fas fa-clock"></i> 30 minutos</span><span><i class="fas fa-check-circle"></i> Mínimo 70%</span></div><div class="quiz-timer" id="quizTimer">30:00</div></div><div class="quiz-questions" id="quizQuestions"></div><div class="quiz-actions"><button class="action-btn submit-quiz-btn" id="submitQuizBtn"><i class="fas fa-check-double"></i> FINALIZAR</button><button class="action-btn reset-quiz-btn" id="resetQuizBtn"><i class="fas fa-redo"></i> REINICIAR</button></div><div class="quiz-result" id="quizResult" style="display:none;"><div class="result-card"><i class="fas fa-graduation-cap"></i><h3 id="resultTitle">Resultado</h3><p id="resultMessage"></p><div class="result-score"><span>Pontuação: <strong id="resultScore">0</strong>%</span></div><button class="action-btn certificate-btn" id="generateCertificateBtn" style="display:none;"><i class="fas fa-certificate"></i> CERTIFICADO</button></div></div></div>
        </section>

        <!-- Aba Ranking -->
        <section id="ranking" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-trophy"></i> Ranking de Instrução</h2><p>Classificação dos melhores</p></div>
            <div class="ranking-container"><div class="ranking-filters"><button class="filter-btn active" data-filter="geral">GERAL</button><button class="filter-btn" data-filter="tiro">TIRO</button><button class="filter-btn" data-filter="teorico">TEÓRICO</button><button class="filter-btn" data-filter="montagem">MONTAGEM</button></div><div class="ranking-list" id="rankingList"></div><div class="user-position"><h3>Sua Posição</h3><div class="position-card" id="userPositionCard"><span class="rank">-</span><div class="user-info"><strong>Você</strong><span>Complete o treinamento</span></div></div></div></div>
        </section>

        <!-- Aba Perfil -->
        <section id="perfil" class="tab-content">
            <div class="tab-header"><h2><i class="fas fa-user"></i> Meu Perfil</h2><p>Gerencie seus dados</p></div>
            <div class="profile-container"><div class="profile-header"><div class="profile-avatar"><div class="avatar-circle"><i class="fas fa-user-shield"></i></div><button class="edit-avatar-btn" onclick="app.changeAvatar()"><i class="fas fa-camera"></i></button></div><div class="profile-info"><h3 id="profileUserName">Visitante</h3><p id="profileUserEmail">Faça login para acessar</p><div class="profile-badges"><span class="badge" id="profileRank">Não Cadastrado</span></div></div><div class="profile-stats"><div class="stat"><span class="stat-number" id="profilePoints">0</span><span class="stat-label">Pontos</span></div><div class="stat"><span class="stat-number" id="profileShots">0</span><span class="stat-label">Disparos</span></div><div class="stat"><span class="stat-number" id="profileAccuracy">0%</span><span class="stat-label">Precisão</span></div></div></div><div class="profile-content"><div class="profile-section"><h3><i class="fas fa-chart-line"></i> Estatísticas</h3><div class="stats-grid"><div class="stat-card"><i class="fas fa-tools"></i><div class="stat-info"><h4 id="statDisassembly">0</h4><p>Desmontagens</p></div></div><div class="stat-card"><i class="fas fa-cogs"></i><div class="stat-info"><h4 id="statAssembly">0</h4><p>Montagens</p></div></div><div class="stat-card"><i class="fas fa-crosshairs"></i><div class="stat-info"><h4 id="statBestScore">0</h4><p>Melhor Pontuação</p></div></div><div class="stat-card"><i class="fas fa-graduation-cap"></i><div class="stat-info"><h4 id="statQuizScore">0%</h4><p>Avaliação</p></div></div></div></div><div class="profile-section"><h3><i class="fas fa-certificate"></i> Certificações</h3><div class="certifications-list" id="certificationsList"><div class="cert-empty">Nenhuma certificação</div></div></div><div class="profile-section"><h3><i class="fas fa-cog"></i> Configurações</h3><div class="settings-grid"><div class="setting-item"><div class="setting-info"><h4>Modo Escuro</h4><p>Interface com tema escuro</p></div><label class="switch"><input type="checkbox" id="darkMode"><span class="slider"></span></label></div></div></div></div></div>
        </section>
    </main>

    <footer><p>Instrução Militar - FAL 7.62mm &copy; 2025</p><div class="footer-links"><a href="#"><i class="fab fa-github"></i></a><a href="#"><i class="fab fa-linkedin"></i></a></div></footer>

    <!-- Modais -->
    <div class="modal" id="profileModal"><div class="modal-content"><span class="close-modal" id="closeModal">&times;</span><h2 class="modal-title">Cadastro Militar</h2><div class="profile-options"><div class="profile-option" data-profile="soldado"><i class="fas fa-user-graduate"></i><h3>SOLDADO</h3><p>Inicie seu treinamento</p></div></div></div></div>
    <div class="login-page" id="soldadoLogin"><div class="login-content"><span class="close-modal" onclick="app.closeLoginPage('soldadoLogin')">&times;</span><h2 class="login-title">Login</h2><form class="login-form" id="soldadoLoginForm"><div class="form-group"><label>E-mail</label><input type="email" id="soldado-email" placeholder="seu@email.mil.br" required></div><div class="form-group"><label>Senha</label><input type="password" id="soldado-password" placeholder="Sua senha" required></div><button type="submit" class="login-button">ACESSAR</button></form><button class="toggle-form" onclick="app.showRegisterForm('soldado')">Cadastre-se</button><button class="back-button" onclick="app.closeLoginPage('soldadoLogin')">Voltar</button></div></div>
    <div class="login-page" id="soldadoRegister"><div class="login-content"><span class="close-modal" onclick="app.closeLoginPage('soldadoRegister')">&times;</span><h2 class="login-title">Cadastro</h2><form class="login-form" id="soldadoRegisterForm"><div class="form-group"><label>Nome</label><input type="text" id="soldado-register-name" required></div><div class="form-group"><label>E-mail</label><input type="email" id="soldado-register-email" required></div><div class="form-group"><label>NIM</label><input type="text" id="soldado-register-numero" required></div><div class="form-group"><label>Senha</label><input type="password" id="soldado-register-password" required minlength="6"></div><div class="form-group"><label>Confirmar</label><input type="password" id="soldado-register-confirm-password" required></div><button type="submit" class="login-button">CRIAR CONTA</button></form><button class="toggle-form" onclick="app.showLoginForm('soldado')">Já tem conta?</button><button class="back-button" onclick="app.closeLoginPage('soldadoRegister')">Voltar</button></div></div>
    <div class="modal" id="certificateModal"><div class="modal-content certificate-modal"><span class="close-modal" onclick="app.closeCertificateModal()">&times;</span><div class="certificate-content" id="certificateContent"></div><div class="certificate-actions"><button class="action-btn" onclick="app.printCertificate()"><i class="fas fa-print"></i> Imprimir</button><button class="action-btn" onclick="app.downloadCertificate()"><i class="fas fa-download"></i> Baixar</button></div></div></div>

    <script>
        // ===== SISTEMA PRINCIPAL - INSTRUÇÃO FAL 7.62mm =====

        class MilitaryInstructionApp {
            constructor() {
                this.currentUser = null;
                this.currentTab = 'inicio';
                this.theme = localStorage.getItem('theme') || 'dark';
                this.disassemblyCompleted = [];
                this.assemblyCompleted = [];
                this.shootingStats = { ammo: 20, score: 0, hits: 0, misses: 0, history: [] };
                this.quizAnswers = {};
                this.quizTimer = null;
                this.breathingInterval = null;
                this.init();
            }

            init() {
                this.loadTheme();
                this.setupEventListeners();
                this.setupTabSystem();
                this.loadUserData();
                this.updateStatsDisplay();
                this.initBreathing();
            }

            loadTheme() {
                document.body.setAttribute('data-theme', this.theme);
                const toggleBtn = document.getElementById('themeToggle');
                if (toggleBtn) toggleBtn.textContent = this.theme === 'dark' ? '☀️' : '🌙';
                const darkModeToggle = document.getElementById('darkMode');
                if (darkModeToggle) darkModeToggle.checked = this.theme === 'dark';
            }

            toggleTheme() {
                this.theme = this.theme === 'dark' ? 'light' : 'dark';
                this.loadTheme();
                localStorage.setItem('theme', this.theme);
            }

            setupEventListeners() {
                document.getElementById('startTrainingBtn')?.addEventListener('click', () => this.openProfileModal());
                document.getElementById('headerLoginBtn')?.addEventListener('click', () => this.currentUser ? this.showUserMenu() : this.openProfileModal());
                document.getElementById('themeToggle')?.addEventListener('click', () => this.toggleTheme());
                document.getElementById('closeModal')?.addEventListener('click', () => this.closeProfileModal());
                document.getElementById('darkMode')?.addEventListener('change', (e) => { this.theme = e.target.checked ? 'dark' : 'light'; this.loadTheme(); });
                
                document.getElementById('soldadoLoginForm')?.addEventListener('submit', (e) => { e.preventDefault(); this.handleLogin(); });
                document.getElementById('soldadoRegisterForm')?.addEventListener('submit', (e) => { e.preventDefault(); this.handleRegister(); });
                
                document.getElementById('resetDisassemblyBtn')?.addEventListener('click', () => this.resetDisassembly());
                document.getElementById('checkDisassemblyBtn')?.addEventListener('click', () => this.checkDisassembly());
                document.getElementById('resetAssemblyBtn')?.addEventListener('click', () => this.resetAssembly());
                document.getElementById('checkAssemblyBtn')?.addEventListener('click', () => this.checkAssembly());
                
                document.getElementById('shootBtn')?.addEventListener('click', () => this.shoot());
                document.getElementById('reloadBtn')?.addEventListener('click', () => this.reload());
                document.getElementById('resetShootingBtn')?.addEventListener('click', () => this.resetShooting());
                
                document.addEventListener('keydown', (e) => {
                    if (this.currentTab === 'simulador') {
                        if (e.code === 'Space') { e.preventDefault(); this.shoot(); }
                        if (e.code === 'KeyR') { e.preventDefault(); this.reload(); }
                    }
                });
                
                document.getElementById('target')?.addEventListener('click', (e) => { e.stopPropagation(); this.shoot(); });
                
                document.getElementById('submitQuizBtn')?.addEventListener('click', () => this.submitQuiz());
                document.getElementById('resetQuizBtn')?.addEventListener('click', () => this.resetQuiz());
                
                document.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.addEventListener('click', () => {
                        document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                        btn.classList.add('active');
                        this.loadRanking(btn.dataset.filter);
                    });
                });
                
                document.querySelectorAll('.profile-option').forEach(opt => {
                    opt.addEventListener('click', () => {
                        const profile = opt.dataset.profile;
                        this.closeProfileModal();
                        setTimeout(() => this.showRegisterForm(profile), 300);
                    });
                });
                
                document.addEventListener('keydown', (e) => { if (e.key === 'Escape') this.closeAllModals(); });
                
                window.addEventListener('click', (e) => {
                    if (e.target.classList.contains('modal')) e.target.style.display = 'none';
                    if (e.target.classList.contains('login-page')) e.target.style.display = 'none';
                });
            }

            setupTabSystem() {
                document.querySelectorAll('.nav-link').forEach(link => {
                    link.addEventListener('click', (e) => {
                        e.preventDefault();
                        this.switchTab(link.getAttribute('data-tab'));
                    });
                });
                this.switchTab('inicio');
            }

            switchTab(tabId) {
                document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
                document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'));
                document.getElementById(tabId)?.classList.add('active');
                document.querySelector(`[data-tab="${tabId}"]`)?.classList.add('active');
                this.currentTab = tabId;
                
                if (tabId === 'desmontagem') this.initDisassembly();
                if (tabId === 'montagem') this.initAssembly();
                if (tabId === 'simulador') this.initShooting();
                if (tabId === 'quiz') this.initQuiz();
                if (tabId === 'ranking') this.loadRanking('geral');
                if (tabId === 'perfil') this.loadProfile();
            }

            handleLogin() {
                const email = document.getElementById('soldado-email')?.value;
                const password = document.getElementById('soldado-password')?.value;
                if (!email || !password) return this.showAlert('Preencha todos os campos!', 'error');
                
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                const user = users[email.toLowerCase()];
                if (!user) return this.showAlert('Usuário não encontrado!', 'error');
                if (user.password !== password) return this.showAlert('Senha incorreta!', 'error');
                
                this.currentUser = user;
                localStorage.setItem('currentMilitaryUser', JSON.stringify(user));
                this.showAlert(`Bem-vindo, ${user.name}!`, 'success');
                this.closeLoginPage('soldadoLogin');
                this.updateUIAfterLogin();
            }

            handleRegister() {
                const name = document.getElementById('soldado-register-name')?.value;
                const email = document.getElementById('soldado-register-email')?.value;
                const nim = document.getElementById('soldado-register-numero')?.value;
                const password = document.getElementById('soldado-register-password')?.value;
                const confirm = document.getElementById('soldado-register-confirm-password')?.value;
                
                if (!name || !email || !nim || !password) return this.showAlert('Preencha todos os campos!', 'error');
                if (password !== confirm) return this.showAlert('Senhas não coincidem!', 'error');
                if (password.length < 6) return this.showAlert('Senha deve ter 6+ caracteres!', 'error');
                
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                if (users[email.toLowerCase()]) return this.showAlert('E-mail já cadastrado!', 'error');
                
                const newUser = {
                    id: Date.now(), name, email: email.toLowerCase(), password, nim,
                    profile: 'soldado', createdAt: new Date().toISOString(),
                    stats: { disassemblyCompletions: 0, assemblyCompletions: 0, bestShootingScore: 0, bestQuizScore: 0, totalShots: 0, totalHits: 0 },
                    certifications: []
                };
                
                users[email.toLowerCase()] = newUser;
                localStorage.setItem('militaryUsers', JSON.stringify(users));
                this.showAlert('Cadastro realizado! Faça login.', 'success');
                this.closeLoginPage('soldadoRegister');
                this.showLoginForm('soldado');
            }

            updateUIAfterLogin() {
                const loginBtn = document.getElementById('headerLoginBtn');
                if (loginBtn) loginBtn.innerHTML = `<i class="fas fa-user-shield"></i> ${this.currentUser.name}`;
                this.loadProfile();
                this.updateStatsDisplay();
                this.loadRanking('geral');
                this.showAlert(`Bem-vindo ao treinamento, ${this.currentUser.name}!`, 'success');
            }

            showUserMenu() {
                document.querySelector('.user-menu')?.remove();
                const menu = document.createElement('div');
                menu.className = 'user-menu';
                menu.innerHTML = `<div class="user-menu-item" onclick="app.switchTab('perfil')"><i class="fas fa-user"></i> Meu Perfil</div><div class="user-menu-item" onclick="app.logout()"><i class="fas fa-sign-out-alt"></i> Sair</div>`;
                document.body.appendChild(menu);
                setTimeout(() => {
                    const closeMenu = (e) => { if (!menu.contains(e.target) && e.target !== document.getElementById('headerLoginBtn')) { menu.remove(); document.removeEventListener('click', closeMenu); } };
                    document.addEventListener('click', closeMenu);
                }, 100);
            }

            logout() {
                if (confirm('Deseja realmente sair?')) {
                    this.currentUser = null;
                    localStorage.removeItem('currentMilitaryUser');
                    document.getElementById('headerLoginBtn').innerHTML = '<i class="fas fa-sign-in-alt"></i> ENTRAR';
                    this.showAlert('Logout realizado!', 'info');
                    this.switchTab('inicio');
                    this.loadProfile();
                }
            }

            initDisassembly() {
                this.disassemblyCompleted = [];
                document.querySelectorAll('#weaponSchemaDisassembly .weapon-part').forEach(p => p.classList.remove('completed'));
                document.querySelectorAll('#sequenceListDisassembly .sequence-item').forEach(i => i.classList.remove('completed'));
                document.getElementById('disassemblyProgressFill').style.width = '0%';
                document.getElementById('disassemblyProgressText').textContent = '0/6 peças';
                document.getElementById('disassemblyFeedback').innerHTML = '<div class="feedback-message"><i class="fas fa-info-circle"></i><span>Clique nas peças na ordem correta</span></div>';
                this.setupPartClickHandlers('disassembly');
            }

            setupPartClickHandlers(mode) {
                const schemaId = mode === 'disassembly' ? 'weaponSchemaDisassembly' : 'weaponSchemaAssembly';
                document.querySelectorAll(`#${schemaId} .weapon-part`).forEach(part => {
                    part.removeEventListener('click', this.partClickHandler);
                    this.partClickHandler = () => this.handlePartClick(part, mode);
                    part.addEventListener('click', this.partClickHandler);
                });
            }

            handlePartClick(part, mode) {
                const partId = part.dataset.part;
                const expectedOrder = parseInt(part.dataset.order);
                const completed = mode === 'disassembly' ? this.disassemblyCompleted : this.assemblyCompleted;
                const nextOrder = completed.length + 1;
                
                if (completed.includes(partId)) {
                    this.showFeedback(`"${part.querySelector('span').textContent}" já foi ${mode === 'disassembly' ? 'removida' : 'instalada'}!`, 'warning');
                    return;
                }
                
                if (expectedOrder === nextOrder) {
                    completed.push(partId);
                    part.classList.add('completed');
                    document.querySelector(`#sequenceList${mode === 'disassembly' ? 'Disassembly' : 'Assembly'} .sequence-item[data-step="${expectedOrder}"]`)?.classList.add('completed');
                    this.updateProgress(mode);
                    this.showFeedback(`✓ ${part.querySelector('span').textContent} ${mode === 'disassembly' ? 'removido' : 'instalado'}!`, 'success');
                    
                    if (completed.length === 6) {
                        this.showFeedback(`🎉 ${mode === 'disassembly' ? 'Desmontagem' : 'Montagem'} concluída!`, 'success');
                        if (this.currentUser) this.saveCompletion(mode);
                    }
                } else {
                    const expectedPart = document.querySelector(`#${mode === 'disassembly' ? 'weaponSchemaDisassembly' : 'weaponSchemaAssembly'} .weapon-part[data-order="${nextOrder}"] span`).textContent;
                    this.showFeedback(`Ordem incorreta! Próximo: ${expectedPart}`, 'error');
                }
            }

            updateProgress(mode) {
                const completed = mode === 'disassembly' ? this.disassemblyCompleted : this.assemblyCompleted;
                const percent = (completed.length / 6) * 100;
                document.getElementById(`${mode}ProgressFill`).style.width = `${percent}%`;
                document.getElementById(`${mode}ProgressText`).textContent = `${completed.length}/6 peças`;
            }

            resetDisassembly() { this.initDisassembly(); this.showFeedback('Desmontagem reiniciada!', 'info'); }
            checkDisassembly() { this.showFeedback(this.disassemblyCompleted.length === 6 ? '✓ Desmontagem correta!' : `⚠️ Faltam ${6 - this.disassemblyCompleted.length} peças`, this.disassemblyCompleted.length === 6 ? 'success' : 'warning'); }
            resetAssembly() { this.initAssembly(); this.showFeedback('Montagem reiniciada!', 'info'); }
            checkAssembly() { this.showFeedback(this.assemblyCompleted.length === 6 ? '✓ Montagem correta!' : `⚠️ Faltam ${6 - this.assemblyCompleted.length} peças`, this.assemblyCompleted.length === 6 ? 'success' : 'warning'); }

            initAssembly() {
                this.assemblyCompleted = [];
                document.querySelectorAll('#weaponSchemaAssembly .weapon-part').forEach(p => p.classList.remove('completed'));
                document.querySelectorAll('#sequenceListAssembly .sequence-item').forEach(i => i.classList.remove('completed'));
                document.getElementById('assemblyProgressFill').style.width = '0%';
                document.getElementById('assemblyProgressText').textContent = '0/6 peças';
                document.getElementById('assemblyFeedback').innerHTML = '<div class="feedback-message"><i class="fas fa-info-circle"></i><span>Clique nas peças na ordem correta</span></div>';
                this.setupPartClickHandlers('assembly');
            }

            saveCompletion(mode) {
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                const user = users[this.currentUser.email];
                if (user) {
                    if (mode === 'disassembly') user.stats.disassemblyCompletions++;
                    else user.stats.assemblyCompletions++;
                    users[this.currentUser.email] = user;
                    localStorage.setItem('militaryUsers', JSON.stringify(users));
                    this.currentUser = user;
                }
            }

            initShooting() {
                this.shootingStats = { ammo: 20, score: 0, hits: 0, misses: 0, history: [] };
                this.updateShootingUI();
                document.getElementById('shootBtn').disabled = false;
            }

            updateShootingUI() {
                document.getElementById('ammoCount').textContent = this.shootingStats.ammo;
                document.getElementById('scoreCount').textContent = this.shootingStats.score;
                document.getElementById('hitCount').textContent = this.shootingStats.hits;
                document.getElementById('missCount').textContent = this.shootingStats.misses;
                const historyDiv = document.getElementById('shootingHistory');
                if (this.shootingStats.history.length === 0) historyDiv.innerHTML = '<div class="history-empty">Nenhum disparo realizado</div>';
                else historyDiv.innerHTML = this.shootingStats.history.map(h => `<div class="history-item"><span>Disparo #${h.id}</span><span class="${h.score === 0 ? 'miss' : `score-${h.score}`}">${h.score === 0 ? 'ERROU' : `${h.score} pts`}</span><span>${h.time}</span></div>`).join('');
                document.getElementById('shootBtn').disabled = this.shootingStats.ammo === 0;
            }

            shoot() {
                if (this.shootingStats.ammo === 0) return this.showAlert('Sem munição! Recarregue.', 'warning');
                this.shootingStats.ammo--;
                const randomX = (Math.random() - 0.5) * 40;
                const randomY = (Math.random() - 0.5) * 40;
                const distance = Math.sqrt(randomX * randomX + randomY * randomY);
                let score = 0;
                if (distance <= 10) score = 10;
                else if (distance <= 20) score = 9;
                else if (distance <= 30) score = 8;
                else if (distance <= 40) score = 7;
                
                if (score > 0) {
                    this.shootingStats.hits++;
                    this.shootingStats.score += score;
                    this.showFeedback(`🎯 ACERTO! ${score} pontos!`, 'success');
                    const marker = document.getElementById('hitMarker');
                    if (marker) {
                        marker.style.display = 'block';
                        marker.style.left = `calc(50% + ${randomX}px)`;
                        marker.style.top = `calc(50% + ${randomY}px)`;
                        setTimeout(() => marker.style.display = 'none', 300);
                    }
                } else {
                    this.shootingStats.misses++;
                    this.showFeedback('❌ ERROU!', 'error');
                }
                
                this.shootingStats.history.unshift({ id: this.shootingStats.history.length + 1, score: score, time: new Date().toLocaleTimeString() });
                if (this.shootingStats.history.length > 20) this.shootingStats.history.pop();
                this.updateShootingUI();
                if (this.currentUser) this.saveShootingStats();
            }

            reload() { this.shootingStats.ammo = 20; this.updateShootingUI(); this.showFeedback('🔫 Arma recarregada!', 'success'); }
            resetShooting() { this.initShooting(); this.showFeedback('Sessão reiniciada!', 'info'); }

            saveShootingStats() {
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                const user = users[this.currentUser.email];
                if (user) {
                    user.stats.totalShots += this.shootingStats.hits + this.shootingStats.misses;
                    user.stats.totalHits += this.shootingStats.hits;
                    if (this.shootingStats.score > user.stats.bestShootingScore) user.stats.bestShootingScore = this.shootingStats.score;
                    users[this.currentUser.email] = user;
                    localStorage.setItem('militaryUsers', JSON.stringify(users));
                    this.currentUser = user;
                }
            }

            initBreathing() {
                const circle = document.getElementById('breathingCircle');
                if (!circle) return;
                let phase = 'inhale', scale = 1, direction = 0.02;
                if (this.breathingInterval) clearInterval(this.breathingInterval);
                this.breathingInterval = setInterval(() => {
                    if (phase === 'inhale') {
                        scale += direction;
                        if (scale >= 1.3) { phase = 'exhale'; circle.querySelector('span').textContent = 'Prenda'; }
                    } else {
                        scale -= direction;
                        if (scale <= 0.8) { phase = 'inhale'; circle.querySelector('span').textContent = 'Inspire'; }
                    }
                    circle.style.transform = `scale(${scale})`;
                    circle.classList.toggle('inhale', phase === 'inhale');
                    circle.classList.toggle('exhale', phase === 'exhale');
                }, 100);
            }

            initQuiz() {
                this.quizAnswers = {};
                if (this.quizTimer) clearInterval(this.quizTimer);
                this.startQuizTimer();
                this.loadQuizQuestions();
                document.getElementById('quizResult').style.display = 'none';
            }

            startQuizTimer() {
                let timeLeft = 30 * 60;
                const timerEl = document.getElementById('quizTimer');
                this.quizTimer = setInterval(() => {
                    const minutes = Math.floor(timeLeft / 60);
                    const seconds = timeLeft % 60;
                    timerEl.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
                    if (timeLeft <= 0) { clearInterval(this.quizTimer); this.submitQuiz(); }
                    timeLeft--;
                }, 1000);
            }

            loadQuizQuestions() {
                const questions = [
                    { text: "Qual o calibre do FAL?", options: ["5.56x45mm", "7.62x39mm", "7.62x51mm", "9x19mm"], correct: 2 },
                    { text: "Capacidade do carregador?", options: ["10", "20", "30", "15"], correct: 1 },
                    { text: "Alcance efetivo?", options: ["300m", "400m", "500m", "600m"], correct: 3 },
                    { text: "1ª regra de segurança?", options: ["Dedo fora do gatilho", "Arma descarregada", "Apontar para chão", "Usar EPI"], correct: 1 },
                    { text: "Sistema de funcionamento?", options: ["Recuo curto", "Aproveitamento de gases", "Blowback", "Recuo longo"], correct: 1 },
                    { text: "Peso descarregado?", options: ["3,2kg", "3,8kg", "4,25kg", "4,8kg"], correct: 2 },
                    { text: "Seletor para semiautomático?", options: ["S", "T", "A", "R"], correct: 1 },
                    { text: "O que significa FAL?", options: ["Fuzil Automático Leve", "Fuzil de Assalto Leve", "Fuzil Automático Latino", "Fuzil de Ação Leve"], correct: 0 },
                    { text: "Velocidade inicial?", options: ["730 m/s", "830 m/s", "930 m/s", "1030 m/s"], correct: 1 },
                    { text: "Quantos raiamentos?", options: ["4", "6", "8", "10"], correct: 1 },
                    { text: "Tipo de ferrolho?", options: ["Fixo", "Rotativo", "Basculante", "Deslizante"], correct: 1 },
                    { text: "Adotado pelo EB em?", options: ["1954", "1964", "1974", "1984"], correct: 1 },
                    { text: "Função do regulador de gases?", options: ["Ajustar cadência", "Regular pressão", "Controlar recuo", "Aumentar alcance"], correct: 1 },
                    { text: "Distância padrão da alça?", options: ["100m", "200m", "300m", "400m"], correct: 1 },
                    { text: "Característica principal?", options: ["Gases ajustável", "30 munições", "Cano 600mm", "Peso reduzido"], correct: 0 }
                ];
                
                const container = document.getElementById('quizQuestions');
                container.innerHTML = questions.map((q, idx) => `
                    <div class="quiz-question" data-qidx="${idx}">
                        <div class="question-text">${idx + 1}. ${q.text}</div>
                        <div class="question-options">
                            ${q.options.map((opt, optIdx) => `<label class="quiz-option"><input type="radio" name="q${idx}" value="${optIdx}"><span>${opt}</span></label>`).join('')}
                        </div>
                    </div>
                `);
                
                document.querySelectorAll('.quiz-option input').forEach(input => {
                    input.addEventListener('change', (e) => {
                        const qidx = e.target.name.replace('q', '');
                        this.quizAnswers[qidx] = parseInt(e.target.value);
                    });
                });
            }

            submitQuiz() {
                if (this.quizTimer) clearInterval(this.quizTimer);
                const correctAnswers = [2,1,3,1,1,2,1,0,1,1,1,1,1,1,0];
                let correctCount = 0;
                
                document.querySelectorAll('.quiz-question').forEach((q, idx) => {
                    const selected = this.quizAnswers[idx];
                    const isCorrect = selected === correctAnswers[idx];
                    if (isCorrect) correctCount++;
                    q.querySelectorAll('.quiz-option').forEach((opt, optIdx) => {
                        if (optIdx === correctAnswers[idx]) opt.classList.add('correct');
                        if (optIdx === selected && !isCorrect) opt.classList.add('wrong');
                    });
                });
                
                const percentage = (correctCount / 15) * 100;
                const approved = percentage >= 70;
                
                document.getElementById('quizResult').style.display = 'block';
                document.getElementById('resultTitle').textContent = approved ? '✅ APROVADO!' : '❌ REPROVADO';
                document.getElementById('resultMessage').innerHTML = approved ? `Parabéns! ${correctCount}/15 acertos (${percentage}%)` : `${correctCount}/15 acertos (${percentage}%). Mínimo 70% para aprovação.`;
                document.getElementById('resultScore').innerHTML = `<strong>${percentage}%</strong> de aproveitamento`;
                
                const certBtn = document.getElementById('generateCertificateBtn');
                certBtn.style.display = approved ? 'block' : 'none';
                if (approved) certBtn.onclick = () => this.generateCertificate(percentage);
                
                document.querySelectorAll('.quiz-option input').forEach(i => i.disabled = true);
                document.getElementById('submitQuizBtn').disabled = true;
                
                if (approved && this.currentUser) this.saveQuizScore(percentage);
            }

            saveQuizScore(percentage) {
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                const user = users[this.currentUser.email];
                if (user && percentage > (user.stats.bestQuizScore || 0)) {
                    user.stats.bestQuizScore = percentage;
                    users[this.currentUser.email] = user;
                    localStorage.setItem('militaryUsers', JSON.stringify(users));
                    this.currentUser = user;
                }
            }

            resetQuiz() { this.initQuiz(); this.showAlert('Quiz reiniciado!', 'info'); }

            loadRanking(filter = 'geral') {
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                let rankingData = Object.values(users).map(user => {
                    let score = 0;
                    if (filter === 'tiro') score = user.stats?.bestShootingScore || 0;
                    else if (filter === 'teorico') score = user.stats?.bestQuizScore || 0;
                    else if (filter === 'montagem') score = (user.stats?.disassemblyCompletions || 0) + (user.stats?.assemblyCompletions || 0);
                    else score = (user.stats?.bestShootingScore || 0) + (user.stats?.bestQuizScore || 0) + ((user.stats?.disassemblyCompletions || 0) * 10) + ((user.stats?.assemblyCompletions || 0) * 10);
                    return { ...user, score };
                });
                rankingData.sort((a, b) => b.score - a.score);
                
                const rankingList = document.getElementById('rankingList');
                if (rankingData.length === 0) rankingList.innerHTML = '<div class="ranking-empty">Nenhum militar cadastrado</div>';
                else rankingList.innerHTML = rankingData.slice(0, 10).map((u, i) => `<div class="ranking-item"><span class="rank">${i+1}º</span><span class="user-avatar">${i===0?'🏆':i===1?'🥈':i===2?'🥉':'👤'}</span><div class="user-info"><strong>${u.name}</strong><span>${u.nim}</span></div><div class="user-score"><strong>${u.score}</strong> pts</div></div>`).join('');
                
                if (this.currentUser) {
                    const rank = rankingData.findIndex(u => u.email === this.currentUser.email) + 1;
                    const posCard = document.getElementById('userPositionCard');
                    if (rank > 0) posCard.innerHTML = `<span class="rank">${rank}º</span><div class="user-info"><strong>${this.currentUser.name}</strong><span>${rankingData[rank-1]?.score || 0} pontos</span></div><div class="progress-bar"><div class="progress" style="width: ${((rankingData[rank-1]?.score || 0) / (rankingData[0]?.score || 1)) * 100}%"></div></div>`;
                }
            }

            loadProfile() {
                if (!this.currentUser) {
                    document.getElementById('profileUserName').textContent = 'Visitante';
                    document.getElementById('profileUserEmail').textContent = 'Faça login para acessar';
                    document.getElementById('profileRank').textContent = 'Não Cadastrado';
                    document.getElementById('profilePoints').textContent = '0';
                    document.getElementById('profileShots').textContent = '0';
                    document.getElementById('profileAccuracy').textContent = '0%';
                    document.getElementById('statDisassembly').textContent = '0';
                    document.getElementById('statAssembly').textContent = '0';
                    document.getElementById('statBestScore').textContent = '0';
                    document.getElementById('statQuizScore').textContent = '0%';
                    document.getElementById('certificationsList').innerHTML = '<div class="cert-empty">Faça login para ver suas certificações</div>';
                    return;
                }
                
                const stats = this.currentUser.stats || {};
                document.getElementById('profileUserName').textContent = this.currentUser.name;
                document.getElementById('profileUserEmail').textContent = this.currentUser.email;
                document.getElementById('profileRank').textContent = this.currentUser.profile.toUpperCase();
                document.getElementById('profilePoints').textContent = (stats.bestShootingScore || 0) + (stats.bestQuizScore || 0);
                document.getElementById('profileShots').textContent = stats.totalShots || 0;
                document.getElementById('profileAccuracy').textContent = stats.totalShots ? Math.round((stats.totalHits / stats.totalShots) * 100) : 0;
                document.getElementById('statDisassembly').textContent = stats.disassemblyCompletions || 0;
                document.getElementById('statAssembly').textContent = stats.assemblyCompletions || 0;
                document.getElementById('statBestScore').textContent = stats.bestShootingScore || 0;
                document.getElementById('statQuizScore').textContent = `${stats.bestQuizScore || 0}%`;
                
                const certs = this.currentUser.certifications || [];
                const certList = document.getElementById('certificationsList');
                if (certs.length === 0) certList.innerHTML = '<div class="cert-empty">Nenhuma certificação obtida</div>';
                else certList.innerHTML = certs.map(c => `<div class="cert-item"><i class="fas fa-certificate"></i><div><h4>${c.name}</h4><p>${new Date(c.date).toLocaleDateString()}</p></div></div>`).join('');
            }

            generateCertificate(percentage) {
                const certContent = document.getElementById('certificateContent');
                const date = new Date().toLocaleDateString('pt-BR');
                certContent.innerHTML = `<div style="text-align:center;padding:40px;border:10px double var(--primary-color);border-radius:20px;"><i class="fas fa-certificate" style="font-size:4rem;color:var(--primary-color);margin-bottom:20px;"></i><h1 style="color:var(--primary-color);">CERTIFICADO</h1><p>Certificamos que</p><h2>${this.currentUser.name}</h2><p>NIM: ${this.currentUser.nim}</p><p>concluiu com ${percentage}% de aproveitamento</p><h3 style="color:var(--primary-color);">FAL 7.62mm</h3><p>${date}</p></div>`;
                
                const certs = this.currentUser.certifications || [];
                certs.push({ name: 'Avaliação Teórica - FAL 7.62mm', date: new Date().toISOString(), score: percentage });
                this.currentUser.certifications = certs;
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                users[this.currentUser.email] = this.currentUser;
                localStorage.setItem('militaryUsers', JSON.stringify(users));
                document.getElementById('certificateModal').style.display = 'flex';
            }

            updateStatsDisplay() {
                const users = JSON.parse(localStorage.getItem('militaryUsers') || '{}');
                const values = Object.values(users);
                document.getElementById('totalSoldiers').textContent = values.length;
                document.getElementById('totalShots').textContent = values.reduce((s, u) => s + (u.stats?.totalShots || 0), 0);
                const avgScore = values.length ? Math.round(values.reduce((s, u) => s + (u.stats?.bestQuizScore || 0), 0) / values.length) : 0;
                document.getElementById('avgScore').textContent = `${avgScore}%`;
                document.getElementById('certifiedCount').textContent = values.filter(u => u.certifications?.length > 0).length;
            }

            showFeedback(msg, type = 'info') {
                const feedbackDiv = this.currentTab === 'desmontagem' ? document.getElementById('disassemblyFeedback') : this.currentTab === 'montagem' ? document.getElementById('assemblyFeedback') : null;
                if (feedbackDiv) {
                    feedbackDiv.innerHTML = `<div class="feedback-message ${type}"><i class="fas ${type === 'success' ? 'fa-check-circle' : type === 'error' ? 'fa-times-circle' : 'fa-info-circle'}"></i><span>${msg}</span></div>`;
                    setTimeout(() => { if (feedbackDiv.children[0] === feedbackDiv.lastChild) feedbackDiv.innerHTML = `<div class="feedback-message"><i class="fas fa-info-circle"></i><span>${this.currentTab === 'desmontagem' ? 'Clique nas peças na ordem correta' : 'Clique nas peças na ordem correta'}</span></div>`; }, 3000);
                } else this.showAlert(msg, type);
            }

            showAlert(msg, type = 'info') {
                const alert = document.createElement('div');
                alert.className = `custom-alert`;
                alert.style.cssText = `position:fixed;top:100px;right:20px;background:${type === 'error' ? '#ff4757' : type === 'success' ? '#4caf50' : type === 'warning' ? '#ff9800' : '#d4af37'};color:#fff;padding:12px 20px;border-radius:10px;z-index:10000;display:flex;align-items:center;gap:10px;animation:slideInRight 0.3s ease;font-weight:bold;`;
                alert.innerHTML = `<i class="fas ${type === 'error' ? 'fa-exclamation-circle' : type === 'success' ? 'fa-check-circle' : 'fa-info-circle'}"></i> ${msg}`;
                document.body.appendChild(alert);
                setTimeout(() => alert.remove(), 4000);
            }

            openProfileModal() { document.getElementById('profileModal').style.display = 'flex'; }
            closeProfileModal() { document.getElementById('profileModal').style.display = 'none'; }
            closeLoginPage(pageId) { document.getElementById(pageId).style.display = 'none'; }
            showLoginForm(profile) { document.getElementById(`${profile}Login`).style.display = 'flex'; }
            showRegisterForm(profile) { document.getElementById(`${profile}Register`).style.display = 'flex'; }
            closeAllModals() { document.querySelectorAll('.modal, .login-page').forEach(m => m.style.display = 'none'); }
            closeCertificateModal() { document.getElementById('certificateModal').style.display = 'none'; }
            printCertificate() { window.print(); }
            downloadCertificate() { this.showAlert('Download em desenvolvimento!', 'info'); }
            changeAvatar() { this.showAlert('Funcionalidade em desenvolvimento!', 'info'); }
            loadUserData() {
                const saved = localStorage.getItem('currentMilitaryUser');
                if (saved) { this.currentUser = JSON.parse(saved); this.updateUIAfterLogin(); }
            }
        }

        let app;
        document.addEventListener('DOMContentLoaded', () => { app = new MilitaryInstructionApp(); });
    </script>
</body>
</html>
