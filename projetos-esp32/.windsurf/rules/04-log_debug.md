---
trigger: model_decision
description: Aplicar quando estiver lidando com saidas de Logs, padronizando o logger do sistema, não importa a linguagem.
---
## **Depuração e Log**

A depuração é uma parte essencial do desenvolvimento de sistemas embarcados e aplicações em Node.js. Todas as mensagens de log devem ser **claras, informativas, didáticas e agrupadas por contexto**, de forma a facilitar o diagnóstico e o rastreamento de eventos em tempo real.

---

### **Padrões Gerais de Saída**

* As mensagens de log devem seguir o formato do esp32 composto pela TAG que representa o setor, tema, classe ou contexto:

  ```
  [setor/tema] Mensagem informativa
  ```

  **Exemplo:**

  ```
  [auth/login] ✅ Token JWT gerado com sucesso.
  [db/connection] ⚙️ Reconnecting to MySQL...
  [sensor/adc] 📊 Sampling rate: 10kHz, mean value: 512
  ```
* Utilize **emoticons** para destacar estados e eventos importantes:

  * ✅ Sucesso
  * ⚠️ Alerta
  * ❌ Erro
  * 🧠 Informação técnica
  * 📊 Estatísticas ou medições
* Sempre exponha **estatísticas relevantes** do sistema, como:

  * Tempo de execução (ms)
  * Consumo de memória ou CPU
  * Número de requisições atendidas
  * Pacotes processados ou bytes transmitidos

---

### **Firmware e Sistemas Embarcados**

Nos sistemas embarcados, os logs devem ser enviados pela **serial UART**, mantendo formatação semelhante aos padrões gerais:

```
[sensor/temp] 📈 Temperature: 36.4°C
[wifi/status] 🌐 Connected to SSID: LabNet
[task/adc_dma] ⚙️ DMA Buffer Overrun Detected
```

* Utilize **macros padronizadas** (`LOG_INFO`, `LOG_WARN`, `LOG_ERROR`) para consistência.
* Em ambientes com **RTOS** (ex.: FreeRTOS), utilize **mecanismos task-safe** (mutexes, buffers circulares) para evitar interferência entre tarefas.

---

### **Boas Práticas de Depuração**

* Mantenha mensagens de log **sintéticas e úteis**, evitando ruído excessivo.
* Diferencie logs temporários de depuração (`debug`) dos logs permanentes de operação (`info`, `warn`, `error`).
* Nas fases de produção, reduza a verbosidade e direcione os logs a sistemas de coleta ou armazenamento persistente.
