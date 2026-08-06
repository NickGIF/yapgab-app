# YapGab

**AI companion platform** — deploy your own white-label instance in minutes.

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/new/template?template=https://github.com/NickGIF/yapgab-app&referralCode=LT3bRM)

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

## Referral

Deployed via referral code **LT3bRM**.
