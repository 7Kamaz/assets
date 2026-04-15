
---
## ⚔ FASE 6 — LABS INTEGRADOS — MODO EXAME
*Dias 45–54 · HTB Free Machines · THM Premium Rooms · Sem Writeup, Sem Guia*

### Objetivo da Fase
Esta fase simula as condições do exame. Cada máquina/room é atacada sem guia, com documentação completa e timer. O objetivo é desenvolver o ritmo de pentest real: recon sistemático → exploit → post-exploit → pivot → report.

![697](https://raw.githubusercontent.com/7Kamaz/assets/main/images/fase6.png)


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
### DIA 45–46 · HTB: Forest (AD) — Modo Exame ⏱ ~2h

- [ ] **🆓 Lab Grátis** HackTheBox: Forest (gratuito no free tier) — AD completo: AS-REP → BloodHound → DCSync
- [ ] **📖 Teoria (40min)** CPTS attack chain: recon → enumeração → AS-REP → bloodhound → privilege escalation no AD → DCSync.
- [ ] **⚒ Prática (70min)** Forest do início ao fim em modo exame: 45 min stuck = nota do que tentou (não writeup). Documentar tudo.
- [ ] **📝 Anotações (10min)** Relatório completo de Forest: sumário exec + 4 findings + evidências (screenshots).

---

### DIA 47–48 · HTB: Sauna (AD) — Modo Exame ⏱ ~2h

- [ ] **🆓 Lab Grátis** HackTheBox: Sauna (gratuito no free tier) — AS-REP Roasting + DCSync + AD lateral movement
- [ ] **📖 Teoria (40min)** Variação do Forest: recon diferente, usuários diferentes. Testar se metodologia AD está internalizada.
- [ ] **⚒ Prática (70min)** Sauna em modo exame. Comparar com Forest: o que mudou, o que ficou igual na metodologia.
- [ ] **📝 Anotações (10min)** Relatório Sauna + comparativo de vetores com Forest

---

### DIA 49–50 · THM: Wreath — Segunda Rodada ⏱ ~2h

- [ ] **🎮 THM Premium** THM: Wreath (Premium) — REPETIR: multi-host, AD, pivoting, Windows + Linux
- [ ] **📖 Teoria (40min)** Wreath é o lab mais próximo do CPTS. Segunda rodada = sem olhar anotações, fluência total.
- [ ] **⚒ Prática (70min)** Wreath completo com timer. Cada pivot deve sair em menos de 10 minutos. Cada host < 45 minutos.
- [ ] **📝 Anotações (10min)** Comparar tempo desta rodada com a primeira. Identificar onde ainda trava.

---

### DIA 51–52 · HTB: Active (AD) + Cronos (Linux Web) ⏱ ~2h

- [ ] **🆓 Lab Grátis** HackTheBox: Active (free) — GPP password → Kerberoast → PSExec. Cronos (free) — DNS + SQLi + Cron PrivEsc
- [ ] **📖 Teoria (40min)** Active: recon → GPP → kerberoast → psexec. Cronos: DNS enum → web exploit → cron privesc.
- [ ] **⚒ Prática (70min)** Active e Cronos em modo exame. Um dia cada. Sem writeup antes de tentar tudo.
- [ ] **📝 Anotações (10min)** Relatório integrado: 2 hosts como se fossem a mesma rede. Executive Summary único.

---

### DIA 53–54 · VulnHub + Lab Livre — Lacunas Identificadas ⏱ ~2h

- [ ] **📺 DCPT 2020** Rever módulos DCPT específicos baseado nos gaps identificados na Fase 6
- [ ] **🎮 THM Premium** THM: room livre — escolher a room do tópico onde ainda trava
- [ ] **🆓 Lab Grátis** VulnHub: Stapler ou pWnOS (gratuito) — Linux multi-vetor
- [ ] **📖 Teoria (40min)** Revisão dirigida: identificar os 3 vetores onde ainda perde mais tempo e atacar especificamente.
- [ ] **⚒ Prática (70min)** VulnHub Stapler + room THM do gap identificado. Em modo exame.
- [ ] **📝 Anotações (10min)** Retrospectiva Fase 6: mapa de confiança por tópico (verde/amarelo/vermelho). Plano para o Final.

---