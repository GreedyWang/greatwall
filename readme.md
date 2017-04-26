#create key
keytool -genkey -alias catserver -keyalg rsa -keysize 1024 -sigalg sha256withrsa -keypass catserver -keystore ~/catserver.keystore -storepass catserverks

#export cer
keytool -export -alias catserver -keystore ~/catserver.keystore -storepass catserverks -file ~/catserver.cer

keytool -import -alias catserver -keystore ~/foxclienttrust.keystore -storepass foxclienttrustks -file ~/catserver.cer


http://blog.csdn.net/fw0124/article/details/41013333