# Ubuntu 18.04

Luego de instalar Ubuntu ejecutar el siguiente comando:

```sh
$ sudo apt-get update
```

## Terminator

```sh
$ sudo apt-get install terminator
```

## Vim

```sh
$ sudo apt-get install vim
```

## Git

Instalar Git:

```sh
$ sudo apt-get install git
```

Configurar usuario global:

```sh
$ git config --global user.name "Mi nombre"
$ git config --global user.email "mi@correo.com"
```

Listar configuración:

```sh
$ git config -l
```

Generar llave ssh:

```sh
$ ssh-keygen -t rsa -C "your_email@example.com"
```

## NPM

```sh
$ sudo apt-get install npm
```

```sh
$ npm -v
3.5.2
```

```sh
$ node -v
8.10.0
```

## n

```sh
$ sudo npm install -g n
$ sudo n 8.10.0
```

```sh
$ node -v
v8.10.0
```

## Angular CLI

```sh
$ sudo npm install -g @angular/cli@1.5.0
$ sudo npm install @angular-devkit/core -g
```

```sh
$ ng --version
Angular CLI: 1.5.0
```

## Google Chrome

Descargar para Ubuntu 32 bit:

```sh
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_i386.deb
```

Instalar:

```sh
$ sudo dpkg -i --force-depends google-chrome-stable_current_i386.deb
```

Descargar para Ubuntu 64 bit:

```sh
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

Instalar:

```sh
$ sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
```

En caso que "dpkg" indique que faltan dependencias, completa la instalación ejecutando el siguiente comando:

```sh
$ sudo apt-get install -f 
```

## Visual Studio Code

Instalar desde "Ubuntu Software".


## Sublime

Instalar desde "Ubuntu Software".

## Atom

Instalar desde "Ubuntu Software".

## Slack

Instalar desde "Ubuntu Software".

## Postman

```sh
$ wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
$ sudo tar -xzf postman.tar.gz -C /opt
$ rm postman.tar.gz
$ sudo ln -s /opt/Postman/Postman /usr/bin/postman
$ sudo apt-get install libgconf-2-4
```

```sh
cat > ~/.local/share/applications/postman.desktop <<EOL
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
EOL
```

## Docker

```sh
$ sudo apt install docker.io
```

```sh
$ docker --version
```

Para iniciar docker manualmente:

```sh
$ sudo systemctl start docker
```

## JRE

```sh
$ sudo apt install default-jre
```

## JDK

Default JDK

```sh
$ sudo apt-get install default-jdk
```

JDK 11

```sh
$ sudo apt install openjdk-11-jdk
```

JDK 9

```sh
$ sudo apt install openjdk-9-jdk
```

JDK 8

```sh
$ sudo apt install openjdk-8-jdk
```

update-alternatives (Gestor de versiones java)

```sh
$ sudo update-alternatives --config java
```

set JAVA_HOME

```sh
export JAVA_HOME=/usr/lib/jvm/{jdk_install_dir}
export PATH=$JAVA_HOME/bin:$PATH
```

Ejemplo, JDK 8:

```sh
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

## Soap UI Open Source

[Link de Descarga](https://www.soapui.org/downloads/soapui.html)

Al archivo descargado dar permiso 777 y ejecutar:

```sh
$ sudo chmod 777 {nombreArchivo}
$ ./{nombreArchivo}
```

## jMeter

Descargar y descomprimir:

[jMeter](http://www-eu.apache.org/dist//jmeter/binaries/apache-jmeter-4.0.zip)

Mover la carpeta de jmeter a /opt

Añadir la siguiente línea al final del archivo /.profile

```sh
PATH=/opt/apache-jmeter-4.0/bin:$PATH
export PATH
```

Guardar archivo e ingresar el siguiente comando:

```sh
source ~/.profile
```

Cerrar las terminales abiertas y abrir una terminal

Escribir en la terminal:

```sh
jmeter
```

## Instalar plugin manager de jMeter

[Plugin Manager](https://jmeter-plugins.org/downloads/all/)

Copiar dentro de la carpeta $jmeterpath/lib/ext/


## Maven

Descargar y descomprimir:

[Maven](https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.3.9/apache-maven-3.3.9-bin.zip)

Descomprimir carpeta y mover a /opt

```sh
$ cd /opt
$ sudo mv /home/andres/Downloads/apache-maven-3.3.9 .
```

Añadir la siguiente línea al final del archivo /.profile

```sh
export PATH=/opt/apache-maven-3.3.9/bin:$PATH
```

Guardar archivo e ingresar el siguiente comando:

```sh
source ~/.profile
```

Cerrar las terminales abiertas y abrir una terminal

Para comprobar la instalación:

```sh
mvn -v
```

## Instalar Jenkins

**Antes de instalar Jenkins es necesario tener instalado Java 7 o Java 8.**

Ingresar el siguiente comando:

```sh
$ wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```

Editar el archivo sources.list 

```sh
$ sudo vim /etc/apt/sources.list
```

y agregar al final del archivo: 

```sh
$ deb https://pkg.jenkins.io/debian-stable binary/
```

Finalmente ingresamos los siguientes comandos:

```sh
$ sudo apt-get update
$ sudo apt-get install jenkins
```

[Fuente](https://pkg.jenkins.io/debian-stable/)

Una vez finalizada la instalación podemos ingresar a desde el navegador en la dirección localhost:8080. Jenkins se ejecuta por defecto en el puerto 8080.

Por seguridad debemos desbloquear Jenkins ingresando la contraseña del administrador. Para esto debemos ver el contenido del archivo que contiene la contraseña, este archivo se encuentra en el path de color rojo que aparece en la página. Debemos copiar este path y pegarlo en la terminal para abrir el archivo con algún editor, es necesario tener usuario root.

```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Luego copiamos y pegamos la contraseña en el textbox "Administrator password".

Click en continuar. Jenkins nos sugiere que instalemos plugins, omitiremos este paso pinchando la "x", finalmente click en "Start using Jenkins". 

Ahora vamos a cambiar la contraseña del administrador, para esto haz click en "admin" --> Configure --> Y en la sección de password, ingresar la nueva contraseña, confirmar contraseña y click en el botón "Save". Con este cambio podrás iniciar sesión con el usuario "admin" y tú nueva contraseña.


## Solución a errores

### Solución al error del rdkafka en el bff: Failed at the node-rdkafka@2.1.0 install script 'node-gyp rebuild'.

```sh
$ sudo apt-get install libsasl2-dev
$ sudo apt install librdkafka-dev
```

### Solución al error del jMeter Plugins Manager "Caused by: java.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty"

1. Editar el archivo /etc/java-11-openjdk/security/java.security. Encontrar la línea que dice keystore.type = pkcs12 y cambiar su valor a jks

2. Eliminar el archivo del certificado:

```sh
$ sudo rm /etc/ssl/certs/java/cacerts
```

3. Ejecutar el comando:

```sh
$ sudo update-ca-certificates -f
```

### Instalación del proyecto microservicio cuentas. Error krb5.h

```sh
$ rm -Rf node_modules
$ sudo apt-get install libkrb5-dev
$ npm install
```
