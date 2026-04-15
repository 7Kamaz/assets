
---
## ⚔ FASE 2 — WEB PROFISSIONAL
*Dias 11–18 · DCPT 2020 módulos web · THM Web Rooms · PortSwigger FREE*

### Objetivo da Fase
Dominar os vetores web que aparecem em TODA prova CPTS: SQLi manual e com sqlmap, XSS reflected/stored, LFI→RCE, file upload bypass, IDOR, SSRF, command injection. Burp Suite Pro como segunda natureza.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase2.png)


---

> [!IMPORTANT] **Barra de Progresso**
> 
> ```dataviewjs
> const tasks = dv.current().file.tasks;
> const total = tasks.length;
> const completed = tasks.where(t => t.completed).length;
> const percent = Math.round((completed / total) * 100);
> 
> dv.paragraph(`### Progresso Atual: ${percent}%`);
> dv.paragraph(`<progress value="${percent}" max="100" style="width:100%; height:20px; accent-color: #00ff00;"></progress>`);
> dv.paragraph(`✅ **${completed}** tarefas concluídas de **${total}** totais.`);
> ```

---
### DIA 11 · Burp Suite Pro — Fluência Completa ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Fundamentos de Web (HTTP, cookies, headers, sessions) + intro ao Burp no DCPT
- [ ] **🎮 THM Premium** THM: Burp Suite: The Basics & Repeater (Premium) — todos os tasks
- [ ] **🆓 Lab Grátis** PortSwigger: Getting Started labs (gratuito: portswigger.net/web-security/getting-started)
- [ ] **📖 Teoria (40min)** Proxy Intercept, Repeater (Ctrl+R), Intruder (4 tipos), Scanner passivo/ativo, Decoder, Target Scope.
- [ ] **⚒ Prática (70min)** Configurar FoxyProxy. Interceptar 10 requests diferentes. Modificar headers, cookies, parâmetros no Repeater.
- [ ] **📝 Anotações (10min)** Bible: fluxo Burp por tipo de ataque (SQLi → Repeater, BF → Intruder, Scan → Scanner)

---

### DIA 12 · SQL Injection Manual ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (SQL Injection: manual, error-based, union-based, blind)
- [ ] **🎮 THM Premium** THM: SQL Injection (Premium) — todos os tasks
- [ ] **🆓 Lab Grátis** PortSwigger: SQL Injection labs gratuitos (error-based, union, blind)
- [ ] **📖 Teoria (40min)** ' OR '1'='1, UNION SELECT, information_schema, sleep(5), error-based extraction. MySQL vs MSSQL vs Oracle syntax.
- [ ] **⚒ Prática (70min)** DVWA: SQLi Easy → Medium → Hard. PortSwigger: 2 labs de SQLi gratuitos. Burp Repeater para cada teste.
- [ ] **📝 Anotações (10min)** Bible: cheatsheet SQLi por tipo (error, union, blind time) com payloads testados

---

### DIA 13 · SQLMap + SQLi Avançado ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (sqlmap: flags, tamper scripts, dump, shell)
- [ ] **🎮 THM Premium** THM: SQL Injection Lab (Premium) — aplicação prática com sqlmap
- [ ] **🆓 Lab Grátis** DVWA + HackTheBox Starting Point: Appointment (SQLi puro, gratuito)
- [ ] **📖 Teoria (40min)** `sqlmap -u URL -p param --dbs --tables --dump --os-shell --level 5 --risk 3 --tamper=space2comment`.
- [ ] **⚒ Prática (70min)** DVWA High: SQLi com sqlmap + tamper. HTB Appointment: exploitar SQLi login bypass manual.
- [ ] **📝 Anotações (10min)** Bible: flags sqlmap mais usadas no CPTS + quando usar tamper

---

### DIA 14 · XSS + LFI → RCE ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (XSS: reflected, stored, DOM. LFI: /etc/passwd, log poisoning, php wrapper)
- [ ] **🎮 THM Premium** THM: Cross-site Scripting (Premium) + THM: File Inclusion (Premium)
- [ ] **🆓 Lab Grátis** PortSwigger: XSS reflected lab gratuito + DVWA LFI
- [ ] **📖 Teoria (40min)** XSS: `<script>alert(1)</script>`, bypass de filtros, stored vs reflected. LFI: `../../../etc/passwd`, log poisoning via User-Agent, `php://filter/convert.base64-encode`.
- [ ] **⚒ Prática (70min)** DVWA: XSS todos os levels. THM File Inclusion: LFI para RCE via log poisoning.
- [ ] **📝 Anotações (10min)** Bible: LFI → RCE pathway (4 etapas) + XSS payload bank

