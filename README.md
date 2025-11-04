<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>UUM Management Museum Audio Guide</title>
  <style>
    :root {
      --uum-blue: #003366;
      --uum-yellow: #ffcc00;
      --white: #ffffff;
      --light-bg: #f4f6fb;
      --card-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      background: var(--light-bg);
      color: #222;
      line-height: 1.6;
    }

    header {
      background: var(--uum-blue);
      color: var(--white);
      padding: 14px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }

    header h1 {
      margin: 0;
      font-size: 1.3em;
      flex: 1 1 100%;
      text-align: center;
    }

    nav {
      display: flex;
      gap: 12px;
      align-items: center;
      justify-content: center;
      flex: 1 1 100%;
      margin-top: 8px;
    }

    nav a {
      color: var(--white);
      text-decoration: none;
      font-weight: 500;
      cursor: pointer;
    }

    nav a:hover {
      color: var(--uum-yellow);
    }

    select {
      background: var(--white);
      color: var(--uum-blue);
      padding: 5px 10px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
    }

    main {
      padding: 20px;
      width: 100%;
      max-width: 900px;
      margin: auto;
    }

    .page {
      display: none;
      animation: fadeIn 0.4s ease-in;
    }
    .page.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .segment {
      background: var(--white);
      padding: 16px;
      border-radius: 14px;
      box-shadow: var(--card-shadow);
      margin-bottom: 22px;
      overflow: hidden;
    }

    .segment img {
      display: block;
      width: 100%;
      height: auto;
      max-height: 250px;
      object-fit: cover;
      border-radius: 12px 12px 0 0;
      margin-bottom: 10px;
    }

    audio {
      width: 100%;
      margin-top: 8px;
    }

    .transcript {
      margin-top: 10px;
      background: #f9f9f9;
      padding: 10px;
      border-left: 4px solid var(--uum-blue);
      border-radius: 6px;
    }

    .feedback-container {
      background: var(--white);
      padding: 20px;
      border-radius: 14px;
      box-shadow: var(--card-shadow);
      max-width: 600px;
      margin: auto;
    }

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

    button:hover {
      background: var(--uum-yellow);
      color: var(--uum-blue);
    }

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
      background: var(--uum-blue);
      color: var(--white);
      padding: 20px 24px;
      text-align: center;
      margin-top: 40px;
      font-size: 0.95em;
    }

    footer a {
      color: var(--uum-yellow);
      text-decoration: none;
    }

    footer a:hover {
      text-decoration: underline;
    }

    /* --- RESPONSIVE STYLING --- */
    @media (min-width: 700px) {
      header {
        flex-wrap: nowrap;
      }
      header h1 {
        flex: 1;
        text-align: left;
        font-size: 1.6em;
      }
      nav {
        flex: 0 0 auto;
        justify-content: flex-end;
        margin-top: 0;
      }
      main {
        padding: 30px;
      }
    }

    @media (max-width: 480px) {
      .segment img {
        max-height: 200px;
      }
      header h1 {
        font-size: 1.1em;
      }
      button {
        font-size: 0.9em;
      }
    }
  </style>
