# FB API
In diesem Repository werden die Beschreibung der API zur HS Finanzbuchhaltung (YAML-Datei) und der Changelog veröffentlicht.

# Elements UI API
Die Schnittstellenbeschreibung kann auch in der Elements UI API direkt als GitHub-Page angezeigt werden unter folgender URL:
https://hamburger-software.github.io/fb-api/

# Code-Generierung
Für die Code-Generierung aus der YAML-Datei kann z.B. der OpenApi Generator verwendet werden (https://openapi-generator.tech/docs/usage/).
Es werden diverse Programmiersprachen unterstützt. 

Die Code-Generierung kann mit dem Kommandozeilen-Tool "openapi-generator-cli" erfolgen. Für C#-Client-Code kann das z.B. so aussehen:
```bat
java -jar openapi-generator-cli-7.12.0.jar generate -i FB-API.yaml -g csharp --generate-alias-as-model --model-name-suffix Model -c config.json --http-user-agent MySolution -o C:\TEMP\Hs.Fb.RestApi
```

Sinnvoll ist die Verwendung eines eigenen Namespaces. Dieser kann über eine Config-Datei (z.B. config.json) angegeben werden, z.B.:
### config.json
```json
{
  "packageName": "Hs.Fb.RestApi.Generated",
  "targetFramework": "net48"
}
```

Außerdem sollte der HTTP-User-Agent gesetzt werden. Das ist über die Kommandozeile möglich: 
```bat
--http-user-agent MySolution
```

# Weitere Informationen
Weitere Informationen für Lösungsersteller gibt es
- in der Hilfe der Finanzbuchhaltung im Kapitel "Anleitung & Wissen / Datenaustausch / API (Webservice) / Anwendungswissen"
- in der Datei "fb_api_webservice.pdf" im Unterverzeichnis "Hilfe_Pdfs" des Programmverzeichnisses der installierten Finanzbuchhaltung (z.B. C:\Program Files (x86)\Hs\Fb) 