---

### DIA 15 · File Upload Bypass ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (File Upload: extensão, content-type, magic bytes, double ext)
- [ ] **🎮 THM Premium** THM: Upload Vulnerabilities (Premium) — todos os tasks
- [ ] **🆓 Lab Grátis** PentesterLab: File Upload exercises (gratuito — conta free tem acesso a exercises básicos)
- [ ] **📖 Teoria (40min)** Vetores: mudar extensão (.php→.phtml, .php5, .phar), mudar Content-Type (image/jpeg), magic bytes (ÿØÿ), double ext.
- [ ] **⚒ Prática (70min)** THM Upload Vulnerabilities: completar todos os tasks. Burp Repeater: testar cada bypass em sequência.
- [ ] **📝 Anotações (10min)** Fluxograma Bible: upload bypass — árvore de decisão do que tentar em cada caso

---

### DIA 16 · IDOR + Auth Bypass + SSRF ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (IDOR, broken access control, SSRF básico)
- [ ] **🎮 THM Premium** THM: OWASP Top 10 (Premium) — tasks de IDOR, Broken Auth e SSRF
- [ ] **🆓 Lab Grátis** PortSwigger: IDOR lab gratuito (Access Control section) + SSRF basic lab gratuito
- [ ] **📖 Teoria (40min)** IDOR: trocar IDs em requests. Auth bypass: alterar roles/cookies/JWT. SSRF: `?url=http://127.0.0.1/admin`, metadata AWS.
- [ ] **⚒ Prática (70min)** PortSwigger: lab IDOR + SSRF básico. DVWA: Insecure CAPTCHA e Weak Session IDs. Manipular JWT manualmente.
- [ ] **📝 Anotações (10min)** Bible: IDOR checklist — onde procurar IDs. SSRF payloads internos e cloud metadata.

---

### DIA 17 · Command Injection + XXE ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (Command Injection: ;, &&, \
- [ ] **🎮 THM Premium** THM: Command Injection (Premium) — tasks de blind e verbose command injection
- [ ] **🆓 Lab Grátis** PortSwigger: Command Injection labs gratuitos (OS command injection — simple e blind)
- [ ] **📖 Teoria (40min)** Payloads: `; id`, `&& whoami`, `
- [ ] **⚒ Prática (70min)** PortSwigger: 2 labs Command Injection free. DVWA: Command Injection todos os levels.
- [ ] **📝 Anotações (10min)** Bible: payloads injection por contexto (Linux vs Windows, verbose vs blind)

---

### DIA 18 · Web — Revisão + Lab Integrado ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão dos módulos DCPT web: rever seções de SQLi avançado, LFI e upload que ficaram pendentes
- [ ] **🎮 THM Premium** THM: Corridor (Premium) — IDOR/path manipulation. THM: Pickle Rick (Premium) — web completo
- [ ] **🆓 Lab Grátis** HackTheBox Starting Point: Tier 1 — Three ou Appointment (HTTP/SQL, gratuito no free tier)
- [ ] **📖 Teoria (40min)** Rever: SQLi manual, XSS stored, LFI→RCE, upload bypass. Solidificar o fluxo com Burp.
- [ ] **⚒ Prática (70min)** Comprometer Pickle Rick (THM) sem writeup. Depois HTB Starting Point Appointment (SQLi puro).
- [ ] **📝 Anotações (10min)** Retrospectiva Fase 2: vetores dominados, vetores ainda frágeis. Plano para Fase 3.
# Testar se tem competência para o WEB-RTA da CWL...

⚔️ 🔥 WEB-RTA — Labs obrigatórios (THM Premium)
🧠 Nível base → fluência (tem que sair rápido)
OWASP Top 10 Room
Burp Suite: The Basics
Burp Suite: Repeater
👉 Aqui você tem que:
Interceptar tudo no automático
Manipular request sem pensar
💥 Nível exploração real (CORE da prova)
SQL Injection
Cross-site Scripting
Command Injection
File Inclusion
Upload Vulnerabilities
👉 Aqui é obrigatório:
Testar payload manual
Usar Burp Repeater sempre
Não depender de ferramenta pronta
🧠 Nível “junção de vulnerabilidades” (onde separa iniciante de pronto)
Pickle Rick
Corridor
Pyrat
👉 Aqui você prova que:
Sabe pensar
Sabe encadear falhas
Não depende de “lab guiado”
🎯 CRITÉRIO FINAL WEB (sem enrolação)
Se você:
Faz Pickle Rick + Pyrat sem ajuda
Resolve vulnerabilidades sem googlar payload pronto
Consegue explicar o que fez
👉 Você tá pronto pro WEB-RTA.

---