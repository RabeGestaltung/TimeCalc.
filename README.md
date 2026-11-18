    # TimeCalc.
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <title>Projekt‑Tool</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    body {
      margin: 0;
      padding: 0;
      background: #f5f5f7;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      color: #111;
    }
    .app {
      max-width: 900px;
      margin: 20px auto;
      padding: 16px;
    }
    .header {
      margin-bottom: 20px;
    }
    .header h1 {
      font-size: 24px;
      margin: 0 0 4px;
    }
    .header p {
      margin: 0;
      color: #666;
      font-size: 14px;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
      margin-bottom: 24px;
    }
    .card {
      background: #fff;
      border-radius: 18px;
      padding: 16px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.08);
      cursor: pointer;
      transition: transform 0.12s, box-shadow 0.12s;
    }
    .card:hover {
      transform: translateY(-2px);
      box-shadow: 0 14px 30px rgba(0,0,0,0.12);
    }
    .card h2 {
      font-size: 18px;
      margin: 0 0 6px;
    }
    .card p {
      margin: 0;
      font-size: 13px;
      color: #666;
    }
    .view {
      background: #fff;
      border-radius: 18px;
      padding: 18px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.08);
      margin-bottom: 16px;
    }
    .view h2 {
      margin-top: 0;
      font-size: 18px;
    }
    .back-btn {
      margin-bottom: 12px;
      font-size: 13px;
      color: #007aff;
      cursor: pointer;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <div class="app">
    <div class="header">
      <h1>Projekt‑Tool</h1>
      <p>Kalender, Zeiten, Projekte & Kalkulation</p>
    </div>

    <!-- Startseite mit Cards -->
    <div id="homeView">
      <div class="grid">
        <div class="card" onclick="openView('calendarView')">
          <h2>Kalender & Projekte</h2>
          <p>Termine eintragen, Projekten zuordnen.</p>
        </div>
        <div class="card" onclick="openView('timeTrackerView')">
          <h2>Zeit‑Stopper & Bilder</h2>
          <p>Arbeitszeiten stoppen, beschreiben, bebildern.</p>
        </div>
        <div class="card" onclick="openView('summaryView')">
          <h2>Kalkulation & Übersicht</h2>
          <p>Gesamtzeiten pro Arbeitsschritt.</p>
        </div>
        <div class="card" onclick="openView('quickStepsView')">
          <h2>Schnell‑Arbeitszeiten</h2>
          <p>Arbeitsschritte antippen, Zeiten übernehmen.</p>
        </div>
      </div>
    </div>

    <!-- View: Kalender & Projekte -->
    <div id="calendarView" class="hidden">
      <div class="view">
        <div class="back-btn" onclick="goHome()">← Zurück</div>
        <h2>Kalender & Projekte</h2>
        <p>Hier kommen später: Projektliste, Termine, Zuordnung.</p>
      </div>
    </div>

    <!-- View: Zeit‑Stopper & Bilder -->
    <div id="timeTrackerView" class="hidden">
      <div class="view">
        <div class="back-btn" onclick="goHome()">← Zurück</div>
        <h2>Zeit‑Stopper & Bilder</h2>
        <p>Hier kommen später: Timer, Beschreibung, Bild‑Upload, Projektzuordnung.</p>
      </div>
    </div>

    <!-- View: Kalkulation & Übersicht -->
    <div id="summaryView" class="hidden">
      <div class="view">
        <div class="back-btn" onclick="goHome()">← Zurück</div>
        <h2>Kalkulation & Übersicht</h2>
        <p>Hier kommen später: Gesamtzeiten pro Arbeitsschritt, Projekt‑Auswertung.</p>
      </div>
    </div>

    <!-- View: Schnell‑Arbeitszeiten -->
    <div id="quickStepsView" class="hidden">
      <div class="view">
        <div class="back-btn" onclick="goHome()">← Zurück</div>
        <h2>Schnell‑Arbeitszeiten</h2>
        <p>Hier kommen später: vordefinierte Arbeitsschritte mit Zeiten, Tippen → Zeit übernehmen.</p>
      </div>
    </div>
  </div>

  <script>
    function openView(id) {
      document.getElementById('homeView').classList.add('hidden');
      ['calendarView','timeTrackerView','summaryView','quickStepsView'].forEach(v => {
        document.getElementById(v).classList.add('hidden');
      });
      document.getElementById(id).classList.remove('hidden');
    }
    function goHome() {
      ['calendarView','timeTrackerView','summaryView','quickStepsView'].forEach(v => {
        document.getElementById(v).classList.add('hidden');
      });
      document.getElementById('homeView').classList.remove('hidden');
    }
  </script>
</body>
</html>

