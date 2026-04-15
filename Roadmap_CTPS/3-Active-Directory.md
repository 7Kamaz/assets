
---
## ⚔ FASE 3 — ACTIVE DIRECTORY — DO ZERO AO DCSYNC
*Dias 19–26 · DCPT 2020 AD modules · THM Attacktive Directory · BloodHound · Impacket*

### Objetivo da Fase
Active Directory é o coração do CPTS. Esta fase cobre a cadeia completa: enumeração → AS-REP Roasting → Kerberoasting → Pass-the-Hash → DCSync. Você precisa executar cada etapa na memória, sem consultar documentação.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase3.png)


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
### DIA 19 · AD — Teoria e Estrutura ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (AD: domínio, floresta, OU, GPO, Kerberos, NTLM, LDAP — teoria completa)
- [ ] **🎮 THM Premium** THM: Active Directory Basics (Premium) — estrutura, objetos, autenticação
- [ ] **🆓 Lab Grátis** BloodHound Community Edition (gratuito: github.com/SpecterOps/BloodHound) — instalar e configurar
- [ ] **📖 Teoria (40min)** Terminologia: Domain, Forest, Trust, OU, GPO, SPN, UPN, SID, RID. Kerberos: AS-REQ/AS-REP/TGS-REQ/TGS-REP. NTLM: challenge-response.
- [ ] **⚒ Prática (70min)** Instalar BloodHound CE + Neo4j. Importar dataset de exemplo. Explorar a interface e queries básicas.
- [ ] **📝 Anotações (10min)** Diagrama Kerberos no Obsidian com cada etapa e ferramenta correspondente

---

### DIA 20 · AD — Enumeração Sem Credenciais ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (enumeração AD com enum4linux, ldapsearch, rpcclient, crackmapexec sem creds)
- [ ] **🎮 THM Premium** THM: Enumerating Active Directory (Premium) — tasks de enumeração com ferramentas reais
- [ ] **🆓 Lab Grátis** HackTheBox: Forest (free — máquina AD clássica, acessível no free tier com VPN)
- [ ] **📖 Teoria (40min)** `enum4linux-ng -A IP`. `rpcclient -U '' IP`. `ldapsearch -x -h IP -b DC=dom,DC=local`. `crackmapexec smb IP`.
- [ ] **⚒ Prática (70min)** Usar Forest (HTB) como alvo: enumerar usuários sem credenciais, mapear estrutura de domínio.
- [ ] **📝 Anotações (10min)** Checklist: o que você sempre coleta na enumeração AD inicial (usuários, grupos, SPNs, shares)

---

### DIA 21 · AS-REP Roasting + Kerberoasting ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (AS-REP Roasting: GetNPUsers. Kerberoasting: GetUserSPNs. Crack com hashcat.)
- [ ] **🎮 THM Premium** THM: Attacktive Directory (Premium) — tasks de AS-REP e Kerberoasting
- [ ] **🆓 Lab Grátis** HackTheBox: Forest (free) — AS-REP Roasting é o vetor inicial dessa máquina
- [ ] **📖 Teoria (40min)** `impacket-GetNPUsers DOM/ -dc-ip IP -usersfile users.txt -no-pass`. `impacket-GetUserSPNs DOM/user:pass -dc-ip IP -request`.
- [ ] **⚒ Prática (70min)** Forest (HTB): AS-REP Roast svc-alfresco → crack com hashcat -m 18200. Depois Kerberoast se houver SPN.
- [ ] **📝 Anotações (10min)** Bible: comando exato AS-REP + Kerberoast + hashcat com modo correto. Diferença dos dois ataques.

---

### DIA 22 · LDAP + BloodHound + ACL Attacks ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (LDAP enum avançado, BloodHound coleta, análise de ACLs perigosas)
- [ ] **🎮 THM Premium** THM: Compromising Active Directory (Premium) — BloodHound e ACL attacks tasks
- [ ] **🆓 Lab Grátis** BloodHound CE (local, gratuito) — importar dados coletados do ambiente de lab
- [ ] **📖 Teoria (40min)** bloodhound-python coleta de dados. Queries BloodHound: Find Shortest Path to DA, Kerberoastable Users, DCSync rights.
- [ ] **⚒ Prática (70min)** Attacktive Directory (THM): coletar dados com bloodhound-python, importar no BloodHound, encontrar path para Domain Admin.
- [ ] **📝 Anotações (10min)** Screenshot do path BloodHound + interpretação das ACLs encontradas na bible

---

