# mobile-deploy

Claude Mobile Only Web Apps.

Each app lives in `car/<app>/` (plain HTML, CSS, JSON) and deploys to `core3.com/car/<app>`.

## Deploy

1. In GitHub: **Actions → Deploy app to Core3 (SFTP) → Run workflow**.
2. Enter the app folder name (e.g. `app1`).

The folder is uploaded over SFTP to `$SFTP_PATH/<app>`. Files are added or overwritten; nothing is deleted on the server.

## One-time setup: repository secrets

In GitHub: **Settings → Secrets and variables → Actions → New repository secret**.

| Secret | Value |
|---|---|
| `SFTP_HOST` | Core3 SFTP host name |
| `SFTP_USER` | SFTP user name |
| `SFTP_PASSWORD` | SFTP password |
| `SFTP_PATH` | Remote folder that holds the apps, e.g. `/public_html/car` |

Never commit credentials to this repo.
