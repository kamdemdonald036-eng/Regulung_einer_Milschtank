# Regulung_einer_Milschtank
# 🧠 MPC Tank Projekt 2024  
**Modul:** Höhere Regelungstechnik und Modellierung  
**Hochschule:** Fachhochschule Westküste  
**Betreuer:** Prof. Dr. K. Völtzer  
**Semester:** WiSe 2024/25  

---

## 📘 Projektbeschreibung
Dieses Projekt behandelt den **Entwurf und die Inbetriebnahme einer modellprädiktiven Mehrgrößenregelung (MPC)** für einen Tankversuchsstand.  
Ziel ist es, **einen vorgegebenen Füllstand und eine gewünschte Temperatur in einem Mischtank schnell und stabil zu erreichen**, unter Verwendung von MATLAB/Simulink und PCS7.

Der entwickelte MPC-Regler soll sowohl in Simulation als auch am realen Versuchsstand getestet werden.

---

## ⚙️ Systemübersicht

### Regelgrößen (Controlled Variables - CV)
- **Füllstand (LIC 30)**  
- **Temperatur (TIC 40)**  

### Stellgrößen (Manipulated Variables - MV)
- **Durchfluss Warmwasser (FIC 50)**  
- **Durchfluss Kaltwasser (FIC 51)**  

### Störgrößen (Disturbance Variables - DV)
- **Kühlwassertemperatur (TIC 10)**  
- **Heizwassertemperatur (TIC 60)**  

**Betriebsgrenzen:**
- Max. Wassertemperatur: 60 °C  
- Mindestfüllstand muss gewährleistet sein  

---

## 🧩 Projektaufgaben

### 🔹 Aufgabe 1 – Analyse und Systemidentifikation
- Beschreibung der Funktionsweise des Versuchsstandes anhand des R&I-Schemas  
- Ermittlung der Stellgrößen und Störgrößen im Arbeitspunkt  
- Durchführung von Sprungantwortversuchen  
- Bestimmung von:
  - Verstärkung \(K_s\)
  - Totzeit \(T_t\)
  - Zeitkonstanten \(T_\Sigma\)
  - Ausgleichszeit  
- Wahl geeigneter Modelltypen (z. B. PT1, IT1, PT2Tt …)  
- Darstellung und Interpretation der Ergebnisse  

---

### 🔹 Aufgabe 2 – Modellbildung
- Festlegung einer geeigneten Abtastzeit  
- Entwicklung eines Testsignals zur simultanen Systemanregung  
- Durchführung der Datenerfassung und Aufteilung in **Trainings-/Validierungsdaten**  
- Modellidentifikation mit der **System Identification Toolbox**  
- Vergleich und Validierung der Modelle (Fit, Korrelation, Sprungantwort)  

---

### 🔹 Aufgabe 3 – MPC-Reglerentwurf
- Entwurf und Tuning eines **MPC-Reglers** für den Tankprozess  
- Priorisierung der Temperaturregelung  
- Simulation und Test an der realen Anlage  
- Vergleich der Ergebnisse:  
  - Ausregelzeit  
  - Überschwingen  
  - Standardabweichung der Regeldifferenz  
- Visualisierung mit `histogram()` und `std()`  

**Test-Szenario:**

| Zeit [s] | Soll-Temperatur [°C] | Soll-Füllstand [l] |
|-----------|---------------------|--------------------|
| 0         | 25.0                | 3.5                |
| 300       | 23.5                | 6.0                |
| 500       | 25.0                | 4.0                |
| 700       | 26.0                | 7.0                |

---

### 🔹 Aufgabe 4 – Präsentation
- Erstellung einer ca. 10-minütigen Präsentation  
- Vorstellung der Methodik, Ergebnisse und des Regelungskonzepts  
- Abgabe der Dokumentation und Simulationsdateien bis **13.01.2025**  

---

## 🧰 Verwendete Tools
- **MATLAB & Simulink**
  - System Identification Toolbox  
  - Model Predictive Control Toolbox  
- **PCS7 / WinCC**
  - Prozessvisualisierung und Kommunikation  
- **OPC-Schnittstelle** zur Datenübertragung  

---

## 💻 Projektstruktur (Empfohlene Ordnerstruktur)

```bash
MPC_Tank_Projekt_2024/
│
├── 📁 data/                 # Mess- und Versuchsdaten
├── 📁 models/               # Identifizierte Modelle und Parameter
├── 📁 matlab/               # MATLAB- und Simulink-Skripte
├── 📁 results/              # Plots, Simulationsergebnisse, Histogramme
├── 📁 docs/                 # Bericht, Präsentation, PDF-Unterlagen
└── README.md
