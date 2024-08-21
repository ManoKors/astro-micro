---
title: Apache PDFBox in Java installieren
description: 
draft: false
tags:
  - Java
  - PDF
---


Wenn du IntelliJ IDEA verwendest, kannst du das Java-Projekt mit der **Apache PDFBox**-Bibliothek einfach einrichten. Hier ist eine Schritt-für-Schritt-Anleitung, wie du das Projekt in IntelliJ IDEA einrichtest und das Beispielprogramm ausführst.
## 1. Erstelle ein neues Projekt in  IntelliJ IDEA!

![[screenshot1.png]]

## 2. Update von pom.xml via Maven
Bei der erstellung eines neuen Projekts in IntelliJ IDEA sieht die `pom.xml`-Datei wie folgt aus:

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<project xmlns="http://maven.apache.org/POM/4.0.0"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">  
    <modelVersion>4.0.0</modelVersion>
  
    <groupId>org.example</groupId>  
    <artifactId>wertpapierleser</artifactId>  
    <version>1.0-SNAPSHOT</version>  
  
    <properties>        
	    <maven.compiler.source>22</maven.compiler.source>  
        <maven.compiler.target>22</maven.compiler.target>  
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
    </properties>
    
</project>
```

### 2.1. Maven-Integration hinzufügen

Um die PDFBox-Bibliothek zum Projekt hinzuzufügen, kannst du Maven verwenden, das eine einfache Verwaltung von Abhängigkeiten ermöglicht. 

1. Öffne die `pom.xml`-Datei deines Projekts
2. Füge die folgende Abhängigkeit zur `pom.xml`-Datei hinzu:
```xml
<dependencies>
    <dependency>
        <groupId>org.apache.pdfbox</groupId>
        <artifactId>pdfbox</artifactId>
        <version>2.0.29</version>
    </dependency>
</dependencies>
```
3. IntelliJ IDEA lädt die Abhängigkeit automatisch herunter, wenn du die `pom.xml`-Datei speicherst.

### 2.2. Neue Java-Klasse erstellen
1. **Erstelle eine neue Java-Klasse**: Rechtsklick auf den `src`-Ordner > "New" > "Java Class". Nenne die Klasse z.B. `Wertpapierabrechnung`.
2. Kopiere den Beispielcode aus der vorherigen Antwort in diese Klasse.