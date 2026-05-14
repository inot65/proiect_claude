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

va apare un folder .claude in cadrul proiectului curent (pe masura ce il implicam in lucru la proiectul curent)

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


in folderul rules/ pot pune mai multe fisiere cu instructiuni, care sunt folosite ca si fisierul CLAUDE.md (sau il pot sparge pe asta in mai multe fisiere cu reguli care le pun in folderul /rules/)
Se pot refolosii in mai multe proiecte !


Exista 3 straturi de CLAUDE.md

1. personal global
    aflat in fisierul : ~/.claude/CLAUDE.md , separat de proiect

2. per proiect
    aflat in fisierul : .claude/CLAUDE.md , in cadrul proiectului
    Este replicat in repository-ul din github

3. enterprise : organizat la nivel de sistem:  CLAUDE.md



daca nu am definit eu CLAUDE.md pentru proiect, pot da comanda:

/init in promptul Claude si acest CLAUDE.md se va autoconstrui, incluzind toate fisierele initiale din folderul proiectului, scutindu-ne de efortul de a-l scrie direct noi.


Ce se face si ce nu se face  in CLAUDE.md
=========================================

ce se face 
----------

- ruleaza /init intr-un folder de proiect nou
- densitate mare de informatie
- hedinguri scurte, puncteaza diverse idei
- lucrurile critice urca-le cat mai SUS
- review-uri si eliminari de informatii periodice, pentrua nu creste prea mult

ce NU se face
-------------

- nu copia documentatii intregi de API in acest fisier (chestie de costuri si bloat)
- nu scrie reguli vagi ( 'fii smart' sau 'nu face greseli') 
- nu depasii ~ 500 de linii
- adauga reguli cin Claude greseste in mod repetat

De regula tehnologia AI evolueaza rapid, asa ca sfaturile mai vechi de 3 luni, nu prea mai sunt valoroase

E bine sa merg pe GROK AI si sa-i ceri ultimele sfaturi cele mai valoroase din ultima luna


fisierul MEMORY.md
==================

este global !

locatia: ~/.claude/projects/<project-hash>/memory/MEMORY.md

Primele 200 linii se incarca in sistem la startul unei noi sesiunii

Claude citeste si scrie in timpul unei sesiuni diverse date, pentru a le tine minte intre sesiuni

Este fisier de note ale lui Claude, il scrie Claude singur, nu utilizatorul. Poti spune lui Claude, ca utilizator, sa memoreze date in MEMORY.md

Claude transcrie memoria de la o sesiune la alta, pt a tine minte chestiile importante facute in trecut



Agenti
======

sunt fisiere de tip .md aflate in folderul /agents/ care au o anumita structura specifica:

name: - nume agent
description: - descriere de nivel al agentului
model: modelul LLM folosit
tools: instrumentele de care se poate folosii pentru a realiza ce am scris in "descriere"
    - Bash (de ex)

Apoi urmeaza niste pasi care se efectueaza pentru a realiza ce dorim noi la nivel de "descriere"
(similar cu CLAUDE.md , dar este la nivel de subagenti ! )

Pentru ce folosim subagentii ?
------------------------------

ca sa separam contextul !

1. nu se mai polueaza contextul printe cu sarcini mai murdare

2. putem folosii un subagent cu un model mai ieftin decat modelul parinte, reducand costurile !

Exista in practica, 3 tipuri de agenti utili
--------------------------------------------

1. agent de research: cautare pe web, citire mult text din carti pdf , word, etc., sumarizeaza texte lungi

2. code review agent: specializat pe cod scris, da feedback obiectiv catre parinte

3. agent QA: asigura testarea codului



Skills (abilitati)
==================

sunt  comenzi date cu slash:

de ex. /init, /compact, /context

in fisierul SKILL.md voi realiza niste comenzi care le voi putea accesa apoi cu in mod clasic cu slash

unde le gasesc :
.claude/skills/<skill-name>/SKILL.md - la nivel de proiect
~/.claude/skills/<skill-name>/SKILL.md - la nivel global
.claude/commands/<skill-name>.md - format mai vechi, dar inca functioneaza !


Template-ul pentru SKILL.md
---------------------------

---
name: api-conventions
description: API design patterns for this codebase
---

When writing API endpoints:
- Use RESTful naming conventions
- Return consistent error formats
- Include request validation



Modurile de permisiune din Claude Code
======================================

sunt 6 moduri

1. default (denumit "ask before edits")

2. acceptEdits (editare automata, cere accept doar pt comenzi shell sau de retea)

3. plan ()

4. auto

5. dontAsk

6. bypassPermissions


Cu shift+TAB pot trece de la o permisiune la alta, ciclic , cind est in prompt-ul Claude


Modul plan
----------

se face de catre Claude Code un plan de activiatate pt a atinge obictivul cerut


Pentru a vedea gradul de utilizare al tokenilor, se foloseste :

/usage

In contul tau se poate chia sa setezi limita maxima pentru extra-usage (care bineninteles ca se plateste), sau poti sa interzici extrausage (cit ai platit, ata folosesti, dupa care STOP !)


comanda /clear, sterge contextul - se da deobicei cand trec la o sarcina complet diferita de ce am facut pina atunci.



Vorbeste despre skill-uri
=========================

Apify - Actorii Apify extrag date web actualizate de pe orice site web pentru aplicații și agenți AI, monitorizarea rețelelor sociale, informații despre concurență, generarea de clienți potențiali și cercetarea produselor.




MCP
===

vine de la : Model Context Protocol

MCP = Skill extern



Plugin-urile
============

context7  - aduce documentatiile la zi si le compreseaza prin compactare 


Subagenti
=========

exista un agenta parinte care poate folosii pentru pararelizare munca o serie de subagenti.

Subagentii din Agent Teams lucreaza in izolare (nu comunica unul cu altul) si transmit rezultatul vatre parinte apoi se opresc. Ei nu pot crea subagenti !

Comparartie intre subagenti si Agent Teams
------------------------------------------

Subagentii pot face agenti copii care comunica intre ei, isi impartasesc din descoperiri si erori, pentru a evita repetarea lor.

Git worktrees
=============

este precursorul lui Agent Teams

faci ca un un singur sub-agent sa lucreze pe un branch al repositoriului, si apoi agentul parinte sa se ocupe de merge final, pentru a imbina toate rezultatele subagentilor in branch-ul principal




Modal (faci deploy API cu Modal)
================================

e o modalitate de a simplifica deploymentul

link:  modal.com


"n8n cloud" face ceva similar


zapier.com, make.com face ceva similar


poti pune pe web unele skill-uri care se vor declansa daca intrii pe link-ul dat !

Mai nou, Claude Code a introdus "routines" care e cam tot aia, numai ca e integrat direct in Claude Code

