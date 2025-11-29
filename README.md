# 🎹 Arduino Piano Cromático – Projeto Completo

Um projeto educacional e interativo criado para demonstrar princípios de eletrônica, frequências musicais e programação utilizando **Arduino**.  
O objetivo é construir um **piano cromático** capaz de tocar todas as notas de uma oitava (brancas e pretas), usando botões, buzzer piezo e programação simples, aproximando o estudo musical do mundo da robótica.


## 📌 Sobre o Projeto

Este projeto foi desenvolvido para unir **música + eletrônica + programação**, criando um piano totalmente funcional usando Arduino.  
A proposta é:

- Aprender conceitos de **frequência sonora** e notas musicais.
- Desenvolver raciocínio lógico ao programar cada nota.
- Trabalhar fundamentos de **eletrônica básica** como botões, resistores e buzzer.
- Criar um instrumento simples, divertido e totalmente personalizável.
- Servir como base para versões avançadas: teclado MIDI, sensores capacitivos, módulos I2C, OLED, e mais.

O piano toca **todas as notas cromáticas de uma oitava**, incluindo sustenidos e bemóis.


## 🧰 Materiais Necessários

| Imagem | Componente | Quantidade |
|--------|------------|------------|
| <img width="100" src="https://github.com/user-attachments/assets/2e2867a9-2318-4619-b7a4-d91a89dd282f" /> | Arduino UNO/Nano | 1 |
| <img width="100" src="https://github.com/user-attachments/assets/a1bcb816-2e7f-4e19-8970-dfb2a904dd88" /> | Buzzer piezo ativo ou passivo | 1 |
| <img width="100" src="https://github.com/user-attachments/assets/0460f0cc-0561-4de7-8ed1-a212d1a51207" /> | Botões (push buttons) | 13 |
| <img width="100" src="https://github.com/user-attachments/assets/267ae956-910a-4f45-9d07-355ff8036776" /> | Resistores 10kΩ | 13 |
| <img width="100" src="https://github.com/user-attachments/assets/a98a1cc5-b1a7-4ae5-8da6-2e1be5b66f0d" /> | Protoboard | 1 |
| <img width="100" src="https://github.com/user-attachments/assets/f40ed66d-a17b-4fe4-aad3-ce2a3569bb83" /> | Jumpers variados | — |
| <img width="100" src="https://github.com/user-attachments/assets/5766b2df-b40b-405f-a5d4-86bec073722f" /> | Caixa impressa em 3D | Opcional |
| <img width="100" src="https://github.com/user-attachments/assets/588306c8-15cc-449b-bcd1-a0ba01048b71" /> | LEDs para cada tecla | Opcional |

## 🎼 Tabela Completa de Notas – Oitava Completa (Padrão Musical)

| Notação Alfabética | Notação Silábica | Frequência (Hz) |
|--------------------|------------------|-----------------|
| C                  | Dó               | 261.63          |
| C# / D♭            | Dó# / Ré♭        | 277.18          |
| D                  | Ré               | 293.66          |
| D# / E♭            | Ré# / Mi♭        | 311.13          |
| E                  | Mi               | 329.63          |
| F                  | Fá               | 349.23          |
| F# / G♭            | Fá# / Sol♭       | 369.99          |
| G                  | Sol              | 392.00          |
| G# / A♭            | Sol# / Lá♭       | 415.30          |
| A                  | Lá (afinação)    | 440.00          |
| A# / B♭            | Lá# / Si♭        | 466.16          |
| B                  | Si               | 493.88          |
| C5                 | Dó (oitava acima)| 523.25          |


## 🧾 Exemplo de Código em Arduino

```cpp
// Piano Cromático – Exemplo Básico
// Autor: Brendow Rodrigues

#define BUZZER 8

// Frequências das notas (oitava 4)
int notas[] = {
  261, // C
  277, // C#
  293, // D
  311, // D#
  329, // E
  349, // F
  369, // F#
  392, // G
  415, // G#
  440, // A
  466, // A#
  493, // B
  523  // C5
};

// Botões conectados ao Arduino
int botoes[] = {2,3,4,5,6,7,9,10,11,12,13,A0,A1};

void setup() {
  pinMode(BUZZER, OUTPUT);

  for (int i = 0; i < 13; i++) {
    pinMode(botoes[i], INPUT_PULLUP);
  }
}

void loop() {
  for (int i = 0; i < 13; i++) {
    if (!digitalRead(botoes[i])) { // Aperto = LOW
      tone(BUZZER, notas[i]);
    }
  }
  noTone(BUZZER);
}
```

---
### **© Brendow Rodrigues**
Web Programador Front-End, técnico em formação e entusiasta de tecnologia, automação e IA. <br>
*🦾 Desenvolvido com 💙, café e Arduino.*


