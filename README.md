<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>UUM Management Museum Audio Guide Website</title>
  <style>
:root {
  --uum-blue: #003366;
  --uum-yellow: #ffcc00;
  --white: #ffffff;
  --light-bg: #2d3957;
}

body {
  font-family: 'Segoe UI', sans-serif;
  margin: 0;
  background: var(--light-bg);
  color: #222;
  line-height: 1.6;
}

/* ===== Header layout ===== */
.uum-header {
  background: var(--white);
  color: var(--uum-blue);
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  padding: 14px 24px;
  gap: 20px;

  border-bottom: 4px solid var(--uum-blue);
}

/* Left section */
.header-left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.uum-logo {
  height: 70px;
  margin-bottom: 4px;
}

.header-subtitle {
  font-size: 0.85em;
  color: var(--uum-blue);
  opacity: 0.9;
}

/* Center title */
.header-center {
  text-align: center;
}

.header-center h1 {
  margin: 0;
  font-size: 1.4em;
  font-weight: 700;
  color: var(--uum-blue);
}

/* Right navigation */
.header-right {
  display: flex;
  align-items: center;
  gap: 14px;
}

.header-right a {
  color: var(--uum-blue);
  text-decoration: none;
  font-weight: 500;
  cursor: pointer;
}

.header-right a:hover {
  color: var(--uum-yellow);
}

