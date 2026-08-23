# Fontes de Alimentação de Bancada

Repositório dedicado ao desenvolvimento de **fontes de alimentação de bancada**, realizadas como projetos acadêmicos durante o curso de **Engenharia da Computação da Universidade Santa Cecília (UNISANTA)**.

O repositório reúne duas etapas do desenvolvimento:

* **Fonte de alimentação de 5 V**, desenvolvida inicialmente para estudo e aplicação dos conceitos básicos de uma fonte regulada.
* **Fonte de alimentação regulável bivolt**, desenvolvida posteriormente como uma evolução do projeto, incorporando seleção de tensão de entrada, saída fixa de 5 V, saída variável, sistema de ventilação, PCB própria e encapsulamento em MDF.

Os projetos envolveram desde o desenvolvimento dos circuitos eletrônicos até a fabricação das placas e construção física dos equipamentos.

---

# 1. Fonte de Alimentação 5 V

A primeira etapa do projeto consistiu no desenvolvimento de uma fonte de alimentação com **saída regulada de 5 V**.

Esse projeto teve como objetivo aplicar os conceitos fundamentais necessários para transformar uma tensão de entrada em uma tensão contínua regulada adequada para alimentar circuitos eletrônicos.

## Características

* Saída regulada de **5 V DC**
* Regulador linear **LM7805**
* Circuito de retificação
* Filtragem da tensão
* Capacitores para estabilização
* Circuito de proteção
* Desenvolvimento da placa de circuito impresso

O **LM7805** foi utilizado como elemento responsável pela regulação da tensão de saída.

## Funcionamento

O funcionamento básico da fonte pode ser representado por:

```text
Entrada AC
    │
    ▼
Transformador
    │
    ▼
Retificação
    │
    ▼
Filtragem
    │
    ▼
LM7805
    │
    ▼
Saída regulada de 5 V DC
```

Essa primeira etapa serviu como base para o desenvolvimento da fonte regulável apresentada posteriormente.

---

# 2. Fonte de Alimentação Regulável Bivolt

A segunda etapa consistiu no desenvolvimento de uma **fonte de alimentação regulável e bivolt**, projetada para aplicações de bancada.

O objetivo inicial do projeto era desenvolver uma fonte com:

* Entrada selecionável entre **110 V e 220 V**;
* Saída fixa de **5 V**;
* Saída variável;
* Corrente mínima de **1 A**;
* Sistema de ventilação;
* PCB própria;
* Encapsulamento físico.

O objetivo acadêmico incluía o desenvolvimento do circuito, layout da placa, encapsulamento, ventilação e validação prática do funcionamento.

## Especificações finais

| Característica              | Especificação      |
| --------------------------- | ------------------ |
| Entrada                     | 110/220 V AC       |
| Transformador               | 12 V / 3 A         |
| Saída fixa                  | 5 V DC             |
| Saída variável              | **11 V a 13 V DC** |
| Regulador da saída variável | LM317              |
| Regulador da saída de 5 V   | LM7805             |
| Regulador de 12 V           | LM7812             |
| Ponte retificadora          | KBU808             |
| Potenciômetro               | 10 kΩ              |
| Dimensão da PCB             | 10 × 7,5 cm        |
| Dimensão do gabinete        | 15 × 11 × 15 cm    |
| Material do gabinete        | MDF                |

---

# 3. Circuito eletrônico

O circuito da fonte é composto por diferentes etapas responsáveis pela transformação e regulagem da energia.

De forma simplificada:

```text
                    ┌──────────────► LM7805 ───► 5 V DC
                    │
Rede AC             │
  │                 │
  ▼                 │
Seletor             │
110/220 V           │
  │                 │
  ▼                 │
Transformador       │
12 V / 3 A          │
  │                 │
  ▼                 │
KBU808              │
Ponte retificadora  │
  │                 │
  ▼                 │
4700 µF             │
Filtragem           │
  │                 │
  ├─────────────────┼──────► LM7812 ───► 12 V
  │                 │
  │                 └──────► LM317 ────► Saída variável
  │                                      │
  │                                      ▼
  │                                  11 V ~ 13 V
  │
  ▼
Tensão contínua filtrada
```

