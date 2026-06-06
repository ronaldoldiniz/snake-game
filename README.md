# 🐍 Snake Game

Um jogo clássico da cobrinha desenvolvido com **HTML**, **CSS** e **JavaScript puro**, utilizando o elemento **Canvas** para renderização gráfica, sistema de pontuação, tela inicial, tela de fim de jogo e salvamento de recorde no navegador com `localStorage`.

---

## 📝 Descrição curta para o GitHub

> Snake Game clássico feito com HTML, CSS e JavaScript puro, usando Canvas, pontuação, recorde com localStorage e controles pelo teclado.

---

## 🎮 Sobre o jogo

O **Snake Game** é uma recriação do tradicional jogo da cobrinha.  
O objetivo é controlar a cobra, comer a comida vermelha, aumentar a pontuação e evitar colisões com as paredes ou com o próprio corpo.

O projeto foi construído em um único arquivo HTML, com estilos CSS e lógica JavaScript integrados, tornando-o simples de executar, estudar, modificar e publicar.

---

## ✨ Funcionalidades

- 🐍 Movimento contínuo da cobra
- 🍎 Geração aleatória de comida
- 🧮 Sistema de pontuação em tempo real
- 🏆 Salvamento automático do recorde no navegador
- 💀 Tela de **Game Over**
- ▶️ Tela inicial com botão para começar
- 🔁 Botão para jogar novamente
- 🎨 Interface visual moderna com tema escuro
- ⌨️ Controle por teclado usando as setas direcionais
- 💾 Uso de `localStorage` para manter o melhor resultado

---

## 🕹️ Como jogar

Use as setas do teclado para controlar a cobra:

| Tecla | Ação |
|---|---|
| ⬆️ Seta para cima | Move para cima |
| ⬇️ Seta para baixo | Move para baixo |
| ⬅️ Seta para esquerda | Move para esquerda |
| ➡️ Seta para direita | Move para direita |

### 🎯 Objetivo

Coma a comida vermelha para ganhar pontos e aumentar o tamanho da cobra.

### ⚠️ Fim de jogo

O jogo termina quando a cobra:

- bate nas bordas do tabuleiro;
- colide com o próprio corpo.

---

## 🚀 Como executar o projeto

### Opção 1 — Abrir diretamente no navegador

1. Baixe ou clone este repositório.
2. Abra o arquivo `SnakeGame.html` no navegador.
3. Clique em **Iniciar**.
4. Jogue usando as setas do teclado.

### Opção 2 — Executar com Live Server no VS Code

1. Abra a pasta do projeto no **Visual Studio Code**.
2. Instale a extensão **Live Server**.
3. Clique com o botão direito no arquivo `SnakeGame.html`.
4. Selecione **Open with Live Server**.

---

## 📁 Estrutura do projeto

```text
snake-game/
│
├── SnakeGame.html
└── README.md
```

---

## 🧱 Tecnologias utilizadas

| Tecnologia | Uso no projeto |
|---|---|
| 🌐 HTML5 | Estrutura da página e elemento Canvas |
| 🎨 CSS3 | Estilização da interface, botões, overlays e layout |
| ⚙️ JavaScript | Lógica do jogo, movimentação, colisões e pontuação |
| 🖼️ Canvas API | Renderização da cobra, comida e tabuleiro |
| 💾 localStorage | Armazenamento do recorde no navegador |

---

## ⚙️ Funcionamento técnico

O jogo utiliza uma grade de **25 x 25 posições** dentro de um Canvas de **500 x 500 pixels**.

Cada bloco da grade possui aproximadamente **20 pixels**, calculado a partir da divisão:

```javascript
const grid = 25;
const tile = canvas.width / grid;
```

A movimentação da cobra é controlada pelas variáveis `dx` e `dy`, que representam a direção atual nos eixos X e Y.

O loop principal do jogo é executado com `setInterval`, chamando a função `tick()` a cada **110 milissegundos**:

```javascript
gameLoop = setInterval(tick, 110);
```

A cada ciclo, o jogo:

1. calcula a nova posição da cabeça da cobra;
2. verifica colisões;
3. verifica se a comida foi capturada;
4. atualiza a pontuação;
5. redesenha o Canvas.

---

## 🧩 Principais funções

