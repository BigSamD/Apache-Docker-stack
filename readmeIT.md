
# Docker Compose per un'Applicazione Web

Questo file docker-compose.yml definisce due servizi, web e node, per creare una semplice applicazione web.

## Servizi

### web

Questo servizio utilizza l'immagine nginx:alpine ed espone la porta 80. Monta la directory host ./ su /usr/share/nginx/html per servire file statici.

### node

Questo servizio utilizza l'immagine node:alpine e monta la directory host ./ su /app. Imposta la directory di lavoro su /app ed esegue `npm install` per installare le dipendenze.

I due servizi lavorano insieme per eseguire un'applicazione Node.js. Il servizio web gestisce le richieste HTTP e serve i file statici, mentre il servizio node esegue l'applicazione vera e propria.

## Utilizzo

Per avviare i container, esegui:

```
docker-compose up
```

Questo scaricherà le immagini se necessario, costruirà i container e avvierà i servizi in base al file docker-compose.yml.

L'applicazione sarà accessibile su http://localhost quando i container sono in esecuzione.

Le modifiche al codice effettuate sull'host dovrebbero essere immediatamente riflesse nei container.

Per fermare i servizi, esegui:

```
docker-compose down
```

Questo comando ferma e rimuove i container.