A fonte utiliza uma ponte retificadora **KBU808**, capacitores eletrolíticos de **4700 µF** para filtragem, reguladores LM7805, LM7812 e LM317, além de componentes de desacoplamento e proteção.

---

# 4. Componentes

Os principais componentes utilizados no projeto são:

* 1 × Transformador bivolt 12 V / 3 A
* 1 × Ponte retificadora KBU808
* 1 × LM7805
* 1 × LM7812
* 1 × LM317
* 3 × Diodos 1N4004
* 2 × Capacitores eletrolíticos de 4700 µF
* 2 × Capacitores de 0,33 µF
* 3 × Capacitores de 0,1 µF
* 1 × Resistor de 220 Ω
* 1 × Potenciômetro de 10 kΩ
* 6 × Conectores borne
* 1 × Seletor 110/220 V de 6 pinos
* 1 × Chave alavanca
* 1 × Fusível
* 1 × Conector para cabo de alimentação

---

# 5. Desenvolvimento da PCB

A esquemática e o layout da placa foram desenvolvidos utilizando o **KiCad 7.0**.

A PCB possui dimensões de:

**10 × 7,5 cm**

A fabricação da placa foi realizada através de **fresagem em placa de fenolite**, utilizando as instalações do **INOVFabLab da Universidade Santa Cecília**.

## Estrutura dos arquivos

Os arquivos relacionados ao desenvolvimento eletrônico podem ser organizados da seguinte maneira:

```text
KiCad/
├── Esquematico/
├── PCB/
└── Gerbers/
```

---

# 6. Desenvolvimento do encapsulamento

O encapsulamento da fonte foi desenvolvido utilizando o **Autodesk Fusion 360**.

O projeto foi pensado para acomodar a PCB, componentes, conexões e sistema de ventilação em uma estrutura compacta.

A fabricação foi realizada utilizando **MDF e corte a laser**.

### Dimensões

```text
15 × 11 × 15 cm
```

Foi utilizada uma placa de MDF de **1,3 × 0,9 m** para a fabricação do gabinete.

---

# 7. Evolução do projeto

O desenvolvimento da fonte regulável ocorreu a partir da experiência adquirida durante a primeira etapa do projeto.

Inicialmente, foi planejada a utilização de **duas placas separadas**. A placa da entrega parcial possuía as saídas fixas de **5 V e 12 V**.

A saída de 5 V seria utilizada para alimentação de uma carga, enquanto a saída de 12 V seria utilizada para alimentar a ventoinha responsável pelo resfriamento do regulador de 5 V.

Durante a prototipagem da primeira placa foram identificados problemas no circuito. Como consequência, o projeto foi reorganizado e os componentes passaram a ser integrados em **uma única placa**.

Também houve uma alteração no circuito responsável pela saída variável. Inicialmente havia sido planejado outro circuito de regulador linear, porém ele foi substituído pelo **LM317**, principalmente pela praticidade de implementação.

---

# 8. Resultado final

Após a montagem e os testes do protótipo, a fonte apresentou:

### Saída fixa

**5 V DC**

### Saída variável

**11 V a 13 V DC**

A faixa obtida representa o resultado final medido no protótipo desenvolvido.

O projeto inicialmente previa uma saída variável de 0 a 12 V, porém a implementação final utilizando o LM317 apresentou uma faixa diferente da especificação inicial.

O relatório técnico registra uma faixa de 1,10 V a 13 V para uma etapa anterior de avaliação, enquanto o resultado final considerado neste repositório é de **11 V a 13 V**, conforme os testes finais realizados no protótipo.

---

# 9. Comparação entre as etapas

