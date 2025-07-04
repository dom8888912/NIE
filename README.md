<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
</head>
<body style="font-family: sans-serif; line-height: 1.6; max-width: 900px; margin: auto; padding: 20px;">

  <h1>📄 Automatisierte Formularausfüllung mit Playwright</h1>

  <p>
    Dieses Python-Skript automatisiert die Anmeldung bzw. Terminvereinbarung auf einer spanischen Regierungsseite
    mithilfe von <a href="https://playwright.dev/python/" target="_blank">Playwright</a>. Es simuliert realistische
    Nutzereingaben und prüft regelmäßig, ob neue Termine für die NIE-Beantragung verfügbar sind.
  </p>

  <p>
    <strong>NIE</strong> steht für <em>Número de Identidad de Extranjero</em> und ist eine Ausländer-Identifikationsnummer,
    die in Spanien für viele rechtliche oder wirtschaftliche Aktivitäten erforderlich ist (z. B. Kontoeröffnung, Mietverträge,
    Behördengänge). Termine für die Beantragung sind stark begrenzt und schnell ausgebucht – dieses Skript unterstützt
    bei der frühzeitigen Erkennung von freien Terminen.
  </p>

  <hr>

  <h2>🔧 Voraussetzungen</h2>
  <ul>
    <li>Python 3.8 oder höher</li>
    <li>Benötigte Pakete (siehe Installation)</li>
    <li>Eine <code>config.yaml</code> Datei (siehe unten)</li>
  </ul>

  <h2>📦 Installation</h2>
  <pre><code>pip install playwright pyyaml
playwright install
  </code></pre>

  <h2>⚙️ Konfiguration</h2>
  <p>Lege eine <code>config.yaml</code> Datei im selben Verzeichnis wie das Skript an:</p>
  <pre><code>provinz: "Madrid"
dokument_typ: "pasaporte"
name: "Max Mustermann"
ausweisnummer: "X1234567"
nationalität: "Alemania"  # oder "zufällig"
geburtsjahr: 1990
headless: true
  </code></pre>

  <p><em>Hinweis:</em> Setze <code>nationalität</code> auf <code>zufällig</code>, um eine zufällige gültige Nationalität auszuwählen.</p>

  <h2>🧠 Hauptfunktionen</h2>
  <ul>
    <li>Realistische Tipp- und Klick-Simulation durch zufällige Mausbewegungen und Verzögerungen</li>
    <li>Formularbefüllung inklusive Auswahlfelder, Texteingaben und Radiobuttons</li>
    <li>Änderungserkennung der Zielseite über SHA256-Hashvergleich</li>
    <li>Screenshot-Erstellung bei Änderung</li>
    <li>Speichern von Cookies und Logs zur Nachverfolgung</li>
  </ul>

  <h2>🚀 Ausführung</h2>
  <pre><code>python scriptname.py</code></pre>
  <p><em>Hinweis:</em> Ersetze <code>scriptname.py</code> durch den tatsächlichen Namen deiner Python-Datei, z. B. <code>nie_checker.py</code>.</p>

  <h2>🗂️ Projektstruktur</h2>
  <table border="1" cellpadding="6" cellspacing="0">
    <thead>
      <tr>
        <th>Datei</th>
        <th>Zweck</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>scriptname.py</code></td>
        <td>Hauptskript</td>
      </tr>
      <tr>
        <td><code>config.yaml</code></td>
        <td>Benutzerdefinierte Konfiguration</td>
      </tr>
      <tr>
        <td><code>log.txt</code></td>
        <td>Logdatei mit Informationen und Fehlern</td>
      </tr>
      <tr>
        <td><code>cookies.json</code></td>
        <td>Gespeicherte Browser-Cookies</td>
      </tr>
      <tr>
        <td><code>screenshot_*.png</code></td>
        <td>Screenshots bei Änderungen</td>
      </tr>
      <tr>
        <td><code>last_hash.txt</code></td>
        <td>Zuletzt bekannter Seiten-Hash</td>
      </tr>
    </tbody>
  </table>

  <h2>🛠️ Tipps</h2>
  <ul>
    <li>Setze <code>headless: false</code> in der <code>config.yaml</code>, um den Browser sichtbar zu machen.</li>
    <li>Ändere den <code>REALISMUS_FAKTOR</code> im Skript, um Eingabe- und Klickgeschwindigkeit zu steuern.</li>
    <li>Es wird ein persistenter Chromium-Browser verwendet, d. h. Cookies & Logins bleiben erhalten.</li>
  </ul>

  <h2>🧾 Lizenz</h2>
  <p>
    Dieses Projekt steht unter keiner offiziellen Lizenz. Nutzung erfolgt auf eigene Verantwortung – insbesondere bei der Anwendung auf offiziellen Webseiten.
  </p>

</body>
</html>
