# Website Design Recreation


## Workflow

1. **Genereaza** un singur fisier 'index.html' utilizand Tailwind CSS (via CDN). Include tot continutul inline - nici un fisier extern m daca nu este cerut.

2. **Captureaza** pagina randata cuPuppeteer ('npx puppeteer screenshot index.html --fullpage' sau echivalent ). Daca pagina are sectiuni distincte, captureazale si pe astea individual.

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

Nu te oprii dupa un pas. Realizează întotdeauna minimum două runde de comparație. 
Te opresti cind userul iti spune sau cind nu raman diferente vizibile.


## Setări tehnice implicite

- utilizeaza Tailwin CSS via CDN ('<script src="https://cdn.tailwindcss.com"></script>')
- utilizeaza imagini de substitutie (placeholders) de la 'https://placehold.co' cind sursa imaginilor nu este furnizata.
- foloseste mobile-first responsive design
- fa un singur fisier 'index.html' daca userul nu cere altfel

Situl de referinta este la adresa: https://resend.com