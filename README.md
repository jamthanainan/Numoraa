<html lang="th">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NUMORA - ถอดรหัสความฝันเป็นตัวเลขมงคล</title>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    body {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #0a0e27 0%, #1a1147 50%, #2d1b69 100%);
      color: #ffffff;
      width: 100%;
      height: 100%;
      overflow-x: hidden;
    }

    * {
      box-sizing: border-box;
    }

    .app-container {
      width: 100%;
      min-height: 100%;
      position: relative;
      overflow: hidden;
    }

    /* Animated Background Effects */
    .cosmic-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    .orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(60px);
      opacity: 0.3;
      animation: float 20s infinite ease-in-out;
    }

    .orb1 {
      width: 300px;
      height: 300px;
      background: radial-gradient(circle, #6366f1 0%, transparent 70%);
      top: 10%;
      left: 20%;
      animation-delay: 0s;
    }

    .orb2 {
      width: 250px;
      height: 250px;
      background: radial-gradient(circle, #8b5cf6 0%, transparent 70%);
      bottom: 20%;
      right: 15%;
      animation-delay: 5s;
    }

    .orb3 {
      width: 200px;
      height: 200px;
      background: radial-gradient(circle, #d97706 0%, transparent 70%);
      top: 50%;
      left: 50%;
      animation-delay: 10s;
    }

    @keyframes float {
      0%, 100% { transform: translate(0, 0) scale(1); }
      25% { transform: translate(30px, -30px) scale(1.1); }
      50% { transform: translate(-20px, 20px) scale(0.9); }
      75% { transform: translate(20px, 10px) scale(1.05); }
    }

    /* Page Container */
    .page {
      position: relative;
      z-index: 1;
      min-height: 100%;
      display: none;
      padding: 40px 20px;
    }

    .page.active {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    /* Page 1: Landing */
    .landing-content {
      text-align: center;
      max-width: 700px;
      width: 100%;
    }

    .logo {
      font-size: 4.5em;
      font-weight: 800;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 50%, #d97706 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 20px;
      letter-spacing: 8px;
      text-shadow: 0 0 40px rgba(251, 191, 36, 0.3);
      animation: glow 3s ease-in-out infinite;
    }

    @keyframes glow {
      0%, 100% { filter: drop-shadow(0 0 20px rgba(251, 191, 36, 0.4)); }
      50% { filter: drop-shadow(0 0 40px rgba(251, 191, 36, 0.7)); }
    }

    .tagline {
      font-size: 1.3em;
      color: #c7d2fe;
      margin-bottom: 50px;
      line-height: 1.6;
      font-weight: 300;
    }

    .mystical-symbol {
      width: 120px;
      height: 120px;
      margin: 30px auto;
      position: relative;
    }

    .symbol-ring {
      position: absolute;
      border: 2px solid #8b5cf6;
      border-radius: 50%;
      opacity: 0.6;
    }

    .ring1 {
      width: 120px;
      height: 120px;
      animation: rotate 10s linear infinite;
    }

    .ring2 {
      width: 90px;
      height: 90px;
      top: 15px;
      left: 15px;
      border-color: #fbbf24;
      animation: rotate 8s linear infinite reverse;
    }

    .ring3 {
      width: 60px;
      height: 60px;
      top: 30px;
      left: 30px;
      border-color: #6366f1;
      animation: rotate 6s linear infinite;
    }

    @keyframes rotate {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .cta-button {
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      color: #0a0e27;
      border: none;
      padding: 18px 50px;
      font-size: 1.2em;
      font-weight: 700;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 30px rgba(251, 191, 36, 0.3);
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .cta-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 40px rgba(251, 191, 36, 0.5);
    }

    /* Page 2: Input Form */
    .form-content {
      max-width: 650px;
      width: 100%;
    }

    .form-title {
      font-size: 2em;
      text-align: center;
      margin-bottom: 40px;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
    }

    .input-group {
      margin-bottom: 30px;
    }

    .input-label {
      display: block;
      margin-bottom: 12px;
      color: #c7d2fe;
      font-size: 1em;
      font-weight: 500;
    }

    .dream-input {
      width: 100%;
      min-height: 180px;
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 15px;
      padding: 20px;
      color: #ffffff;
      font-size: 1em;
      font-family: inherit;
      resize: vertical;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .dream-input:focus {
      outline: none;
      border-color: #8b5cf6;
      box-shadow: 0 0 20px rgba(139, 92, 246, 0.3);
    }

    .mood-selector {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      gap: 15px;
      margin-top: 15px;
    }

    .mood-option {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 12px;
      padding: 20px 10px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .mood-option:hover {
      border-color: #8b5cf6;
      transform: translateY(-2px);
    }

    .mood-option.selected {
      border-color: #fbbf24;
      background: rgba(251, 191, 36, 0.1);
    }

    .mood-icon {
      font-size: 2em;
      margin-bottom: 8px;
    }

    .mood-label {
      font-size: 0.9em;
      color: #c7d2fe;
    }

    .analyze-button {
      width: 100%;
      background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
      color: #ffffff;
      border: none;
      padding: 18px;
      font-size: 1.2em;
      font-weight: 700;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 30px rgba(139, 92, 246, 0.3);
      margin-top: 30px;
    }

    .analyze-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 40px rgba(139, 92, 246, 0.5);
    }

    .back-button {
      background: rgba(255, 255, 255, 0.1);
      color: #c7d2fe;
      border: 1px solid rgba(255, 255, 255, 0.2);
      padding: 12px 30px;
      font-size: 1em;
      font-weight: 600;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 20px;
      display: block;
      margin-left: auto;
      margin-right: auto;
    }

    .back-button:hover {
      background: rgba(255, 255, 255, 0.15);
      border-color: rgba(255, 255, 255, 0.3);
    }

    /* Page 3: Results */
    .results-content {
      max-width: 900px;
      width: 100%;
    }

    .results-title {
      font-size: 2.5em;
      text-align: center;
      margin-bottom: 50px;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
    }

    .primary-number {
      text-align: center;
      margin-bottom: 50px;
    }

    .number-display {
      font-size: 8em;
      font-weight: 900;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 50%, #d97706 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 0 60px rgba(251, 191, 36, 0.4);
      line-height: 1;
      margin-bottom: 15px;
    }

    .number-label {
      font-size: 1.2em;
      color: #c7d2fe;
      font-weight: 300;
    }

    .number-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
      margin-bottom: 50px;
    }

    .number-card {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      text-align: center;
      backdrop-filter: blur(10px);
      transition: all 0.3s ease;
    }

    .number-card:hover {
      transform: translateY(-5px);
      border-color: #8b5cf6;
      box-shadow: 0 15px 40px rgba(139, 92, 246, 0.3);
    }

    .card-number {
      font-size: 3em;
      font-weight: 800;
      color: #fbbf24;
      margin-bottom: 10px;
    }

    .card-label {
      font-size: 1em;
      color: #c7d2fe;
      margin-bottom: 15px;
    }

    .card-description {
      font-size: 0.9em;
      color: #a5b4fc;
      line-height: 1.5;
    }

    /* Energy Wheel */
    .energy-wheel-container {
      margin: 50px 0;
      text-align: center;
    }

    .wheel-title {
      font-size: 1.8em;
      color: #fbbf24;
      margin-bottom: 20px;
      font-weight: 600;
    }

    .wheel-description {
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.6;
      margin-bottom: 30px;
      text-align: center;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }

    .energy-wheel {
      width: 350px;
      height: 350px;
      margin: 0 auto;
      position: relative;
      border-radius: 50%;
      background: conic-gradient(
        from 0deg,
        rgba(251, 191, 36, 0.2) 0deg 72deg,
        rgba(139, 92, 246, 0.2) 72deg 144deg,
        rgba(99, 102, 241, 0.2) 144deg 216deg,
        rgba(217, 119, 6, 0.2) 216deg 288deg,
        rgba(139, 92, 246, 0.2) 288deg 360deg
      );
      border: 3px solid rgba(251, 191, 36, 0.5);
      box-shadow: 0 0 40px rgba(251, 191, 36, 0.3), inset 0 0 40px rgba(251, 191, 36, 0.1);
      animation: rotateWheel 30s linear infinite;
    }

    @keyframes rotateWheel {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .wheel-center {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 100px;
      height: 100px;
      background: radial-gradient(circle, #fbbf24 0%, #d97706 100%);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.5em;
      font-weight: 900;
      color: #0a0e27;
      box-shadow: 0 0 30px rgba(251, 191, 36, 0.6);
    }

    .wheel-labels {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
      margin-top: 40px;
    }

    .wheel-label-item {
      text-align: center;
    }

    .label-icon {
      font-size: 2em;
      margin-bottom: 8px;
    }

    .label-text {
      font-size: 0.9em;
      color: #c7d2fe;
      font-weight: 500;
    }

    .label-value {
      font-size: 0.85em;
      color: #a5b4fc;
      margin-top: 5px;
    }

    /* AI Explanation */
    .ai-explanation {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      margin-top: 40px;
      backdrop-filter: blur(10px);
    }

    .explanation-title {
      font-size: 1.5em;
      color: #fbbf24;
      margin-bottom: 20px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .explanation-text {
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.8;
    }

    /* Daily Advice */
    .daily-advice {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      margin-top: 30px;
      backdrop-filter: blur(10px);
    }

    .advice-title {
      font-size: 1.5em;
      color: #fbbf24;
      margin-bottom: 25px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .advice-content {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .advice-item {
      display: flex;
      gap: 15px;
      align-items: flex-start;
      padding: 20px;
      background: rgba(255, 255, 255, 0.03);
      border-radius: 15px;
      border-left: 4px solid #8b5cf6;
    }

    .advice-item.lucky-color {
      border-left-color: #fbbf24;
    }

    .advice-icon {
      font-size: 1.8em;
      flex-shrink: 0;
    }

    .advice-text {
      flex: 1;
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.6;
    }

    .advice-text strong {
      display: block;
      color: #fbbf24;
      margin-bottom: 8px;
      font-size: 1.05em;
    }

    .multi-color-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 15px;
      margin-top: 15px;
    }

    .color-aspect-item {
      display: flex;
      align-items: center;
      gap: 15px;
      padding: 15px;
      background: rgba(255, 255, 255, 0.03);
      border-radius: 12px;
      border-left: 3px solid;
      transition: all 0.3s ease;
    }

    .color-aspect-item:hover {
      background: rgba(255, 255, 255, 0.06);
      transform: translateX(5px);
    }

    .color-aspect-item.love { border-left-color: #E91E63; }
    .color-aspect-item.career { border-left-color: #D4AF37; }
    .color-aspect-item.money { border-left-color: #27AE60; }
    .color-aspect-item.health { border-left-color: #3498DB; }
    .color-aspect-item.wisdom { border-left-color: #8b5cf6; }

    .color-swatch {
      width: 50px;
      height: 50px;
      border-radius: 10px;
      background: #8b5cf6;
      border: 2px solid rgba(255, 255, 255, 0.3);
      box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);
      flex-shrink: 0;
    }

    .color-details {
      flex: 1;
    }

    .color-aspect-title {
      font-size: 1em;
      color: #fbbf24;
      font-weight: 600;
      margin-bottom: 5px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .color-name {
      font-size: 0.95em;
      color: #c7d2fe;
      margin-bottom: 4px;
    }

    .color-meaning {
      color: #a5b4fc;
      font-size: 0.85em;
      font-style: italic;
      line-height: 1.4;
    }

    @media (max-width: 768px) {
      .logo {
        font-size: 3em;
      }

      .tagline {
        font-size: 1.1em;
      }

      .number-display {
        font-size: 5em;
      }

      .energy-wheel {
        width: 280px;
        height: 280px;
      }

      .wheel-center {
        width: 80px;
        height: 80px;
        font-size: 2em;
      }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body>
  <div class="app-container"><!-- Cosmic Background -->
   <div class="cosmic-bg">
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>
   </div><!-- Page 1: Landing -->
   <div id="page1" class="page active">
    <div class="landing-content">
     <h1 class="logo" id="logoText">NUMORA</h1>
     <p class="tagline" id="taglineText">ถอดรหัสความฝันของคุณ ให้กลายเป็นตัวเลขมงคลเฉพาะบุคคล</p>
     <div class="mystical-symbol">
      <div class="symbol-ring ring1"></div>
      <div class="symbol-ring ring2"></div>
      <div class="symbol-ring ring3"></div>
     </div><button class="cta-button" id="ctaButton" onclick="navigateToPage(2)">เริ่มถอดรหัสความฝัน</button>
    </div>
   </div><!-- Page 2: Input Form -->
   <div id="page2" class="page">
    <div class="form-content">
     <h2 class="form-title">บอกเล่าความฝันหรือเหตุการณ์ของคุณ</h2>
     <div class="input-group"><label class="input-label" for="dreamInput">ความฝันหรือเหตุการณ์วันนี้</label> <textarea id="dreamInput" class="dream-input" placeholder="บอกเล่าความฝันหรือเหตุการณ์ที่เกิดขึ้นวันนี้..."></textarea>
     </div>
     <div class="input-group"><label class="input-label" id="moodLabel">อารมณ์ของคุณวันนี้ (เลือกได้หลายอารมณ์)</label>
      <div class="mood-selector">
       <div class="mood-option" data-mood="happy" onclick="selectMood('happy')">
        <div class="mood-icon">
         😊
        </div>
        <div class="mood-label">
         ดีใจ
        </div>
       </div>
       <div class="mood-option" data-mood="neutral" onclick="selectMood('neutral')">
        <div class="mood-icon">
         😐
        </div>
        <div class="mood-label">
         เฉย ๆ
        </div>
       </div>
       <div class="mood-option" data-mood="stressed" onclick="selectMood('stressed')">
        <div class="mood-icon">
         😰
        </div>
        <div class="mood-label">
         เครียด
        </div>
       </div>
       <div class="mood-option" data-mood="worried" onclick="selectMood('worried')">
        <div class="mood-icon">
         😟
        </div>
        <div class="mood-label">
         กังวล
        </div>
       </div>
       <div class="mood-option" data-mood="excited" onclick="selectMood('excited')">
        <div class="mood-icon">
         🤩
        </div>
        <div class="mood-label">
         ตื่นเต้น
        </div>
       </div>
      </div>
     </div><button class="analyze-button" id="analyzeButton" onclick="analyzeAndShowResults()">แปลงความฝันเป็นตัวเลข</button> <button class="back-button" onclick="navigateToPage(1)">กลับ</button>
    </div>
   </div><!-- Page 3: Results -->
   <div id="page3" class="page">
    <div class="results-content">
     <h2 class="results-title" id="resultTitle">เลขมงคลของคุณ</h2>
     <div class="primary-number">
      <div class="number-display" id="primaryNumber">
       7
      </div>
      <div class="number-label" id="primaryNumberLabel">
       เลขมงคลหลัก (หลักเดียว)
      </div>
     </div>
     <div class="number-cards">
      <div class="number-card">
       <div class="card-number" id="twoDigitNumber">
        37
       </div>
       <div class="card-label">
        เลขสองหลัก
       </div>
       <div class="card-description">
        เสริมพลังและโชคลาภ
       </div>
      </div>
      <div class="number-card">
       <div class="card-number" id="threeDigitNumber">
        547
       </div>
       <div class="card-label">
        เลขสามหลัก
       </div>
       <div class="card-description">
        นำพาสู่ความสำเร็จ
       </div>
      </div>
      <div class="number-card">
       <div class="card-number" id="cautionNumber">
        9
       </div>
       <div class="card-label" id="cautionNumberLabel">
        เลขที่ควรระวัง
       </div>
       <div class="card-description">
        ใช้ด้วยความระมัดระวัง
       </div>
      </div>
     </div>
     <div class="energy-wheel-container">
      <h3 class="wheel-title">วงจรพลังงานของคุณ</h3>
      <p class="wheel-description">วงจรพลังงานแสดงถึงพลังแห่งจักรวาลที่หมุนเวียนรอบตัวคุณในวันนี้ เลขมงคลหลักของคุณอยู่ที่ศูนย์กลางของวงจร ส่งผลต่อพลังงาน อารมณ์ และโชคชะตาตลอดทั้งวัน</p>
      <div class="energy-wheel">
       <div class="wheel-center" id="wheelCenter">
        7
       </div>
      </div>
      <div class="wheel-labels">
       <div class="wheel-label-item">
        <div class="label-icon">
         🔮
        </div>
        <div class="label-text">
         สัญลักษณ์
        </div>
        <div class="label-value">
         ดาวเจ็ดดวง
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         💫
        </div>
        <div class="label-text">
         อารมณ์
        </div>
        <div class="label-value">
         สงบและชัดเจน
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         🌊
        </div>
        <div class="label-text">
         การเปลี่ยนแปลง
        </div>
        <div class="label-value">
         ค่อยเป็นค่อยไป
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         ⏰
        </div>
        <div class="label-text">
         เวลาที่ดี
        </div>
        <div class="label-value">
         07:00 - 19:00
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         ✨
        </div>
        <div class="label-text">
         ความหมาย
        </div>
        <div class="label-value">
         ปัญญาและการเรียนรู้
        </div>
       </div>
      </div>
     </div>
     <div class="ai-explanation">
      <h3 class="explanation-title"><span>🤖</span> <span>AI วิเคราะห์ความฝันของคุณ</span></h3>
      <p class="explanation-text" id="aiExplanation">จากความฝันที่คุณบอกเล่า ระบบ AI ได้วิเคราะห์พบว่าคุณกำลังอยู่ในช่วงของการเรียนรู้และค้นพบสิ่งใหม่ ๆ ตัวเลข 7 สะท้อนถึงปัญญา การไตร่ตรอง และความเข้าใจลึกซึ้ง ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาคำตอบ และความหมายที่ลึกซึ้งยิ่งขึ้นในชีวิต เลขเสริม 3 และ 5 จะช่วยเสริมพลังความคิดสร้างสรรค์และการสื่อสาร ในขณะที่เลข 9 เป็นเลขที่ควรระวังเรื่องการปล่อยวางมากเกินไป</p>
     </div>
     <div class="daily-advice">
      <h3 class="advice-title"><span>💫</span> <span>คำแนะนำประจำวันนี้</span></h3>
      <div class="advice-content">
       <div class="advice-item">
        <div class="advice-icon">
         ✅
        </div>
        <div class="advice-text"><strong>สิ่งที่ควรทำวันนี้</strong> <span id="adviceDo">ใช้เวลาคิดและไตร่ตรองอย่างรอบคอบก่อนตัดสินใจสำคัญ นี่คือช่วงเวลาแห่งการค้นหาความจริง</span>
        </div>
       </div>
       <div class="advice-item">
        <div class="advice-icon">
         ⚠️
        </div>
        <div class="advice-text"><strong>สิ่งที่ควรหลีกเลี่ยง</strong> <span id="adviceAvoid">หลีกเลี่ยงการตัดสินใจด้วยอารมณ์ หรือปล่อยวางเรื่องสำคัญทิ้งไว้</span>
        </div>
       </div>
       <div class="advice-item lucky-color">
        <div class="advice-icon">
         👕
        </div>
        <div class="advice-text"><strong>สีเสื้อมงคลตามด้านต่าง ๆ</strong>
         <div id="colorRecommendations" class="multi-color-grid"><!-- Colors will be populated by JavaScript -->
         </div>
        </div>
       </div>
      </div>
     </div><button class="back-button" onclick="navigateToPage(1)">กลับสู่หน้าหลัก</button>
    </div>
   </div>
  </div>
  <script>
    const defaultConfig = {
      logo_text: "NUMORA",
      tagline: "ถอดรหัสความฝันของคุณ ให้กลายเป็นตัวเลขมงคลเฉพาะบุคคล",
      cta_button: "เริ่มถอดรหัสความฝัน",
      input_placeholder: "บอกเล่าความฝันที่ฝันมา หรือเหตุการณ์สำคัญที่เกิดขึ้นในวันนี้...",
      mood_label: "อารมณ์ของคุณวันนี้ (เลือกได้หลายอารมณ์)",
      analyze_button: "แปลงความฝันเป็นตัวเลข",
      result_title: "เลขมงคลของคุณ",
      primary_number_label: "เลขมงคลหลัก",
      support_number_label: "เลขเสริมดวง",
      caution_number_label: "เลขที่ควรระวัง",
      background_color: "#0a0e27",
      gold_color: "#fbbf24",
      purple_color: "#8b5cf6",
      text_color: "#ffffff",
      secondary_text_color: "#c7d2fe",
      font_family: "Inter",
      font_size: 16
    };

    let selectedMoods = [];

    async function onConfigChange(config) {
      const logoText = config.logo_text || defaultConfig.logo_text;
      const tagline = config.tagline || defaultConfig.tagline;
      const ctaButton = config.cta_button || defaultConfig.cta_button;
      const inputPlaceholder = config.input_placeholder || defaultConfig.input_placeholder;
      const moodLabel = config.mood_label || defaultConfig.mood_label;
      const analyzeButton = config.analyze_button || defaultConfig.analyze_button;
      const resultTitle = config.result_title || defaultConfig.result_title;
      const primaryNumberLabel = config.primary_number_label || defaultConfig.primary_number_label;
      const supportNumberLabel = config.support_number_label || defaultConfig.support_number_label;
      const cautionNumberLabel = config.caution_number_label || defaultConfig.caution_number_label;
      const fontFamily = config.font_family || defaultConfig.font_family;
      const fontSize = config.font_size || defaultConfig.font_size;
      const goldColor = config.gold_color || defaultConfig.gold_color;
      const purpleColor = config.purple_color || defaultConfig.purple_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const secondaryTextColor = config.secondary_text_color || defaultConfig.secondary_text_color;

      document.getElementById('logoText').textContent = logoText;
      document.getElementById('taglineText').textContent = tagline;
      document.getElementById('ctaButton').textContent = ctaButton;
      document.getElementById('dreamInput').placeholder = inputPlaceholder;
      document.getElementById('moodLabel').textContent = moodLabel;
      document.getElementById('analyzeButton').textContent = analyzeButton;
      document.getElementById('resultTitle').textContent = resultTitle;
      document.getElementById('primaryNumberLabel').textContent = primaryNumberLabel;
      document.getElementById('supportNumberLabel').textContent = supportNumberLabel;
      document.getElementById('cautionNumberLabel').textContent = cautionNumberLabel;

      document.body.style.fontFamily = `${fontFamily}, 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif`;
      document.body.style.fontSize = `${fontSize}px`;

      const headings = document.querySelectorAll('.logo, .form-title, .results-title');
      headings.forEach(h => h.style.fontSize = `${fontSize * 2.5}px`);

      const buttons = document.querySelectorAll('.cta-button, .analyze-button');
      buttons.forEach(btn => btn.style.fontSize = `${fontSize * 1.2}px`);

      const labels = document.querySelectorAll('.tagline, .input-label, .number-label');
      labels.forEach(label => label.style.fontSize = `${fontSize * 1.1}px`);
    }

    function navigateToPage(pageNumber) {
      document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
      document.getElementById(`page${pageNumber}`).classList.add('active');
    }

    function selectMood(mood) {
      const option = document.querySelector(`[data-mood="${mood}"]`);
      
      if (selectedMoods.includes(mood)) {
        selectedMoods = selectedMoods.filter(m => m !== mood);
        option.classList.remove('selected');
      } else {
        selectedMoods.push(mood);
        option.classList.add('selected');
      }
    }

    const numberMeanings = {
      1: {
        explanation: "คุณกำลังอยู่ในช่วงของการเริ่มต้นใหม่และการเป็นผู้นำ ตัวเลข 1 สะท้อนถึงความมั่นใจ ความกล้าหาญ และพลังแห่งการสร้างสรรค์ ความฝันของคุณบ่งบอกว่าถึงเวลาแล้วที่จะก้าวออกไปและเริ่มต้นสิ่งใหม่ ๆ",
        doAdvice: "จงมั่นใจในตัวเองและกล้าที่จะเริ่มต้นโครงการใหม่ นี่คือช่วงเวลาที่ดีสำหรับการเป็นผู้นำ",
        avoidAdvice: "หลีกเลี่ยงความลังเลและการรอคอยให้คนอื่นเริ่มก่อน อย่ากลัวที่จะโดดเด่น",
        colorsByAspect: {
          love: { color: "#E91E63", name: "สีชมพูบานเย็น", meaning: "ดึงดูดความรักใหม่และเพิ่มเสน่ห์", icon: "💖" },
          career: { color: "#E74C3C", name: "สีแดง", meaning: "เสริมความมั่นใจและความกล้าหาญในการทำงาน", icon: "💼" },
          money: { color: "#F39C12", name: "สีส้มทอง", meaning: "ดึงดูดโชคลาภและโอกาสทางการเงิน", icon: "💰" },
          health: { color: "#E67E22", name: "สีส้มอิฐ", meaning: "เพิ่มพลังงานและความแข็งแรง", icon: "💪" },
          wisdom: { color: "#9B59B6", name: "สีม่วงอ่อน", meaning: "กระตุ้นความคิดสร้างสรรค์และการตัดสินใจ", icon: "🧠" }
        }
      },
      2: {
        explanation: "คุณกำลังอยู่ในช่วงของความสมดุลและความสัมพันธ์ ตัวเลข 2 สะท้อนถึงการประสานงาน ความอ่อนโยน และการทำงานเป็นทีม ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาความกลมกลืนและความเข้าใจกับผู้อื่น",
        doAdvice: "มุ่งเน้นการสร้างความสัมพันธ์ที่ดีและรับฟังผู้อื่น ความร่วมมือจะนำมาซึ่งความสำเร็จ",
        avoidAdvice: "หลีกเลี่ยงการขัดแย้งที่ไม่จำเป็น อย่าเอาแต่ใจตัวเองหรือดื้อรั้นจนเกินไป",
        colorsByAspect: {
          love: { color: "#FFC0CB", name: "สีชมพูพีช", meaning: "เสริมความอ่อนหวานและความเข้าใจในความสัมพันธ์", icon: "💖" },
          career: { color: "#F39C12", name: "สีส้ม", meaning: "ส่งเสริมความร่วมมือและการทำงานเป็นทีม", icon: "💼" },
          money: { color: "#FFD700", name: "สีทองอ่อน", meaning: "ดึงดูดความร่ำรวยผ่านความสัมพันธ์", icon: "💰" },
          health: { color: "#87CEEB", name: "สีฟ้าอ่อน", meaning: "ช่วยลดความเครียดและสร้างความสงบ", icon: "💪" },
          wisdom: { color: "#DDA0DD", name: "สีม่วงพลัม", meaning: "เพิ่มสัญชาตญาณและความเข้าใจผู้อื่น", icon: "🧠" }
        }
      },
      3: {
        explanation: "คุณกำลังอยู่ในช่วงของความคิดสร้างสรรค์และการแสดงออก ตัวเลข 3 สะท้อนถึงความสนุกสนาน การสื่อสาร และพลังแห่งจินตนาการ ความฝันของคุณบ่งบอกว่าถึงเวลาแล้วที่จะแสดงความสามารถของตัวเอง",
        doAdvice: "ปลดปล่อยความคิดสร้างสรรค์และแสดงออกอย่างเต็มที่ นี่คือช่วงเวลาแห่งความสนุกและความสุข",
        avoidAdvice: "หลีกเลี่ยงการกดอารมณ์หรือเก็บความรู้สึกไว้ข้างใน อย่าเครียดจนเกินไป",
        colorsByAspect: {
          love: { color: "#FF69B4", name: "สีชมพูสดใส", meaning: "เพิ่มความสนุกและความตื่นเต้นในความรัก", icon: "💖" },
          career: { color: "#F1C40F", name: "สีเหลือง", meaning: "กระตุ้นความคิดสร้างสรรค์และการสื่อสาร", icon: "💼" },
          money: { color: "#FFA500", name: "สีส้มสด", meaning: "ดึงดูดโอกาสจากความคิดสร้างสรรค์", icon: "💰" },
          health: { color: "#32CD32", name: "สีเขียวมะนาว", meaning: "เพิ่มพลังชีวิตและความร่าเริง", icon: "💪" },
          wisdom: { color: "#00CED1", name: "สีฟ้าเขียว", meaning: "เปิดกว้างสู่ความคิดใหม่ ๆ", icon: "🧠" }
        }
      },
      4: {
        explanation: "คุณกำลังอยู่ในช่วงของความมั่นคงและการวางรากฐาน ตัวเลข 4 สะท้อนถึงความมีระเบียบ ความอดทน และการทำงานหนัก ความฝันของคุณบ่งบอกว่าคุณกำลังสร้างพื้นฐานที่มั่นคงสำหรับอนาคต",
        doAdvice: "มุ่งมั่นทำงานอย่างเป็นระบบและมีแผนที่ชัดเจน ความอดทนจะนำพาคุณไปสู่เป้าหมาย",
        avoidAdvice: "หลีกเลี่ยงการรีบร้อนหรือข้ามขั้นตอนสำคัญ อย่าประมาทหรือขาดความรอบคอบ",
        colorsByAspect: {
          love: { color: "#8B4513", name: "สีน้ำตาลอ่อน", meaning: "สร้างความมั่นคงและความไว้วางใจ", icon: "💖" },
          career: { color: "#4A4A4A", name: "สีเทาเข้ม", meaning: "เสริมความเป็นมืออาชีพและความน่าเชื่อถือ", icon: "💼" },
          money: { color: "#27AE60", name: "สีเขียว", meaning: "สร้างรากฐานการเงินที่มั่นคง", icon: "💰" },
          health: { color: "#2E8B57", name: "สีเขียวเข้ม", meaning: "เสริมความแข็งแรงและความอดทน", icon: "💪" },
          wisdom: { color: "#696969", name: "สีเทากลาง", meaning: "เพิ่มความมีระเบียบและการวางแผน", icon: "🧠" }
        }
      },
      5: {
        explanation: "คุณกำลังอยู่ในช่วงของการผจญภัยและการเปลี่ยนแปลง ตัวเลข 5 สะท้อนถึงความอิสระ ความยืดหยุ่น และการเรียนรู้สิ่งใหม่ ความฝันของคุณบ่งบอกว่าคุณพร้อมสำหรับประสบการณ์ใหม่ ๆ",
        doAdvice: "เปิดรับสิ่งใหม่และอย่ากลัวที่จะเปลี่ยนแปลง นี่คือช่วงเวลาแห่งการเติบโตและการค้นพบ",
        avoidAdvice: "หลีกเลี่ยงการยึดติดกับความเคยชินมากเกินไป อย่ากลัวความเสี่ยงที่สร้างสรรค์",
        colorsByAspect: {
          love: { color: "#FF6347", name: "สีแดงส้ม", meaning: "เพิ่มความตื่นเต้นและการผจญภัยในความรัก", icon: "💖" },
          career: { color: "#3498DB", name: "สีฟ้า", meaning: "เปิดโอกาสใหม่ ๆ และการเปลี่ยนแปลง", icon: "💼" },
          money: { color: "#1ABC9C", name: "สีเขียวมิ้นต์", meaning: "ดึงดูดโอกาสที่ไม่คาดคิด", icon: "💰" },
          health: { color: "#20B2AA", name: "สีเขียวทะเล", meaning: "เพิ่มความยืดหยุ่นและการปรับตัว", icon: "💪" },
          wisdom: { color: "#4169E1", name: "สีน้ำเงินรอยัล", meaning: "ขยายขอบเขตความคิดและการเรียนรู้", icon: "🧠" }
        }
      },
      6: {
        explanation: "คุณกำลังอยู่ในช่วงของความรับผิดชอบและการดูแล ตัวเลข 6 สะท้อนถึงความรัก ครอบครัว และความสมดุลในชีวิต ความฝันของคุณบ่งบอกว่าคุณกำลังมุ่งเน้นที่การสร้างความอบอุ่นและความปลอดภัย",
        doAdvice: "ใส่ใจคนรอบข้างและสร้างความสัมพันธ์ที่อบอุ่น นี่คือเวลาที่ดีสำหรับครอบครัวและคนที่รัก",
        avoidAdvice: "หลีกเลี่ยงการเอาแต่ใจตัวเองหรือไม่แยแสคนรอบข้าง อย่าเพิกเฉยต่อความรู้สึกของผู้อื่น",
        colorsByAspect: {
          love: { color: "#E91E63", name: "สีชมพูเข้ม", meaning: "เสริมความรักและความผูกพัน", icon: "💖" },
          career: { color: "#C0392B", name: "สีแดงเลือดหมู", meaning: "เสริมความรับผิดชอบและความน่าเชื่อถือ", icon: "💼" },
          money: { color: "#D4AF37", name: "สีทอง", meaning: "ดึงดูดความมั่งคั่งผ่านการดูแลและรับผิดชอบ", icon: "💰" },
          health: { color: "#2ECC71", name: "สีเขียวสด", meaning: "เสริมสุขภาพและความสมดุลทางใจ", icon: "💪" },
          wisdom: { color: "#34495E", name: "สีเทาน้ำเงิน", meaning: "เพิ่มความเข้าใจและความเห็นอกเห็นใจ", icon: "🧠" }
        }
      },
      7: {
        explanation: "คุณกำลังอยู่ในช่วงของการเรียนรู้และค้นพบสิ่งใหม่ ๆ ตัวเลข 7 สะท้อนถึงปัญญา การไตร่ตรอง และความเข้าใจลึกซึ้ง ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาคำตอบและความหมายที่ลึกซึ้งยิ่งขึ้นในชีวิต",
        doAdvice: "ใช้เวลาคิดและไตร่ตรองอย่างรอบคอบก่อนตัดสินใจสำคัญ นี่คือช่วงเวลาแห่งการค้นหาความจริง",
        avoidAdvice: "หลีกเลี่ยงการตัดสินใจด้วยอารมณ์ หรือปล่อยวางเรื่องสำคัญทิ้งไว้",
        colorsByAspect: {
          love: { color: "#C39BD3", name: "สีม่วงลาเวนเดอร์", meaning: "เสริมความเข้าใจลึกซึ้งในความสัมพันธ์", icon: "💖" },
          career: { color: "#8b5cf6", name: "สีม่วง", meaning: "เสริมปัญญาและความคิดวิเคราะห์", icon: "💼" },
          money: { color: "#7D3C98", name: "สีม่วงเข้ม", meaning: "ดึงดูดโอกาสจากความรู้และทักษะ", icon: "💰" },
          health: { color: "#5DADE2", name: "สีฟ้าสดใส", meaning: "เสริมสุขภาพทางจิตและความสงบ", icon: "💪" },
          wisdom: { color: "#6C3483", name: "สีม่วงพลัม", meaning: "กระตุ้นปัญญาและสัญชาตญาณ", icon: "🧠" }
        }
      },
      8: {
        explanation: "คุณกำลังอยู่ในช่วงของความสำเร็จและความมั่งคั่ง ตัวเลข 8 สะท้อนถึงพลังอำนาจ ความร่ำรวย และผลสำเร็จที่จับต้องได้ ความฝันของคุณบ่งบอกว่าคุณกำลังเข้าใกล้เป้าหมายที่ตั้งไว้",
        doAdvice: "มุ่งมั่นทำงานเพื่อความสำเร็จและอย่ากลัวที่จะตั้งเป้าหมายใหญ่ ๆ นี่คือช่วงเวลาแห่งความเจริญก้าวหน้า",
        avoidAdvice: "หลีกเลี่ยงความโลภหรือการใช้อำนาจในทางที่ผิด อย่าลืมคุณค่าที่แท้จริงของชีวิต",
        colorsByAspect: {
          love: { color: "#EC7063", name: "สีแดงอมชมพู", meaning: "เสริมความหลังใหลและความมุ่งมั่นในความรัก", icon: "💖" },
          career: { color: "#D4AF37", name: "สีทอง", meaning: "เสริมความสำเร็จและความเป็นผู้นำ", icon: "💼" },
          money: { color: "#27AE60", name: "สีเขียวเข้ม", meaning: "ดึงดูดความร่ำรวยและโชคลาภ", icon: "💰" },
          health: { color: "#D68910", name: "สีส้มทอง", meaning: "เพิ่มพลังและความแข็งแรง", icon: "💪" },
          wisdom: { color: "#512E5F", name: "สีม่วงมงคล", meaning: "เพิ่มปัญญาในการใช้อำนาจอย่างถูกต้อง", icon: "🧠" }
        }
      },
      9: {
        explanation: "คุณกำลังอยู่ในช่วงของการสิ้นสุดและการเริ่มต้นใหม่ ตัวเลข 9 สะท้อนถึงความเมตตา ปัญญา และการปล่อยวาง ความฝันของคุณบ่งบอกว่าถึงเวลาแล้วที่จะยุติบางสิ่งเพื่อเปิดทางให้สิ่งใหม่",
        doAdvice: "เรียนรู้ที่จะให้อภัยและปล่อยวางสิ่งที่ผ่านไป นี่คือเวลาแห่งการเติมเต็มและความเข้าใจ",
        avoidAdvice: "หลีกเลี่ยงการยึดติดกับอดีตหรือไม่ยอมรับความเปลี่ยนแปลง อย่าเห็นแก่ตัวจนเกินไป",
        colorsByAspect: {
          love: { color: "#D7BDE2", name: "สีม่วงอ่อน", meaning: "เสริมความเมตตาและการให้อภัย", icon: "💖" },
          career: { color: "#9B59B6", name: "สีม่วงอมชมพู", meaning: "เสริมปัญญาและความเข้าใจผู้อื่น", icon: "💼" },
          money: { color: "#BB8FCE", name: "สีม่วงพาสเทล", meaning: "ดึงดูดความมั่งคั่งจากการปล่อยวาง", icon: "💰" },
          health: { color: "#AED6F1", name: "สีฟ้าอ่อน", meaning: "เสริมการปลดปล่อยและความสงบ", icon: "💪" },
          wisdom: { color: "#7FB3D5", name: "สีฟ้าปัญญา", meaning: "เสริมการเติมเต็มและความเข้าใจชีวิต", icon: "🧠" }
        }
      }
    };

    function renderColorRecommendations(colors) {
      const container = document.getElementById('colorRecommendations');
      
      const aspects = [
        { key: 'love', title: 'ความรัก', class: 'love' },
        { key: 'career', title: 'การงาน', class: 'career' },
        { key: 'money', title: 'การเงิน', class: 'money' },
        { key: 'health', title: 'สุขภาพ', class: 'health' },
        { key: 'wisdom', title: 'ปัญญา', class: 'wisdom' }
      ];

      container.innerHTML = aspects.map(aspect => {
        const colorData = colors[aspect.key];
        return `
          <div class="color-aspect-item ${aspect.class}">
            <div class="color-swatch" style="background: ${colorData.color}; box-shadow: 0 4px 15px ${colorData.color}66;"></div>
            <div class="color-details">
              <div class="color-aspect-title">
                <span>${colorData.icon}</span>
                <span>${aspect.title}</span>
              </div>
              <div class="color-name">${colorData.name}</div>
              <div class="color-meaning">${colorData.meaning}</div>
            </div>
          </div>
        `;
      }).join('');
    }

    function analyzeAndShowResults() {
      const dreamText = document.getElementById('dreamInput').value;
      
      if (!dreamText.trim()) {
        return;
      }

      const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
      const randomPrimary = numbers[Math.floor(Math.random() * numbers.length)];
      const randomTwoDigit = Math.floor(Math.random() * 90) + 10;
      const randomThreeDigit = Math.floor(Math.random() * 900) + 100;
      const randomCaution = numbers[Math.floor(Math.random() * numbers.length)];

      document.getElementById('primaryNumber').textContent = randomPrimary;
      document.getElementById('wheelCenter').textContent = randomPrimary;
      document.getElementById('twoDigitNumber').textContent = randomTwoDigit;
      document.getElementById('threeDigitNumber').textContent = randomThreeDigit;
      document.getElementById('cautionNumber').textContent = randomCaution;

      const meaning = numberMeanings[randomPrimary];
      document.getElementById('aiExplanation').textContent = meaning.explanation;
      document.getElementById('adviceDo').textContent = meaning.doAdvice;
      document.getElementById('adviceAvoid').textContent = meaning.avoidAdvice;
      
      renderColorRecommendations(meaning.colorsByAspect);

      navigateToPage(3);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.gold_color || defaultConfig.gold_color,
              set: (value) => {
                config.gold_color = value;
                window.elementSdk.setConfig({ gold_color: value });
              }
            },
            {
              get: () => config.purple_color || defaultConfig.purple_color,
              set: (value) => {
                config.purple_color = value;
                window.elementSdk.setConfig({ purple_color: value });
              }
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => {
                config.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () => config.secondary_text_color || defaultConfig.secondary_text_color,
              set: (value) => {
                config.secondary_text_color = value;
                window.elementSdk.setConfig({ secondary_text_color: value });
              }
            }
          ],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => {
              config.font_family = value;
              window.elementSdk.setConfig({ font_family: value });
            }
          },
          fontSizeable: {
            get: () => config.font_size || defaultConfig.font_size,
            set: (value) => {
              config.font_size = value;
              window.elementSdk.setConfig({ font_size: value });
            }
          }
        }),
        mapToEditPanelValues: (config) => new Map([
          ["logo_text", config.logo_text || defaultConfig.logo_text],
          ["tagline", config.tagline || defaultConfig.tagline],
          ["cta_button", config.cta_button || defaultConfig.cta_button],
          ["input_placeholder", config.input_placeholder || defaultConfig.input_placeholder],
          ["mood_label", config.mood_label || defaultConfig.mood_label],
          ["analyze_button", config.analyze_button || defaultConfig.analyze_button],
          ["result_title", config.result_title || defaultConfig.result_title],
          ["primary_number_label", config.primary_number_label || defaultConfig.primary_number_label],
          ["support_number_label", config.support_number_label || defaultConfig.support_number_label],
          ["caution_number_label", config.caution_number_label || defaultConfig.caution_number_label]
        ])
      });
    }
  </script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NUMORA - ถอดรหัสความฝันเป็นตัวเลขมงคล</title>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    body {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #0a0e27 0%, #1a1147 50%, #2d1b69 100%);
      color: #ffffff;
      width: 100%;
      height: 100%;
      overflow-x: hidden;
    }

    * {
      box-sizing: border-box;
    }

    .app-container {
      width: 100%;
      min-height: 100%;
      position: relative;
      overflow: hidden;
    }

    /* Animated Background Effects */
    .cosmic-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    .orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(60px);
      opacity: 0.3;
      animation: float 20s infinite ease-in-out;
    }

    .orb1 {
      width: 300px;
      height: 300px;
      background: radial-gradient(circle, #6366f1 0%, transparent 70%);
      top: 10%;
      left: 20%;
      animation-delay: 0s;
    }

    .orb2 {
      width: 250px;
      height: 250px;
      background: radial-gradient(circle, #8b5cf6 0%, transparent 70%);
      bottom: 20%;
      right: 15%;
      animation-delay: 5s;
    }

    .orb3 {
      width: 200px;
      height: 200px;
      background: radial-gradient(circle, #d97706 0%, transparent 70%);
      top: 50%;
      left: 50%;
      animation-delay: 10s;
    }

    @keyframes float {
      0%, 100% { transform: translate(0, 0) scale(1); }
      25% { transform: translate(30px, -30px) scale(1.1); }
      50% { transform: translate(-20px, 20px) scale(0.9); }
      75% { transform: translate(20px, 10px) scale(1.05); }
    }

    /* Page Container */
    .page {
      position: relative;
      z-index: 1;
      min-height: 100%;
      display: none;
      padding: 40px 20px;
    }

    .page.active {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    /* Page 1: Landing */
    .landing-content {
      text-align: center;
      max-width: 700px;
      width: 100%;
    }

    .logo {
      font-size: 4.5em;
      font-weight: 800;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 50%, #d97706 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 20px;
      letter-spacing: 8px;
      text-shadow: 0 0 40px rgba(251, 191, 36, 0.3);
      animation: glow 3s ease-in-out infinite;
    }

    @keyframes glow {
      0%, 100% { filter: drop-shadow(0 0 20px rgba(251, 191, 36, 0.4)); }
      50% { filter: drop-shadow(0 0 40px rgba(251, 191, 36, 0.7)); }
    }

    .tagline {
      font-size: 1.3em;
      color: #c7d2fe;
      margin-bottom: 50px;
      line-height: 1.6;
      font-weight: 300;
    }

    .mystical-symbol {
      width: 120px;
      height: 120px;
      margin: 30px auto;
      position: relative;
    }

    .symbol-ring {
      position: absolute;
      border: 2px solid #8b5cf6;
      border-radius: 50%;
      opacity: 0.6;
    }

    .ring1 {
      width: 120px;
      height: 120px;
      animation: rotate 10s linear infinite;
    }

    .ring2 {
      width: 90px;
      height: 90px;
      top: 15px;
      left: 15px;
      border-color: #fbbf24;
      animation: rotate 8s linear infinite reverse;
    }

    .ring3 {
      width: 60px;
      height: 60px;
      top: 30px;
      left: 30px;
      border-color: #6366f1;
      animation: rotate 6s linear infinite;
    }

    @keyframes rotate {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .cta-button {
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      color: #0a0e27;
      border: none;
      padding: 18px 50px;
      font-size: 1.2em;
      font-weight: 700;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 30px rgba(251, 191, 36, 0.3);
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .cta-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 40px rgba(251, 191, 36, 0.5);
    }

    /* Page 2: Input Form */
    .form-content {
      max-width: 650px;
      width: 100%;
    }

    .form-title {
      font-size: 2em;
      text-align: center;
      margin-bottom: 40px;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
    }

    .input-group {
      margin-bottom: 30px;
    }

    .input-label {
      display: block;
      margin-bottom: 12px;
      color: #c7d2fe;
      font-size: 1em;
      font-weight: 500;
    }

    .dream-input {
      width: 100%;
      min-height: 180px;
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 15px;
      padding: 20px;
      color: #ffffff;
      font-size: 1em;
      font-family: inherit;
      resize: vertical;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .dream-input:focus {
      outline: none;
      border-color: #8b5cf6;
      box-shadow: 0 0 20px rgba(139, 92, 246, 0.3);
    }

    .mood-selector {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      gap: 15px;
      margin-top: 15px;
    }

    .mood-option {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 12px;
      padding: 20px 10px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .mood-option:hover {
      border-color: #8b5cf6;
      transform: translateY(-2px);
    }

    .mood-option.selected {
      border-color: #fbbf24;
      background: rgba(251, 191, 36, 0.1);
    }

    .mood-icon {
      font-size: 2em;
      margin-bottom: 8px;
    }

    .mood-label {
      font-size: 0.9em;
      color: #c7d2fe;
    }

    .analyze-button {
      width: 100%;
      background: linear-gradient(135deg, #8b5cf6 0%, #6366f1 100%);
      color: #ffffff;
      border: none;
      padding: 18px;
      font-size: 1.2em;
      font-weight: 700;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 10px 30px rgba(139, 92, 246, 0.3);
      margin-top: 30px;
    }

    .analyze-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 15px 40px rgba(139, 92, 246, 0.5);
    }

    .back-button {
      background: rgba(255, 255, 255, 0.1);
      color: #c7d2fe;
      border: 1px solid rgba(255, 255, 255, 0.2);
      padding: 12px 30px;
      font-size: 1em;
      font-weight: 600;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 20px;
      display: block;
      margin-left: auto;
      margin-right: auto;
    }

    .back-button:hover {
      background: rgba(255, 255, 255, 0.15);
      border-color: rgba(255, 255, 255, 0.3);
    }

    /* Page 3: Results */
    .results-content {
      max-width: 900px;
      width: 100%;
    }

    .results-title {
      font-size: 2.5em;
      text-align: center;
      margin-bottom: 50px;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
    }

    .primary-number {
      text-align: center;
      margin-bottom: 50px;
    }

    .number-display {
      font-size: 8em;
      font-weight: 900;
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 50%, #d97706 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 0 60px rgba(251, 191, 36, 0.4);
      line-height: 1;
      margin-bottom: 15px;
    }

    .number-label {
      font-size: 1.2em;
      color: #c7d2fe;
      font-weight: 300;
    }

    .number-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
      margin-bottom: 50px;
    }

    .number-card {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      text-align: center;
      backdrop-filter: blur(10px);
      transition: all 0.3s ease;
    }

    .number-card:hover {
      transform: translateY(-5px);
      border-color: #8b5cf6;
      box-shadow: 0 15px 40px rgba(139, 92, 246, 0.3);
    }

    .card-number {
      font-size: 3em;
      font-weight: 800;
      color: #fbbf24;
      margin-bottom: 10px;
    }

    .card-label {
      font-size: 1em;
      color: #c7d2fe;
      margin-bottom: 15px;
    }

    .card-description {
      font-size: 0.9em;
      color: #a5b4fc;
      line-height: 1.5;
    }

    /* Energy Wheel */
    .energy-wheel-container {
      margin: 50px 0;
      text-align: center;
    }

    .wheel-title {
      font-size: 1.8em;
      color: #fbbf24;
      margin-bottom: 20px;
      font-weight: 600;
    }

    .wheel-description {
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.6;
      margin-bottom: 30px;
      text-align: center;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }

    .energy-wheel {
      width: 350px;
      height: 350px;
      margin: 0 auto;
      position: relative;
      border-radius: 50%;
      background: conic-gradient(
        from 0deg,
        rgba(251, 191, 36, 0.2) 0deg 72deg,
        rgba(139, 92, 246, 0.2) 72deg 144deg,
        rgba(99, 102, 241, 0.2) 144deg 216deg,
        rgba(217, 119, 6, 0.2) 216deg 288deg,
        rgba(139, 92, 246, 0.2) 288deg 360deg
      );
      border: 3px solid rgba(251, 191, 36, 0.5);
      box-shadow: 0 0 40px rgba(251, 191, 36, 0.3), inset 0 0 40px rgba(251, 191, 36, 0.1);
      animation: rotateWheel 30s linear infinite;
    }

    @keyframes rotateWheel {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .wheel-center {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 100px;
      height: 100px;
      background: radial-gradient(circle, #fbbf24 0%, #d97706 100%);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.5em;
      font-weight: 900;
      color: #0a0e27;
      box-shadow: 0 0 30px rgba(251, 191, 36, 0.6);
    }

    .wheel-labels {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
      margin-top: 40px;
    }

    .wheel-label-item {
      text-align: center;
    }

    .label-icon {
      font-size: 2em;
      margin-bottom: 8px;
    }

    .label-text {
      font-size: 0.9em;
      color: #c7d2fe;
      font-weight: 500;
    }

    .label-value {
      font-size: 0.85em;
      color: #a5b4fc;
      margin-top: 5px;
    }

    /* AI Explanation */
    .ai-explanation {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      margin-top: 40px;
      backdrop-filter: blur(10px);
    }

    .explanation-title {
      font-size: 1.5em;
      color: #fbbf24;
      margin-bottom: 20px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .explanation-text {
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.8;
    }

    /* Daily Advice */
    .daily-advice {
      background: rgba(255, 255, 255, 0.05);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 20px;
      padding: 30px;
      margin-top: 30px;
      backdrop-filter: blur(10px);
    }

    .advice-title {
      font-size: 1.5em;
      color: #fbbf24;
      margin-bottom: 25px;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .advice-content {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .advice-item {
      display: flex;
      gap: 15px;
      align-items: flex-start;
      padding: 20px;
      background: rgba(255, 255, 255, 0.03);
      border-radius: 15px;
      border-left: 4px solid #8b5cf6;
    }

    .advice-item.lucky-color {
      border-left-color: #fbbf24;
    }

    .advice-icon {
      font-size: 1.8em;
      flex-shrink: 0;
    }

    .advice-text {
      flex: 1;
      font-size: 1em;
      color: #c7d2fe;
      line-height: 1.6;
    }

    .advice-text strong {
      display: block;
      color: #fbbf24;
      margin-bottom: 8px;
      font-size: 1.05em;
    }

    .color-recommendation {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-top: 10px;
    }

    .multi-color-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 15px;
      margin-top: 15px;
    }

    .color-aspect-item {
      display: flex;
      align-items: center;
      gap: 15px;
      padding: 15px;
      background: rgba(255, 255, 255, 0.03);
      border-radius: 12px;
      border-left: 3px solid;
      transition: all 0.3s ease;
    }

    .color-aspect-item:hover {
      background: rgba(255, 255, 255, 0.06);
      transform: translateX(5px);
    }

    .color-aspect-item.love { border-left-color: #E91E63; }
    .color-aspect-item.career { border-left-color: #D4AF37; }
    .color-aspect-item.money { border-left-color: #27AE60; }
    .color-aspect-item.health { border-left-color: #3498DB; }
    .color-aspect-item.wisdom { border-left-color: #8b5cf6; }

    .color-swatch {
      width: 50px;
      height: 50px;
      border-radius: 10px;
      background: #8b5cf6;
      border: 2px solid rgba(255, 255, 255, 0.3);
      box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);
      flex-shrink: 0;
    }

    .color-details {
      flex: 1;
    }

    .color-aspect-title {
      font-size: 1em;
      color: #fbbf24;
      font-weight: 600;
      margin-bottom: 5px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .color-name {
      font-size: 0.95em;
      color: #c7d2fe;
      margin-bottom: 4px;
    }

    .color-meaning {
      color: #a5b4fc;
      font-size: 0.85em;
      font-style: italic;
      line-height: 1.4;
    }

    @media (max-width: 768px) {
      .logo {
        font-size: 3em;
      }

      .tagline {
        font-size: 1.1em;
      }

      .number-display {
        font-size: 5em;
      }

      .energy-wheel {
        width: 280px;
        height: 280px;
      }

      .wheel-center {
        width: 80px;
        height: 80px;
        font-size: 2em;
      }
    }
  </style>
  <div class="app-container"><!-- Cosmic Background -->
   <div class="cosmic-bg">
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>
   </div><!-- Page 1: Landing -->
   <div id="page1" class="page active">
    <div class="landing-content">
     <h1 class="logo" id="logoText">NUMORA</h1>
     <p class="tagline" id="taglineText">ถอดรหัสความฝันของคุณ ให้กลายเป็นตัวเลขมงคลเฉพาะบุคคล</p>
     <div class="mystical-symbol">
      <div class="symbol-ring ring1"></div>
      <div class="symbol-ring ring2"></div>
      <div class="symbol-ring ring3"></div>
     </div><button class="cta-button" id="ctaButton" onclick="navigateToPage(2)">เริ่มถอดรหัสความฝัน</button>
    </div>
   </div><!-- Page 2: Input Form -->
   <div id="page2" class="page">
    <div class="form-content">
     <h2 class="form-title">บอกเล่าความฝันหรือเหตุการณ์ของคุณ</h2>
     <div class="input-group"><label class="input-label" for="dreamInput">ความฝัน���รือเหตุก���รณ์วันนี้</label> <textarea id="dreamInput" class="dream-input" placeholder="บอกเล่าความฝันหรือเหตุการณ์ที่เกิดขึ้นวันนี้..."></textarea>
     </div>
     <div class="input-group"><label class="input-label" id="moodLabel">อารมณ์ของคุณวันนี้ (เลือกได้หลายอารมณ์)</label>
      <div class="mood-selector">
       <div class="mood-option" data-mood="happy" onclick="selectMood('happy')">
        <div class="mood-icon">
         😊
        </div>
        <div class="mood-label">
         ดีใจ
        </div>
       </div>
       <div class="mood-option" data-mood="neutral" onclick="selectMood('neutral')">
        <div class="mood-icon">
         😐
        </div>
        <div class="mood-label">
         เฉย ๆ
        </div>
       </div>
       <div class="mood-option" data-mood="stressed" onclick="selectMood('stressed')">
        <div class="mood-icon">
         😰
        </div>
        <div class="mood-label">
         เครียด
        </div>
       </div>
       <div class="mood-option" data-mood="worried" onclick="selectMood('worried')">
        <div class="mood-icon">
         😟
        </div>
        <div class="mood-label">
         กังวล
        </div>
       </div>
       <div class="mood-option" data-mood="excited" onclick="selectMood('excited')">
        <div class="mood-icon">
         🤩
        </div>
        <div class="mood-label">
         ตื่นเต้น
        </div>
       </div>
      </div>
     </div><button class="analyze-button" id="analyzeButton" onclick="analyzeAndShowResults()">แปลงความฝันเป็นตัวเลข</button> <button class="back-button" onclick="navigateToPage(1)">กลับ</button>
    </div>
   </div><!-- Page 3: Results -->
   <div id="page3" class="page">
    <div class="results-content">
     <h2 class="results-title" id="resultTitle">เลขมงคลของคุณ</h2>
     <div class="primary-number">
      <div class="number-display" id="primaryNumber">
       7
      </div>
      <div class="number-label" id="primaryNumberLabel">
       เลขมงคลหลัก (หลักเดียว)
      </div>
     </div>
     <div class="number-cards">
      <div class="number-card">
       <div class="card-number" id="twoDigitNumber">
        37
       </div>
       <div class="card-label">
        เลขสองหลัก
       </div>
       <div class="card-description">
        เสริมพลังและโชคลาภ
       </div>
      </div>
      <div class="number-card">
       <div class="card-number" id="threeDigitNumber">
        547
       </div>
       <div class="card-label">
        เลขสามหลัก
       </div>
       <div class="card-description">
        นำพาสู่ความสำเร็จ
       </div>
      </div>
      <div class="number-card">
       <div class="card-number" id="cautionNumber">
        9
       </div>
       <div class="card-label" id="cautionNumberLabel">
        เลขที่ควรระวัง
       </div>
       <div class="card-description">
        ใช้ด้วยความระมัดระวัง
       </div>
      </div>
     </div>
     <div class="energy-wheel-container">
      <h3 class="wheel-title">วงจรพลังงานของคุณ</h3>
      <p class="wheel-description">วงจรพลังงานแสดงถึงพลังแห่งจักรวาลที่หมุนเวียนรอบตัวคุณในวันนี้ เลขมงคลหลักของคุณอยู่ที่ศูนย์กลางของวงจร ส่งผลต่อพลังงาน อารมณ์ และโชคชะตาตลอดทั้งวัน</p>
      <div class="energy-wheel">
       <div class="wheel-center" id="wheelCenter">
        7
       </div>
      </div>
      <div class="wheel-labels">
       <div class="wheel-label-item">
        <div class="label-icon">
         🔮
        </div>
        <div class="label-text">
         สัญลักษณ์
        </div>
        <div class="label-value">
         ดาวเจ็ดดวง
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         💫
        </div>
        <div class="label-text">
         อารมณ์
        </div>
        <div class="label-value">
         สงบและชัดเจน
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         🌊
        </div>
        <div class="label-text">
         การเปลี่ยนแปลง
        </div>
        <div class="label-value">
         ค่อยเป็นค่อยไป
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         ⏰
        </div>
        <div class="label-text">
         เวลาที่ดี
        </div>
        <div class="label-value">
         07:00 - 19:00
        </div>
       </div>
       <div class="wheel-label-item">
        <div class="label-icon">
         ✨
        </div>
        <div class="label-text">
         ความหมาย
        </div>
        <div class="label-value">
         ปัญญาและการเรียนรู้
        </div>
       </div>
      </div>
     </div>
     <div class="ai-explanation">
      <h3 class="explanation-title"><span>🤖</span> <span>AI วิเคราะห์ความฝันของคุณ</span></h3>
      <p class="explanation-text" id="aiExplanation">จากความฝันที่คุณบอกเล่า ระบบ AI ได้วิเคราะห์พบว่าคุณกำลังอยู่ในช่วงของการเรียนรู้และค้นพบสิ่งใหม่ ๆ ตัวเลข 7 สะท้อนถึงปัญญา การไตร่ตรอง และความเข้าใจลึ��ซึ้ง ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาคำตอบ และความหมายที่ลึกซึ้งยิ่งขึ้นในชีวิต เลขเสริม 3 และ 5 จะช่วยเสริมพลังความคิดสร้างสรรค์และการสื่อสาร ในขณะที่เลข 9 เป็นเลขที่ควรระวังเรื่องการปล่อยวางมาก���กินไป</p>
     </div>
     <div class="daily-advice">
      <h3 class="advice-title"><span>💫</span> <span>คำแนะนำประจำวันนี้</span></h3>
      <div class="advice-content">
       <div class="advice-item">
        <div class="advice-icon">
         ✅
        </div>
        <div class="advice-text"><strong>สิ่งที่ควรทำวันนี้</strong> <span id="adviceDo">ใช้เวลาคิดและไตร่ตรองอย่างรอบคอบก่อนตัดสินใจสำคัญ นี่คือช่วงเวลาแห่งการค้นหาความจริง</span>
        </div>
       </div>
       <div class="advice-item">
        <div class="advice-icon">
         ⚠️
        </div>
        <div class="advice-text"><strong>สิ่งที่ควรหลีกเลี่ยง</strong> <span id="adviceAvoid">หลีกเลี่ยงกา��ตัดสินใจด้วยอารมณ์ หรือปล่อยวางเรื่องสำคัญทิ้งไว้</span>
        </div>
       </div>
       <div class="advice-item lucky-color">
        <div class="advice-icon">
         👕
        </div>
        <div class="advice-text"><strong>สีเสื้อมงคลตามด้านต่าง ๆ</strong>
         <div id="colorRecommendations" class="multi-color-grid"><!-- Colors will be populated by JavaScript -->
         </div>
        </div>
       </div>
      </div>
     </div><button class="back-button" onclick="navigateToPage(1)">กลับสู่หน้าหลัก</button>
    </div>
   </div>
  </div>
  <script>
    const defaultConfig = {
      logo_text: "NUMORA",
      tagline: "ถอดรหัสความฝันของคุณ ให้กลายเป็นตัวเลขมงคลเฉพาะบุคคล",
      cta_button: "เริ่มถอดรหัสความฝัน",
      input_placeholder: "บอกเล่าความฝันที่ฝันมา หรือเหตุการณ์สำคัญที่เกิดขึ้นในวันนี้...",
      mood_label: "อารมณ์ของคุณวันนี้ (เลือกได้หลายอารมณ์)",
      analyze_button: "แปลงความฝันเป็นตัวเลข",
      result_title: "เลขมงคลของคุณ",
      primary_number_label: "���ลขมงคลหลัก",
      support_number_label: "เลขเสริมดวง",
      caution_number_label: "เลขที่ควรระวัง",
      background_color: "#0a0e27",
      gold_color: "#fbbf24",
      purple_color: "#8b5cf6",
      text_color: "#ffffff",
      secondary_text_color: "#c7d2fe",
      font_family: "Inter",
      font_size: 16
    };

    let selectedMoods = [];

    async function onConfigChange(config) {
      const logoText = config.logo_text || defaultConfig.logo_text;
      const tagline = config.tagline || defaultConfig.tagline;
      const ctaButton = config.cta_button || defaultConfig.cta_button;
      const inputPlaceholder = config.input_placeholder || defaultConfig.input_placeholder;
      const moodLabel = config.mood_label || defaultConfig.mood_label;
      const analyzeButton = config.analyze_button || defaultConfig.analyze_button;
      const resultTitle = config.result_title || defaultConfig.result_title;
      const primaryNumberLabel = config.primary_number_label || defaultConfig.primary_number_label;
      const supportNumberLabel = config.support_number_label || defaultConfig.support_number_label;
      const cautionNumberLabel = config.caution_number_label || defaultConfig.caution_number_label;
      const fontFamily = config.font_family || defaultConfig.font_family;
      const fontSize = config.font_size || defaultConfig.font_size;
      const goldColor = config.gold_color || defaultConfig.gold_color;
      const purpleColor = config.purple_color || defaultConfig.purple_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const secondaryTextColor = config.secondary_text_color || defaultConfig.secondary_text_color;

      document.getElementById('logoText').textContent = logoText;
      document.getElementById('taglineText').textContent = tagline;
      document.getElementById('ctaButton').textContent = ctaButton;
      document.getElementById('dreamInput').placeholder = inputPlaceholder;
      document.getElementById('moodLabel').textContent = moodLabel;
      document.getElementById('analyzeButton').textContent = analyzeButton;
      document.getElementById('resultTitle').textContent = resultTitle;
      document.getElementById('primaryNumberLabel').textContent = primaryNumberLabel;
      document.getElementById('supportNumberLabel').textContent = supportNumberLabel;
      document.getElementById('cautionNumberLabel').textContent = cautionNumberLabel;

      document.body.style.fontFamily = `${fontFamily}, 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif`;
      document.body.style.fontSize = `${fontSize}px`;

      const headings = document.querySelectorAll('.logo, .form-title, .results-title');
      headings.forEach(h => h.style.fontSize = `${fontSize * 2.5}px`);

      const buttons = document.querySelectorAll('.cta-button, .analyze-button');
      buttons.forEach(btn => btn.style.fontSize = `${fontSize * 1.2}px`);

      const labels = document.querySelectorAll('.tagline, .input-label, .number-label');
      labels.forEach(label => label.style.fontSize = `${fontSize * 1.1}px`);
    }

    function navigateToPage(pageNumber) {
      document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
      document.getElementById(`page${pageNumber}`).classList.add('active');
    }

    function selectMood(mood) {
      const option = document.querySelector(`[data-mood="${mood}"]`);
      
      if (selectedMoods.includes(mood)) {
        selectedMoods = selectedMoods.filter(m => m !== mood);
        option.classList.remove('selected');
      } else {
        selectedMoods.push(mood);
        option.classList.add('selected');
      }
    }

    const numberMeanings = {
      1: {
        explanation: "คุณกำลังอยู่ในช่วงของการเริ่มต้นใหม่และการเป็นผู้นำ ตัวเลข 1 สะท้อนถึงความมั่นใจ ความกล้าหาญ และพลังแห่งการสร้างสรรค์ ความฝันของคุณบ่งบอกว่าถึงเวลาแล้วที่จะก้าวออกไปและเริ่มต้นสิ่งใหม่ ๆ",
        doAdvice: "จงมั่นใจในตัวเองและกล้าที่จะเริ่มต้นโครงการใหม่ นี่คือช่วงเวลาที่ดีสำหรับการเป็นผู้นำ",
        avoidAdvice: "หลีกเลี่ยงความลังเลและกา���รอคอยให้��นอื่นเริ่มก่อน อย่ากลัวที่จะโดดเด่น",
        luckyColor: "#E74C3C",
        colorName: "สีแดง",
        colorMeaning: "เสริมพลังและความมั่นใจ"
      },
      2: {
        explanation: "คุณกำลังอยู่ในช่วงของความสมดุลและความสัมพันธ์ ตัวเลข 2 สะท้อนถึงการประสานงาน ความอ่อนโยน และการทำงานเป็นทีม ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาความกลมกลืนและความเข้าใจกับผู้อื่น",
        doAdvice: "มุ่งเน้นการสร้างความสัมพันธ์ที่ดีและรับฟังผู้อื่น ควา��ร่วมมือจะนำมาซึ่งความสำเร็จ",
        avoidAdvice: "หล���กเลี่ยงการขัดแย้งที่ไม่จำเป็น อย่าเอาแต่ใจตัวเองหรือดื้อรั้นจนเกินไป",
        luckyColor: "#F39C12",
        colorName: "สีส้ม",
        colorMeaning: "เสริมความอบอุ่นและมิตรภาพ"
      },
      3: {
        explanation: "คุณกำลังอยู่ในช่วงของความคิดสร้างสรรค์และการแสดงออก ตัวเลข 3 สะท้อนถึงความสนุกสนาน การสื่อสาร และพลังแห่งจินตนาการ ความฝันของคุณบ่งบอกว่าถึงเวลาแล้วที่จะแสดงความสามารถของตัวเอง",
        doAdvice: "ปลดปล่อยความคิดสร��างสรรค์และแสดงออกอย่างเต็มที่ นี่คือช่วงเวลาแห่งความสนุกและความสุข",
        avoidAdvice: "หลีกเลี่ยงการกดอารมณ์หรือเก็บความรู้สึกไว้ข้างใน อย่าเครียดจนเกินไป",
        luckyColor: "#F1C40F",
        colorName: "สีเหลือง",
        colorMeaning: "เสริมความคิดสร้างสรรค์และความสนุกสนาน"
      },
      4: {
        explanation: "คุณกำลังอยู่ในช่วงของความมั่นคงและการวางรากฐาน ตัวเลข 4 สะท้อนถึงความมีระเบียบ ความอดทน และการทำงานหนัก ความฝันขอ��คุณบ่งบอกว่าคุณกำลังสร้างพื้นฐานที่��ข็งแกร่งสำหรับอนาคต",
        doAdvice: "มุ่งมั่นทำงานอย่างเป็นระบบและมีแผนที่ชัดเจน ความอดทนจะนำพาคุณไปสู่เป้าหมาย",
        avoidAdvice: "หลีกเลี่ยงการรีบร้อนหรือข้ามขั้นตอนสำคัญ อย่าประมาทหรือขาดความรอบคอบ",
        luckyColor: "#27AE60",
        colorName: "สีเขียว",
        colorMeaning: "เสริมความมั่นคงและการเติบโต"
      },
      5: {
        explanation: "คุณกำลังอยู่ในช่วงของการผจญภัยและการเปลี่ยนแปลง ตัวเลข 5 สะท้อนถึงความอิสระ ความยืดหยุ่น และการเรียนรู้สิ่งใหม่ ความฝันของคุณบ่งบอกว่าคุณพร้อมสำหรับประสบการณ์ใหม่ ๆ",
        doAdvice: "เปิดรับสิ่งใหม่และอย่ากลัวที่จะเปลี่ยนแปลง นี่คือช่วงเวลาแห่งการเติบโตและการค้นพบ",
        avoidAdvice: "หลีกเลี่ยงการยึดติดกับความเคยชินมากเกินไป อย่ากลัวความเสี่ยงที่สร้างสรรค์",
        luckyColor: "#3498DB",
        colorName: "สีฟ้า",
        colorMeaning: "เสริมความอิสระและการผจญภัย"
      },
      6: {
        explanation: "คุณกำลังอยู่ในช่วงของความรับผิดชอบและการดูแล ตัวเลข 6 สะท้อนถึงความรัก ครอบครัว และความสมดุลในชีวิต ความฝันของคุณบ่งบอกว่าคุณกำลังมุ่งเน้นที่การสร้างความอบอุ่นและความปลอดภัย",
        doAdvice: "ใส่ใจคนรอบข้างและสร้างความสัมพันธ์ที่อบอุ่น นี่คือเวลาที่ดีสำหรับครอบครัวและคนที่รัก",
        avoidAdvice: "หลีกเลี่ยงการเอาแต่ใจตัวเองหรือไม่แยแสคนรอบข้าง อย่าเพิกเฉยต่อความรู้สึกของผู้อื่น",
        luckyColor: "#E91E63",
        colorName: "สีชมพู",
        colorMeaning: "เสริมความรักและความเอาใจใส่"
      },
      7: {
        explanation: "คุณกำลังอยู่ในช่วงของการเรียนรู้และค้นพบสิ่งใหม่ ๆ ตัวเลข 7 สะท้อนถึงปัญญา การไตร่ตรอง และความเข้าใจลึกซึ้ง ความฝันของคุณบ่งบอกว่าคุณกำลังมองหาคำตอบและความหมายที่ลึกซึ้งยิ่งขึ้นในชีวิต",
        doAdvice: "ใช้เวลาคิดและไตร่ตรองอย่างรอบคอบก่อนตัดสินใจสำคัญ นี่คือช่วงเวลาแห่งการค้นหาความจริง",
        avoidAdvice: "หลีกเลี่��งการ��ัดสินใจด้วยอารมณ์ หรือปล่อยวางเรื่องสำคัญทิ้งไว้",
        luckyColor: "#8b5cf6",
        colorName: "สีม่วง",
        colorMeaning: "เสริมปัญญาและสัญชาตญาณ"
      },
      8: {
        explanation: "คุณกำลังอยู่ในช่วงของความสำเร็จและความมั่งคั่ง ตัวเลข 8 สะท้อนถึงพลังอำนาจ ความร่ำรวย และผลสำเร็จที่จับต้องได้ ความฝันของคุณบ่งบอกว่าคุณกำลังเข้าใกล้เป้าหมายที่ตั้งไว้",
        doAdvice: "มุ่งมั่นทำงานเพื่อความสำเร็จและอย่ากลัวที่จะตั้งเป้าหมายใหญ่ ๆ นี่คือช่วงเวลาแห่งความเจริญก้าวหน้า",
        avoidAdvice: "หลีกเลี่ยงความโลภหรือการใช้อำนาจในทางที่ผิด อย่าลืมคุณค่าที่แท้จริงของชีวิต",
        luckyColor: "#D4AF37",
        colorName: "สีทอง",
        colorMeaning: "เสริมความมั่งคั่งและความสำเร็จ"
      },
      9: {
        explanation: "คุณกำลังอยู่ในช่วงของการสิ้นสุดและการเริ่มต้นใหม่ ตัวเลข 9 สะท้อนถึงความเมตตา ปัญญา และการปล่อยวาง ความฝันของคุณบ่งบอกว่าถึงเวล��แล้วท��่จะยุติบางสิ่งเพื่อเปิดทางให้สิ่งใหม่",
        doAdvice: "เรียนรู้ที่จะให้อภัยและปล่อยวางสิ่งที่ผ่านไป นี่คือเวลาแห่งการเติมเต็มและความเข้าใจ",
        avoidAdvice: "หลีกเลี่ยงการยึดติดกับอดีตหรือไม่ยอมรับความเปลี่ยนแปลง อย่าเห็นแก่ตัวจนเกินไป",
        luckyColor: "#9B59B6",
        colorName: "สีม่วงอมชมพู",
        colorMeaning: "เสริมความเมตตาและการปล่อยวาง"
      }
    };

    function analyzeAndShowResults() {
      const dreamText = document.getElementById('dreamInput').value;
      
      if (!dreamText.trim()) {
        return;
      }

      const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
      const randomPrimary = numbers[Math.floor(Math.random() * numbers.length)];
      const randomTwoDigit = Math.floor(Math.random() * 90) + 10;
      const randomThreeDigit = Math.floor(Math.random() * 900) + 100;
      const randomCaution = numbers[Math.floor(Math.random() * numbers.length)];

      document.getElementById('primaryNumber').textContent = randomPrimary;
      document.getElementById('wheelCenter').textContent = randomPrimary;
      document.getElementById('twoDigitNumber').textContent = randomTwoDigit;
      document.getElementById('threeDigitNumber').textContent = randomThreeDigit;
      document.getElementById('cautionNumber').textContent = randomCaution;

      const meaning = numberMeanings[randomPrimary];
      document.getElementById('aiExplanation').textContent = meaning.explanation;
      document.getElementById('adviceDo').textContent = meaning.doAdvice;
      document.getElementById('adviceAvoid').textContent = meaning.avoidAdvice;
      document.getElementById('luckyColorSwatch').style.background = meaning.luckyColor;
      document.getElementById('luckyColorName').textContent = meaning.colorName;
      document.getElementById('luckyColorMeaning').textContent = meaning.colorMeaning;

      navigateToPage(3);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.gold_color || defaultConfig.gold_color,
              set: (value) => {
                config.gold_color = value;
                window.elementSdk.setConfig({ gold_color: value });
              }
            },
            {
              get: () => config.purple_color || defaultConfig.purple_color,
              set: (value) => {
                config.purple_color = value;
                window.elementSdk.setConfig({ purple_color: value });
              }
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => {
                config.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () => config.secondary_text_color || defaultConfig.secondary_text_color,
              set: (value) => {
                config.secondary_text_color = value;
                window.elementSdk.setConfig({ secondary_text_color: value });
              }
            }
          ],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => {
              config.font_family = value;
              window.elementSdk.setConfig({ font_family: value });
            }
          },
          fontSizeable: {
            get: () => config.font_size || defaultConfig.font_size,
            set: (value) => {
              config.font_size = value;
              window.elementSdk.setConfig({ font_size: value });
            }
          }
        }),
        mapToEditPanelValues: (config) => new Map([
          ["logo_text", config.logo_text || defaultConfig.logo_text],
          ["tagline", config.tagline || defaultConfig.tagline],
          ["cta_button", config.cta_button || defaultConfig.cta_button],
          ["input_placeholder", config.input_placeholder || defaultConfig.input_placeholder],
          ["mood_label", config.mood_label || defaultConfig.mood_label],
          ["analyze_button", config.analyze_button || defaultConfig.analyze_button],
          ["result_title", config.result_title || defaultConfig.result_title],
          ["primary_number_label", config.primary_number_label || defaultConfig.primary_number_label],
          ["support_number_label", config.support_number_label || defaultConfig.support_number_label],
          ["caution_number_label", config.caution_number_label || defaultConfig.caution_number_label]
        ])
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a618687540e203d',t:'MTc2NDQxMzIzMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
