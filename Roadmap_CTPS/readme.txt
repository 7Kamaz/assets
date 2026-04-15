# ⚔️ PRÉ-CPTS ROADMAP
**Djair Martins / Kamaz**  
`DCPT 2020` · `TryHackMe Premium` · `Labs Gratuitos`  
*Preparação total antes de iniciar os módulos HTB Academy CPTS*

---

<p align="center">
  <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase0.webp" alt="Banner Roadmap" width="100%">
</p>

## 📊 Progresso da Jornada
> [!IMPORTANT]
> No GitHub, a barra de progresso abaixo é estática. Para um gráfico dinâmico, utilize o **Obsidian** com o plugin Dataview ou o **Notion**.

**Status Atual:** 🟢 Fase 1 em andamento
![Progress Bar](https://geps.dev/progress/15?dangerColor=ff0000&warningColor=ffff00&successColor=00ff00)
*15% concluído*

---

## 🗺️ Mapa Visual — PRÉ-CPTS (60 Dias)

| Fase | Status | Conteúdo | Link |
| :---: | :---: | :--- | :--- |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase1_capa.png" width="150"> | 🟢 | Fundamentos + Linux/Win + Redes | [Fase 1](#-fase-1-dias-110) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase2_capa.png" width="150"> | 🟡 | Web Profissional (SQLi, XSS, LFI) | [Fase 2](#-fase-2-dias-11-18) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase3_capa.png" width="150"> | ⚪ | Active Directory — Zero ao DCSync | [Fase 3](#-fase-3-dias-19-26) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase4_capa.png" width="150"> | ⚪ | Pivoting + Lateral Movement | [Fase 4](#-fase-4-dias-27-34) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase5_capa.png" width="150"> | ⚪ | PrivEsc + Shells + Reporting | [Fase 5](#-fase-5-dias-35-44) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase6_capa.png" width="150"> | ⚪ | Labs Integrados — Modo Exame | [Fase 6](#) |
| <img src="https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase_final_capa.png" width="150"> | ⚪ | Simulado CPTS + Revisão | [Final](#) |

---

## 🎯 Sobre Este Roadmap
Este documento é a **FASE ZERO** do seu caminho para o CPTS. O objetivo é que você chegue nos módulos da CPTS com a mentalidade, os reflexos e a capacidade técnica de quem já poderia fazer a prova.

- **📺 DCPT 2020:** 40+ módulos · 500+ aulas · 64h de conteúdo. O backbone teórico-prático em português.
- **🎮 TryHackMe Premium:** Rooms guiadas com labs ativos. AD, Wreath, Linux/Win PrivEsc.
- **📁 [Acessar Drive Desec - DCPT](https://drive.google.com/drive/u/4/folders/1Ce9lXBn9ldxZUeljY1BhCQ12VTlfcjUm)**

---

## ⚡ Regras de Sobrevivência
> [!CAUTION]
> - 🔴 **2 horas por dia** — não menos, não mais (consistência vence intensidade).
> - 🔴 **Stuck por 45 minutos** = anote o que tentou → pesquise → documente o aprendizado.
> - 🔴 **A Bible no Obsidian** é mais importante que qualquer lab. Sem anotação, o lab não conta.

---

## 📺 Checklist de Módulos (DCPT 2020)

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

## 🎧 Podcast/Vídeo do Dia
> [!INFO]
> Ouça enquanto caminha, come ou dirige. Conteúdo que acrescenta profissionalmente.

*🚧 Em obras...*

---
<p align="center">
  <b><a href="https://drive.google.com/drive/u/4/folders/1Ce9lXBn9ldxZUeljY1BhCQ12VTlfcjUm">📁 ACESSAR DRIVE DESEC - DCPT</a></b>
</p>
