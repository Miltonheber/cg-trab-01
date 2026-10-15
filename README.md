# Grupo 6 - Câmara / Movimento

Trabalho prático 01 de Computação Gráfica. Demonstração interativa em OpenGL, desenvolvida em Python com pygame, onde o utilizador anda numa cena 3D com uma câmara em primeira pessoa (FPS).

## Sobre o projecto

A aplicação abre uma janela de 900x700 com:

- um chão cinzento (plano de 10x10 unidades);
- um cubo azul semi-transparente flutuando sobre o chão;
- uma sombra "falsa" do cubo projectada no chão (achatando o cubo em Y);
- uma reflexão "falsa" do cubo no chão (espelhando o cubo em Y e usando transparência);
- uma luz pontual fixa no mundo, com iluminação ativa.

O foco do trabalho é a **câmara**: a perspectiva está na matriz de projecção (`gluPerspective`) e a vista é montada em cada frame (`set_view`), com movimento e rotação controlados pelo teclado e pelo rato. A velocidade de movimento é independente do frame rate, porque usa o tempo decorrido entre frames (`dt`).

Todo o código está em [main.py](main.py).

## Requisitos

- Python 3.12
- Pacotes Python:
  - `pygame` 2.6.1
  - `PyOpenGL` 3.1.10
- Um ambiente gráfico com suporte a OpenGL (drivers de GPU atualizados).

## Como instalar

Na pasta do projecto:

```bash
python3.12 -m venv .venv
source .venv/bin/activate
pip install pygame==2.6.1 PyOpenGL==3.1.10
```

No Windows, a ativação do ambiente virtual é feita com `.venv\Scripts\activate`.

Se a pasta `.venv` já existir e tiver os pacotes instalados, basta ativá-la (passo `source .venv/bin/activate`).

## Como correr

Com o ambiente virtual ativo:

```bash
python main.py
```

Ou, sem ativar o ambiente:

```bash
.venv/bin/python main.py
```

## Controlos

| Tecla / Ação | Função                              |
| ------------ | ----------------------------------- |
| `W`          | Andar para a frente                 |
| `S`          | Andar para trás                     |
| `A`          | Andar para a esquerda               |
| `D`          | Andar para a direita                |
| `E`          | Subir                               |
| `Q`          | Descer (não desce abaixo de 0.3)    |
| Rato         | Rodar a câmara (esquerda/direita e cima/baixo) |
| `ESC`        | Sair da aplicação                   |

O rato fica capturado pela janela e escondido enquanto a aplicação está a correr. Para sair, use `ESC` (ou feche a janela).

A inclinação vertical está limitada a ±89° para evitar que a câmara "dê a volta".

## Estrutura

```
cg-trabalho-pratico-01/
├── main.py        # Código da aplicação (câmara, chão, cubo, sombra e reflexão)
├── README.md      # Este ficheiro
└── .venv/         # Ambiente virtual Python (não é necessário versionar)
```

## Notas

- Os valores de sensibilidade do rato (`MOUSE_SENS`), velocidade (`MOVE_SPEED`) e posição inicial da câmara (`cam`) estão definidos no início de `main.py`.
- A sombra e a reflexão são simulações simples, não usam técnicas avançadas de renderização (como stencil buffer ou mapas de sombra).
# cg-trab-01