.header-right select {
  background: var(--white);
  color: var(--uum-blue);
  padding: 4px 8px;
  border-radius: 6px;
  border: 1px solid var(--uum-blue);
  cursor: pointer;
}


    nav {
      display: flex;
      gap: 14px;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
      width: 100%;
      margin-top: 10px;
    }

    nav a {
      color: var(--white);
      text-decoration: none;
      font-weight: 500;
      cursor: pointer;
    }

    nav a:hover { color: var(--uum-yellow); }

    select {
      background: var(--white);
      color: var(--uum-blue);
      padding: 4px 8px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
    }

    main {
      padding: 24px;
      max-width: 1000px;
      margin: auto;
      box-sizing: border-box;
    }

    .page {
      display: none;
      animation: fadeIn 0.4s ease-in;
    }

    .page.active { display: block; }

    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

    .segment {
      background: var(--white);
      padding: 20px;
      border-radius: 14px;
      box-shadow: var(--card-shadow);
      margin-bottom: 26px;
      overflow: hidden;
    }

    .segment img {
      display: block;
      width: 100%;
      max-height: 250px;
      object-fit: cover;
      border-radius: 12px 12px 0 0;
      margin-bottom: 12px;
    }

    audio {
      width: 100%;
      max-width: 100%;
      margin-top: 10px;
    }

    .transcript-btn {
      background: var(--uum-blue);
      color: var(--white);
      border: none;
      border-radius: 6px;
      padding: 8px 12px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 8px;
    }

    .transcript-btn:hover { background: var(--uum-yellow); color: var(--uum-blue); }

    .transcript {
      display: none;
      margin-top: 10px;
      background: #f9f9f9;
      padding: 12px;
      border-left: 4px solid var(--uum-blue);
      border-radius: 6px;
      font-size: 0.95em;
      word-wrap: break-word;
    }

    .feedback-container {
      background: var(--white);
      padding: 24px;
      border-radius: 14px;
      box-shadow: var(--card-shadow);
      max-width: 600px;
      margin: auto;
    }

    .feedback-container h2 { color: var(--uum-blue); }

    form {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    input, textarea {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 1em;
      width: 100%;
      box-sizing: border-box;
    }

    button {
      background: var(--uum-blue);
      color: var(--white);
      border: none;
      border-radius: 8px;
      padding: 10px;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover { background: var(--uum-yellow); color: var(--uum-blue); }

    .feedback-display {
      margin-top: 20px;
      border-top: 2px solid #eee;
      padding-top: 10px;
    }

    .back-btn {
      display: inline-block;
      margin-top: 15px;
      color: var(--uum-blue);
      text-decoration: none;
      font-weight: 600;
      cursor: pointer;
    }

    footer {
      background: var(--white);
      color: var(--uum-blue);
      padding: 20px 24px;
      text-align: center;
      margin-top: 40px;
      font-size: 0.95em;
    }

    footer a { color: var(--uum-yellow); text-decoration: none; font-weight: 500; }
    footer a:hover { text-decoration: underline; }

    /* ===== Responsive adjustments ===== */
   @media (max-width: 768px) {
   .uum-header {
    grid-template-columns: 1fr;
    text-align: center;
   }

   .header-left {
    align-items: center;
   }

   .header-right {
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 10px;
   }
}
  </style>



</head>
<body>
  <header class="uum-header">
  <!-- LEFT: Logo + Subtitle -->
  <div class="header-left">
    <img src="uumlogo.png" alt="UUM Logo" class="uum-logo">
    <span class="header-subtitle" id="header-subtitle">
    </span>
  </div>

  <!-- CENTER: Main title -->
  <div class="header-center">
    <h1 id="title"></h1>
  </div>

  <!-- RIGHT: Navigation -->
  <nav class="header-right">
    <a id="nav-audio"></a>
    <a id="nav-feedback"></a>
    <select id="lang-select">
      <option value="ms">BM</option>
      <option value="en">EN</option>
    </select>
  </nav>
  </header>

  <main>
    <!-- AUDIO PAGE -->
    <section id="audio-page" class="page active">
      <h2 id="audio-heading"></h2>

      <div class="segment">
        <img src="imagessegment1.jpg" alt="Segment 1">
        <h3 id="seg1-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen1-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen1-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg1-trans"></button>
        <div class="transcript" id="seg1-trans"></div>
      </div>

      <div class="segment">
        <img src="imagessegment2.jpg" alt="Segment 2">
        <h3 id="seg2-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen2-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen2-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg2-trans"></button>
        <div class="transcript" id="seg2-trans"></div>
      </div>

      <div class="segment">
        <img src="imagessegment3.jpg" alt="Segment 3">
        <h3 id="seg3-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen3-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen3-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg3-trans"></button>
        <div class="transcript" id="seg3-trans"></div>
      </div>

      <div class="segment">
        <img src="imagessegment4.jpg" alt="Segment 4">
        <h3 id="seg4-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen4-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen4-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg4-trans"></button>
        <div class="transcript" id="seg4-trans"></div>
      </div>

      <div class="segment">
        <img src="imagessegment5.jpg" alt="Segment 5">
        <h3 id="seg5-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen5-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen5-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg5-trans"></button>
        <div class="transcript" id="seg5-trans"></div>
      </div>

      <div class="segment">
        <img src="imagessegment6.jpg" alt="Segment 6">
        <h3 id="seg6-title"></h3>
        <audio class="audio-bm" controls src="audiosegmen6-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen6-en.mp3" style="display:none;"></audio>
        <button class="transcript-btn" data-target="seg6-trans"></button>
        <div class="transcript" id="seg6-trans"></div>
      </div>

    </section>

    <!-- FEEDBACK PAGE -->
    <section id="feedback-page" class="page">
      <div class="feedback-container">
        <h2 id="feedback-title"></h2>
        <form id="feedbackForm">
          <label id="label-name"></label>
          <input type="text" id="name" required placeholder="">
          <label id="label-feedback"></label>
          <textarea id="feedback" rows="4" required placeholder=""></textarea>
          <button type="submit" id="submit-btn"></button>
        </form>
        <div class="feedback-display" id="feedbackDisplay">
          <h3 id="submitted-title"></h3>
        </div>
        
        <a class="back-btn" id="backAudio"></a>
      </div>
    </section>
  </main>

  <footer>
    <p id="footer1"></p>
    <p id="footer2"></p>
    <p id="footer3"></p>
    <p id="footer4"></p>
  </footer>

  <script>
    const pages = document.querySelectorAll('.page');
    const navAudio = document.getElementById('nav-audio');
    const navFeedback = document.getElementById('nav-feedback');
    const backAudio = document.getElementById('backAudio');
    const langSelect = document.getElementById('lang-select');

    function showPage(id) {
      pages.forEach(p => p.classList.remove('active'));
      document.getElementById(id).classList.add('active');
      window.scrollTo(0,0);
    }
    navAudio.addEventListener('click', () => showPage('audio-page'));
    navFeedback.addEventListener('click', () => showPage('feedback-page'));
    backAudio.addEventListener('click', () => showPage('audio-page'));

    // Feedback storage
    const form = document.getElementById('feedbackForm');
    const display = document.getElementById('feedbackDisplay');
    const savedFeedbacks = JSON.parse(localStorage.getItem('feedbacks') || "[]");
    savedFeedbacks.forEach(fb => {
      const entry = document.createElement('p');
      entry.innerHTML = `<strong>${fb.name}:</strong> ${fb.feedback}`;
      display.appendChild(entry);
    });
    form.addEventListener('submit', e => {
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const feedback = document.getElementById('feedback').value.trim();
      if (name && feedback) {
        const entry = document.createElement('p');
        entry.innerHTML = `<strong>${name}:</strong> ${feedback}`;
        display.appendChild(entry);
        savedFeedbacks.push({ name, feedback });
        localStorage.setItem('feedbacks', JSON.stringify(savedFeedbacks));
        form.reset();
      }
    });

    // Language data
    const langData = {
      ms: {
        title: "Panduan Audio Muzium Pengurusan UUM",
        navAudio: "Panduan Audio",
        navFeedback: "Borang Maklum Balas",
        audioHeading: " ",
        segTitles: [
          "Zon A: Sejarah Penubuhan UUM",
          "Zon B: Visi dan Misi Universiti",
          "Zon C: Fakulti dan Pusat Pengajian",
          "Zon D: Koleksi Muzium",
          "Zon E: Tokoh dan Sumbangan",
          "Zon F: Nurin"
        ],
        transcripts: [
          "Universiti Utara Malaysia ditubuhkan pada tahun 1984 di Sintok...",
          "Visi UUM adalah untuk menjadi universiti pengurusan terkemuka...",
          "UUM mempunyai pelbagai fakulti dan pusat pengajian yang fokus kepada bidang pengurusan...",
          "Muzium ini mempamerkan pelbagai artifak dan sejarah penubuhan universiti...",
          "Bahagian ini memperkenalkan tokoh dan sumbangan penting kepada pembangunan UUM...",
          "Nurin Nabilah"
        ],
        feedbackTitle: "Borang Maklum Balas",
        labelName: "Nama:",
        labelFeedback: "Maklum Balas:",
        placeholderName: " ",
        placeholderFeedback: " ",
        submitBtn: "Hantar Maklum Balas",
        submittedTitle: "Maklum Balas Dihantar:",
        backBtn: "← Kembali ke Panduan Audio",
        transcriptBtn: "Transkrip",
        footer1: `UUM Management Museum | <a href="https://library.uum.edu.my/uum-management-museum/" target="_blank">Universiti Utara Malaysia</a>`,
        footer2: `Email: museum@uum.edu.my | Tel: +604 928 2614`,
        footer3: `© 2025 Panduan Audio Muzium UUM. Semua Hak Terpelihara.`      },
      en: {
        title: "UUM Management Museum Audio Guide",
        navAudio: "Audio Guide",
        navFeedback: "Feedback Form",
        audioHeading: " ",
        segTitles: [
          "Zone A: History of UUM",
          "Zone B: Vision and Mission",
          "Zone C: Faculties and Academic Centers",
          "Zone D: Museum Collections",
          "Zone E: Key Figures and Contributions",
          "Zone F : Nurin"
        ],
        transcripts: [
          "Universiti Utara Malaysia was established in 1984 in Sintok...",
          "UUM’s vision is to be a leading management university...",
          "UUM has multiple faculties and academic centers focused on management...",
          "The museum showcases various artifacts and historical documents...",
          "This section introduces key figures and their contributions to UUM...",
          "Nurin nabilah binti nik shahrul nizam"
        ],
        feedbackTitle: "Feedback Form",
        labelName: "Name:",
        labelFeedback: "Feedback:",
        placeholderName: "",
        placeholderFeedback: "",
        submitBtn: "Submit Feedback",
        submittedTitle: "Feedback Submitted:",
        backBtn: "← Back to Audio Guide",
        transcriptBtn: "Transcript",
        footer1: `UUM Management Museum | <a href="https://library.uum.edu.my/uum-management-museum/" target="_blank">Universiti Utara Malaysia</a>`,
        footer2: `Email: museum@uum.edu.my | Tel: +604 928 2614`,
        footer3: `© 2025 UUM Museum Audio Guide. All Rights Reserved.`,
      }
    };

    function applyLanguage(lang) {
      const t = langData[lang];
      document.getElementById('title').innerText = t.title;
      document.getElementById('nav-audio').innerText = t.navAudio;
      document.getElementById('nav-feedback').innerText = t.navFeedback;
      document.getElementById('audio-heading').innerText = t.audioHeading;

      for (let i = 1; i <= 6; i++) {
        document.getElementById(`seg${i}-title`).innerText = t.segTitles[i-1];
        document.getElementById(`seg${i}-trans`).innerText = t.transcripts[i-1];
      }

      document.getElementById('feedback-title').innerText = t.feedbackTitle;
      document.getElementById('label-name').innerText = t.labelName;
      document.getElementById('label-feedback').innerText = t.labelFeedback;
      document.getElementById('name').placeholder = t.placeholderName;
      document.getElementById('feedback').placeholder = t.placeholderFeedback;
      document.getElementById('submit-btn').innerText = t.submitBtn;
      document.getElementById('submitted-title').innerText = t.submittedTitle;
      document.getElementById('backAudio').innerText = t.backBtn;

      document.querySelectorAll('.transcript-btn').forEach(btn => btn.innerText = t.transcriptBtn);

      document.querySelectorAll('.audio-bm').forEach(a => a.style.display = lang==='ms' ? 'block':'none');
      document.querySelectorAll('.audio-en').forEach(a => a.style.display = lang==='en' ? 'block':'none');

      document.getElementById('footer1').innerHTML = t.footer1;
      document.getElementById('footer2').innerHTML = t.footer2;
      document.getElementById('footer3').innerHTML = t.footer3;
    }

    langSelect.addEventListener('change', () => {
      const lang = langSelect.value;
      localStorage.setItem('lang', lang);
      applyLanguage(lang);
    });


    applyLanguage(localStorage.getItem('lang') || 'ms');

    // Transcript toggle
    document.querySelectorAll('.transcript-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        const t = document.getElementById(btn.dataset.target);
        t.style.display = t.style.display === 'block' ? 'none' : 'block';
      });
    });
  </script>
</body>
</html>
