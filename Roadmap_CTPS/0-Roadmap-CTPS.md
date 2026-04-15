# ⚔ PRÉ-CPTS ROADMAP
**Djair Martins / Kamaz**  
DCPT 2020 · TryHackMe Premium · Labs Gratuitos  
*Preparação total antes de iniciar os módulos HTB Academy CPTS*

---
![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase0.webp)

## 📊 PROGRESSO DA JORNADA
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
## 📺 CHECKLIST DE MÓDULOS (DCPT 2020)

### 🟢 FASE 1 (Dias 1–10)
- [ ] Fundamentos de Segurança — Terminologia, metodologia, ética
- [ ] Redes e Protocolos — OSI, TCP/IP, DNS, SMB, HTTP, Kerberos intro
- [ ] Sistemas Operacionais — Linux navegação, permissões, serviços. Windows CLI, registro, ACLs
- [ ] Scripting e Programação — Bash e Python para automação de pentest
- [ ] Ferramentas Essenciais — Nmap, Metasploit intro, Burp Suite intro, Netcat, Tmux

### 🔵 FASE 2 (Dias 11–18)
- [ ] Fundamentos de Web — HTTP, cookies, headers, sessões, APIs REST
- [ ] Pentest Externo/Web — SQL Injection (manual + sqlmap), XSS, LFI/RFI, File Upload, IDOR
- [ ] Bypass de Segurança — WAF bypass, encoding, filter evasion
- [ ] OSINT e Reconhecimento — theHarvester, Shodan, Google Dorks, crt.sh, Recon-ng

### 🟡 FASE 3 (Dias 19–26)
- [ ] Pentest Interno — Active Directory: estrutura, objetos, autenticação NTLM e Kerberos
- [ ] Enumeração AD — enum4linux, ldapsearch, rpcclient, CrackMapExec sem creds
- [ ] Ataques AD — AS-REP Roasting, Kerberoasting, Pass-the-Hash, DCSync
- [ ] BloodHound — Coleta de dados, queries, attack path analysis
- [ ] Responder e NTLM Relay — LLMNR/NBT-NS poisoning, ntlmrelayx

### 🟣 FASE 4 (Dias 27–34)
- [ ] Password Attacks — Hashcat modes, John the Ripper, wordlists customizadas, regras
- [ ] Brute Force e Spraying — CrackMapExec spray, Kerbrute, credential stuffing
- [ ] Pivoting e Tunneling — SSH Dynamic/Local/Remote, proxychains, Ligolo-ng, Chisel, Socat
- [ ] Movimentação Lateral — psexec, wmiexec, evil-winrm, DCOM, token impersonation
- [ ] Credential Hunting — arquivos de configuração, SAM, histórico, registry

### 🔴 FASE 5 (Dias 35–44)
- [ ] Pós-Exploração Linux — LinPEAS, sudo, SUID, capabilities, cron, NFS, Docker escape
- [ ] Pós-Exploração Windows — WinPEAS, serviços vulneráveis, unquoted path, tokens/Potato
- [ ] Shells e Estabilização — Shell upgrade (pty/stty), tipos de shell, bind vs reverse
- [ ] Transferência de Arquivos — HTTP server, certutil, SMB server, wget, curl
- [ ] CMS e Aplicações — WordPress, Tomcat, Jenkins, Drupal, Joomla
- [ ] Conduzindo um Pentest — Relatório: estrutura, findings, CVSS, evidências, remediação

---
## 🎯 SOBRE ESTE ROADMAP
Este documento é a **FASE ZERO** do seu caminho para o CPTS. 
O objetivo é que você chegue nos módulos da CPTS com a mentalidade, os reflexos e a capacidade técnica de quem já poderia fazer a prova.

> [!abstract] **📺 DCPT 2020**
> 40+ módulos · 500+ aulas · 64h de conteúdo. O backbone teórico-prático em português.
> [🔗 Abrir Google Drive (DCPT)](https://drive.google.com/drive/u/4/folders/1Ce9lXBn9ldxZUeljY1BhCQ12VTlfcjUm)

> [!example] **🎮 TryHackMe Premium**
> Rooms guiadas com labs ativos. AD, Wreath, Linux/Win PrivEsc. Prática real com feedback.

---

## 🗺 MAPA VISUAL — PRÉ-CPTS (60 DIAS)

| Fase | Status | Conteúdo                          | Link                        |
| :--- | :----- | :-------------------------------- | :-------------------------- |
| 1    | 🟢     | Fundamentos + Linux/Win + Redes   | [[1-Fundamentos]]           |
| 2    | 🟡     | Web Profissional (SQLi, XSS, LFI) | [[2-Web-Profissional]]      |
| 3    | ⚪      | Active Directory — Zero ao DCSync | [[3-Active-Directory]]      |
| 4    | ⚪      | Pivoting + Lateral Movement       | [[4-Pivoting]]              |
| 5    | ⚪      | PrivEsc + Shells + Reporting      | [[5-PrivEsc-Linux&Windows]] |
| 6    | ⚪      | Labs Integrados — Modo Exame      | [[6-Labs-Integrados]]       |
| 7    | ⚪      | Simulado CPTS + Revisão           | [[7-Simulado-CPTS]]         |

---

## ⚡ REGRAS DE SOBREVIVÊNCIA
> [!danger] **NÃO PULE AS REGRAS**
> - 🔴 **2 horas por dia** — não menos, não mais (consistência vence intensidade).
> - 🔴 **Stuck por 45 minutos** = anote o que tentou → pesquise → documente o aprendizado.
> - 🔴 **A Bible no Obsidian** é mais importante que qualquer lab. Sem anotação, o lab não conta.

---
## 🎧 PODCAST/VÍDEO DO DIA
> [!info] **Aprendizado Passivo**
> Ouça enquanto caminha, come ou dirige. Conteúdo que acrescenta profissionalmente.

*! Em obras...*

---
> **[📁 ACESSAR DRIVE DESEC - DCPT](https://drive.google.com/drive/u/4/folders/1Ce9lXBn9ldxZUeljY1BhCQ12VTlfcjUm)**