### DIA 23 · Pass-the-Hash + WinRM + Evil-WinRM ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (PTH com psexec, wmiexec. Evil-WinRM. Movimentação lateral com hashes.)
- [ ] **🎮 THM Premium** THM: Attacktive Directory (Premium) — task de pass-the-hash e movimentação lateral
- [ ] **🆓 Lab Grátis** HackTheBox: Sauna (free) — AS-REP → hash → PTH para movimentação
- [ ] **📖 Teoria (40min)** `impacket-psexec DOM/user@IP -hashes :HASH`. `impacket-wmiexec` (menos barulhento). `evil-winrm -H HASH`.
- [ ] **⚒ Prática (70min)** Sauna (HTB): replicar o fluxo completo AS-REP → crack → PTH → lateral para encontrar DA hash.
- [ ] **📝 Anotações (10min)** Bible: quando usar psexec vs wmiexec vs winrm (por barulho e porta disponível)

---

### DIA 24 · DCSync + Secretsdump + Golden Ticket ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (DCSync com secretsdump, extração de NTDS, Golden Ticket conceito)
- [ ] **🎮 THM Premium** THM: Post-Exploitation Basics (Premium) — DCSync e extração de hashes tasks
- [ ] **🆓 Lab Grátis** HackTheBox: Forest (free) — DCSync é o passo final nessa máquina
- [ ] **📖 Teoria (40min)** `impacket-secretsdump DOM/admin:pass@DC_IP`. Entender NTDS.dit vs SAM. Crack do krbtgt hash.
- [ ] **⚒ Prática (70min)** Forest (HTB): comprometer até DCSync completo. Extrair todos os hashes. Tentar PTH com hash do Administrator.
- [ ] **📝 Anotações (10min)** Bible: fluxo completo AD attack chain — das 6 etapas com comando exato

---

### DIA 25 · Responder + NTLM Relay + SMB Relay ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Responder: LLMNR/NBT-NS poisoning. NTLM Relay com ntlmrelayx.)
- [ ] **🎮 THM Premium** THM: Compromising Active Directory (Premium) — tasks de Responder e NTLM relay
- [ ] **🆓 Lab Grátis** Responder (gratuito: github.com/lgandx/Responder) — open source, já incluso no Kali
- [ ] **📖 Teoria (40min)** `sudo responder -I tun0 -wPv`. Capturar NetNTLMv2. Crack com hashcat -m 5600. ntlmrelayx para relay.
- [ ] **⚒ Prática (70min)** Lab virtual local com 2 VMs Windows: Responder no Kali, poisoning de LLMNR na rede local. Capturar e crackear hash.
- [ ] **📝 Anotações (10min)** Bible: quando usar Responder (rede interna, LLMNR ativo) vs quando relay é possível (SMB signing off)

---

### DIA 26 · AD — Revisão + Lab Integrado Attacktive Directory ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão dos módulos DCPT AD: rever seções que ficaram com dúvida
- [ ] **🎮 THM Premium** THM: Attacktive Directory (Premium) — REPETIR do início, agora sem consultar nada
- [ ] **🆓 Lab Grátis** HackTheBox: Active (free) — máquina AD com Kerberoasting via GPP password
- [ ] **📖 Teoria (40min)** Rever todo fluxo: enumeração → AS-REP/Kerberoast → BloodHound → PTH → DCSync.
- [ ] **⚒ Prática (70min)** Attacktive Directory do zero, do começo ao fim. Depois Active (HTB) sem writeup.
- [ ] **📝 Anotações (10min)** Fluxograma AD attack chain completo no Obsidian com ferramentas e comandos
# Testar se tem competência para o AD-RTS da CWL...

🏰 🔥 AD-RTS — Labs obrigatórios (THM Premium)
Aqui é onde 90% trava.
🧠 Base obrigatória (se não souber isso, nem tenta)
Active Directory Basics
Enumerating Active Directory
👉 Você precisa:
Entender Kerberos (não decorar, entender)
Saber enumerar sem creds
💥 CORE — ataque real de AD
Attacktive Directory
👉 Esse aqui é O LAB.
Se você não fizer ele sozinho → esquece AD-RTS.
Você precisa conseguir:
AS-REP Roasting
Kerberoasting
BloodHound
Escalada até DA
⚔️ Nível profissional (simulação de prova)
Wreath
👉 Esse aqui é brutal.
Você precisa:
Pivoting real
Multi-host
Windows + Linux
Lateral movement
Se você fizer isso sozinho → você já tá acima de muita gente certificada.
🧠 Pós-exploração (obrigatório pra fechar AD)
Lateral Movement and Pivoting
Exploiting Active Directory
🎯 CRITÉRIO FINAL AD (sem ilusão)
Se você consegue:
Attacktive Directory sem ajuda
Wreath completo sem travar mais de 1h por etapa
Fazer chain até DA
👉 Você tá pronto pro AD-RTS.

---