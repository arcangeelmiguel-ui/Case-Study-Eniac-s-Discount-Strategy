# ENIAC — Discount Strategy

## Projekt-Kontext

Dieses Projekt entstand im Rahmen des **DSAI-Kurses von WBS Coding**.

Analysiert wurde ein Datensatz der **fiktiven Firma ENIAC**. Der Datensatz wurde bereinigt und ausgewertet, um die Rabatt-Strategie des Unternehmens nachzuvollziehen und zu verbessern.

**Leitfrage:** Kosten Rabatte uns Umsatz und Ruf?

**Datenbasis**
- 46.605 bereinigte Bestellzeilen
- 9.992 Produkte im Katalog
- 14,4 Mio. € Umsatz in der Analyse
- 180 Marken nach Bereinigung

**Berechnungslogik**
- Umsatz je Zeile = `unit_price × product_quantity`
- Rabatt je Zeile = `1 − unit_price / price`
- Gruppierung nach bereinigter Marke, Preisklasse und Produktkategorie

---

## Was hier anders gemacht wurde

Nicht nach SKU-Präfix gruppiert. Sondern nach tatsächlicher Marke.

Das ist der entscheidende Schritt in dieser Analyse. Wer nach Präfix gruppiert, zählt Bundles als Marke und konfigurierte Produkte als Zubehör. Das Ergebnis ist dann falsch, auch wenn die Berechnung stimmt.

**Korrektur: Pack**

`PAC` stand für 1.396 Produkte. Nach Bereinigung:

- 829–894 echte Bundles, z. B. Synology NAS + Seagate
- 506 konfigurierte 【entity-Apple¦canonical_name=Apple】 MacBooks
- Rest: sonstige konfigurierte Produkte

**Konsequenz:** Pack ist kein Brand. Pack ist ein Bundle-Geschäft. Wer Pack als Marke lässt, überschätzt Pack und unterschätzt 【entity-Apple¦canonical_name=Apple】.

---

## Drei Befunde

### 1. Wert ist konzentriert, Menge ist verteilt

- 8 Marken tragen 80% des Umsatzes
- 34 Marken tragen 80% der Stückzahl

Ein 【entity-Mac¦canonical_name=Mac】 liegt bei rund 2.000 €. Ein Kabel bei rund 10 €. Wer nur Stückzahl betrachtet, sieht das Geschäft nicht.

### 2. Rabatt verläuft gegenläufig zum Umsatz

| Preisklasse | Rabatt | Anteil am Umsatz |
| :--- | :--- | :--- |
| Unter 50 € | 26,5% | 3,2% |
| Über 1.000 € | 11,1% | 47,2% |

Viel Rabatt, wo wenig Umsatz entsteht. Wenig Rabatt, wo viel Umsatz entsteht. Das schützt das Premium-Bild.

### 3. Apple ist Investition, kein Verlust

- 60,7% des Umsatzes
- 23,8% der Stückzahl
- 11,1% Rabatt
- 48% des gesamten Rabattgeldes = 1,17 Mio. €

11% von 9,2 Mio. € sind mehr Geld als 74% von Jawbone. Prozent täuscht. Euro nicht.

---

## Empfehlung

**1. Apple-Rabatt kontrollieren, nicht streichen.**
Von 11,1% auf 10,1% senken und testen. Ein Prozentpunkt entspricht ca. 105.000 €. Puffer: 4 von 100 Käufern dürfen abspringen, ohne Umsatzverlust.

**2. Zubehör nicht weiter rabattieren.**
Zubehör trägt bereits 26,5% Rabatt und nur 3,2% Umsatz.

**3. Pack separat steuern.**
Pack ist kein Brand. Es ist ein Bundle-Geschäft mit 14,6% gewichtetem Rabatt.

**4. Ruf schützen, wo er entsteht.**
Bei MacBooks fast kein Rabatt. Bei Synology 2,8%. Das ist das Markenbild.

---

## Dateien

| Datei | Inhalt |
| :--- | :--- |
| `Eniac_Discount-Strategy_Presentation_2026-11-13_vFinal.pdf` | Präsentation — Folien, Abbildungen, Empfehlung |
| `Eniac_Discount-Strategy_Pilot_2026-11-13_vFinal.ipynb` | Pilot in Google Colab — Code, Checks, Pareto, Rabatt-Analyse, Code für alle Abbildungen der Präsentation |
| `data / alle_marken_180.csv` | Alle 180 Marken nach bereinigter Marke, mit Umsatz und Stückzahl |

> Abgrenzung: Ausgewiesen wird Umsatz und Rabattgeld, nicht Gewinn. Ohne Einkaufspreise ist kein Gewinn berechenbar.

## Lesehinweis

2 Minuten: Tabelle unter „Drei Befunde" lesen.
10 Minuten: Folie 9 (Markenverteilung), Folie 10 (Preisklasse), Folie 11 (Apple Rabattgeld) ansehen. Dort steht die gesamte Argumentation.

---

## Danksagung

Persönlich war die Sprache die größte Herausforderung.
Ich habe viel Hilfe von Tim und Walter bekommen. Ohne sie wäre das nicht gegangen.
Wir haben als Team gut gearbeitet. Manchmal haben wir uns auch außerhalb der Stunden getroffen. Das war notwendig und produktiv. Und es hat sich gelohnt.
