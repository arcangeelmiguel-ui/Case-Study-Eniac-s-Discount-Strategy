<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ENIAC - Discount Strategy</title>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{background:#0F0F0F;color:#F5F3EF;font-family:'Inter',sans-serif;line-height:1.6}
.serif{font-family:'Instrument Serif',serif}
.mono{font-family:'JetBrains Mono',monospace}
.hero{padding:72px 40px 32px;max-width:1000px;margin:0 auto}
.badge{display:inline-block;background:#F5F3EF;color:#111;padding:8px 16px;border-radius:100px;font-size:11px;letter-spacing:.12em;margin-bottom:28px}
.hero h1{font-size:clamp(44px,7vw,84px);line-height:.9;letter-spacing:-.04em;font-weight:400}
.hero h1 i{font-style:italic;color:#FF8A3D}
.sub{margin-top:20px;font-size:14px;opacity:.65;max-width:720px;line-height:1.6}
.container{max-width:1000px;margin:0 auto;padding:0 40px 40px}
.card{background:#1A1A1A;border:1px solid #2A2A2A;border-radius:20px;padding:32px;margin-bottom:18px}
.card.light{background:#F5F3EF;color:#111;border-color:#EAE6E1}
.label{font-size:11px;letter-spacing:.15em;text-transform:uppercase;opacity:.55;margin-bottom:14px}
.big{font-size:19px;line-height:1.6}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}
@media(max-width:760px){.grid{grid-template-columns:1fr}}
.kpi{font-size:42px;line-height:1}
table{width:100%;border-collapse:collapse;margin-top:10px}
th{text-align:left;font-size:11px;letter-spacing:.1em;padding:10px 0;border-bottom:1px solid #333;opacity:.6}
td{padding:12px 0;border-bottom:1px solid #2A2A2A;font-size:14px}
.light td{border-bottom:1px solid #eee}
.light th{border-bottom:1px solid #111}
.pill{display:inline-block;background:#FF8A3D;color:#111;padding:6px 12px;border-radius:100px;font-size:11px;font-weight:600}
code{background:#2A2A2A;padding:2px 7px;border-radius:6px;font-size:13px}
.light code{background:#EAE6E1}
.footer{text-align:center;opacity:.35;font-size:11px;padding:20px 0 40px}
</style>
</head>
<body>
<div class="hero">
<div class="mono badge">CASE STUDY &nbsp;•&nbsp; REAL DATA &nbsp;•&nbsp; NO TEMPLATE</div>
<h1 class="serif">ENIAC<br><i>Discount Strategy</i></h1>
<div class="sub">Kosten Rabatte uns Umsatz und Ruf?<br>Eine Antwort mit Daten, nicht mit Meinung. Wir haben nicht gefragt, ob Rabatt gut oder schlecht ist. Wir haben gemessen, wohin der Rabatt geht, wer ihn bekommt und was er zurückbringt.</div>
</div>
<div class="container">
<div class="card">
<div class="mono label">Was das hier ist — und was nicht</div>
<div class="big">Das ist <b>kein Schulbeispiel mit erfundenen Zahlen.</b> Das ist eine echte Übung mit echten Transaktionsdaten von ENIAC: was wirklich verkauft wurde, zu welchem Preis, mit welchem Rabatt.<br><br>Wir haben den Datensatz erst sauber gemacht — besonders die Marke <b>Pack</b>, die keine Marke ist, sondern ein Bundle — und dann gefragt: <b>Wo verlieren wir Marge? Wo schützen wir das Markenbild? Und wo ist Rabatt eigentlich Investition?</b></div>
</div>
<div class="grid">
<div class="card light">
<div class="mono label">Datenbasis</div>
<div><span class="kpi serif">46.605</span><br>saubere Bestellungen</div><br>
<div><span class="kpi serif">9.992</span><br>Produkte im Katalog</div><br>
<div><span class="kpi serif">~14,4 Mio. €</span><br>Umsatz in der Analyse</div>
</div>
<div class="card">
<div class="mono label">Methode in einem Satz</div>
<div class="big">Umsatz je Zeile = <code>unit_price × product_quantity</code>.<br>Rabatt je Zeile = <code>1 − unit_price / price</code>.<br>Danach gruppiert nach <b>echter Marke</b>, <b>Preisklasse</b> und <b>Produktkategorie</b> — nicht nach SKU-Präfix allein.</div>
<div style="margin-top:18px"><span class="pill">WICHTIG: Pack wurde korrigiert</span></div>
<div style="font-size:14px;opacity:.75;margin-top:12px">PAC war 1.396 Produkte. Davon sind nur 829–894 echte Bundles (z.B. Synology NAS + Seagate). 506 sind konfigurierte 【entity-Apple¦canonical_name=Apple】 MacBooks, 53 sind OWC Packs. Wer Pack als Marke lässt, überschätzt Pack und unterschätzt 【entity-Apple¦canonical_name=Apple】.</div>
</div>
</div>
<div class="card">
<div class="mono label">Die drei Befunde, die alles entscheiden</div>
<table>
<tr><th>BEFUND</th><th>ZAHL</th><th>WAS ES HEISST</th></tr>
<tr><td><b>1. Wert ist konzentriert, Menge ist verteilt</b></td><td>8 Marken = 80% Umsatz<br>34 Marken = 80% Stück</td><td>Wer nur auf Stück schaut, sieht das Geschäft nicht. Ein Mac = 2.000 €, ein Kabel = 10 €.</td></tr>
<tr><td><b>2. Der Rabatt ist umgekehrt zum Umsatz</b></td><td>Unter 50 €: 26,5% Rabatt, nur 3,2% Umsatz<br>Über 1.000 €: 11,1% Rabatt, 47,2% Umsatz</td><td>Viel Rabatt, wo wenig Geld ist. Wenig Rabatt, wo viel Geld ist. Das schützt das Premium-Bild.</td></tr>
<tr><td><b>3. 【entity-Apple¦canonical_name=Apple】 ist die Investition, nicht der Verlust</b></td><td>60,7% Umsatz, 23,8% Stück<br>11,1% Rabatt, aber 48% vom gesamten Rabattgeld = 1,17 Mio. €</td><td>11% von 9,2 Mio. € sind mehr Geld als 74% von Jawbone. Prozent täuscht, Euro nicht.</td></tr>
</table>
</div>
<div class="card light">
<div class="mono label">Conclusion — Was wir empfehlen</div>
<div class="big"><b>1. Rabatt bei 【entity-Apple¦canonical_name=Apple】 nicht streichen, sondern kontrollieren.</b> Von 11,1% auf 10,1% senken und testen. Ein Prozentpunkt spart ca. <b>105.000 €</b>. Puffer: 4 von 100 Käufern dürfen abspringen, ohne Umsatzverlust.<br><br><b>2. Bei Zubehör nicht mehr Rabatt geben.</b> Zubehör hat schon 26,5% Rabatt und bringt nur 3,2% Umsatz.<br><br><b>3. Pack separat steuern.</b> Pack ist kein Brand. Es ist ein Bundle-Geschäft mit 14,6% gewichtetem Rabatt.<br><br><b>4. Ruf schützen, wo es zählt.</b> Bei MacBooks fast kein Rabatt. Bei Synology nur 2,8%. Das ist das Markenbild.</div>
</div>
<div class="card">
<div class="mono label">Dateien in diesem Repo</div>
<table>
<tr><th>DATEI</th><th>WAS DRIN IST</th></tr>
<tr><td><code>Eniac_Discount-Strategy_Presentation_2026-11-13_vFinal.pdf</code></td><td>Die Präsentation — Folien, Grafiken, Empfehlung</td></tr>
<tr><td><code>notebooks/Eniac_Pilot.ipynb</code></td><td>Der Pilot in Google Colab — Code, Checks, Pareto, Rabatt-Analyse</td></tr>
<tr><td><code>data / alle_marken_180.csv</code></td><td>Alle 180 Marken nach echter Marke, mit Umsatz und Menge</td></tr>
</table>
<div style="font-size:13px;opacity:.6;margin-top:14px">Hinweis: Umsatz = <code>unit_price × quantity</code> aus den verkauften Zeilen, nicht Katalogpreis. Gewinn ohne Einkaufspreise nicht berechenbar — wir sprechen bewusst von Umsatz und Rabattgeld, nicht von Gewinn.</div>
</div>
<div class="card">
<div class="mono label">Wie man das liest</div>
<div class="big" style="font-size:16px">Wenn du nur 2 Minuten hast: Lies die Tabelle oben. Wenn du 10 Minuten hast: Schau dir Folie 9 (Markenverteilung), Folie 10 (Preisklasse) und Folie 11 (【entity-Apple¦canonical_name=Apple】 48% Rabattgeld) an. Da steht die ganze Geschichte.</div>
</div>
</div>
<div class="footer mono">ENIAC_DISCOUNT-STRATEGY • README • WBS WEITERBILDUNG • CASE STUDY</div>
</body>
</html>
