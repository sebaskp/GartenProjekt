# GartenProjekt

Eine kleine 3D-Gartenszene mit A-Frame.

## Starten

Die Szene braucht einen lokalen Webserver, damit die JSON-Datei geladen werden kann.

```powershell
cd "Garten 2"
node -e "const http=require('http'),fs=require('fs'),path=require('path');http.createServer((req,res)=>{const file=path.join(process.cwd(),decodeURIComponent(new URL(req.url,'http://localhost').pathname));fs.readFile(file,(err,data)=>{if(err){res.writeHead(404);res.end('Nicht gefunden');return;}res.end(data);});}).listen(8000,()=>console.log('http://localhost:8000/GartenProjekt.html'));"
```

Danach im Browser öffnen:

http://localhost:8000/GartenProjekt.html

## Wettersteuerung

Die Datei `testdaten_stress_ruhe.json` wird automatisch geladen und abgespielt.

- Stress ab `10`: Gewitter
- Stress bis `6`: sonniges Wetter
- Dazwischen bleibt das aktuelle Wetter bestehen

## Dateien

- `GartenProjekt.html`: 3D-Szene und Wetterlogik
- `testdaten_stress_ruhe.json`: Testwerte für den Stress
- `README.md`: diese Anleitung