| Característica   |        Fonte 5 V | Fonte Regulável Bivolt |
| ---------------- | ---------------: | ---------------------: |
| Saída fixa       |              5 V |                    5 V |
| Saída variável   |              Não |                11–13 V |
| Entrada bivolt   | Não especificada |                    Sim |
| LM7805           |              Sim |                    Sim |
| LM317            |              Não |                    Sim |
| LM7812           |              Não |                    Sim |
| PCB própria      |              Sim |                    Sim |
| Encapsulamento   |                - |                    MDF |
| Ventilação       |                - |                    Sim |
| Projeto mecânico |                - |             Fusion 360 |

---

# 10. Organização do repositório

```text
Fontes-de-Alimentacao/
│
├── README.md
│
├── Fonte-5V/
│   ├── KiCad/
│   │   ├── Esquematico/
│   │   ├── PCB/
│   │   └── Gerbers/
│   │
│   ├── Imagens/
│   └── Documentacao/
│
├── Fonte-Regulavel-Bivolt/
│   ├── KiCad/
│   │   ├── Esquematico/
│   │   ├── PCB/
│   │   └── Gerbers/
│   │
│   ├── Fusion360/
│   ├── Imagens/
│   └── Documentacao/
│
└── Relatorio/
    └── RELATORIO_FONTE.pdf
```

---

# 11. Ferramentas utilizadas

## Eletrônica

* **KiCad 7.0**
* Projeto de esquemática
* Projeto de PCB
* Geração de arquivos de fabricação

## Projeto mecânico

* **Autodesk Fusion 360**
* Modelagem do encapsulamento
* Preparação para fabricação

## Fabricação

* Fresagem de PCB em placa de fenolite
* Corte a laser de MDF

---

# 12. Objetivos acadêmicos

O desenvolvimento das fontes permitiu aplicar conceitos de eletrônica desde o projeto do circuito até a fabricação e validação do equipamento.

Entre os principais conhecimentos aplicados estão:

* Retificação de tensão;
* Filtragem;
* Regulagem de tensão;
* Reguladores lineares;
* Dissipação térmica;
* Proteção de componentes;
* Desenvolvimento de PCB;
* Montagem de circuitos;
* Projeto mecânico;
* Fabricação digital;
* Testes e validação de hardware.

O projeto também possibilitou compreender, na prática, as etapas necessárias para transformar uma ideia de circuito em um equipamento físico funcional.

---

# 13. Imagens

## Fonte de 5 V

Adicione aqui imagens da primeira fonte:

```text
Fonte-5V/Imagens/
```

## PCB da fonte regulável

Adicione aqui a imagem da PCB desenvolvida no KiCad.

## Esquemático

Adicione aqui a imagem do esquemático completo.

## Encapsulamento

Adicione aqui imagens do modelo desenvolvido no Fusion 360.

## Fonte final

Adicione aqui imagens da fonte montada e finalizada.

---

# 14. Autores

**Caique Caruso Toscani da Costa**

**Gabriel Kevin Souza Cruz**

**Engenharia da Computação**
**Universidade Santa Cecília — UNISANTA**

Santos, São Paulo — Brasil
2026

---

# 15. Segurança

> **ATENÇÃO:** este projeto trabalha diretamente com tensão de rede elétrica de **110/220 V AC**.

A montagem, manutenção ou reprodução do circuito deve ser realizada utilizando procedimentos adequados de segurança elétrica e por pessoas capacitadas.

Este projeto foi desenvolvido para fins **acadêmicos e educacionais**.

# 16. Documentação

O relatório técnico completo do projeto, desenvolvido para a disciplina de **Tópicos de Eletrônica** da Universidade Santa Cecília, está disponível neste repositório.

📄 **[Relatório Técnico](./Relatorio/RELATORIO_FONTE.pdf)**

O documento apresenta o desenvolvimento do projeto, incluindo:

* Introdução e objetivos;
* Materiais e métodos;
* Desenvolvimento do circuito;
* Projeto da PCB;
* Desenvolvimento do encapsulamento;
* Resultados obtidos;
* Conclusão;
* Referências utilizadas.
