# Lost City GDD (em produção)

### **Game Design Document (GDD) - Versão 0.5**

**Título do Jogo:** Lost City

**Engine:** UEFN (Unreal Editor for Fortnite)

**Gênero:** Roguelike, Ação, Sobrevivência

**Plataforma:** Fortnite Creative (UEFN)

**Nome:** Thomas Taiga Martinez Nakagawa

**Curso:** Engenharia de Software

**Data de entrega:** 31/10/2025

---

## **Resumo**

 Lost City é um jogo de ação, sobrevivência e roguelike, desenvolvido na plataforma Fortnite Creative com o Unreal Editor for Fortnite (UEFN). Inspirado em Resident Evil, Mad Max, The Last of Us, Call of Duty Zombies e Zombie Ville 3D como principal inspiração, o jogo combina ambientação pós-apocalíptica com combate intenso em primeira pessoa (First Person) e foco em cooperação entre até quatro jogadores.

O jogador enfrenta hordas de inimigos criados do zero, com malhas esqueléticas próprias e IA personalizada de perseguição, totalmente programada em Verse. O objetivo é sobreviver o máximo possível enquanto coleta recursos, aprimora habilidades e enfrenta desafios progressivamente mais difíceis. A experiência é projetada para ser imersiva e dinâmica, com efeitos visuais e sonoros intensos, dano personalizado para cada arma, e sistema de progressão persistente com salvamento de dados individuais.

O desenvolvimento serve como um estudo prático de engenharia de software, destacando-se pela implementação de sistemas complexos como: spawners dinâmicos, lógica de coleta, dano escalável por arma, sistema de morte e respawn, save de persistência, e integração completa de IA inimiga em tempo real.

Limitações técnicas incluem o uso apenas dos recursos e armas disponíveis no Fortnite (sem veículos).

Entre os requisitos funcionais, estão: spawn dinâmico de inimigos, coleta de dinheiro, efeitos sonoros imersivos, sistema de progressão persistente, sistema de ondas (Waves) com aumento gradual de HP e dano dos inimigos, e uma Random Box que concede armas aleatórias durante as partidas.

Já entre os não-funcionais, destacam-se: performance mínima de 30 FPS, tempo de carregamento reduzido, e sincronização precisa de áudio.

O loop principal do jogo envolve: início em uma área segura, teleporte para zonas de combate, enfrentamento de hordas em waves, respawn em caso de morte e reinício com progressão mantida. O jogador busca avançar o máximo possível e se tornar o melhor sobrevivente, superando o maior número de ondas antes de ser derrotado.

O projeto segue um cronograma dividido em etapas: planejamento inicial, prototipagem, implementação de mecânicas avançadas, polimento, testes e entrega final. Futuramente, estão previstas atualizações com novos tipos de zumbis e a introdução de chefes (Bosses) para expandir o conteúdo e a dificuldade do jogo.
 
---

## **1. Introdução**

 Lost City é um projeto de desenvolvimento de um jogo de ação, sobrevivência e roguelike, criado na plataforma Fortnite Creative com o Unreal Editor for Fortnite (UEFN). Inspirado em Resident Evil, Mad Max, The Last of Us, Call of Duty Zombies e principalmente no Zombie Ville 3D, o jogo coloca os jogadores em um mundo pós-apocalíptico devastado, onde enfrentam ondas crescentes de inimigos, aprimoram suas armas e buscam sobreviver o maior número possível de rodadas. A experiência é vivida totalmente em primeira pessoa (First Person), com foco em cooperação entre até quatro jogadores, priorizando imersão, estratégia e trabalho em equipe.

A escolha deste projeto é especialmente relevante para o campo da engenharia de software aplicada a jogos, pois envolve a criação de sistemas avançados de IA personalizados — os inimigos são desenvolvidos do zero, com malhas esqueléticas próprias, comportamento de perseguição inteligente e animações integradas, tudo implementado através da linguagem Verse, lançada em março de 2023. Além disso, o desenvolvimento abrange sistemas de spawn dinâmico, persistência de dados dos jogadores (save system), dano individual por arma, e progressão contínua entre partidas, exigindo um alto nível de organização de código e lógica de jogo.