</head>
<body>

  <header>
    <h1 id="title">Panduan Audio Muzium Pengurusan UUM</h1>
    <nav>
      <a id="nav-audio">Panduan Audio</a>
      <a id="nav-feedback">Borang Maklum Balas</a>
      <select id="lang-select">
        <option value="ms">BM</option>
        <option value="en">EN</option>
      </select>
    </nav>
  </header>

  <main>
    <!-- AUDIO PAGE -->
    <section id="audio-page" class="page active">
      <h2 id="audio-heading">Segmen Audio Panduan Muzium</h2>

      <div class="segment">
        <img src="imagessegment1.jpg" alt="Segment 1">
        <h3 id="seg1-title">Segmen 1: Sejarah Penubuhan UUM</h3>
        <audio class="audio-bm" controls src="audiosegmen1-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen1-en.mp3" style="display:none;"></audio>
        <div class="transcript" id="seg1-trans">Universiti Utara Malaysia ditubuhkan pada tahun 1984...</div>
      </div>

      <div class="segment">
        <img src="imagessegment2.jpg" alt="Segment 2">
        <h3 id="seg2-title">Segmen 2: Visi dan Misi Universiti</h3>
        <audio class="audio-bm" controls src="audiosegmen2-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen2-en.mp3" style="display:none;"></audio>
        <div class="transcript" id="seg2-trans">Visi UUM adalah untuk menjadi universiti pengurusan terkemuka...</div>
      </div>

      <div class="segment">
        <img src="imagessegment3.jpg" alt="Segment 3">
        <h3 id="seg3-title">Segmen 3: Fakulti dan Pusat Pengajian</h3>
        <audio class="audio-bm" controls src="audiosegmen3-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen3-en.mp3" style="display:none;"></audio>
        <div class="transcript" id="seg3-trans">UUM terdiri daripada beberapa fakulti dan pusat pengajian...</div>
      </div>

      <div class="segment">
        <img src="imagessegment4.jpg" alt="Segment 4">
        <h3 id="seg4-title">Segmen 4: Koleksi Muzium</h3>
        <audio class="audio-bm" controls src="audiosegmen4-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen4-en.mp3" style="display:none;"></audio>
        <div class="transcript" id="seg4-trans">Muzium ini mempamerkan pelbagai artifak sejarah...</div>
      </div>

      <div class="segment">
        <img src="imagessegment5.jpg" alt="Segment 5">
        <h3 id="seg5-title">Segmen 5: Tokoh dan Sumbangan</h3>
        <audio class="audio-bm" controls src="audiosegmen5-bm.mp3"></audio>
        <audio class="audio-en" controls src="audiosegmen5-en.mp3" style="display:none;"></audio>
        <div class="transcript" id="seg5-trans">Bahagian ini memperkenalkan tokoh-tokoh penting...</div>
      </div>
    </section>

    <!-- FEEDBACK PAGE -->
    <section id="feedback-page" class="page">
      <div class="feedback-container">
        <h2 id="feedback-title">Borang Maklum Balas</h2>
        <form id="feedbackForm">
          <label id="label-name">Nama:</label>
          <input type="text" id="name" required placeholder="Masukkan nama anda">
          <label id="label-feedback">Maklum Balas:</label>
          <textarea id="feedback" rows="4" required placeholder="Tulis maklum balas anda di sini"></textarea>
          <button type="submit" id="submit-btn">Hantar Maklum Balas</button>
        </form>
        <div class="feedback-display" id="feedbackDisplay">
          <h3 id="submitted-title">Maklum Balas Dihantar:</h3>
        </div>
        <a class="back-btn" id="backAudio">← Kembali ke Panduan Audio</a>
      </div>
    </section>
  </main>

  <footer>
    <p><strong>UUM Management Museum</strong> | Universiti Utara Malaysia</p>
    <p>Email: <a href="mailto:museum@uum.edu.my">museum@uum.edu.my</a> | Tel: +604-928 4000</p>
    <p><a href="https://www.uum.edu.my" target="_blank">www.uum.edu.my</a></p>
    <p>© 2025 UUM Museum Audio Guide. All Rights Reserved.</p>
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
      window.scrollTo(0, 0);
    }

    navAudio.addEventListener('click', () => showPage('audio-page'));
    navFeedback.addEventListener('click', () => showPage('feedback-page'));
    backAudio.addEventListener('click', () => showPage('audio-page'));

    // === FEEDBACK STORAGE ===
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

    // === LANGUAGE SWITCH ===
    const translations = {
      ms: {
        title: "Panduan Audio Muzium Pengurusan UUM",
        navAudio: "Panduan Audio",
        navFeedback: "Borang Maklum Balas",
        audioHeading: "Segmen Audio Panduan Muzium",
        seg1: "Segmen 1: Sejarah Penubuhan UUM",
        seg2: "Segmen 2: Visi dan Misi Universiti",
        seg3: "Segmen 3: Fakulti dan Pusat Pengajian",
        seg4: "Segmen 4: Koleksi Muzium",
        seg5: "Segmen 5: Tokoh dan Sumbangan",
        transcripts: [
          "Universiti Utara Malaysia ditubuhkan pada tahun 1984...",
          "Visi UUM adalah untuk menjadi universiti pengurusan terkemuka...",
          "UUM terdiri daripada beberapa fakulti dan pusat pengajian...",
          "Muzium ini mempamerkan pelbagai artifak sejarah...",
          "Bahagian ini memperkenalkan tokoh-tokoh penting..."
        ],
        feedbackTitle: "Borang Maklum Balas",
        labelName: "Nama:",
        labelFeedback: "Maklum Balas:",
        submit: "Hantar Maklum Balas",
        submittedTitle: "Maklum Balas Dihantar:",
        back: "← Kembali ke Panduan Audio"
      },
      en: {
        title: "UUM Management Museum Audio Guide",
        navAudio: "Audio Guide",
        navFeedback: "Feedback Form",
        audioHeading: "Museum Audio Guide Segments",
        seg1: "Segment 1: History of UUM",
        seg2: "Segment 2: Vision and Mission",
        seg3: "Segment 3: Faculties and Schools",
        seg4: "Segment 4: Museum Collections",
        seg5: "Segment 5: Key Figures and Contributions",
        transcripts: [
          "Universiti Utara Malaysia was established in 1984...",
          "UUM’s vision is to be a leading management university...",
          "UUM consists of various faculties and academic centres...",
          "The museum showcases a wide range of historical artifacts...",
          "This section introduces key figures who contributed to UUM’s growth..."
        ],
        feedbackTitle: "Feedback Form",
        labelName: "Name:",
        labelFeedback: "Feedback:",
        submit: "Submit Feedback",
        submittedTitle: "Feedback Submitted:",
        back: "← Back to Audio Guide"
      }
    };

    function applyLanguage(lang) {
      const t = translations[lang];
      document.getElementById('title').innerText = t.title;
      document.getElementById('nav-audio').innerText = t.navAudio;
      document.getElementById('nav-feedback').innerText = t.navFeedback;
      document.getElementById('audio-heading').innerText = t.audioHeading;

      for (let i = 1; i <= 5; i++) {
        document.getElementById(`seg${i}-title`).innerText = t[`seg${i}`];
        document.getElementById(`seg${i}-trans`).innerText = t.transcripts[i - 1];
      }

      document.getElementById('feedback-title').innerText = t.feedbackTitle;
      document.getElementById('label-name').innerText = t.labelName;
      document.getElementById('label-feedback').innerText = t.labelFeedback;
      document.getElementById('submit-btn').innerText = t.submit;
      document.getElementById('submitted-title').innerText = t.submittedTitle;
      document.getElementById('backAudio').innerText = t.back;

      // switch audio visibility
      document.querySelectorAll('.audio-bm').forEach(a => a.style.display = lang === 'ms' ? 'block' : 'none');
      document.querySelectorAll('.audio-en').forEach(a => a.style.display = lang === 'en' ? 'block' : 'none');
    }

    langSelect.addEventListener('change', () => {
      const lang = langSelect.value;
      localStorage.setItem('lang', lang);
      applyLanguage(lang);
    });

    const savedLang = localStorage.getItem('lang') || 'ms';
    langSelect.value = savedLang;
    applyLanguage(savedLang);
  </script>

</body>
</html>
