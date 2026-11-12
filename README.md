# Dadi Vocali Accessibili

[![Version](https://img.shields.io/badge/version-1.0.3-blue.svg)](https://github.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PWA Ready](https://img.shields.io/badge/PWA-Ready-success.svg)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![Web Speech API](https://img.shields.io/badge/Web_Speech_API-Supported-orange.svg)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)
[![Accessibility](https://img.shields.io/badge/Accessibility-Screen_Free_UX-brightgreen.svg)](https://www.w3.org/WAI/)

Applicazione web progressiva (PWA) progettata per permettere a giocatori non vedenti o ipovedenti di lanciare i dadi per giochi di ruolo (come Dungeons & Dragons) in totale autonomia, utilizzando esclusivamente comandi vocali, feedback audio e un'interfaccia touch a schermo intero ad alto contrasto.

## Caratteristiche Principali

* **Controllo Vocale Bidirezionale (Web Speech API):**
  * **Input vocale:** Riconosce formule naturali in lingua italiana come *"1d20"*, *"un di quattro"*, *"due di sei più cinque"*, *"3d8 meno 2"* e *"testa o croce"*.
  * **Output vocale:** Legge ad alta voce il risultato del lancio selezionando automaticamente la migliore voce femminile italiana disponibile sul sistema.

* **Supporto Completo Dadi GdR e Meccaniche Speciali:**
  * Dadi poliedrici standard: **d4, d6, d8, d10, d12, d20, d100**.
  * Lancio moneta: **Testa o Croce**.
  * **Vantaggio e Svantaggio:** Supporta comandi come *"2d20 con vantaggio"* o *"2d20 con svantaggio"* (con eventuali modificatori), annunciando entrambi i risultati usciti e specificando il valore selezionato.

* **Isolamento Audio/Microfono (Anti-Eco):** Blocca preventivamente l'ascolto del microfono durante la sintesi vocale per evitare che l'applicazione interpreti la propria voce come un comando. Include inoltre un filtro anti-rimbalzo per prevenire lanci duplicati sullo stesso turno vocale.

* **Interfaccia Touch a Schermo Intero ad Alto Contrasto:**
  * Nessun pulsante piccolo o menu visivo complesso: l'intero schermo funge da area interattiva.
  * Sfondo nero assoluto con testo bianco e giallo ad altissima leggibilità per utenti con residuo visivo.

* **Progressive Web App (PWA):** Installabile su dispositivi mobili e desktop con supporto offline tramite Service Worker.

## Installazione e Utilizzo

### Installazione come App (PWA)

1. Apri l'applicazione tramite browser su smartphone o desktop (es. tramite GitHub Pages).
2. **Su Android (Chrome):** Apri il menu del browser e seleziona **"Installa app"** o **"Aggiungi a schermata Home"**.
3. **Su iOS (Safari):** Tocca il pulsante di condivisione e seleziona **"Aggiungi alla schermata Home"**.

### Comandi e Interazione

* **Tocco singolo sullo schermo (o Barra Spaziatrice / Invio):** L'applicazione pronuncia *"Lancia i dadi"* e attiva l'ascolto del microfono.
* **Doppio tocco sullo schermo (o tasto R):** Ripete immediatamente l'ultimo lancio effettuato senza dover ridettare la formula.

### Esempi di Comandi Vocali

| Comando Pronunciato | Formula Interpretata | Esempio di Risposta Vocale |
| :--- | :--- | :--- |
| *"1d20"* oppure *"un di venti"* | `1d20` | *"14"* |
| *"2d6 più 5"* | `2d6+5` | *"12"* |
| *"3d8 meno 1"* | `3d8-1` | *"15"* |
| *"2d20 con vantaggio"* | `2d20 (vantaggio)` | *"4 e 17. Con vantaggio: 17"* |
| *"2d20 con svantaggio più 3"* | `2d20+3 (svantaggio)` | *"18 e 6. Con svantaggio: 6, totale 9"* |
| *"testa o croce"* | `Testa o Croce` | *"Testa"* |

## Struttura del Repository

```text
.
├── index.html        # Interfaccia ad alto contrasto, parser vocale e logica dadi (v1.0.3)
├── manifest.json     # Configurazione PWA per installazione su dispositivo
├── sw.js             # Service Worker per caching e funzionamento offline
├── icon-192.png      # Icona applicazione (192x192)
├── icon-512.png      # Icona applicazione (512x512)
└── README.md         # Documentazione del progetto
```

## Note Tecniche

* **Compatibilità Browser:** Il riconoscimento vocale utilizza la `SpeechRecognition` / `webkitSpeechRecognition` API. Funziona in modo ottimale su Google Chrome (Android/Desktop) e Microsoft Edge.
* **Connessione:** L'interfaccia e la sintesi vocale funzionano interamente offline grazie al Service Worker; il riconoscimento vocale potrebbe richiedere una connessione dati attiva in base al motore vocale configurato sul dispositivo.

## Licenza

Questo progetto è distribuito sotto licenza **MIT**. Consulta il file `LICENSE` per i dettagli completi.