O objetivo principal do projeto é proporcionar uma experiência intensa e imersiva de combate e sobrevivência em grupo, desafiando os jogadores a resistirem a ondas cada vez mais difíceis de inimigos enquanto competem para se tornarem os melhores sobreviventes. Entre os objetivos secundários, destacam-se o desenvolvimento de sistemas de combate balanceados, efeitos visuais e sonoros realistas, Random Box de armas aleatórias, e mecânicas de progressão que garantem uma jogabilidade envolvente e recompensadora.

Futuramente, o projeto será expandido com novos tipos de zumbis, chefes (Bosses) e melhorias de IA, mantendo o ciclo de evolução contínua e aprimorando a longevidade e a rejogabilidade do título.

---

## **2. Descrição do Projeto**

O tema do projeto é o desenvolvimento de um jogo de sobrevivência e ação chamado Lost City, criado na plataforma Fortnite Creative utilizando o Unreal Editor for Fortnite (UEFN). O jogo é inspirado no clássico "Zombie Ville 3D", mas expande a experiência ao oferecer um ambiente pós-apocalíptico inspirado ao Mad Max onde o jogador enfrenta hordas de inimigose aprimora habilidades em um ciclo contínuo de combate e exploração. O produto final é um jogo dinâmico e desafiador que combina elementos de roguelike e ação, proporcionando uma experiência imersiva com efeitos sonoros e visuais de alta qualidade.

- **Os principais problemas que o projeto visa resolver são:**
   - Dificuldade de procurar ou criar modelagens 3D dos Assets do jogo.
   - Dificuldade de implemetar os esqueletos numa modelagem 3D para animar os inimigos.
   - Ausência de Progressão Significativa: Lost City oferece um sistema de coleta de recursos e aprimoramento de habilidades, garantindo ao jogador um senso contínuo de progresso.
 
- **No entanto, o projeto também possui algumas limitações definidas para manter o escopo viável:**
   - Limitações de criar uma arma personalizada, usar somente armas existentes no Fortnite.
   - Limitações de criar um veículo personalizado. Onde deixamos de colocar o veículo no jogo.
 
<p align="center">
  <img src="https://github.com/Taiga-Naka/portifolio-uefn/blob/main/Ambient%201.jpg" width="600" heigh="400"/>
</p
 
---

## **3. Especificação Técnica**

### 3.1 Requisitos de Software

O desenvolvimento do **Lost City** será realizado na plataforma **Fortnite Creative**, utilizando o **Unreal Editor for Fortnite (UEFN)**.  
A escolha dessa plataforma se deve à sua flexibilidade para criação de **experiências personalizadas**, suporte a **gráficos avançados**, **IA complexa** e integração direta com a **linguagem Verse**, permitindo controle total sobre lógica de jogo, sistemas dinâmicos e persistência de dados.

#### Requisitos Funcionais (RF)

- **RF01:** O jogo deve permitir que até **quatro jogadores cooperem** em uma mesma sessão, iniciando a partida em uma **área segura** com acesso a **lojas de armas e upgrades**.  
- **RF02:** O sistema deve **gerar inimigos de diferentes tipos** (comum, médio, rápido, tanque e futuramente Boss) usando **spawners dinâmicos** com comportamento e estatísticas variáveis conforme a **wave atual**.  
- **RF03:** Todos os inimigos devem utilizar **IA personalizada criada do zero**, com **malhas esqueléticas próprias**, comportamento de **perseguição e ataque** desenvolvido via **programação em Verse**.  
- **RF04:** O jogo deve incluir um **sistema de dano personalizado por arma**, permitindo que cada tipo de arma tenha valores específicos de dano, alcance e cadência.  
- **RF05:** O jogador deve poder **coletar dinheiro ao derrotar inimigos**, com o recurso **desaparecendo após determinado tempo** ou ao se afastar da área.  
- **RF06:** O sistema deve oferecer **efeitos sonoros imersivos**, incluindo **sons ambientais, de combate, passos e inimigos**, ajustados por distância e posição 3D.  
- **RF07:** O jogador deve possuir um **sistema de morte e respawn**, com **animação de fade de tela**, **tempo de invulnerabilidade** e **retorno à área segura**.  
- **RF08:** O jogo deve incluir um **sistema de waves (ondas)**, onde **a cada nova wave os inimigos têm HP e dano aumentados** progressivamente.  
- **RF09:** O mapa deve conter uma **Random Box** que concede **armas aleatórias** ao jogador mediante o uso de dinheiro coletado.  
- **RF10:** O sistema deve permitir **salvamento persistente de dados** (dinheiro, progresso e estatísticas) entre sessões de jogo, garantindo **continuidade de progressão**.  
- **RF11:** Futuramente, o jogo deve suportar **novos tipos de inimigos e chefes (Bosses)** através de atualizações de conteúdo.  

