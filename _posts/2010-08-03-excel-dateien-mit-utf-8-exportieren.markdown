---
layout: post
title:  "CSV-Dateien als UTF-8 mit Excel anzeigen"
date:   2010-08-03 16:13:00
categories: Java
---


CSV-Dateien, die das UTF-8 Encoding verwenden, werden mit Excel mit dem Latin-1 Encoding angezeigt.
Dies kann man durch Verwendung des "byte-order marker (BOM)" ändern. Ist der BOM Charackter gleich dem Charackter 'FEFF', dann wird die Datei als UTF-8 identifiziert.

Hier z.B. ein Beispiel, wie man das mit Java macht: 


```java
OutputStreamWriter writer = new OutputStreamWriter(FileOutputStream(new File("output.csv")), "UTF-8");
writer.write('uFEFF');
```