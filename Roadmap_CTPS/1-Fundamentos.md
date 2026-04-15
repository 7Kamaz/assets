
---
## ⚔ FASE 1 — FUNDAMENTOS + LINUX + WINDOWS + REDES
*Dias 01–10 · DCPT 2020 módulos iniciais · THM: Linux Fundamentals · Labs locais gratuitos*

### Objetivo da Fase
Solidificar a base técnica que o CPTS assume que você já tem. Linux fluente, Windows CLI, redes/protocolos, scripting básico em Bash e Python. Você já tem eJPT, então esta fase é aceleração, não iniciação.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase1.png)

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
### DIA 1 · Setup + Linux Essentials ⏱ ~2h

- [x] **📺 DCPT 2020** Módulo: Fundamentos de Segurança · Módulo: Sistemas Operacionais (Linux intro, navegação, permissões)
- [x] **🎮 THM Premium** THM: Linux Fundamentals Part 1 (Premium) — tasks 1 a 8
- [ ] **🆓 Lab Grátis** DVWA local (gratuito: dvwa.co.uk) — instalar e configurar
- [x] **📖 Teoria (40min)** Rever: hierarquia Linux, permissões SUID, find/grep/awk/sed. Anotar o que mudou desde o eJPT.
- [x] **⚒ Prática (70min)** Terminal: navegar sistema, criar usuários, chmod/chown, `find / -perm -4000`, `ps aux
- [x] **📝 Anotações (10min)** Obsidian: página 'Linux Essentials' com comandos testados + output real

---

### DIA 2 · Linux Avançado — Scripts + Serviços ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Scripting e Programação (Bash) · Módulo: Ferramentas Essenciais (curl, wget, netcat, tmux)
- [ ] **🎮 THM Premium** THM: Linux Fundamentals Part 2 & 3 (Premium)
- [ ] **🆓 Lab Grátis** OverTheWire Bandit levels 0–10 (gratuito: overthewire.org) — exercícios de terminal
- [ ] **📖 Teoria (40min)** Bash: variáveis, loops, funções, redirecionamento. Netcat: listeners, file transfer, reverse shell básico.
- [ ] **⚒ Prática (70min)** Escrever script: `port_scan.sh` que usa netcat para testar range de IPs. Testar em rede local.
- [ ] **📝 Anotações (10min)** Adicionar à bible: comandos Bash + netcat que você vai usar no exame

---

### DIA 3 · Windows — CLI + PowerShell ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Sistemas Operacionais (Windows intro, serviços, registro, ACLs, WMI)
- [ ] **🎮 THM Premium** THM: Windows Fundamentals 1 & 2 (Premium) — sections sobre CLI e serviços
- [ ] **🆓 Lab Grátis** TryHackMe: Windows Command Line (free tier) — reforço de CMD básico
- [ ] **📖 Teoria (40min)** CMD: net user, net group, whoami /all, sc qc, wmic. PowerShell: Get-Process, Get-Service, Invoke-WebRequest.
- [ ] **⚒ Prática (70min)** Máquina Windows local (VM): executar comandos de enumeração. Mapear diferenças CMD vs PowerShell.
- [ ] **📝 Anotações (10min)** Tabela Bible: 20 comandos Windows essenciais com saída esperada

---

### DIA 4 · Redes + Protocolos ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Redes e Protocolos (OSI, TCP/IP, DNS, SMB, HTTP, NTLM, Kerberos intro)
- [ ] **🎮 THM Premium** THM: Pre-Security — Network Fundamentals (Premium) — DNS, HTTP, SMB sections
- [ ] **🆓 Lab Grátis** PortSwigger: HTTP fundamentals (gratuito: portswigger.net/web-security/http)
- [ ] **📖 Teoria (40min)** OSI camadas na prática. Como funciona handshake TCP. DNS query flow. SMB shares. NTLM challenge-response.
- [ ] **⚒ Prática (70min)** Wireshark (gratuito): capturar tráfego HTTP e DNS na sua rede. Identificar handshake TCP. Ver headers HTTP.
- [ ] **📝 Anotações (10min)** Diagrama em Obsidian: fluxo de autenticação NTLM e Kerberos (vai usar muito no AD)

---

### DIA 5 · Nmap Profissional ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Scanning e Enumeration (Nmap flags, NSE scripts, outputs, evasão básica)
- [ ] **🎮 THM Premium** THM: Nmap (Premium) — todos os tasks incluindo NSE e evasão
- [ ] **🆓 Lab Grátis** HackTheBox Starting Point (free): Tier 0 — Meow ou Dancing (foco no scan inicial)
- [ ] **📖 Teoria (40min)** Flags críticas: -sS -sU -sV -sC -A -p- --min-rate --open -Pn -n -oA. NSE: vuln, http-enum, smb-enum-shares.
- [ ] **⚒ Prática (70min)** Montar script `nmap_full.sh`: scan de discovery + scan completo + serviços + output em 3 formatos.
- [ ] **📝 Anotações (10min)** Adicionar à bible: metodologia de scan em 3 etapas com comandos exatos

---

### DIA 6 · Enumeração de Serviços — FTP / SMB / SSH ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Enumeration (FTP anonymous, SMB shares, SSH versão fingerprint, SNMP)
- [ ] **🎮 THM Premium** THM: Network Services (Premium) — FTP, SMB, Telnet, NFS rooms
- [ ] **🆓 Lab Grátis** VulnHub: Mr. Robot (gratuito: vulnhub.com) — foco na enumeração inicial
- [ ] **📖 Teoria (40min)** enum4linux-ng, smbclient, smbmap, crackmapexec SMB sem creds. FTP anonymous. SSH fingerprint. SMTP VRFY.
- [ ] **⚒ Prática (70min)** Lab com Metasploitable2 (gratuito: sourceforge): enumerar todos os serviços. Documentar vetores encontrados.
- [ ] **📝 Anotações (10min)** Checklist de enumeração por porta (adicionar ao template de host no Obsidian)

---

### DIA 7 · OSINT + Reconhecimento Externo ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: OSINT (passive recon, theHarvester, Maltego, Shodan, Google Dorks, WHOIS, certs)
- [ ] **🎮 THM Premium** THM: Passive Reconnaissance & Active Reconnaissance (Premium)
- [ ] **🆓 Lab Grátis** Recon-ng (gratuito: open source) — OSINT framework local
- [ ] **📖 Teoria (40min)** Google Dorks: site:, filetype:, inurl:, intitle:. Certificate Transparency: crt.sh. Shodan basics. WHOIS lookup.
- [ ] **⚒ Prática (70min)** Escolher um alvo de bug bounty público (HackerOne) e fazer OSINT passivo completo. Documentar.
- [ ] **📝 Anotações (10min)** Template Obsidian: 'Recon Externo' com todas as fontes e o que coletar em cada uma

---

### DIA 8 · Scripting Python para Pentest ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Scripting e Programação (Python intro, socket, requests, argparse, manipulação de arquivos)
- [ ] **🎮 THM Premium** THM: Python Basics (Premium) — tasks focadas em automação de segurança
- [ ] **🆓 Lab Grátis** PentesterLab Free: exercícios de scripting (pentesterlab.com — criar conta grátis)
- [ ] **📖 Teoria (40min)** Python: socket para port scan, requests para web requests, argparse para CLI tools, subprocess para comandos.
- [ ] **⚒ Prática (70min)** Escrever: `banner_grabber.py` (socket), `http_enum.py` (requests), `wordlist_gen.py` (manipulação de strings).
- [ ] **📝 Anotações (10min)** Bible: templates Python que você vai reusar no exame

---

### DIA 9 · Ferramentas Essenciais — Setup e Fluência ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Ferramentas Essenciais (Metasploit intro, Burp Suite intro, Nikto, Gobuster/ffuf)
- [ ] **🎮 THM Premium** THM: Metasploit (Premium) — Introduction to Metasploit, usando msfconsole
- [ ] **🆓 Lab Grátis** PortSwigger: Getting Started lab (gratuito) — configurar Burp proxy, Repeater básico
- [ ] **📖 Teoria (40min)** Metasploit: search, use, show options, set RHOSTS/LHOST, run, sessions -i. Burp: Proxy, Repeater, Intruder.
- [ ] **⚒ Prática (70min)** Metasploitable2: explorar um serviço com Metasploit. Interceptar request com Burp. ffuf em diretório.
- [ ] **📝 Anotações (10min)** Comparar: quando usar Metasploit vs manual. Adicionar à bible.

---

### DIA 10 · Revisão + Mini Lab Integrado ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão dos módulos DCPT Fase 1: anotar dúvidas e rever seções com menor retenção
- [ ] **🎮 THM Premium** THM: Basic Pentesting (Premium) — room de integração, aplica tudo da Fase 1
- [ ] **🆓 Lab Grátis** VulnHub: Kioptrix Level 1 (gratuito: vulnhub.com) — máquina clássica de prática
- [ ] **📖 Teoria (40min)** Rever: Linux + Windows CLI, Nmap, enumeração de serviços, OSINT, Burp, Metasploit.
- [ ] **⚒ Prática (70min)** Comprometer o Kioptrix Level 1 SEM writeup. 45 minutos stuck = anotação do que tentou, depois pesquisar.
- [ ] **📝 Anotações (10min)** Retrospectiva: o que vai carregado para a Fase 2. Quais gaps identificados.

---
