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
