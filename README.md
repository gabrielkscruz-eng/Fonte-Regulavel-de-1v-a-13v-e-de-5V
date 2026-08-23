# Fonte de Alimentação de Bancada

Projeto de desenvolvimento de **fontes de alimentação para bancada**, realizado no curso de **Engenharia da Computação da Universidade Santa Cecília (UNISANTA)**.

O repositório reúne duas etapas do desenvolvimento:

* **Fonte de alimentação fixa de 5 V**
* **Fonte de alimentação regulável bivolt**

O projeto envolveu o desenvolvimento dos circuitos eletrônicos, criação das placas de circuito impresso, prototipagem, testes e desenvolvimento do encapsulamento da fonte regulável.

---

## Sobre o projeto

Fontes de alimentação são utilizadas para fornecer tensão adequada e estável para circuitos eletrônicos. Em aplicações de bancada, uma fonte regulável permite trabalhar com diferentes níveis de tensão durante testes e desenvolvimento de circuitos.

Neste projeto foram desenvolvidas duas fontes em etapas. A primeira foi uma **fonte fixa de 5 V**, utilizada como uma etapa inicial de desenvolvimento. Posteriormente, foi desenvolvida uma **fonte regulável bivolt**, incorporando uma saída fixa de 5 V e uma saída variável.

O desenvolvimento permitiu aplicar conhecimentos relacionados a **retificação, filtragem, regulagem de tensão, dissipação térmica, proteção de componentes, desenvolvimento de PCB e fabricação do encapsulamento**.

---

# Fonte de 5 V

A primeira etapa do projeto consistiu no desenvolvimento de uma fonte com **saída fixa de 5 V**.

O circuito utiliza o **LM7805** como regulador de tensão e foi desenvolvido utilizando o KiCad.

### Principais características

* Saída regulada de **5 V DC**
* Regulador **LM7805**
* Circuito de retificação
* Filtragem da tensão
* Capacitores para estabilização
* PCB própria

### Fluxo simplificado

```text
Entrada AC
    │
    ▼
Transformação
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
Saída 5 V DC
```

Os arquivos referentes à fonte fixa estão disponíveis na pasta:

**[`Fonte_5V_Fixa`](./Fonte_5V_Fixa/)**

Nela estão disponíveis os arquivos de projeto do KiCad e os documentos em PDF referentes ao esquemático e à placa.

---

# Fonte Regulável Bivolt

A segunda etapa consistiu no desenvolvimento de uma **fonte de alimentação regulável e bivolt**.

O projeto foi desenvolvido com o objetivo de possuir uma entrada selecionável entre **110 V e 220 V**, uma saída fixa de 5 V e uma saída variável.

O projeto também incluiu o desenvolvimento da PCB, sistema de ventilação e encapsulamento físico.

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

A relação de componentes do projeto inclui, entre outros, ponte retificadora KBU808, reguladores LM7805, LM7812 e LM317, diodos 1N4004, capacitores de 4700 µF, capacitores de desacoplamento, resistor de 220 Ω e potenciômetro de 10 kΩ.

---

# Funcionamento

O funcionamento da fonte regulável pode ser dividido em algumas etapas principais:

```text
                 ┌──────────────► LM7805 ───► 5 V DC
                 │
Rede AC          │
  │              │
  ▼              │
Seletor          │
110/220 V        │
  │              │
  ▼              │
Transformador    │
12 V / 3 A       │
  │              │
  ▼              │
KBU808            │
Retificação       │
  │              │
  ▼              │
Filtragem         │
4700 µF           │
  │              │
  ├───────────────┼──────► LM7812 ───► 12 V
  │              │
  │              └──────► LM317 ────► Saída variável
  │                                      │
  ▼                                      ▼
Tensão DC filtrada                    11 V ~ 13 V
```

O transformador reduz a tensão da rede, a ponte KBU808 realiza a retificação e os capacitores fazem a filtragem da tensão. Após essa etapa, os reguladores são responsáveis por gerar as saídas previstas no projeto.

---

# Componentes principais

## Fonte regulável

* Transformador bivolt **12 V / 3 A**
* Ponte retificadora **KBU808**
* **LM7805**
* **LM7812**
* **LM317**
* 3 × diodos **1N4004**
* 2 × capacitores eletrolíticos **4700 µF**
* 2 × capacitores **0,33 µF**
* 3 × capacitores **0,1 µF**
* Resistor **220 Ω**
* Potenciômetro **10 kΩ**
* 6 × conectores borne
* Seletor **110/220 V**
* Chave alavanca
* Fusível
* Conector para cabo de alimentação

---

# Desenvolvimento da PCB

A esquemática e o layout da placa foram desenvolvidos utilizando o **KiCad 7.0**.

A PCB possui dimensões de aproximadamente:

**10 × 7,5 cm**

A fabricação da placa foi realizada por meio de **fresagem em placa de fenolite** nas instalações do **INOVFabLab da Universidade Santa Cecília**.

Os arquivos editáveis do KiCad estão disponíveis diretamente neste repositório, permitindo visualizar e modificar o projeto eletrônico.

### Arquivos disponíveis

```text
Fonte_regulavel/
├── fonte_regulavel.kicad_pro
├── fonte_regulavel.kicad_sch
├── fonte_regulavel.kicad_pcb
├── Esquemática Fonte regulavel.pdf
└── Placa da Fonte Regulavel.pdf
```

---

# Desenvolvimento do encapsulamento

O encapsulamento da fonte regulável foi desenvolvido utilizando o **Autodesk Fusion 360**.

