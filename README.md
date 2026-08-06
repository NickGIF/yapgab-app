# YapGab

**AI companion platform** — deploy your own white-label instance in one click.

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/template/M16VAV?referralCode=LT3bRM)

---

## What gets provisioned automatically

When you click **Deploy on Railway**, Railway will:

- Pull the pre-built YapGab Docker image
- Create a **PostgreSQL** database and wire `DATABASE_URL` automatically
- Generate `SESSION_SECRET` and `CONFIG_ENCRYPTION_KEY` as secure random values

You will **not** need to touch a terminal or edit any config files for these.

---

## What you enter manually

Railway will prompt you for one variable during deploy:

| Variable | Where to get it |
|---|---|
| `YAPGAB_LICENSE_KEY` | Provided when you purchase a YapGab creator license at [yapgab.com](https://yapgab.com) |

---

## After deployment — in-app setup wizard

Once the app starts, open the URL Railway gives you and complete the **Setup Wizard**. The wizard walks you through connecting:

- **ElevenLabs** — conversational AI voice (API key + Agent ID)
- **Stripe** — payments (publishable key, secret key, webhook secret)
- **Resend** — transactional email (API key + sending domain)

All of these are entered through the wizard UI — no SSH, no environment variable editing required.

---

## Setting your domain URL

Railway gives your app a default URL like `https://myapp.up.railway.app`. If you want email links and callbacks to use that URL (or a custom domain), set the `APP_BASE_URL` variable:

**To set it after your first deploy:**

1. Open your Railway project → click the **yapgab** service → **Variables** tab
2. Add `APP_BASE_URL` with your Railway URL, e.g. `https://myapp.up.railway.app`
3. Railway redeploys automatically (~30 seconds) — no downtime

**To use a custom domain:**

1. Railway project → **Settings** → **Domains** → add your domain and update your DNS
2. Once DNS is live, update `APP_BASE_URL` to your custom domain, e.g. `https://myapp.com`

`APP_BASE_URL` is used for links inside transactional emails and payment callbacks. You can leave it unset initially and add it any time.

---

## Referral

Deployed via referral code **LT3bRM**.
