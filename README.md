# kafka-connect-datagen

```bash
confluent destroy
mvn clean compile package
confluent-hub install --no-prompt target/components/packages/confluentinc-kafka-connect-datagen-5.0.0.zip
confluent start connect
sleep 10
confluent config datagen -d ./connector_datagen.config
sleep 5
confluent status connectors
confluent consume test1 --value-format avro --max-messages 5 --property print.key=true --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer

```
