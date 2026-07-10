# agenda-cron

Taktgeber für die Terminerinnerungen der **Agenda**-Terminkalender-App.

Der Workflow [`tick.yml`](.github/workflows/tick.yml) ruft alle 5 Minuten den
Erinnerungs-Endpoint der App auf (`/api/tick`). Der Server prüft dann, ob in
Kürze Termine anstehen, und verschickt Push-Mitteilungen aufs Handy.

- Der Endpoint ist durch ein Secret geschützt (`CRON_SECRET`, hinterlegt als
  Actions-Secret — hier im Repo liegt nichts Geheimes).
- [`keepalive.yml`](.github/workflows/keepalive.yml) pusht einmal im Monat einen
  leeren Commit, damit GitHub die Scheduled-Workflows nicht nach 60 Tagen
  Inaktivität deaktiviert.

Dieses Repo ist öffentlich, weil GitHub Actions in öffentlichen Repos
kostenlos und unbegrenzt sind.
