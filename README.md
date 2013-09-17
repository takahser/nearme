nearme
=====
Hinweis: Für die korrekte Darstellung der Settings, bitte im Text-Mode anschauen.

ZHAW - Methoden der Programmierung - Fallstudie "nearme"

Initialer Setup
----------------
1. Smartphone-WebApp
mvn archetype:generate \
  -DarchetypeArtifactId=android-quickstart \
  -DarchetypeGroupId=de.akquinet.android.archetypes \
  -DarchetypeVersion=1.0.11 \
  -DgroupId=ch.zhaw.mdp.lhb.citr \
  -DartifactId=citr-app
2. Java-Server
http://persistentdesigns.com/wp/jersey-spring-and-jpa/

Voraussetzungen
----------------
- Maven 
- Java Eclipse
- Tomcat-Server  (V. 7, auf Standard-Port 8080)
- MySQL-Server
- GPS-fähiges Smartphone

Lokaler-Setup
----------------
1. Repository clone erzeugen.
2. Variable 'SLF4J' definieren (SDK).
3. IDE-Spezifische stubs generieren und Projekt importieren.
    Eclipse: http://edu.panter.ch/MavenEclipse
    Intelij: http://maven.apache.org/plugins/maven-idea-plugin/usage.html
4. Tomcat: tomcat-users.xml (hinzufügen):
   <role rolename="manager-script"/>
   <user username="USERNAME" password="Pa$$w0rd" roles="manager-script"/>
5. Maven: settings.xml (hinzufügen):
    <servers>
     <server>
      <id>tomcat-local</id>
      <username>USERNAME</username>
      <password>Pa$$w0rd</password>
    </server>  
  </servers>

Build & Installation (Server)
----------------
1. Tomcat-Server & MySQL starten
2. mvn tomcat7:deploy

Tests:
----------------
- Im Maven-Test-Package sollten nur Tests implementiert werden, welche nicht auf SLF4J zugreifen.
- Bei Ausführung von Maven Tests wird ein GPS-fähiges Gerät benötigt (e.g. Notebook mit WiFi)