#### Requisitos Não-Funcionais (RNF)

- **RNF01:** O jogo deve manter uma **taxa de quadros mínima de 30 FPS** em todas as plataformas suportadas pelo Fortnite Creative.  
- **RNF02:** O **áudio deve ser sincronizado** com os eventos de jogo com latência inferior a **200ms**.  
- **RNF03:** O **tempo de carregamento inicial** não deve ultrapassar **15 segundos**.  
- **RNF04:** O projeto deve ser **otimizado para servidores online do Fortnite**, garantindo **baixa latência, estabilidade e sincronização entre os quatro jogadores**.  
- **RNF05:** O sistema de IA e efeitos deve ser projetado com **eficiência de performance**, evitando sobrecarga de memória e garantindo **escalabilidade para futuras atualizações**.  

## 3.2 Mecânicas Principais

As mecânicas principais de **Lost City** foram desenvolvidas inteiramente através de **programação personalizada em Verse**, sem o uso de dispositivos padrão como *NPC Spawner*.  
Cada inimigo, comportamento e evento é controlado por lógica própria, garantindo **maior liberdade criativa**, **imersão** e **precisão no balanceamento do jogo**.

### Sistema de Inimigos

- **IA Personalizada:**
  - Todos os inimigos são criados do **zero**, utilizando **malhas esqueléticas próprias**, animações exclusivas e uma IA de perseguição programada manualmente.
  - A IA é capaz de **detectar jogadores pelo campo de visão e proximidade**, perseguindo-os e atacando com base em comportamento reativo (ex: priorizar o jogador mais próximo ou com menor vida).
  - Cada tipo de inimigo possui **atributos únicos**, como velocidade, dano e pontos de vida.

- **Tipos de Inimigos:**
  1. **Walker (Pequeno):** rápido, razoável e ataque básico.  
  2. Outros zumbis terão em futuros updates.

- **Sistema de Waves:**
  - O jogo é baseado em **ondas progressivas (Waves)**.
  - A cada nova wave, os inimigos têm seu **HP e dano aumentados** proporcionalmente.
  - A contagem de inimigos por wave é definida dinamicamente, garantindo **equilíbrio e ritmo de desafio constante**.
  - Quando todos os inimigos de uma wave são eliminados, a próxima começa após um curto intervalo de tempo.
  - O objetivo dos jogadores é **sobreviver o maior número de waves possível**.

- **Delay de Spawn:**
  - O sistema aplica **intervalos de spawn** entre inimigos para manter o fluxo equilibrado de combate.
  - Esses intervalos são ajustados dinamicamente de acordo com o número de jogadores na partida.

### Sistema de Armas e Dano

- **Dano Personalizado:**
  - Cada arma possui **valores únicos de dano**, cadência e alcance, programados individualmente.
  - O dano é calculado de forma **dinâmica**, permitindo diferenciação entre tipos de arma (pistola, rifle, shotgun, etc).
  - Futuramente, novas armas poderão ser adicionadas com **balanço individual de dano e impacto**.

- **Random Box:**
  - O mapa conta com uma **Random Box** que concede **armas aleatórias** em troca de dinheiro coletado dos inimigos.
  - O jogador pode utilizar esse sistema para tentar obter armas raras ou mais poderosas durante a partida.

### Áudio e Efeitos Sonoros

