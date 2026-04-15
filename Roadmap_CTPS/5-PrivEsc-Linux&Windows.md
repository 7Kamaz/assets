
---
## ⚔ FASE 5 — PRIVILEGE ESCALATION + SHELLS + REPORTING
*Dias 35–44 · DCPT 2020 · THM PrivEsc Rooms · GTFOBins · SysReptor*

### Objetivo da Fase
PrivEsc é onde a maioria perde tempo no CPTS. Esta fase cobre todos os vetores Linux e Windows de forma sistemática. Também cobre shells estáveis, transferência de arquivos e relatório profissional — metade da nota do exame.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase5.png)


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
### DIA 35 · Linux PrivEsc — Enumeração Sistemática ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pós-Exploração (Linux PrivEsc: linPEAS, sudo -l, SUID, capabilities, cron, writable paths)
- [ ] **🎮 THM Premium** THM: Linux Privilege Escalation (Premium) — todos os tasks em sequência
- [ ] **🆓 Lab Grátis** LinPEAS (gratuito: github.com/peass-ng/PEASS-ng) + GTFOBins (gratuito: gtfobins.github.io)
- [ ] **📖 Teoria (40min)** `sudo -l`. `find / -perm -4000 2>/dev/null`. `getcap -r / 2>/dev/null`. `cat /etc/crontab`. writeable files: `find / -writable 2>/dev/null`.
- [ ] **⚒ Prática (70min)** THM Linux PrivEsc: completar todos os vetores (sudo, SUID, caps, cron, NFS). Consultar GTFOBins para cada binário.
- [ ] **📝 Anotações (10min)** Checklist Bible: ordem de checagem em Linux PrivEsc (do mais rápido ao mais demorado)

---

### DIA 36 · Linux PrivEsc — Vetores Avançados ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pós-Exploração (LD_PRELOAD, shared libraries, logrotate, Docker group, tmux hijacking)
- [ ] **🎮 THM Premium** THM: Linux PrivEsc Arena (Premium) — lab com múltiplos vetores para praticar
- [ ] **🆓 Lab Grátis** VulnHub: Kioptrix Level 2 ou Mr. Robot (gratuito: vulnhub.com) — privesc em Linux real
- [ ] **📖 Teoria (40min)** LD_PRELOAD abuse, LD_LIBRARY_PATH. NFS no_root_squash. Docker group escape. Logrotate exploit. Tmux session hijack.
- [ ] **⚒ Prática (70min)** LinPEAS em Kioptrix Level 2: interpretar output completo, identificar vetores, explorar sem guia.
- [ ] **📝 Anotações (10min)** Tabela Bible: vetores Linux PrivEsc com condição necessária e comando de exploração

---

### DIA 37 · Windows PrivEsc — Enumeração Sistemática ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pós-Exploração (Windows PrivEsc: winPEAS, whoami /all, unquoted path, weak service perms)
- [ ] **🎮 THM Premium** THM: Windows Privilege Escalation (Premium) — todos os tasks em sequência
- [ ] **🆓 Lab Grátis** WinPEAS (gratuito: github.com/peass-ng/PEASS-ng) + SharpUp (gratuito: github.com/GhostPack/SharpUp)
- [ ] **📖 Teoria (40min)** `whoami /all` (procurar SeImpersonate, SeAssignPrimary). winPEAS output: serviços, unquoted paths, creds em registry.
- [ ] **⚒ Prática (70min)** THM Windows PrivEsc: completar todos os vetores (unquoted, DLL hijack, registry, AlwaysInstallElevated, serviços).
- [ ] **📝 Anotações (10min)** Checklist Bible: ordem de checagem Windows PrivEsc (do mais provável ao menos comum)

---

### DIA 38 · Windows PrivEsc — Tokens + Potato Attacks ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pós-Exploração (SeImpersonatePrivilege: Juicy Potato, PrintSpoofer, GodPotato. Token abuse.)
- [ ] **🎮 THM Premium** THM: Steel Mountain (Premium) — privesc Windows com exploração de serviço
- [ ] **🆓 Lab Grátis** PrintSpoofer (gratuito: github.com/itm4n/PrintSpoofer) + GodPotato (gratuito: github.com/BeichenDream/GodPotato)
- [ ] **📖 Teoria (40min)** Quando usar cada Potato: Juicy (≤Win Server 2016), PrintSpoofer (≥Win 10/2019), GodPotato (mais recente). Token impersonation no Incognito.
- [ ] **⚒ Prática (70min)** Steel Mountain (THM): PrivEsc via serviço vulnerável + explorar SeImpersonate com PrintSpoofer.
- [ ] **📝 Anotações (10min)** Bible: tabela Potato attacks por versão Windows + requisito (qual privilege necessário)

---

