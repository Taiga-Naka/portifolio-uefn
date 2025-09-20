# Lost City GDD (em produção)

### **Game Design Document (GDD) - Versão 0.1**

**Título do Jogo:** Lost City

**Engine:** UEFN (Unreal Editor for Fortnite)

**Gênero:** Roguelike, Ação, Sobrevivência

**Plataforma:** Fortnite Creative (UEFN)

**Nome:** Thomas Taiga Martinez Nakagawa

**Curso:** Engenharia de Software

**Data de entrega:** dd/mm/aaaa

---

## **Resumo**

 Lost City é um jogo de ação, sobrevivência e roguelike, desenvolvido na plataforma Fortnite Creative com o Unreal Editor for Fortnite (UEFN). Inspirado a gameplay em Zombie Ville 3D, O ambiente de Mad Max, A animação de The Last of Us, e Terror e sobrevivência de Resident Evil. O jogador enfrenta hordas de inimigos em um mundo pós-apocalíptico, enquanto coleta recursos, aprimora habilidades e sobrevive o máximo possível. O jogo foca na criação de uma experiência dinâmica e imersiva, utilizando sistemas personalizados de IA, efeitos visuais/sonoros e mecânicas de progressão.

O desenvolvimento serve como um estudo prático de engenharia de software, destacando-se pela implementação de sistemas complexos, como spawners dinâmicos, lógica de coleta, sistema de morte e respawn, e uso da nova linguagem Verse. Limitações técnicas incluem o uso apenas de armas e veículos disponíveis no Fortnite.

Entre os requisitos funcionais estão: spawn dinâmico de inimigos, coleta de dinheiro, efeitos sonoros imersivos, e sistema de progressão persistente. Já entre os não-funcionais destacam-se a performance (mínimo 30 FPS), tempo de carregamento, e sincronização de áudio.

O loop principal do jogo envolve: início em uma área segura, teleporte para áreas de combate, coleta de recursos, respawn em caso de morte, e reinício com progressão mantida. O projeto é estruturado com um cronograma dividido em etapas: planejamento inicial, prototipagem, implementação de mecânicas avançadas, polimento, testes e entrega final.
 
---

## **1. Introdução**

 Lost City é um projeto de desenvolvimento de um jogo no estilo roguelike, ação e sobrevivência, criado na plataforma Fortnite Creative utilizando o Unreal Editor for Fortnite (UEFN). Inspirado no "Zombie Ville 3D", o jogo coloca os jogadores em um ambiente pós-apocalíptico, onde enfrentam hordas de inimigos enquanto exploram o mundo, coletam recursos e aprimoram suas habilidades. O jogador deve sobreviver o máximo de tempo possível, enfrentando desafios crescentes e explorando mecânicas de combate e progressão.

A escolha desse projeto é relevante para o campo da engenharia de software, pois abrange o desenvolvimento de sistemas complexos, por exemplo, um sistema de IA (Bot) personalizado, incluindo controle de spawn de inimigos, gerenciamento de recursos, balanceamentos e implementação de animações, efeitos visuais e sonoros. Além disso, o uso da UEFN aplica uma nova linguagem de programação chamado "Verse", lançado em março de 2023.

O objetivo principal do projeto é criar uma experiência de jogo imersiva e desafiadora, onde o jogador enfrenta ondas de inimigos em um cenário dinâmico e perigoso. Objetivos secundários incluem o desenvolvimento de mecânicas de combate, coleta de recursos, animações e efeitos sonoros que garantam uma jogabilidade envolvente, além da implementação de sistemas de morte, respawn e progressão que mantenham o jogador engajado.

---

## **2. Descrição do Projeto**

O tema do projeto é o desenvolvimento de um jogo de sobrevivência e ação chamado Lost City, criado na plataforma Fortnite Creative utilizando o Unreal Editor for Fortnite (UEFN). O jogo é inspirado no clássico "Zombie Ville 3D", mas expande a experiência ao oferecer um ambiente pós-apocalíptico inspirado ao Mad Max onde o jogador enfrenta hordas de inimigos, coleta recursos e aprimora habilidades em um ciclo contínuo de combate e exploração. O produto final é um jogo dinâmico e desafiador que combina elementos de roguelike e ação, proporcionando uma experiência imersiva com efeitos sonoros e visuais de alta qualidade.

- **Os principais problemas que o projeto visa resolver são:**
   - Dificuldade de procurar ou criar modelagens 3D dos Assets do jogo.
   - Dificuldade de implemetar os esqueletos numa modelagem 3D para animar os inimigos.
   - Ausência de Progressão Significativa: Lost City oferece um sistema de coleta de recursos e aprimoramento de habilidades, garantindo ao jogador um senso contínuo de progresso.
 