- **Efeitos Sonoros Imersivos:**
  - Sons de ambiente (vento, destruição, ecos).
  - Efeitos dos inimigos (grunhidos, passos, ataque e morte).
  - Sons de combate (tiros, recarregamento, impacto e dano).
  - Cada som é posicionado em **3D espacial**, reagindo à distância e direção do jogador.
  - A ambientação sonora é um dos pilares da **imersão e tensão do jogo**.

### Animações

- **Inimigos:**
  - Animações de **movimento**, **ataque**, **tomar dano** e **morte**.
  - O comportamento de animação é sincronizado com a IA, garantindo fluidez e realismo nas ações.

- **Spawn:**
  - Efeitos visuais no surgimento dos inimigos, simulando **explosões de energia, fumaça ou partículas saindo do chão**.
  - Cada tipo de inimigo pode ter um estilo visual distinto de spawn.

- **Ambiente:**
  - Elementos visuais animados no cenário (fumaça, poeira, luzes piscando, fogo distante) reforçam o clima pós-apocalíptico.
  - Utiliza **efeitos de partículas e luz dinâmica** para intensificar a atmosfera.

### Morte e Respawn

- **Morte do Jogador:**
  - Ao morrer, a tela passa por um **efeito de fade escuro**, representando a queda do jogador.
  - Um temporizador controla o tempo de retorno, e o jogador é **reposicionado na área segura** após a recuperação.
  - Em partidas cooperativas, outros jogadores podem continuar lutando enquanto o aliado respawna.

- **Feedback Visual:**
  - Um **efeito visual de energia** ou partículas indica o estado de invulnerabilidade temporária.
  - Esse feedback ajuda a comunicar claramente o status do jogador durante o respawn.

### Loop de Gameplay

1. Jogadores iniciam em uma **zona segura**.  
2. São teleportados automaticamente para o **campo de combate**.  
3. As **waves de inimigos** começam a surgir e aumentar de intensidade.  
4. Jogadores tentam **sobreviver o máximo possível**, utilizando armas obtidas.  
5. Ao morrer, respawnam e retornam à luta até a **derrota total da equipe**.  
6. O progresso é **salvo e persistente** para futuras sessões.  

---

## 4. Fluxo do Jogo

O fluxo de gameplay de **Lost City** é estruturado para manter o jogador em constante ação e imersão.  
A experiência alterna entre **momentos de preparação, combate intenso e progressão**, com um ciclo contínuo de **ondas (Waves)** cada vez mais desafiadoras.  
O jogo é totalmente **cooperativo**, permitindo que até **4 jogadores** enfrentem hordas em conjunto, compartilhando estratégias e sobrevivendo o máximo possível.

### 1. Início

- O jogador inicia em uma **área segura**, onde recebe uma **breve introdução ao objetivo do jogo** e tem acesso a:
  - **Lojas de armas e upgrades.**
  - **Painel de status e progresso**, exibindo waves completadas e estatísticas básicas.
- Esta área serve como **ponto de preparação e reagrupamento** antes do combate.

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e80d5e6-bc4d-48c4-a522-aaf30d336c81" width="600" heigh="400"/>
</p>

### 2. Início da Partida e Combate

- Quando a partida começa, os jogadores são **teleportados automaticamente** para o **campo de batalha principal**.
- O sistema de **spawn personalizado** cria inimigos em tempo real, de forma dinâmica, com base na posição e quantidade de jogadores.
- O objetivo é **sobreviver o máximo possível** enfrentando **ondas progressivas (Waves)**.
- A cada wave:
  - Novos inimigos são gerados com **HP e dano aumentados**.
  - A dificuldade se ajusta conforme o desempenho da equipe.
- **Random Box**, com chance de obter armas aleatórias.
- O combate é **em primeira pessoa (First Person)**, com **dano personalizado para cada arma**, sons imersivos e feedback visual a cada acerto.

<p align="center">
  <img src="https://github.com/user-attachments/assets/2d1c8cc2-1695-4483-bc34-5f3734711650" width="600" heigh="400"/> 
</p>

### 3. Morte e Respawn

- Ao morrer, o jogador:
  - Passa por um **efeito de fade de tela**, reforçando a sensação de transição entre morte e respawn.
  - Retorna ao Lobby
