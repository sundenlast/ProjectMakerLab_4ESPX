# Documentação — Carrinho Robô

## 1. Ficha de requisitos

| Item                  | Especificação                                    |
| --------------------- | ------------------------------------------------ |
| Dimensões             | 200 × 150 mm                                     |
| Quantidade de motores | 2 motores DC                                     |
| Placa controladora    | ESP32                                            |
| Posição dos motores   | Um em cada lateral do chassi                     |
| Posição do ESP32      | Centro do chassi                                 |
| Posição da bateria    | Parte traseira                                   |
| Posição do sensor     | Parte frontal                                    |
| Carenagem             | Cobertura removível para proteger os componentes |

## 2. Croqui do chassi

### Vista superior

```                       VISTA SUPERIOR
                              FRENTE
                                ↓

             ┌─────────────────────────────────┐
             │                                 │
             │       ┌───────────────┐         │ 200mm comprimento
             │       │    SENSOR     │         │
             │       └───────────────┘         │
             │                                 │
 MOTOR ESQ.  │       ┌───────────────┐         │  MOTOR DIR.
     ●───────┤       │     ESP 32    │         ├───────●
             │       │               │         │
             │       └───────────────┘         │
             │                                 │
             │       ┌───────────────┐         │
             │       │    BATERIA    │         │
             │       │  2 PILHAS     │         │
             │       │  + SUPORTE    │         │
             │       └───────────────┘         │
             │                                 │
             └─────────────────────────────────┘
             ←──────────── 150 mm ─────────────→

```

**Legenda:**

* ● Motores/rodas
* ESP32: placa controladora
* Bateria: alimentação
* Sensor: sensor frontal
* Chassi: base retangular
* Carenagem: cobertura superior removível

## 3. Diagrama de Alimentação

                       +----------------+
                       |  2 PILHAS      |
                       |  EM SUPORTE    |
                       +-------+--------+
                               |
                               | +
                               ▼
                         +-----------+
                         |   CHAVE   |
                         | ON / OFF  |
                         +-----+-----+
                               |
                               +----------------------+
                               |                      |
                               ▼                      ▼
                      +----------------+       +---------------+
                      | DRIVER MOTOR   |       | REGULADOR     |
                      |                |       | DE TENSÃO     |
                      +-------+--------+       +-------+-------+
                              |                        |
                    +---------+---------+              |
                    |                   |              |
                    ▼                   ▼              ▼
              +-----------+       +-----------+    +-------+
              | MOTOR ESQ. |       | MOTOR DIR.|    | ESP32 |
              +-----------+       +-----------+    +---+---+
                                                     |
                                  +------------------+----------------+
                                  |                                   |
                                  ▼                                   ▼
                              [SENSOR]                          [CONTROLE DRIVER]
                                  +------------------+----------------+
                                                     |
                                                     ▼
                                              Comunicação serial
                                                 (TX / RX)