- **No entanto, o projeto também possui algumas limitações definidas para manter o escopo viável:**
   - Limitações de criar uma arma personalizada, usar somente armas existentes no Fortnite.
   - Limitações de criar um veículo personalizado.
 
<p align="center">
  <img src="https://github.com/Taiga-Naka/portifolio-uefn/blob/main/Ambient%201.jpg" width="600" heigh="400"/>
</p

<p align="center">
  <img src="https://github.com/Taiga-Naka/portifolio-uefn/blob/main/Ambient%202.jpg" width="600" heigh="400"/>
</p
 
 <p align="center">
  <img src="https://github.com/Taiga-Naka/portifolio-uefn/blob/main/Ambient%203.jpg" width="600" heigh="400"/>
</p
 
 <p align="center">
  <img src="https://github.com/Taiga-Naka/portifolio-uefn/blob/main/Ambient%204.jpg" width="600" heigh="400"/>
</p
---

## **3. Especificação Técnica**

### **3.1. Requisitos de Software**
O desenvolvimento do jogo Lost City será realizado na plataforma Fortnite Creative, utilizando o Unreal Editor for Fortnite (UEFN). A escolha dessa plataforma se deve à sua capacidade de criar jogos dinâmicos com suporte a gráficos avançados e mecânicas de jogo personalizáveis.

- **Lista de Requisitos:**
   - **Requisitos Funcionais (RF):**
        - RF01: O jogo deve permitir ao jogador iniciar uma partida em uma área segura com lojas de armas e upgrades.
        - RF02: O sistema deve gerar inimigos de diferentes tipos (pequeno, médio, grande, e Boss) usando spawners dinâmicos.
        - RF03: O jogador deve ser capaz de coletar dinheiro ao derrotar inimigos, e esses recursos devem desaparecer se o jogador se afastar.
        - RF04: O jogo deve oferecer efeitos sonoros imersivos, incluindo sons de ambiente, combate e inimigos.
        - RF05: O sistema deve permitir ao jogador morrer e respawnar, com uma animação de fade de tela e estado de invulnerabilidade inicial.
        - RF06: O jogador deve ter acesso a um sistema de progressão, que mantém o dinheiro coletado e experiência entre partidas.
   
   - **Requisitos Não-Funcionais (RNF):**
        - RNF01: O jogo deve manter uma taxa de quadros mínima de 30 FPS em todas as plataformas suportadas pelo Fortnite Creative.
        - RNF02: O áudio deve ser sincronizado com os eventos de jogo em menos de 200ms de latência.
        - RNF03: O tempo de carregamento inicial não deve exceder 15 segundos.
        - RNF04: O jogo deve ser otimizado para rodar em servidores online do Fortnite, garantindo estabilidade durante as partidas.

### **3.2 Mecânicas Principais**

**Spawn de Inimigos**

- **NPC Spawner:**
    - O NPC Spawner é **teleportado** para jogadores onde os inimigos estarão spawnando.
    - Existem **5 tipos de Spawners** diferentes, cada um gerando inimigos únicos com tipos diferentes como: pequeno, médio (velocidade), grande (tank), Boss.
    - Ao ficar longe da distância no spawn teleportado, será **teleportado novamente** para o jogador.
    - Ao teleportar, todos os NPCs spawnados são **resetados**.
- **Delay de Spawn:**
    - Os inimigos não spawnam todos de uma vez. Um **delay** é aplicado entre cada spawn para manter o desafio equilibrado.

**Coleta de Recursos**

- **Dinheiro Coletável:**
    - Inimigos derrotados dropam **dinheiro** que pode ser coletado pelo jogador.
    - O dinheiro **desaparece** se o jogador se afastar além de uma distância pré-definida.

**Áudio e Efeitos Sonoros**

- **Efeitos Sonoros:**
    - O jogo utilizará **variedades** de efeitos sonoros para criar uma atmosfera imersiva.
    - Exemplos:
        1. Som ambiental.
        2. Efeitos sonoros dos inimigos (grunhidos, passos, spawn, morte, etc).
        3. Sons de combate (tiros, golpes, dano, mortes, etc).

**Animação**

- **Animação de Inimigo:**
    - Criar uma animação de movimento, ataque, dano e morte.
- **Animação de Spawn:**
    - Criar uma animação visual para o spawn dos inimigos, como um efeito de surgimento a partir do chão ou uma explosão de partículas.
- **Animação Ambiental:**
    - Criar uma animação visual do ambiente do jogo para ser mais imersivo.

