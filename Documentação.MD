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

```text
             FRENTE
               ↓
        ┌─────────────────┐
        │     SENSOR      │
        │                 │
        │      ESP32      │
        │                 │
 MOTOR  │                 │  MOTOR
  ESQ.  │     BATERIA     │  DIR.
   ●────┤                 ├────●
        └─────────────────┘
             ↑
          200 mm

          Largura: 150 mm
```

**Legenda:**

* ● Motores/rodas
* ESP32: placa controladora
* Bateria: alimentação
* Sensor: sensor frontal
* Chassi: base retangular
* Carenagem: cobertura superior removível
