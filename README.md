# YapGab

**AI companion platform** — deploy your own white-label instance in one click.

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/template/M16VAV?referralCode=LT3bRM)

---

## What gets provisioned automatically

When you click **Deploy on Railway**, Railway will:

- Pull the pre-built YapGab Docker image
- Create a **PostgreSQL** database and wire `DATABASE_URL` automatically
- Auto-generate `CONFIG_ENCRYPTION_KEY` and `SESSION_SECRET` on first boot (stored securely in Postgres)

---

## What you enter manually

Railway will prompt you for these variables during deploy:

| Variable | What to enter |
|---|---|
| `PGPASSWORD` | Any password for the Postgres database (e.g. a random string — write it down) |
| `YAPGAB_LICENSE_KEY` | Provided when you purchase a YapGab creator license at [yapgab.com](https://yapgab.com) |

`DATABASE_URL` is wired automatically from the Postgres service — you don't need to enter it.

---

## After deployment — in-app setup wizard

Once the app starts, open the URL Railway gives you and complete the **Setup Wizard**. The wizard walks you through connecting:

- **ElevenLabs** — conversational AI voice (API key + Agent ID)
- **Stripe** — payments (publishable key, secret key, webhook secret)
- **Resend** — transactional email (API key + sending domain)

All of these are entered through the wizard UI — no SSH, no environment variable editing required.

---

## Optional: promote auto-generated secrets to env vars

On first boot YapGab auto-generates `CONFIG_ENCRYPTION_KEY` and `SESSION_SECRET` and stores
them in Postgres. The app logs both values at startup. For additional security in-depth, copy
those values from the Railway Logs tab and add them to your Variables tab, then redeploy:

```
CONFIG_ENCRYPTION_KEY = <value from logs>
SESSION_SECRET        = <value from logs>
```

After this the secrets are stored in two places (env var + DB) — losing either one alone won't
affect your deployment.

---

## Setting your domain URL

Railway gives your app a default URL like `https://myapp.up.railway.app`. If you want email
links and callbacks to use that URL (or a custom domain), set the `APP_BASE_URL` variable:

1. Open your Railway project → click the **yapgab** service → **Variables** tab
2. Add `APP_BASE_URL` with your Railway URL, e.g. `https://myapp.up.railway.app`
3. Railway redeploys automatically (~30 seconds)

---

## Referral

Deployed via referral code **LT3bRM**.