- O jogador é **respawnado na área segura**, podendo retornar à luta na próxima wave.
- Caso todos os jogadores sejam eliminados, a partida é encerrada e o sistema registra o **número total de waves vencidas**.

### 4. Loop de Jogo

O ciclo principal de Lost City segue a estrutura abaixo:

1. Jogadores iniciam na **área segura**.  
2. São teleportados para o **campo de combate**.  
3. Enfrentam **waves de inimigos**, com dificuldade progressiva.  
4. Jogadores mortos respawnam pro Lobby.  
5. Quando todos morrem, o jogo registra o **progresso e estatísticas**.  
6. O sistema **salva os dados persistentes** de cada jogador (nível, armas e waves alcançadas).  
7. O ciclo recomeça, permitindo **novas tentativas e evolução contínua**.  

---

## 5. Próximos Passos

Para garantir o **avanço contínuo e estruturado** do desenvolvimento do projeto **Lost City**, o cronograma está dividido em **etapas estratégicas** com metas de **curto, médio e longo prazo**, abrangendo desde o planejamento até o polimento final e entrega.

### 5.1 Planejamento Inicial

- Definir o **escopo final do projeto**, com todos os sistemas principais documentados (IA, dano, waves, respawn e save).  
- Criar um **cronograma detalhado** com entregas semanais e checkpoints de progresso.  
- Validar a **viabilidade técnica** com colegas/professor, especialmente quanto à IA, desempenho e limitações do UEFN.  
- Estruturar pastas, nomenclaturas e convenções de código **Verse** para manter o projeto organizado.  

### 5.2 Desenvolvimento do Protótipo (Curto Prazo)

- Configurar o **ambiente de desenvolvimento na UEFN** e integrar scripts iniciais em Verse.  
- Criar o **mapa base**, contendo:
  - Área segura inicial.  
  - Zona de combate principal.  
- Implementar o **sistema personalizado de spawn e IA** básica (movimento, perseguição e ataque).  
- Adicionar o **sistema de waves** inicial com progressão automática.  
- Implementar **sistema de dano customizado por arma** e detecção de colisão.  
- Realizar **testes de gameplay cooperativo** entre múltiplos jogadores para validar funcionamento em rede.  

### 5.3 Implementação de Mecânicas Avançadas (Médio Prazo)
  
- Implementar o **sistema de save persistente**, salvando progresso e estatísticas de cada jogador.  
- Adicionar **efeitos sonoros e visuais personalizados** (combate, morte, ambiente e spawn de inimigos).  
- Inserir **Random Box de armas aleatórias**, com lógica de rotação e raridade.  
- Integrar **animações completas dos inimigos** (movimento, ataque, dano e morte).  
- Balancear o **nível de dificuldade das waves** com base no desempenho da equipe.  

### 5.4 Otimização e Polimento (Longo Prazo)

- Realizar **testes de balanceamento e performance** em diferentes plataformas (PC e console).  
- Otimizar o uso de memória e scripts Verse para **manter estabilidade e 30+ FPS**.  
- Refinar **feedback visual e sonoro** para máxima imersão (partículas, luz, ambiência, impacto).  
- Corrigir **bugs, travamentos e inconsistências** detectadas nos testes.  
- Revisar iluminação, pós-processamento e ambientação para aprimorar o **clima pós-apocalíptico**.  

### 5.5 Testes e Feedback

- Conduzir testes internos.  
- Coletar **feedback estruturado** sobre:
  - Dificuldade e ritmo das waves.  
  - Performance e estabilidade.  
  - Imersão e diversão geral.  
- Aplicar **ajustes iterativos** nas mecânicas, IA e balanceamento conforme o feedback.  

### 5.6 Preparação para Entrega

- Gravar uma **gameplay demonstrativa** do jogo completo, mostrando as principais features.  
- Criar **documentação de apoio** (instruções de jogo, imagens, mapa de fluxo e créditos).  
- Revisar o **GDD completo**, atualizando conforme as mudanças feitas durante o desenvolvimento.  
- Preparar **apresentação final e entrega oficial** do projeto conforme o cronograma do curso.  

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
