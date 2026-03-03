# Paris Tout Services — Site Statique

Site HTML/CSS statique pour **paristoutservices.com** — déployé automatiquement sur Hostinger via GitHub Actions.

## Structure

```
static/           ← Fichiers déployés sur Hostinger /public_html/
├── index.html
├── services.html
├── a-propos.html
├── realisations.html
├── contact.html
├── mentions-legales.html
├── politique-confidentialite.html
├── sitemap.xml
├── robots.txt
├── .htaccess
├── css/style.css
├── js/main.js
└── assets/
    ├── logo-pts-new.png    ← À copier depuis src/assets
    ├── hero-plumber.jpg    ← À copier depuis src/assets
    ├── realisations/
    └── partners/
```

## Déploiement automatique

Push sur `main` → GitHub Actions → FTP vers Hostinger.

### Secrets GitHub à configurer

Dans **Settings → Secrets and variables → Actions** :

| Nom | Valeur |
|-----|--------|
| `FTP_SERVER` | `ftp.paristoutservices.com` |
| `FTP_USERNAME` | Identifiant FTP Hostinger |
| `FTP_PASSWORD` | Mot de passe FTP Hostinger |

## Formulaire contact (Formspree)

1. Créer un compte sur formspree.io avec paristoutservices@gmail.com
2. Créer un formulaire → copier l'ID (ex: `xpwqaazb`)
3. Dans `static/contact.html`, remplacer `XXXXX` par l'ID Formspree :
   ```html
   <form action="https://formspree.io/f/xpwqaazb" ...>
   ```

## Images à copier

Copier depuis le projet React d'origine :
```bash
cp src/assets/logo-pts-new.png static/assets/
cp src/assets/hero-plumber.jpg static/assets/
```

## SEO — Vérifications post-déploiement

- [ ] curl -I https://www.paristoutservices.com  → vérifier canonical
- [ ] Google Search Console → soumettre sitemap.xml
- [ ] Tester Schema.org sur validator.schema.org
- [ ] Valider HTML sur validator.w3.org
- [ ] Lighthouse SEO score 90+
