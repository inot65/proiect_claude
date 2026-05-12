# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This project focuses on recreating the design of a reference website (currently https://resend.com) using a single-file HTML approach with Tailwind CSS.

## Common Commands
- Capture page screenshot: `npx puppeteer screenshot index.html --fullpage`

## Architecture & Structure
- `index.html`: The main entry point containing all HTML and Tailwind CSS styles.
- `screencapture-*.png`: Reference and comparison screenshots used for visual auditing.

## Website Design Recreation Workflow
1. **Genereaza** un singur fisier 'index.html' utilizand Tailwind CSS (via CDN). Include tot continutul inline - nici un fisier extern m daca nu este cerut.
2. **Captureaza** pagina randata cu Puppeteer ('npx puppeteer screenshot index.html --fullpage' sau echivalent). Daca pagina are sectiuni distincte, captureazale si pe astea individual.
3. **Compara** screenshot-ul tau cu imaginea de referinta. Cauta nepotriviri in:
    - spatiere si padding (masurat in px)
    - dimensiune fonta, latime si inaltime linii
    - culori (valori hexa exacte)
    - aliniere si pozitionare
    - unghiul border , umbre si efecte
    - comportamentul responsiv
    - dimensiuni imagini/iconuri si plasament
4. **Fixeaza** orice nepotrivire gasita
5. **Re-captureaza** si compara inca odata
6. **Repeta** pasii 3-5 pina cand rezultatul este in aproximativ 2-3px de referinta oriunde.

Nu te oprii dupa un pas. Realizează întotdeauna minimum două runde de comparație. Te opresti cind userul iti spune sau cind nu raman diferente vizibile.

## Setări tehnice implicite
- utilizeaza Tailwind CSS via CDN ('<script src="https://cdn.tailwindcss.com"></script>')
- utilizeaza imagini de substitutie (placeholders) de la 'https://placehold.co' cind sursa imaginilor nu este furnizata.
- folosese mobile-first responsive design
- fa un singur fisier 'index.html' daca userul nu cere altfel
- Situl de referinta: https://resend.com
