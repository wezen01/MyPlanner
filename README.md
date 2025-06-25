# MyPlanner

MyPlanner è una piattaforma full-stack per la gestione e l'analisi delle finanze personali. Offre un'interfaccia moderna e funzionalità avanzate per monitorare entrate, uscite, risparmi e tendenze finanziarie nel tempo.

## Progetti inclusi

- **MyPlanner (Backend)**  
  API RESTful sviluppata in .NET con autenticazione JWT, Entity Framework Core e SQL Server.
  
- **myplanner-frontend (Frontend)**  
  Applicazione React, con grafici interattivi, dashboard e gestione delle transazioni.

## Funzionalità principali

- Autenticazione sicura con JWT, gestione automatica della sessione.
- Dashboard interattiva con riepilogo di bilancio, entrate e uscite.
- Gestione delle transazioni: aggiunta, filtro, modifica e cancellazione.
- Storico mensile con riepiloghi per mese e anno.
- Visualizzazione grafica dei dati finanziari.
- Sezione "salvadanaio" per la gestione dei risparmi.
- Logout automatico dopo un'ora di inattività.

## Tecnologie utilizzate

### Backend (.NET)

- Linguaggio: C#
- Framework: ASP.NET Core Web API
- Database: SQL Server (gestito tramite SSMS)
- ORM: Entity Framework Core
- Autenticazione: Token Bearer JWT

### Frontend (React)

- Libreria: React (JavaScript)
- Tecnologie: HTML5, CSS3
- Grafici: Chart.js tramite react-chartjs-2
- Altri strumenti: Axios, React Router

## Avvio rapido

### 1. Backend (.NET)

- Aprire la solution `MyPlanner.sln` in Visual Studio.
- Configurare la stringa di connessione e i parametri JWT nel file `appsettings.json`.
- Avviare il backend in modalità HTTPS tramite terminale:

```bash
dotnet run --launch-profile "https"
```

### 2. Frontend (React)

```bash
cd myplanner-frontend
npm install
npm start
```

L'applicazione sarà disponibile all'indirizzo: [http://localhost:3000](http://localhost:3000)

Verificare che il backend sia attivo su HTTPS e accessibile. In caso contrario, configurare il proxy nel frontend.

## Struttura del progetto

```
/MyPlanner/               - Root del progetto
├── MyPlanner/            - Backend (.NET API)
│   ├── Controllers/
│   ├── Models/
│   └── ...
├── myplanner-frontend/   - Frontend (React)
│   ├── src/
│   ├── components/
│   └── ...
├── MyPlanner.sln         - Solution file (.NET)
└── .gitignore
```

## Note tecniche

- Autenticazione  
  Il backend emette un token JWT valido per un'ora. Il frontend rileva la scadenza e forza il logout automatico.

- API  
  Le richieste al backend richiedono il token JWT nell'header `Authorization`:

  ```
  Authorization: Bearer <token>
  ```

- Database  
  L'applicazione utilizza SQL Server tramite Entity Framework Core. La stringa di connessione è configurabile nel file `appsettings.json`.

- Grafici  
  La visualizzazione grafica dei dati finanziari è implementata con react-chartjs-2 (wrapper React per Chart.js).

## Supporto

- Verificare che backend e frontend siano avviati correttamente.
- Accertarsi che il backend sia raggiungibile via HTTPS e che le porte siano corrette.
- Controllare la console del browser e i log di Visual Studio per eventuali errori.
- In caso di problemi di autenticazione, eliminare il token JWT salvato localmente e ripetere il login.
