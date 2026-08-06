# YapGab

**AI companion platform** — deploy your own white-label instance in one click.

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/template/uy6M3t?referralCode=LT3bRM)

---

## What gets provisioned automatically

When you click **Deploy on Railway**, Railway will:

- Pull the pre-built YapGab Docker image
- Create a **PostgreSQL** database and wire `DATABASE_URL` automatically
- Auto-generate `CONFIG_ENCRYPTION_KEY` and `SESSION_SECRET` on first boot (stored securely in Postgres so they survive restarts)

---

## What you enter manually

Railway will prompt you for two variables during deploy:

| Variable | What to enter |
|---|---|
| `PGPASSWORD` | Any password for the Postgres database (write it down — you can change it later) |
| `YAPGAB_LICENSE_KEY` | Provided when you purchase a YapGab creator license at [yapgab.com](https://yapgab.com) |

`DATABASE_URL` is wired automatically from the Postgres service — you don't need to enter it.

---

## After deployment — in-app setup wizard

Once the app starts, open the URL Railway gives you and complete the **Setup Wizard**. The wizard walks you through connecting:

- **ElevenLabs** — conversational AI voice (API key + Agent ID)
- **Stripe** — payments (publishable key, secret key, webhook secret)
- **Resend** — transactional email (API key + sending domain)

All of these are entered through the wizard UI — no SSH, no terminal, no environment variable editing required.

---

## Optional: promote auto-generated secrets to env vars

On first boot YapGab auto-generates `CONFIG_ENCRYPTION_KEY` and `SESSION_SECRET` and logs
them prominently. For additional security, copy those values from the Railway **Logs** tab
and add them as variables in the Railway **Variables** tab, then redeploy.

---

## Setting your domain URL

Railway gives your app a default URL like `https://myapp.up.railway.app`. To make email
links and payment callbacks use that URL, add `APP_BASE_URL` to the yapgab service Variables
tab (e.g. `APP_BASE_URL = https://myapp.up.railway.app`). You can set this any time after deploy.

---

Deployed via referral code **LT3bRM**.
