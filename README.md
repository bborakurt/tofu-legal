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
progress, nutrition settings, goal and consumption log stay on the phone; Şef paid through Apple and managed by
RevenueCat (US): the TOFU user ID (no name or e-mail), purchase records and its SDK's technical data (IDFV, IP),
for validating, linking and restoring the subscription and RevenueCat's subscription statistics; purchase and
restore need an account, and a restore asks before moving Şef from another TOFU account; in-app account deletion
(Profil > Hesap > "Hesabı sil") asks RevenueCat to delete the customer first, then deletes the Supabase user, and
never cancels the Apple subscription; no ads, tracking, IDFA, usage analytics or crash reporting. The source of
truth is the app repo's `docs/AUTH_BACKEND.md` and `Tofu/PrivacyInfo.xcprivacy`. Update these pages before the app
starts doing anything new with data (for example market features or a new service provider).

Not verified, so the pages don't promise it: whether RevenueCat's automatic syncs (renewals) can move Şef between
two TOFU accounts on one Apple ID without the consent question (terms § 7 says it may happen).
