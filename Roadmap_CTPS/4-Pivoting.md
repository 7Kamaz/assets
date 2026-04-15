
---
## ⚔ FASE 4 — PIVOTING + PASSWORD ATTACKS + LATERAL MOVEMENT
*Dias 27–34 · DCPT 2020 · THM Wreath + Borderlands · Ligolo-ng + Chisel*

### Objetivo da Fase
Pivoting sem Metasploit é obrigatório no CPTS. Esta fase cobre Ligolo-ng, Chisel e SSH tunneling. Combinado com password attacks completos (cracking, spraying, wordlists customizadas) e movimentação lateral profissional.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase4.webp)


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
### DIA 27 · Password Attacks — Cracking + Wordlists ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Password Attacks: hashcat, john, wordlists, regras, masked attacks)
- [ ] **🎮 THM Premium** THM: Crack The Hash (Premium) — identificar tipo de hash e crackear com hashcat/john
- [ ] **🆓 Lab Grátis** hashcat (gratuito: hashcat.net) — Kali já inclui. SecLists (gratuito: github.com/danielmiessler/SecLists)
- [ ] **📖 Teoria (40min)** Hashcat modes: -m 1000 (NTLM), -m 5600 (NetNTLM), -m 13100 (TGS/Kerberoast), -m 18200 (AS-REP), -m 1800 (sha512crypt). Regras: --rules-file.
- [ ] **⚒ Prática (70min)** Praticar: identificar tipo de 10 hashes diferentes. Crackear cada um com wordlist correta. Criar regra customizada.
- [ ] **📝 Anotações (10min)** Bible: tabela de modos hashcat por tipo de hash + wordlist recomendada para cada

---

### DIA 28 · Password Spraying + Credential Stuffing ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Password Spraying: CrackMapExec, Kerbrute. Regras de lockout.)
- [ ] **🎮 THM Premium** THM: Password Attacks (Premium) — tasks de spraying e brute force de serviços
- [ ] **🆓 Lab Grátis** Kerbrute (gratuito: github.com/ropnop/kerbrute) — user enumeration e password spray em AD
- [ ] **📖 Teoria (40min)** CrackMapExec spray: `cme smb IP -u users.txt -p 'Senha123!' --continue-on-success`. Kerbrute: `passwordspray -d DOM`.
- [ ] **⚒ Prática (70min)** Lab local com AD: fazer spray com lista de 5 usuários e 1 senha. Observar logs de evento 4625 no Windows.
- [ ] **📝 Anotações (10min)** Bible: spray cadência (1 senha por vez, intervalo entre tentativas, observar lockout threshold)

---

### DIA 29 · SSH Tunneling + Port Forwarding ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Pivoting: SSH Dynamic, Local e Remote Port Forwarding, proxychains)
- [ ] **🎮 THM Premium** THM: Wreath (Premium) — início da room: SSH tunneling para acessar rede interna
- [ ] **🆓 Lab Grátis** SSH (gratuito: built-in) + proxychains (gratuito: kali built-in)
- [ ] **📖 Teoria (40min)** `ssh -D 1080 -N -f user@PIVOT` (SOCKS). `ssh -L 8080:INTERNO:80 user@PIVOT` (local fwd). `ssh -R` (remote). proxychains config.
- [ ] **⚒ Prática (70min)** Lab 2 VMs: via pivot SSH, acessar serviço na rede interna. Verificar com proxychains + nmap.
- [ ] **📝 Anotações (10min)** Bible: 3 tipos de SSH tunnel com diagrama e quando usar cada

---

### DIA 30 · Ligolo-ng — Pivoting Profissional ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Pivoting avançado — Ligolo-ng setup e uso)
- [ ] **🎮 THM Premium** THM: Wreath (Premium) — seção de pivoting avançado
- [ ] **🆓 Lab Grátis** Ligolo-ng (gratuito: github.com/nicocha30/ligolo-ng) — padrão CPTS para pivoting
- [ ] **📖 Teoria (40min)** Ligolo-ng: proxy + agent setup. Adicionar rota de rede. Comparar com proxychains: velocidade, estabilidade.
- [ ] **⚒ Prática (70min)** Lab 3 VMs: Kali → Pivot → Interno. Configurar Ligolo-ng. Escanear rede interna a partir do Kali diretamente.
- [ ] **📝 Anotações (10min)** Bible: setup Ligolo-ng em 5 comandos (proxy + agent + tunnel + route)