### DIA 39 · Shells Estáveis + Transferência de Arquivos ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pós-Exploração (Shell estabilização: pty, stty. File transfer: HTTP, SMB, certutil, wget, curl.)
- [ ] **🎮 THM Premium** THM: What the Shell? (Premium) — tipos de shell, bind vs reverse, upgrading shells
- [ ] **🆓 Lab Grátis** Python HTTP server (gratuito: built-in) + Impacket SMB server (gratuito)
- [ ] **📖 Teoria (40min)** `python3 -c 'import pty;pty.spawn("/bin/bash")'` + stty raw -echo + export TERM=xterm. `certutil -urlcache -f URL`. SMB: impacket-smbserver.
- [ ] **⚒ Prática (70min)** Praticar: 5 métodos diferentes de shell upgrade (python, script, socat, rlwrap, pwncat). 5 métodos de file transfer.
- [ ] **📝 Anotações (10min)** Bible: shell upgrade cheat sheet + file transfer cheat sheet (Linux e Windows)

---

### DIA 40 · CMS Attacks — WordPress, Tomcat, Jenkins ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Externo/Web (CMS: WordPress wpscan, Joomla joomscan, Tomcat WAR upload, Jenkins RCE)
- [ ] **🎮 THM Premium** THM: Pyrat (Premium) — web + privilege escalation integrado
- [ ] **🆓 Lab Grátis** WPScan (gratuito: wpscan.com — free API, 25 requests/dia) + Droopescan (gratuito: github)
- [ ] **📖 Teoria (40min)** WordPress: `wpscan --enumerate u,p,t`. xmlrpc.php brute force. Theme editor RCE. Tomcat: mgr/html + WAR upload. Jenkins: Groovy console RCE.
- [ ] **⚒ Prática (70min)** Pyrat (THM): enumeração web + exploit + privesc. Depois: DVWA/lab WordPress local com plugin vulnerável.
- [ ] **📝 Anotações (10min)** Bible: fluxo de ataque CMS por plataforma (3 etapas para cada)

---

### DIA 41 · OSINT Avançado + Reconhecimento Externo Completo ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Reconhecimento (OSINT avançado: Shodan, crt.sh, GitHub dorking, Wayback Machine, email harvesting)
- [ ] **🎮 THM Premium** THM: Google Dorking & OSINT (Premium) — tasks de recon passivo avançado
- [ ] **🆓 Lab Grátis** Shodan (gratuito: shodan.io — conta free tem pesquisa básica) + Amass (gratuito: github.com/owasp-amass/amass)
- [ ] **📖 Teoria (40min)** GitHub: `org:EMPRESA extension:env OR extension:config`. crt.sh: `%.empresa.com`. `theHarvester -d dom -b all`.
- [ ] **⚒ Prática (70min)** Alvo bug bounty público (HackerOne): recon externo completo. Mapear todos os subdomínios, IPs, tecnologias.
- [ ] **📝 Anotações (10min)** Bible: template OSINT — checklist de fontes e o que coletar em cada

---

### DIA 42 · Relatório Profissional — Estrutura e Findings ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Conduzindo um Pentest (Relatório: estrutura, sumário executivo, findings com CVSS, evidências, remediação)
- [ ] **🎮 THM Premium** THM: Advent of Cyber — Day de Report Writing (Premium) — estrutura de relatório
- [ ] **🆓 Lab Grátis** SysReptor (gratuito: github.com/Syslifters/sysreptor) — ferramenta open source de relatório de pentest
- [ ] **📖 Teoria (40min)** Componentes: Sumário Executivo (para não-técnicos), Metodologia, Findings (título, descrição, evidência, CVSS, impacto, remediação), Apêndices.
- [ ] **⚒ Prática (70min)** SysReptor: instalar e configurar. Escrever um finding completo para a vulnerabilidade mais crítica que você explorou nas fases anteriores.
- [ ] **📝 Anotações (10min)** Template Obsidian: finding template com todos os campos. Calcular CVSS manualmente para 3 vulnerabilidades.

---

### DIA 43 · Lab Integrado — Agent Sudo ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão: rever módulos DCPT que ficaram pendentes (especialmente AD e post-exploitation)
- [ ] **🎮 THM Premium** THM: Agent Sudo (Premium) — lab integrado: web + steg + privesc Linux
- [ ] **🆓 Lab Grátis** VulnHub: DerpNStink (gratuito) — WordPress + SQLi + PrivEsc Linux integrado
- [ ] **📖 Teoria (40min)** Rever: linPEAS interpretação, winPEAS interpretação, shell upgrade, file transfer, report.
- [ ] **⚒ Prática (70min)** Agent Sudo (THM): completar sem writeup. Documentar como relatório real (finding por finding).
- [ ] **📝 Anotações (10min)** Rascunho de relatório do Agent Sudo: sumário executivo + 3 findings completos

---

### DIA 44 · Revisão Fase 5 + Simulado Mini ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão de todos os módulos DCPT: identificar 3 módulos com menor retenção e rever
- [ ] **🎮 THM Premium** THM: Relevant (Premium) — Windows pentest completo: recon, exploit, privesc
- [ ] **🆓 Lab Grátis** HackTheBox: Cronos (free, se ativo) — Linux + web + privesc
- [ ] **📖 Teoria (40min)** Rever: vetores PrivEsc Linux e Windows, shell upgrade, file transfer, CMS attacks.
- [ ] **⚒ Prática (70min)** Relevant (THM) sem writeup. Documentar como relatório (5 findings). Cronos (HTB) sem writeup.
- [ ] **📝 Anotações (10min)** Retrospectiva Fase 5: o que está sólido, o que precisa de mais prática. Plano para Fase 6.

---