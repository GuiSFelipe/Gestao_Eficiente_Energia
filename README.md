Informações relevantes:

Arduino uno: Placa para conectar ao sensor PIR.
Detecção de Presença: Utiliza o sensor PIR para identificar a presença de pessoas em um ambiente.
Controle Automático: Ativa ou desativa dispositivos (como luzes) com base nos dados do sensor.
Comunicação MQTT: Envia e recebe mensagens em tempo real, permitindo o controle remoto dos dispositivos.
Monitoramento Local: Integra o ESP32 com um broker MQTT local (por exemplo, Mosquitto) para análise dos eventos.

Como Usar
1. Configurar o Ambiente
Instale a Arduino IDE.
Adicione o suporte ao ESP32 no gerenciador de placas da IDE.
Instale a biblioteca PubSubClient para integração MQTT.
Configurar o Hardware com Arduino Uno, ESP32, Protoboard e Sensor PIR
Conexão do Sensor PIR ao Arduino Uno:

2. Como montar
VCC → 5V no Arduino Uno
GND → GND no Arduino Uno
OUT → Pino digital 7 no Arduino Uno
O Arduino processará os dados recebidos do sensor PIR e enviará comandos ao ESP32.
Conexão do ESP32 ao Protoboard e ao Arduino Uno:

Conecte o pino TX do Arduino Uno ao pino RX do ESP32 (e vice-versa para RX e TX).
Compartilhe um GND comum entre o Arduino Uno, ESP32 e os dispositivos no protoboard.
A comunicação entre o Arduino e o ESP32 será feita via Serial para enviar informações sobre o estado do sensor PIR.
Conexão do LED ao ESP32 no Protoboard:

Pino positivo do LED → Pino 3 no ESP32.
Resistor conectado em série entre o LED e o pino para limitar a corrente.
Pino negativo do LED → GND no ESP32 (via protoboard).

O sensor PIR detecta movimento e envia um sinal ao Arduino Uno.
O Arduino processa o sinal e envia uma mensagem ao ESP32 via Serial.
O ESP32 publica o estado no broker MQTT e aciona o LED conforme o movimento detectado.
3. Configurar o Código
Atualize as credenciais Wi-Fi no código (ssid e password).
Configure o endereço do broker MQTT (mqttServer) para o IP do broker local.
Faça o upload do código para o ESP32.
4. Testar o Sistema
Use o MQTT Explorer para monitorar mensagens publicadas no tópico configurado.
Acione o sensor PIR e verifique o comportamento do LED ou dos dispositivos conectados.
