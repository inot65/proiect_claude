Exemple de site-uri gata construite:

godly.website - site cu diverse exemple de elemente grafice create cu AI si codul html/css/js necesar pentru a le implementa. Se pot copia si adapta exemplele.

componente de folosit:

21st.dev - componente React cu AI - 

desenare si prezentare:

excalidraw.com - whiteboard, desenat cu AI si transformat in cod HTML, CSS si JS, se pot desena wireframe-uri si prototipuri - https://next.excalidraw.com/?gemini-app=true - link cu AI integrat.


API key:
AIzaSyCThSSP4I9D8YIApher83hTx3gzvbC3pyQ

Name:
Gemini API Key

Project name:
projects/1023904387025

Project number:
1023904387025


https://generativelanguage.googleapis.com/v1beta/openai/


gemini-1.5-flash ?


lansare claude cu modelul gemma4:31b-cloud: 

> ollama launch claude --model gemma4:31b-cloud


Publicare pe situri a aplicatiei realizate:

se poate face pe Vercel, Modal, Netlify



Chestii avansate in Claude
--------------------------

exista un folder ascuns .claude  in care ai cam 10-15 functionalitati avansate

se pot face setari:
- per proiect , in folderul .claude
- globale, in folderul ~/.claude/

Seteri per proiect
------------------

- exista fisierul settings.json, care este un agregator de permisiuni al echipei de lucru la proiect, si hooks-uri
- exista fisierul settings.local.json, care este stocat doar local, este inclus in .gitignore pt a nu fi replicat pe github, pt ca pot contine chestii secrete
- CLAUDE.md este un fisier cu instructiuni de proiect, replicat pe github
- CLAUDE.local.md este un fisier personal de note, nereplicat pe github
- agents/, este un folder pt subagenti
- skils/, este un folder cu comenzi slash
- rules/, este un folder cu fisiere modulare de instructiuni
        cum ar fi:
            - code-style.md
            - frontend/react.md
- fisierul .mcp.json:  servere MCP care tin de proiect


