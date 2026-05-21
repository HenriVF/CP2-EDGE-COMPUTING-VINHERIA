# Monitoramento Ambiental - Vinheria Agnello 🍷

Projeto de sistema embarcado em Arduino para monitoramento climático automatizado do depósito de vinhos da Vinheria Agnello, garantindo a qualidade do produto contra variações de luz, temperatura e umidade.

## 🛠️ Componentes e Pinout
* **Arduino UNO**
* **Sensor DHT22 / DHT11** -> Pino Digital `10`
* **Sensor LDR (Luminosidade)** -> Pino Analógico `A0`
* **Display LCD 16x2 I2C** -> Pinos `A4` (SDA) e `A5` (SCL)
* **Buzzer Piezoelétrico** -> Pino Digital `4`
* **LED Verde** (Ambiente OK / Escuro) -> Pino Digital `13`
* **LED Amarelo** (Alerta / Meia Luz / Temp Fora) -> Pino Digital `12`
* **LED Vermelho** (Perigo / Muito Claro / Umid Fora) -> Pino Digital `11`

---

## 📈 Regras de Negócio e Alertas

### 1. Luminosidade (LDR)
* **Escuro (> 700 raw):** LED Verde ligado.
* **Meia Luz (300 a 700 raw):** LED Amarelo ligado + Mensagem `"Ambiente a meia luz"` no LCD.
* **Muito Claro (< 300 raw):** LED Vermelho ligado + Buzzer contínuo + Mensagem `"Ambiente muito CLARO"` no LCD.

### 2. Temperatura (Ideal: 10°C a 15°C)
* **Dentro da faixa:** Mensagem `"Temperatura OK"` + Valor no LCD.
* **Fora da faixa (< 10°C ou > 15°C):** LED Amarelo ligado + Buzzer contínuo + Mensagem `"Temp. ALTA"` ou `"Temp. BAIXA"` no LCD.

### 3. Umidade (Ideal: 50% a 70%)
* **Dentro da faixa:** Mensagem `"Umidade OK"` + Valor no LCD.
* **Fora da faixa (< 50% ou > 70%):** LED Vermelho ligado + Buzzer contínuo + Mensagem `"Umidade. Alta"` ou `"Umidade. Baixa"` no LCD.

---

## 💻 Diferenciais da Implementation
* **Média de 5 Leituras:** Coleta e calcula a média aritmética de 5 amostras antes de atualizar os dados.
* **Tempo Não-Bloqueante (`millis()`):** Atualização precisa e sem travamentos a cada 5 segundos.
* **Display em Carrossel:** Alterna as telas de exibição automaticamente para melhor legibilidade.

---

## 🔗 Links do Projeto
* **Simulador (Wokwi / Tinkercad):** https://wokwi.com/projects/464585768497339393
* **Simulação em Video:** https://youtu.be/3f_ntoK0khY
* **Vídeo Explicativo (Pitch 3 min):** https://youtu.be/D9PvItUKeuA

## 👥 Integrantes
* Henrique Vieira Ferreira  - RM569586
* Leonardo Gracioli Barrocal - RM571031


