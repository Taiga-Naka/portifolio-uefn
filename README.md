# Lost City GDD (em produção)

### **Game Design Document (GDD) - Versão 0.0**

**Título do Jogo:** Lost City

**Engine:** UEFN (Unreal Editor for Fortnite)

**Gênero:** Roguelike, Ação, Sobrevivência

**Plataforma:** Fortnite Creative (UEFN)

**Nome:** Thomas Taiga Martinez Nakagawa
**Curso:** Engenharia de Software
**Nome:** Thomas Taiga Martinez Nakagawa

---

## **1. Visão Geral**

 O jogo é uma adaptação de “*Zombie Ville 3D”*, onde o jogador enfrenta hordas de inimigos em um mundo aberto, em um ambiente pós-apocalíptico. O objetivo é sobreviver o maior tempo possível, coletar recursos (dinheiro) e melhorar habilidades para enfrentar inimigos cada vez mais desafiadores. O jogo combina mecânicas de combate, coleta de recursos, elementos de progressão (Ranking), efeitos visuais/sonoros imersivos para criar uma experiência envolvente e jogo com um foco em ação rápida.

---

## **2. Mecânicas Principais**

### **2.1. Spawn de Inimigos**

- **NPC Spawner:**
    - O NPC Spawner é **teleportado** para jogadores onde os inimigos estarão spawnando.
    - Existem **5 tipos de Spawners** diferentes, cada um gerando inimigos únicos com tipos diferentes como: pequeno, médio (velocidade), grande (tank), Boss.
    - Ao ficar longe da distância no spawn teleportado, será **teleportado novamente** para o jogador.
    - Ao teleportar, todos os NPCs spawnados são **resetados**.
- **Delay de Spawn:**
    - Os inimigos não spawnam todos de uma vez. Um **delay** é aplicado entre cada spawn para manter o desafio equilibrado.

### **2.2. Coleta de Recursos**

- **Dinheiro Coletável:**
    - Inimigos derrotados dropam **dinheiro** que pode ser coletado pelo jogador.
    - O dinheiro **desaparece** se o jogador se afastar além de uma distância pré-definida.

### **2.3. Áudio e Efeitos Sonoros**

- **Efeitos Sonoros:**
    - O jogo utilizará **variedades** de efeitos sonoros para criar uma atmosfera imersiva.
    - Exemplos:
        1. Som ambiental.
        2. Efeitos sonoros dos inimigos (grunhidos, passos, spawn, morte, etc).
        3. Sons de combate (tiros, golpes, dano, mortes, etc).

### **2.4. Animação**

- **Animação de Inimigo:**
    - Criar uma animação de movimento, ataque, dano e morte.
- **Animação de Spawn:**
    - Criar uma animação visual para o spawn dos inimigos, como um efeito de surgimento a partir do chão ou uma explosão de partículas.
- **Animação Ambiental:**
    - Criar uma animação visual do ambiente do jogo para ser mais imersivo.

### **2.5. Morte e Respawn**

- **Morte do Jogador:**
    - Ao ser morto, um **fade de tela** é ativado, escurecendo gradualmente a tela.
    - Caso for jogar com equipe, o jogador respawna em um estado **"Hide"** (invisível/invulnerável) transformando em um fantasma durante o respawn, indicando o estado de invulnerabilidade, conseguindo coletar recursos.

---

## **3. Fluxo do Jogo**

1. **Início:**
    - O jogador começa em uma área segura, com uma breve introdução ao objetivo do jogo com lojas de armas, upgrades e entre outros.
2. **Exploração e Combate:**
    - O jogador é teleportado para áreas com Spawners de inimigos.
    - Deve derrotar inimigos, coletar dinheiro e sobreviver o maior tempo possível.
3. **Morte e Recuperação:**
    - Ao morrer, o jogador respawna com um período de invulnerabilidade até toda equipe morrer.
    - O progresso (dinheiro coletado e EXP) é mantido com save.
4. **Loop de Jogo:**
    - O jogo continua em um ciclo de exploração, combate e coleta, com dificuldade progressiva.

---

## **4. Elementos Técnicos**

### **4.1. UEFN (Unreal Editor for Fortnite)**

- **NPC Spawners:**
    - Criar 5 tipos de inimigos e Spawners diferentes.
    - Configurar distância de teleporte/reset com base na proximidade do jogador.
- **Dinheiro Coletável (Volume Device ou Trigger Device ou Button Device):**
    - Criar um sistema de coleta com dispositivos de interação da UEFN.
    - Configurar desaparecimento do dinheiro com base na distância.
- **Áudio Player:**
    - Implementar vários de efeitos sonoros utilizando o sistema de áudio da UEFN.
- **Animação (Cinematic Device e Importar animações por fora como FBX e GLB):**
    - Criar animações utilizando sequenciadores, cinemáticas ou partículas da UEFN.
- **Morte e Respawn:**
    - Configurar fade de tela com dispositivos de câmera da UEFN.
    - Transformar em fantasma caso jogue com equipe.
