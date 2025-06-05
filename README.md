# Game-Controller

# Controle Virtual Responsivo em HTML e CSS

Este projeto apresenta um design de controle virtual (**gamepad**) totalmente responsivo, criado utilizando **HTML**, **CSS** (com **Tailwind CSS** para utilitários) e uma pequena quantidade de **JavaScript** para feedback de toque.  
O objetivo é fornecer uma interface de controle visual que se adapta a diferentes tamanhos de tela, oferecendo uma experiência de "console" em desktops e uma visualização otimizada para tela cheia em dispositivos móveis e tablets.

---

## Funcionalidades

- **D-Pad Moderno**: Um direcional digital (**D-Pad**) circular com botões para cima, baixo, esquerda e direita.

- **Botões de Ação (Diamond Layout)**: Quatro botões de ação principais (Y, X, B, A) dispostos em um formato de losango, inspirados em controles modernos:
  - **Y**: Amarelo  
  - **X**: Azul  
  - **B**: Vermelho  
  - **A**: Verde

- **Botões Centrais**: Dois botões menores para funções como _"View"_ (ícone de menu hambúrguer) e _"Menu"_ (ícone de três linhas).

---

## Design Responsivo Inteligente

- **Desktop ("Consolezinho")**: Em telas maiores (geralmente acima de `768px` de largura), o controle é exibido como um elemento compacto e centralizado, simulando um pequeno console.

- **Celular/Tablet (Tela Cheia)**: Em telas menores (≤ `768px`), o controle se expande para ocupar toda a tela. Os botões e o D-Pad são redimensionados usando a unidade `vmin` e a função `clamp()` do CSS, garantindo usabilidade com toque em diferentes dispositivos e orientações (retrato/paisagem).

---

## Feedback Visual e de Toque

- Efeitos de `hover` e `active` nos botões para feedback visual em desktops.
- JavaScript captura eventos `touchstart` e `touchend`, aplicando efeitos de _"pressão"_ (transformação de escala, brilho, cor) em dispositivos móveis.
- A meta tag `user-scalable=no` previne o zoom acidental em dispositivos móveis.

---

## Estilização Moderna

- Utiliza **Tailwind CSS** (via CDN) para classes utilitárias.
- CSS customizado com aparência escura, sombras, transições suaves e responsividade total.

---

## Como Funciona

O layout do controle é construído com **HTML semântico**, e a estilização é feita com **CSS** (utilitário + customizado).

### Estrutura

- Corpo principal (`.controller-body`)
  - Cluster do D-Pad (`.controls-cluster-left`)
  - Cluster dos botões de ação (`.controls-cluster-right`)
  - Botões centrais (`.center-buttons-container`), posicionados de forma absoluta ou estática.

### Responsividade

- **Media queries** CSS são utilizadas para adaptação.  
  A principal transição ocorre com `max-width: 768px`.

- No modo mobile/tela cheia:
  - `.controller-body` vira `width: 100%` e `height: 100%`
  - `flex-direction: row`
  - `clamp(MIN, PREFERRED, MAX)` é usado para tamanho de botões/textos com `vmin`.

### JavaScript para Toque

- Listeners `touchstart` e `touchend` adicionados aos botões.
- `preventDefault()` evita zoom/scroll indesejado.
- Estilos de feedback são aplicados durante o toque e removidos após.

---

## Como Usar / Visualizar

1. Clone ou baixe este repositório.
2. Abra o arquivo `NOME_DO_SEU_ARQUIVO.html` em qualquer navegador moderno.
3. Redimensione a janela (ou abra em um celular/tablet) para ver a responsividade em ação.

---

## Tecnologias Utilizadas

- HTML5  
- CSS3  
- Tailwind CSS (via CDN)  
- Flexbox  
- Grid Layout  
- Media Queries  
- `clamp()`  
- JavaScript
