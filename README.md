# ENIAC — Discount Strategy

## Projekt-Kontext

Dieses Projekt entstand im Rahmen des **DSAI-Kurses von WBS Coding**.

Es wurde ein Datensatz der **fiktiven Firma Eniac** bereinigt und analysiert, um die Rabatt-Strategie des Unternehmens nachzuvollziehen und zu verbessern.

**Frage:** Kosten Rabatte uns Umsatz und Ruf?

**Datenbasis:** 46.605 saubere Bestellungen, 9.992 Produkte im Katalog, ~14,4 Mio. € Umsatz in der Analyse.

**Methode:** Umsatz je Zeile = `unit_price × product_quantity`. Rabatt je Zeile = `1 − unit_price / price`. Danach gruppiert nach echter Marke, Preisklasse und Produktkategorie.

---

## Was das hier ist — und was nicht

Das ist **kein Schulbeispiel mit erfundenen Zahlen.** Das ist eine echte Übung mit echten Transaktionsdaten von Eniac: was wirklich verkauft wurde, zu welchem Preis, mit welchem Rabatt.

Wir haben den Datensatz erst sauber gemacht — besonders die Marke **Pack**, die keine Marke ist, sondern ein Bundle — und dann gefragt: Wo verlieren wir Marge? Wo schützen wir das Markenbild? Und wo ist Rabatt eigentlich Investition?

> **WICHTIG: Pack wurde korrigiert.** PAC war 1.396 Produkte. Davon sind nur 829–894 echte Bundles (z.B. Synology NAS + Seagate). 506 sind konfigurierte 【entity-Apple¦canonical_name=Apple】 MacBooks. Wer Pack als Marke lässt, überschätzt Pack und unterschätzt 【entity-Apple¦canonical_name=Apple】.

## Die drei Befunde, die alles entscheiden

| Befund | Zahl | Was es heisst |
| :--- | :--- | :--- |
| **1. Wert ist konzentriert, Menge ist verteilt** | 8 Marken = 80% Umsatz<br>34 Marken = 80% Stück | Wer nur auf Stück schaut, sieht das Geschäft nicht. Ein Mac = 2.000 €, ein Kabel = 10 €. |
| **2. Der Rabatt ist umgekehrt zum Umsatz** | Unter 50 €: 26,5% Rabatt, nur 3,2% Umsatz<br>Über 1.000 €: 11,1% Rabatt, 47,2% Umsatz | Viel Rabatt, wo wenig Geld ist. Wenig Rabatt, wo viel Geld ist. Das schützt das Premium-Bild. |
| **3. 【entity-Apple¦canonical_name=Apple】 ist die Investition, nicht der Verlust** | 60,7% Umsatz, 23,8% Stück<br>11,1% Rabatt, aber 48% vom gesamten Rabattgeld = 1,17 Mio. € | 11% von 9,2 Mio. € sind mehr Geld als 74% von Jawbone. Prozent täuscht, Euro nicht. |

## Conclusion — Was wir empfehlen

**1. Rabatt bei 【entity-Apple¦canonical_name=Apple】 nicht streichen, sondern kontrollieren.** Von 11,1% auf 10,1% senken und testen. Ein Prozentpunkt spart ca. **105.000 €**. Puffer: 4 von 100 Käufern dürfen abspringen, ohne Umsatzverlust.

**2. Bei Zubehör nicht mehr Rabatt geben.** Zubehör hat schon 26,5% Rabatt und bringt nur 3,2% Umsatz.

**3. Pack separat steuern.** Pack ist kein Brand. Es ist ein Bundle-Geschäft mit 14,6% gewichtetem Rabatt.

**4. Ruf schützen, wo es zählt.** Bei MacBooks fast kein Rabatt. Bei Synology nur 2,8%. Das ist das Markenbild.

## Dateien in diesem Repo

| Datei | Was drin ist |
| :--- | :--- |
| `Eniac_Discount-Strategy_Presentation_2026-11-13_vFinal.pdf` | Die Präsentation — Folien, Grafiken, Empfehlung |
| `Eniac_Discount-Strategy_Pilot_2026-11-13_vFinal.ipynb` | Der Pilot in Google Colab — Code, Checks, Pareto, Rabatt-Analyse, **Code für alle Abbildungen der Präsentation** |
| `data / alle_marken_180.csv` | Alle 180 Marken nach echter Marke, mit Umsatz und Menge |

> Hinweis: Umsatz = `unit_price × quantity` aus den verkauften Zeilen, nicht Katalogpreis. Gewinn ohne Einkaufspreise nicht berechenbar — wir sprechen bewusst von Umsatz und Rabattgeld, nicht von Gewinn.

## Wie man das liest

Wenn du nur 2 Minuten hast: Lies die Tabelle oben. Wenn du 10 Minuten hast: Schau dir Folie 9 (Markenverteilung), Folie 10 (Preisklasse) und Folie 11 (【entity-Apple¦canonical_name=Apple】 48% Rabattgeld) an. Da steht die ganze Geschichte.

---

## Danksagung

Persönlich war die Sprache die größte Herausforderung.
Ich habe viel Hilfe von Tim und Walter bekommen. Ohne sie wäre das nicht gegangen.
Wir haben als Team wirklich gut gearbeitet. Manchmal haben wir uns auch außerhalb der Stunden getroffen. Das war notwendig und produktiv. Und es hat sich gelohnt.