---

### DIA 31 · Chisel + Socat ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Chisel: reverse pivot, Socat: port relay)
- [ ] **🎮 THM Premium** THM: Wreath (Premium) — tasks de Chisel e Socat
- [ ] **🆓 Lab Grátis** Chisel (gratuito: github.com/jpillora/chisel) + Socat (gratuito: kali built-in)
- [ ] **📖 Teoria (40min)** Chisel server + client para tunnel reverso. Socat como relay de porta. Quando usar cada um vs Ligolo-ng.
- [ ] **⚒ Prática (70min)** Wreath (THM): usar Chisel para o pivot Windows que requer técnica específica. Socat como relay alternativo.
- [ ] **📝 Anotações (10min)** Tabela comparativa: Ligolo-ng vs Chisel vs SSH tunnel (por cenário e requisito)

---

### DIA 32 · Lateral Movement — PSExec, WMI, WinRM ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Lateral Movement: psexec (445), wmiexec (135), evil-winrm (5985). DCOM.)
- [ ] **🎮 THM Premium** THM: Lateral Movement and Pivoting (Premium) — todos os vetores de movimento lateral
- [ ] **🆓 Lab Grátis** Impacket (gratuito: github.com/fortra/impacket) — psexec.py, wmiexec.py, smbexec.py
- [ ] **📖 Teoria (40min)** psexec.py (barulhento, cria serviço), wmiexec.py (menos barulho, WMI), evil-winrm (5985). Spawn shell via WMI remoto. DCOM exec.
- [ ] **⚒ Prática (70min)** Wreath (THM): movimentação lateral entre hosts internos. Usar psexec, depois wmiexec, comparar logs gerados.
- [ ] **📝 Anotações (10min)** Bible: tabela lateral movement por protocolo disponível (SMB/WMI/WinRM) + requisitos de cred/hash

---

### DIA 33 · Token Impersonation + Credenciais no Ambiente ⏱ ~2h

- [ ] **📺 DCPT 2020** Módulo: Pentest Interno (Credential Hunting: arquivos de config, histórico, SAM, LSASS, mimikatz conceito)
- [ ] **🎮 THM Premium** THM: Exploiting Active Directory (Premium) — token impersonation e credential hunting tasks
- [ ] **🆓 Lab Grátis** Incognito (Metasploit module, gratuito) + secretsdump para locais
- [ ] **📖 Teoria (40min)** Credential hunting: `findstr /si password *.xml *.ini *.txt`. SAM local: `reg save HKLM\SAM sam.bak`. LSASS: Task Manager dump.
- [ ] **⚒ Prática (70min)** Wreath (THM): encontrar credenciais nos hosts comprometidos. Usar para lateral movement seguinte.
- [ ] **📝 Anotações (10min)** Checklist Bible: 15 lugares para procurar credenciais em Windows comprometido

---

### DIA 34 · Pivoting — Revisão + Lab Wreath Completo ⏱ ~2h

- [ ] **📺 DCPT 2020** Revisão: rever seções de pivoting e movimentação lateral que ficaram com dúvida
- [ ] **🎮 THM Premium** THM: Wreath (Premium) — COMPLETAR a room inteira do início ao fim
- [ ] **🆓 Lab Grátis** HackTheBox: Dante Pro Lab (se tiver acesso) ou máquina HTB com pivot (Reddish — free se ativo)
- [ ] **📖 Teoria (40min)** Rever: Ligolo setup, Chisel, SSH tunneling, lateral movement, credential hunting.
- [ ] **⚒ Prática (70min)** Wreath completo sem writeup. É a room mais próxima do CPTS em estrutura (multi-host, multi-pivot).
- [ ] **📝 Anotações (10min)** Retrospectiva Fase 4: mapa mental de pivoting no Obsidian. O que carrega para a Fase 5.

---