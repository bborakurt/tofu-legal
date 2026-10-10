# TOFU legal site

Static pages for the TOFU iOS app, deployed on Vercel's free plan: `/privacy` and `/terms`. No build step and no
dependencies.

## Before you publish

All placeholders are filled (developer: Bora Kurt; contact: bborakurtt@gmail.com). If you edit the pages, check that
no placeholder is left: `grep -n "\[" privacy.html terms.html`

## Publish on Vercel

1. Create a free account at vercel.com.
2. Easiest: install the CLI (`npm i -g vercel`), then run `vercel --prod` inside this folder and accept the defaults
   (framework: Other, no build command, output directory: `.`).
3. Or: put this folder in its own GitHub repository and import it at vercel.com/new.

The pages are then at `https://<project>.vercel.app/privacy` and `/terms`.

## Keep it true

The pages describe only what the app does today: Supabase for sign-up and sign-in (name, e-mail, password) and for
the account's food preferences except excluded foods/allergies (`user_preferences`), weekly plan with pantry and
shopping state (`weekly_plans`) and planning history (`planning_history`), all also kept on the phone; cooking/Rota
progress stays on the phone; in-app
account deletion (Profil > Hesap > "Hesabı sil"), everything else stored on the phone,
Şef through Apple, no analytics, ads or tracking. Update them before the app starts doing
anything new with data (for example syncing plans to a server or market features).