**Morte e Respawn**

- **Morte do Jogador:**
    - Ao ser morto, um **fade de tela** é ativado, escurecendo gradualmente a tela.
    - Caso for jogar com equipe, o jogador respawna em um estado **"Hide"** (invisível/invulnerável) transformando em um fantasma durante o respawn, indicando o estado de invulnerabilidade, conseguindo coletar recursos.

---

## **4. Fluxo do Jogo**

1. **Início:**
    - O jogador começa em uma área segura, com uma breve introdução ao objetivo do jogo com lojas de armas, upgrades e entre outros.

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e80d5e6-bc4d-48c4-a522-aaf30d336c81" width="600" heigh="400"/>
</p>
      
2. **Exploração e Combate:**
    - O jogador é teleportado para áreas com Spawners de inimigos.
    - Deve derrotar inimigos, coletar dinheiro e sobreviver o maior tempo possível.
  
 <p align="center">
  <img src="https://github.com/user-attachments/assets/2d1c8cc2-1695-4483-bc34-5f3734711650" width="600" heigh="400"/> 
 </p>

3. **Morte e Recuperação:**
    - Ao morrer, o jogador respawna com um período de invulnerabilidade até toda equipe morrer.
    - O progresso (dinheiro coletado e EXP) é mantido com save.

 <p align="center">
  <img src="https://github.com/user-attachments/assets/6c7b72d0-4eca-4f16-93d4-f5746e366afb" width="600" heigh="400"/> 
 </p>
      
4. **Loop de Jogo:**
    - O jogo continua em um ciclo de exploração, combate e coleta, com dificuldade progressiva.

---

## **5. Próximos Passos**

Para garantir o avanço contínuo e organizado do desenvolvimento do projeto *Lost City*, os próximos passos estão divididos em categorias com metas de curto, médio e longo prazo:

### **5.1 Planejamento Inicial**

*  Finalizar o escopo do projeto com todos os sistemas principais definidos.
*  Criar um cronograma detalhado com entregas semanais.
*  Validar os requisitos com colegas/professor para garantir viabilidade.

### **5.2 Desenvolvimento de Protótipo (Curto Prazo)**

*  Configurar o ambiente de desenvolvimento na UEFN.
*  Criar um mapa básico com a área segura e zona de spawn.
*  Implementar sistema de spawn de inimigos simples.
*  Adicionar NPCs com comportamento básico (seguir jogador, atacar).
*  Testar e validar mecânicas iniciais (spawn, combate, coleta de dinheiro).

### **5.3 Implementação de Mecânicas Avançadas (Médio Prazo)**

*  Desenvolver sistema de respawn com estado "fantasma".
*  Implementar sistema de progressão (coleta de EXP e dinheiro persistente).
*  Adicionar efeitos sonoros e visuais aos principais eventos do jogo.
*  Ajustar dificuldade com base no tempo ou onda de inimigos.
*  Criar animações para inimigos (movimento, ataque, dano, morte).

### **5.4 Otimização e Polimento (Longo Prazo)**

*  Balancear o jogo com testes internos.
*  Otimizar desempenho para manter taxa de quadros mínima.
*  Refinar efeitos sonoros e visuais para maior imersão.
*  Corrigir bugs e inconsistências relatadas nos testes.

### **5.5 Testes e Feedback**

*  Realizar testes com usuários (colegas de sala, jogadores do Fortnite).
*  Coletar feedback estruturado sobre dificuldade, performance e diversão.
*  Ajustar mecânicas com base no feedback coletado.

### **5.6 Preparação para Entrega**

*  Gravar gameplay demonstrativo do jogo finalizado.
*  Criar documentação de apoio (instruções, imagens do jogo, etc).
*  Revisar o GDD completo e atualizar com base nas mudanças feitas.
*  Entregar projeto e apresentação final conforme cronograma do curso.

---
 
### **Referências**

- **Links para referências**
    - [Zombieville USA 3D](https://store.steampowered.com/agecheck/app/1801520/)
    - [Zombieville USA 3D](https://www.reddit.com/r/indiegames/comments/1hybgzc/zombieville_usa_3d_my_project_of_3_years_has_a/?tl=pt-br&rdt=61545)
- **Links para ferramentas**
    - [UEFN](https://dev.epicgames.com/community/fortnite/getting-started/uefn)
    - [Fortnite](https://www.fortnite.com/?lang=pt-BR)
    - [Dados Para análises do público](https://fortnite.gg/creative)

---

### **Aprovações dos Professores**

- **Professor 1**
   - Aprovação
- **Professor 2**
   - Aprovação
- **Professor 3**
   - Aprovação
