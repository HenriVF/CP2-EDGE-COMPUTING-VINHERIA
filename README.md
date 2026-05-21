# Monitoramento Ambiental - Vinheria Agnello 1ESPW 🍷

[cite_start]Projeto de sistema embarcado em Arduino para monitoramento climático automatizado do depósito de vinhos da Vinheria Agnello [cite: 6, 36][cite_start], garantindo a qualidade do produto contra variações de luz, temperatura e umidade[cite: 18, 35].

## 🛠️ Componentes e Pinout
* **Arduino UNO**
* [cite_start]**Sensor DHT22 / DHT11** -> Pino Digital `10` [cite: 36, 82]
* **Sensor LDR (Luminosidade)** -> Pino Analógico `A0`
* [cite_start]**Display LCD 16x2 I2C** -> Pinos `A4` (SDA) e `A5` (SCL) [cite: 38, 86]
* [cite_start]**Buzzer Piezoelétrico** -> Pino Digital `4` [cite: 39]
* [cite_start]**LED Verde** (Ambiente OK / Escuro) -> Pino Digital `13` [cite: 42]
* [cite_start]**LED Amarelo** (Alerta / Meia Luz / Temp Fora) -> Pino Digital `12` [cite: 44, 53]
* [cite_start]**LED Vermelho** (Perigo / Muito Claro / Umid Fora) -> Pino Digital `11` [cite: 45, 59]

---

## 📈 Regras de Negócio e Alertas

### 1. Luminosidade (LDR)
* [cite_start]**Escuro (> 700 raw):** LED Verde ligado[cite: 42].
* [cite_start]**Meia Luz (300 a 700 raw):** LED Amarelo ligado + Mensagem `"Ambiente a meia luz"` no LCD[cite: 44].
* [cite_start]**Muito Claro (< 300 raw):** LED Vermelho ligado + Buzzer contínuo + Mensagem `"Ambiente muito CLARO"` no LCD[cite: 45, 46].

### [cite_start]2. Temperatura (Ideal: 10°C a 15°C) [cite: 47]
* [cite_start]**Dentro da faixa:** Mensagem `"Temperatura OK"` + Valor no LCD[cite: 47].
* [cite_start]**Fora da faixa (< 10°C ou > 15°C):** LED Amarelo ligado + Buzzer contínuo + Mensagem `"Temp. ALTA"` ou `"Temp. BAIXA"` no LCD[cite: 53, 54, 55].

### [cite_start]3. Umidade (Ideal: 50% a 70%) [cite: 51]
* [cite_start]**Dentro da faixa:** Mensagem `"Umidade OK"` + Valor no LCD[cite: 51].
* [cite_start]**Fora da faixa (< 50% ou > 70%):** LED Vermelho ligado + Buzzer contínuo + Mensagem `"Umidade. Alta"` ou `"Umidade. Baixa"` no LCD[cite: 59, 61, 62].

---

## 💻 Diferenciais da Implementação
* [cite_start]**Média de 5 Leituras:** Coleta e calcula a média aritmética de 5 amostras antes de atualizar os dados[cite: 52].
* [cite_start]**Tempo Não-Bloqueante (`millis()`):** Atualização precisa e sem travamentos a cada 5 segundos[cite: 52, 85].
* [cite_start]**Display em Carrossel:** Alterna as telas de exibição automaticamente para melhor legibilidade[cite: 38].

---

## 🔗 Links do Projeto
* [cite_start]**Simulador (Wokwi / Tinkercad):** [INSIRA_O_LINK_AQUI] [cite: 80]
* [cite_start]**Vídeo Explicativo (Pitch 3 min):** [INSIRA_O_LINK_AQUI] [cite: 90]

## 👥 Integrantes
* [cite_start]Nome do Aluno 1 - RMXXXXX [cite: 97]
* [cite_start]Nome do Aluno 2 - RMXXXXX [cite: 97]

---
[cite_start]_Copyright © 2026 FIAP - Engenharia de Software_ [cite: 4, 102]