| Função | Responsabilidade |
|---|---|
| `init()` | Inicializa a cobra, pontuação, direção e comida |
| `spawnFood()` | Gera uma nova comida em uma posição livre |
| `drawTile()` | Desenha um bloco da cobra no Canvas |
| `drawFood()` | Desenha a comida no Canvas |
| `draw()` | Redesenha todo o tabuleiro |
| `update()` | Atualiza a lógica do jogo |
| `tick()` | Executa um ciclo do jogo |
| `startGame()` | Inicia uma nova partida |
| `restart()` | Reinicia o jogo após o Game Over |
| `endGame()` | Finaliza a partida e exibe a pontuação |

---

## 🧠 Regras implementadas

- A cobra começa com apenas uma parte.
- A direção inicial é para a direita.
- A cobra cresce ao comer a comida.
- A pontuação aumenta em 1 ponto a cada comida coletada.
- O recorde é atualizado automaticamente quando a pontuação atual supera o melhor resultado anterior.
- A comida nunca nasce em cima da cobra.
- O jogador não pode inverter diretamente a direção da cobra.
  - Exemplo: se estiver indo para a direita, não pode ir imediatamente para a esquerda.
- A colisão com a parede encerra o jogo.
- A colisão com o próprio corpo encerra o jogo.

---

## 🖼️ Interface

A interface possui três estados principais:

### 🟢 Tela inicial

Exibe o nome do jogo, uma breve instrução e o botão **Iniciar**.

### 🎮 Tela de jogo

Exibe:

- pontuação atual;
- recorde;
- área do Canvas;
- instrução de controle.

### 💀 Tela de Game Over

Exibe:

- mensagem de fim de jogo;
- pontuação final;
- botão para jogar novamente.

---

## 🏆 Sistema de recorde

O recorde é salvo localmente no navegador usando a chave:

```javascript
snake-best
```

Isso permite que o melhor resultado continue disponível mesmo após fechar e abrir o navegador novamente.

---

## 🎨 Personalização

Alguns pontos fáceis de personalizar:

| Item | Onde alterar |
|---|---|
| Tamanho do tabuleiro | `canvas width` e `canvas height` |
| Quantidade de células | `const grid = 25` |
| Velocidade do jogo | `setInterval(tick, 110)` |
| Cor da cobra | `#22c55e` e `#4ade80` |
| Cor da comida | `#ef4444` |
| Cor de fundo | `#111827` e `#1f2937` |
| Nome do jogo | Tag `<h1>` e `<title>` |

---

## 📌 Melhorias futuras

Algumas ideias para evoluir o projeto:

- 📱 Adicionar controles para dispositivos móveis
- 🔊 Inserir efeitos sonoros
- 🎵 Adicionar música de fundo
- ⚡ Criar níveis de dificuldade
- ⏸️ Adicionar botão de pausa
- 🧱 Inserir obstáculos no mapa
- 🌎 Publicar com GitHub Pages
- 🧾 Separar o projeto em arquivos `index.html`, `style.css` e `script.js`
- 🧪 Adicionar testes básicos para funções da lógica
- 🏅 Criar ranking local com múltiplas pontuações

---

## 🌎 Publicação no GitHub Pages

Para publicar o jogo no GitHub Pages:

1. Envie os arquivos para um repositório no GitHub.
2. Acesse **Settings**.
3. Clique em **Pages**.
4. Em **Branch**, selecione `main`.
5. Selecione a pasta `/root`.
6. Clique em **Save**.
7. Aguarde o GitHub gerar o link público.

> Observação: para facilitar a publicação, é recomendado renomear `SnakeGame.html` para `index.html`.

---

## ✅ Status do projeto

🟢 Projeto funcional e pronto para execução no navegador.

---

## 👨‍💻 Autor

Desenvolvido como projeto de jogo web com HTML, CSS e JavaScript.

---

## 📄 Licença

Este projeto pode ser utilizado para fins de estudo, prática e evolução em desenvolvimento web.

Caso utilize em um repositório público, recomenda-se adicionar uma licença, como:

- MIT License
- Apache License 2.0
- GNU GPL v3

---

## ⭐ Apoie o projeto

Se este projeto ajudou você, considere deixar uma estrela no repositório. ⭐
