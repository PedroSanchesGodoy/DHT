# DHT
## Codigo: 

#include <Bonezegei_DHT11.h>

#define DHTPIN 4   // Use outro pino, NÃO 34
Bonezegei_DHT11 dht(DHTPIN);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  delay(2000); // 2s já é suficiente

  if (dht.getData()) {
    float umidade = dht.getHumidity();
    float temperatura = dht.getTemperature();

    Serial.print("Umidade: ");
    Serial.print(umidade);
    Serial.print("% Temperatura: ");
    Serial.print(temperatura);
    Serial.println(" °C");
  } else {
    Serial.println("Falha ao ler do sensor DHT!");
  }
}


## Sensor:

<img width="589" height="781" alt="image" src="https://github.com/user-attachments/assets/a442032b-283a-4fe7-ac26-b3a5022a1ca0" />

Sensor DHT!



## FIOS:


![Dht](https://github.com/user-attachments/assets/0f4d4ce9-a766-4fb8-bf3c-71634249778e)

Você conectará o fio laranja (VCC) no 3 volts ou 5 volts.

Você conctará o fio marrom (GND) no ground

Você conectará o fio cinza (SDA) na porta digital.

<img width="578" height="776" alt="image" src="https://github.com/user-attachments/assets/03c06b8b-9c3a-4fa6-90ea-8d2e29d563fd" />