A estrutura foi projetada para acomodar a placa eletrônica e os demais componentes da fonte.

A fabricação foi realizada em **MDF utilizando corte a laser**.

### Dimensões

**15 × 11 × 15 cm**

Foi utilizada uma placa de MDF de 1,3 × 0,9 m para a fabricação do gabinete.

O arquivo do encapsulamento está disponível na pasta:

**[`Gabinete`](./Gabinete/)**

---

# Evolução do projeto

O desenvolvimento da fonte regulável ocorreu a partir da experiência obtida durante a primeira etapa do projeto.

Inicialmente, foi planejada a utilização de duas placas. A placa da entrega parcial possuía saídas fixas de **5 V e 12 V**, sendo a saída de 5 V destinada à carga e a saída de 12 V destinada à ventoinha utilizada para auxiliar no resfriamento do regulador.

Durante a prototipagem foram identificados problemas na placa da entrega parcial. Como consequência, foi decidido integrar os componentes em uma única placa.

Também houve uma alteração no circuito da saída variável. O circuito inicialmente planejado foi substituído pelo **LM317**, devido à praticidade de implementação.

---

# Resultado final

Após a montagem e os testes do protótipo, foram obtidas as seguintes saídas:

### Saída fixa

**5 V DC**

### Saída variável

**11 V a 13 V DC**

A saída variável apresentada neste README corresponde ao **resultado final obtido nos testes do protótipo**.

O relatório acadêmico registra, em sua seção de resultados, uma faixa de 1,10 V a 13 V para o protótipo documentado naquele momento. O valor de **11 V a 13 V** apresentado aqui corresponde ao resultado final considerado para este repositório.

---

# Comparação das duas fontes

| Característica |        Fonte 5 V | Fonte Regulável |
| -------------- | ---------------: | --------------: |
| Saída fixa     |              5 V |             5 V |
| Saída variável |              Não |         11–13 V |
| Entrada bivolt | Não especificada |       110/220 V |
| LM7805         |              Sim |             Sim |
| LM7812         |              Não |             Sim |
| LM317          |              Não |             Sim |
| PCB            |              Sim |             Sim |
| Encapsulamento |              Não |             MDF |
| Ventilação     |              Não |             Sim |

---

# Organização do repositório

```text
Fonte-Regulavel-de-1v-a-13v-e-de-5V-main/
│
├── README.md
│
├── Documentação/
│   └── RELATÓRIO FONTE.pdf
│
├── Fonte_5V_Fixa/
│   ├── Esquemática da placa de 5V.pdf
│   ├── Fonte_5v.kicad_pcb
│   ├── Fonte_5v.kicad_pro
│   ├── Fonte_5v.kicad_sch
│   └── Placa de 5V.pdf
│
├── Fonte_regulavel/
│   ├── Esquemática Fonte regulavel.pdf
│   ├── Placa da Fonte Regulavel.pdf
│   ├── fonte_regulavel.kicad_pcb
│   ├── fonte_regulavel.kicad_pro
│   └── fonte_regulavel.kicad_sch
│
└── Gabinete/
    └── Encapsulamento da Fonte regulavel.rld
```

---

# Documentação

O relatório técnico completo do projeto está disponível em formato PDF na pasta **Documentação**.

📄 **[Relatório Técnico](./Documentação/RELATÓRIO%20FONTE.pdf)**

O relatório apresenta:

* Introdução e objetivos;
* Materiais e métodos;
* Desenvolvimento do circuito;
* Desenvolvimento das placas;
* Desenvolvimento do encapsulamento;
* Resultados;
* Conclusão;
* Referências;
* Imagens e registros do projeto.

As **imagens e registros visuais do desenvolvimento e da fonte final estão disponíveis no relatório técnico em PDF**.

Além do relatório, os PDFs de esquemática e layout das placas estão disponíveis nas respectivas pastas dos projetos.

---

# Ferramentas utilizadas

### Projeto eletrônico

* **KiCad 7.0**
* Desenvolvimento de esquemática
* Desenvolvimento de PCB
* Geração dos arquivos de fabricação

### Projeto mecânico

* **Autodesk Fusion 360**
* Modelagem do encapsulamento

### Fabricação

* Fresagem de PCB em placa de fenolite
* Corte a laser de MDF

---

# Objetivos acadêmicos

O projeto teve como objetivo aplicar, de forma prática, conhecimentos adquiridos na disciplina de **Tópicos de Eletrônica**, abrangendo diferentes etapas do desenvolvimento de hardware.

Entre os principais conhecimentos aplicados estão:

* Retificação de tensão;
* Filtragem;
* Regulagem de tensão;
* Utilização de reguladores lineares;
* Dissipação térmica;
* Proteção de componentes;
* Desenvolvimento de PCB;
* Montagem eletrônica;
* Projeto mecânico;
* Fabricação digital;
* Testes e validação de hardware.

O desenvolvimento permitiu compreender na prática as etapas necessárias para transformar um circuito eletrônico em um equipamento físico funcional.

---

# Autores

**Caique Caruso Toscani da Costa**

**Gabriel Kevin Souza Cruz**

**Curso de Engenharia da Computação**
**Universidade Santa Cecília — UNISANTA**

Santos, São Paulo — Brasil
2026

---

# Segurança

> **ATENÇÃO:** este projeto trabalha com tensão de rede elétrica de **110/220 V AC**.

A montagem, manutenção ou reprodução do circuito deve ser realizada com procedimentos adequados de segurança elétrica e por pessoas capacitadas.

Este projeto foi desenvolvido para fins **acadêmicos e educacionais**.
