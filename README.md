# DevOps-Server
Configurar un equipo para desarrollo de software 
Ubuntu 18.04
Luego de instalar Ubuntu ejecutar el siguiente comando:

$ sudo apt-get update

Git
Instalar Git:

$ sudo apt-get install git
Configurar usuario global:

$ git config --global user.name "Mi nombre"
$ git config --global user.email "mi@correo.com"
Listar configuración:

$ git config -l
Generar llave ssh:
$ ssh-keygen -t rsa -C "your_email@example.com"

NPM
$ sudo apt-get install npm
$ npm -v
3.5.2
$ node -v
8.10.0

n
$ sudo npm install -g n
$ sudo n 8.10.0
$ node -v
v8.10.0


Angular CLI
$ sudo npm install -g @angular/cli@1.5.0
$ sudo npm install @angular-devkit/core -g
$ ng --version
Angular CLI: 1.5.0


Google Chrome
Descargar para Ubuntu 64 bit:

$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

Instalar:

$ sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
En caso que "dpkg" indique que faltan dependencias, completa la instalación ejecutando el siguiente comando:

$ sudo apt-get install -f 


Visual Studio Code
Instalar desde "Ubuntu Software".


Postman
$ wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
$ sudo tar -xzf postman.tar.gz -C /opt
$ rm postman.tar.gz
$ sudo ln -s /opt/Postman/Postman /usr/bin/postman
$ sudo apt-get install libgconf-2-4


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
                                                        

                                                       
Docker
$ sudo apt install docker.io
$ docker --version
Para iniciar docker manualmente:

$ sudo systemctl start docker
                                                        
                                                        
JDK
Default JDK
$ sudo apt-get install default-jdk

JDK 11
$ sudo apt install openjdk-11-jdk
                                                        
JDK 9
$ sudo apt install openjdk-9-jdk
                                                        
                                                       
JDK 8
$ sudo apt install openjdk-8-jdk
                                                        
update-alternatives (Gestor de versiones java)
$ sudo update-alternatives --config java
                                                        
set JAVA_HOME
export JAVA_HOME=/usr/lib/jvm/{jdk_install_dir}
export PATH=$JAVA_HOME/bin:$PATH
                                                        
Ejemplo, JDK 8:
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
        
                                                        
Maven
Descargar y descomprimir:

Maven https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.3.9/apache-maven-3.3.9-bin.zip

Descomprimir carpeta y mover a /opt

$ cd /opt
$ sudo mv /home/andres/Downloads/apache-maven-3.3.9 .
Añadir la siguiente línea al final del archivo /.profile

export PATH=/opt/apache-maven-3.3.9/bin:$PATH
Guardar archivo e ingresar el siguiente comando:

source ~/.profile
Cerrar las terminales abiertas y abrir una terminal

Para comprobar la instalación:

mvn -v              
             
                                                        

                                                        
                                                        
                                 
                                                        
                                                        
                                                        
                                                        
                                                        
                                                        




