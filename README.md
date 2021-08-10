<Teclado-Gestual

 Teclado para PC utilizando sensor de Gestos

 Neste projeto utilizei Arduino Due, sensor de Cores e Gestos APDS9930 e o Sensor Ultrassonico HC-SR04.

 Para programar o Due, é importante lembrar que a porta ligada ao PC deve ser a USB PROGRAMMING, e para uso após tudo estar como desejado pode conectar apenas a USB NATIVE para que o mesmo funcione como um teclado.

 **Funções de Cada Sensor**
 *HC-SR04.*
- Medição da distância no qual o usuário se encontra
- Limitar a leitura do sensor de gestos
 *APDS-9930.*
 - Captar o sentido de movimentação da mão
 - Converter o gesto captado em uma teclado (Pode escolher qualquer uma, as do programa são apenas exemplos)

 **Diagrama de Ligação**
 *HC-SR04.*
 - VCC: 5V do Arduino DUE
 - Trig: Pino 6 do Arduino DUE
 - Echo: Pino 7 do Arduino DUE
 - GND: GND do Arduino DUE

 *APDS-9930.*
 - GND: GND do Arduino DUE
 - VCC: 5V do Arduino DUE
 - SDA: Pino 20 - SDA do Arduino DUE
 - SCL: Pino 21 - SCL do Arduino DUE