#config SSL for HADOOP
#create keystore.jks 
keytool -keystore keystore.jks -genkey -alias client
#export major certificate CA
keytool -exportcert -keystore keystore.jks -alias client -storepass password -file node.cer
#create truststore.jks
keytool -importcert -keystore truststore.jks -alias node1 -storepass password -file node.cer
