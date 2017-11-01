# Front-End Checklist

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

La **Checklist Front-End FRENCH / francaise** est une liste exhaustive de tous les élements dont vous avez besoin avant de lancer votre site HTML en production.

C'est basé sur des années d'experience des développeurs Front-End, en y ajoutant divers checklists de projets open-source.

*Partager cette checklist en votant sur Product Hunt*
[![](http://res.cloudinary.com/djnyaloac/image/upload/v1508896898/upvote-producthunt_vzys4c.jpg)](https://www.producthunt.com/posts/front-end-checklist)

## Table of Contents

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## Comment l'utiliser ?

Tous les élements de la **Front-End Checklist** sont requis dans la majorité de vos projets, mais certains peuvent être omis ou ne sont pas essentiels (par exemple, dans le cas d'une app d'administration , vous n'avez pas besoin de flux RSS). Nous avons choisi d'utiliser  3 niveaux de flexibilité:

* ![Bas][low_img] signifie que l'élement est **recommandé** mais peut être omis dans certaines situations.
* ![Moyen][medium_img] signifie que l'élement est **hautement recommandé** et peut éventuellement être omis dans certains cas particuliers . Certains élements s'ils sont omis peuvent avoir des mauvais effets secondaires en terme de performance ou de référencement (SEO).
* ![Haut][high_img] signifie que l'élement **est indispensable**. Vous pouvez provoquer des dysfonctionnements dans votre page, ou avoir des problèmes d'accessibilité, voir de SEO. La priorité des tests doit d'abord s'assurer de ces éléments en premiers.

Plusieurs resources possèdent un emoticon pour vous aider à comprendre quel type de contenu il s'agit :

* 📖: documentation ou article
* 🛠: outil online  / outil de test
* 📹: media ou contenu vidéo 

---

## Head

> **Notes:** Vous pouvez trouver [une liste de toute les balises](https://github.com/joshbuchea/HEAD) qui peuvent être trouvés dans la section  `<head>` d'un document HTML.

### Meta tag

* [ ] **Doctype:** ![Haute][high_img] Le Doctype est HTML5 et doit être en haut de toutes vos pages HTML.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> * 📖 [Determiné l'encodage - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Les prochains 3 meta tags (Charset, X-UA Compatible and Viewport) doivent venir en premier dans le head.*

* [ ] **Charset:** ![Haute][high_img] Le charset declaré (UTF-8) est correctement declaré.

```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Moyen][medium_img] Le meta tag X-UA-Compatible est présent.

```html
<!-- Instruct Internet Explorer to use its latest rendering engine -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Specifié le mode d'héritage des documents (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![Haute][high_img] Le viewport est correctement déclaré.

```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![Haute][high_img] Un titre est utilisé sur chaque page (SEO: Google calcule la largeur des pixels de chaque caractères utilisés dans le titre, et coupe entre 472 et 482 pixels. La limite moyenne de caractères se situe autour des 55).

```html
<!-- Document Title -->
<title>Page Title less than 55 characters</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** ![Haute][high_img] Une meta description est fourni, elle est unique et ne contient pas plus de 150 caractères.

```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```

> * 📖[Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Moyen][medium_img] Chaque favicon a été créé et s'affiche correctement. Si vous avez un `favicon.ico`, posez le à la racine de votre site. Normallement vous n'avez pas besoin d'utiliser de balise. Cependant, cela reste une bonne pratique de le relier comme dans l'exemple ci-dessous. Aujourd'hui, **Le PNG est recommendé** en remplacement du format `.ico` (dimensions: 32x32px).

```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Bas][low_img] Les favicons Apple touch apple-mobile-web-app-capable sont présents. *(Créer vos icones Apple avec au pire des dimensions de 200x200px pour supporter toutes les dimensions dont vous aurez besoin)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> * 📖 [Configurer des Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Bas][low_img] Les tuiles Windows sont présentes et liées.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

Le balisage xml minimum requis pour le balisage du fichier browserconfig.xml doit être:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Moyen][medium_img] Utiliser `rel="canonical"` pour éviter le contenu dupliqué.

```html
<!-- Helps prevent duplicate content issues -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML tags

* [ ] **Language attribute:** ![Haute][high_img] L'attribut `lang` de votre site est spécifié et indique le langage de la page courrante.

```html
<html lang="en">
```

* [ ] **Direction attribute:** ![Moyen][medium_img] Le sens de lecture est specifié dans le tag html (Il peut être indiqué dans un autre tag HTML).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] Le tag language de votre site est specifié et est en relation avec le language de la page courrante.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low][low_img] Les commentaires conditionnels sont présents pour IE si besoin.

> * 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Bas][low_img] Si votre projet est un blog ou a des articles, un flux RSS est fourni.

* [ ] **Inline critical CSS:** ![Moyen][medium_img] CSS avec le style des contenus qui doivent être immédiatement visibles pendant le chargement ("au dessus de la ligne de flottaison") sont appelés "CSS critiques". Ils sont inclus avant le CSS principal et entre les balises `<style></style>` dans une seule ligne (en étant minifié).
> * 🛠 [Critical by Addy Osmani on GitHub](https://github.com/addyosmani/critical) automates this

* [ ] **CSS order:** ![Haute][high_img] Tous les fichiers CSS sont chargés avant n'importe quel fichier JavaScript dans la section `<head>`. (Parfois certains fichiers JS sont chargés en asynchrones en haut de page, et font donc exception à la règle).

### Social meta

***Facebook OG*** et ***Twitter Cards*** sont, pour tous les sites, hautement recommendés. Les autres tag de média sociaux peuvent être utiles si vous ciblez une audience particulère et que vous voulez vous assurer une affichage particulier.

* [ ] **Facebook Open Graph:** ![Low][low_img] Tous les Open Graph Facebook (OG) sont testés et aucun ne manque ou contient de fausses informations. Les images doivent être au minimum de 600 x 315 pixels, mais 1200 x 630 pixels est recommendé.

> **Notes:** L'utilisation des balises `og:image:width` et `og:image:height` qui spécifient les dimensions des images au crawler permettent le rendu des images immédiatement sans avoir besoin de les redimensionner avec un système asynchrone.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Next tags are optional but recommended -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 📖 [Best Practices - Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
> * 🛠 TTester votre page avec [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ Retour en haut](#table-of-contents)**

---

## HTML

### Bonnes pratiques

* [ ] **HTML5 Semantic Elements:** ![Haut][high_img] Les élements sémantiques HTML5 ont une utilisation spécifique (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![Haut][high_img] Les pages d'erreurs 404 et 5xx existent. Rappelez vous que les pages d'erreurs 5xx ont besoin de CSS intégrés (pas d'appel externe au serveur courrant).

* [ ] **Noopener:** ![Moyen][medium_img] Dans le cas ou vous utilisez des liens externes avec `target="_blank"`, votre lien devrait avoir l'attribut `rel="noopener"` pour prévenir du tab nabbing (piratage par onglet). Si vous devez supporter les anciennes versions de Firefox, utiliser alors `rel="noopener noreferrer"`.

> * 📖 [A propos de rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Nettoyage de commentaires:** ![Bas][low_img] Le code non nécessaire doit être supprimé avant l'envoi en production.

### HTML testing

* [ ] **W3C compliant:** ![Haut][high_img] Toutes les pages doivent avoir passé la validation W3C pour identifier de possibles problèmes dans le code HTML.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Haut][high_img] J'utiliser ces outils pour m'aider à analyser des problèmes que je pourrais avoir dans le code  HTML.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

> * 🛠 [Sonar a linting tool for the web](https://sonarwhal.com/)

* [ ] **Link checker:** ![Haut][high_img] Vérification qu'il n'y ai pas de liens brisés (pages 404).

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Moyen][medium_img] Votre site doit affiché un contenu correct malgré la présence d'adblocker (Vous pouvez fournir un message pour encourager les gens à les désactiver).



**[⬆ Retour en haut](#table-of-contents)**

---

## Webfonts

> **Notes:** Utiliser les webfonts peut causer des problèmes de textes invisibles avec Flash - consider having fallback fonts and/or utilizing webfont loaders to control behavior.
> * 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Webfont format:** ![Haut][high_img] WOFF, WOFF2 et TTF sont tous supportés par les navigateurs modernes.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![Haut][high_img] La taille des Webfont ne doit pas excéder 2 MB (toutes les variantes incluses).

* [ ] **Webfont loader:** ![Bas][low_img] Control loading behavior with a webfont loader

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ retour en haut](#table-of-contents)**

---

## CSS

> **Notes:** Regardez les [guidelines CSS](https://cssguidelin.es/) et les [Guidelines Sass](https://sass-guidelin.es/) fournis par de nombreux développeurs Front-End. Si vous avez des doutes sur des propriétés CSS, vous pouvez visiter la [Reference CSS](http://cssreference.io/). Il y a aussi ce court [Guide](http://codeguide.co/) pour la cohérence.

* [ ] **Responsive Web Design:** ![Haut][high_img] Le site utiliser un design responsive.
* [ ] **CSS Print:** ![Moyen][medium_img] Une feuille d'impression CSS est incluse et permet une impression correcte sur chacune des pages.
* [ ] **Preprocessors:** ![Bas][low_img] L'utilisation d'un preprocessor CSS ([Sass](http://sass-lang.com/) est conseillé).

* [ ] **Unique ID:** ![Haut][high_img] Si des IDs sont utilisés, ils sont uniques à une page.
* [ ] **Reset CSS:** ![Haut][high_img] Une CSS reset (reset, normalize ou reboot) est utilisé et mise à jour. *(Si vous utiliser un  Framework CSS comme Bootstrap ou Foundation, une feuille Normalize est déjà incluse.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Bas][low_img] Toutes les classes (ou les id- utilisés dans les fichiers JavaScript) commencent par **js-** et ne sont pas stylés dans les fichiers CSS.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Embedded ou inline CSS:** ![Haut][high_img] Tous les CSS embarqués dans des balises `<style>` ou utilisant le CSS en style: le sont uniquement pour de bonnes raisons (e.g. background-image pour des sliders, ou des CSS critiques).
* [ ] **Vendor prefixes:** ![Haut][high_img] les préfixes des CSS sont utilisés en prenant soin de la compatibilité des navigateurs.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![Haut][high_img] Les fichiers CSS sont concatenés dans un fichier unique. *(Pas pour HTTP/2)*
- [ ] **Minification:** ![Haut][high_img] Les fichiers CSS sont minifiés.
- [ ] **Non-blocking:** ![Moyen][medium_img] Les fichiers CSS ne doivent pas être bloquants pour que le DOM puisse se charger rapidement.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Bas][low_img] Supprimer les CSS inutilisés.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testing

* [ ] **Stylelint:** ![Haut][high_img] Tous les fichiers CSS ou SCSS ne doivent pas avoir une seule erreur.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![Haut][high_img] All pages were tested at the following breakpoints: 320px, 768px, 1024px (can be more / different according to your analytics).

* [ ] **CSS Validator:** ![Moyen][medium_img] The CSS was tested and pertinent errors were corrected.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** ![Haut][high_img] All pages were tested on all current desktop browsers (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![Haut][high_img] All pages were tested on all current mobile browsers (Native browser, Chrome, Safari...).
* [ ] **OS:**  ![Haut][high_img] All pages were tested on all current OS (Windows, Android, iOS, Mac...).

- [ ] **Pixel perfect:** ![Haut][high_img] Pages are close to pixel perfect. Depending on the quality of the creatives, you may not be 100% accurate, but your page needs to be close to your template.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** ![High][high_img] All pages need to be tested for LTR and RTL languages if they need to be supported.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **Notes:** For a complete understanding of image optimization, check the free ebook **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### Best practices

* [ ] **Optimization:** ![High][high_img] All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.
> * 🛠 Use [Kraken.io](https://kraken.io/web-interface) awesome alternative for both png and jpg optimization. Up to 1mb per files on free plan.

* [ ] **Picture/Srcset:** ![Medium][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Low][low_img] You provide layout images 2x or 3x, support retina display.
* [ ] **Sprite:** ![Medium][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![High][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image size is known (can be omitted for CSS sizing).
* [ ] **Alternative text:** ![High][high_img] All `<img>` have an alternative text which describe the image visually.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images are lazyloaded (A noscript fallback is always provided).

**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![High][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![High][high_img] JavaScript files are concatenated.
* [ ] **Minification:** ![High][high_img] JavaScript files are minified (you can add the `.min` suffix).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **Non-blocking:** ![Medium][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using `defer` attribute.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] If you need to target some specific features you can use a custom Modernizr to add classes in your `<html>` tag.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### Scan and check your web site

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Best practices

* [ ] **HTTPS:** ![Medium][medium_img] HTTPS is used on every pages and for all external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] The HTTP header is set to 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] You ensure that requests made to your server-side are legitimate and originate from your website / app to prevent CSRF attacks.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Your page or website is free from XSS possible issues.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] Prevents Google Chrome and Internet Explorer from trying to mime-sniff the content-type of a response away from the one being declared by the server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] Protects your visitors against clickjacking attacks.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

* [ ] **Content Security Policy** ![Medium][medium_img] Defines how content is loaded on your site and from where it is permitted to be loaded. Can also be used to protect against clickjacking attacks.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
> * 📖 [CSP Cheat Sheet - OWASP](https://www.owasp.org/index.php/Content_Security_Policy_Cheat_Sheet)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### Best practices

- [ ] **Weight page:** ![High][high_img] The weight of each page is between 0 and 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] Your HTML is minified.
> * 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

* [ ] **Cookie size:** If you are using cookies be sure each cookie doesn't exceed 4096 bytes and your domain name doesn't have more than 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** ![Medium][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your users activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake and TLS negociation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![High][high_img] Headings should be used properly in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>` has `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` has `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` has `role="main"`.

> * 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)
> * 📖 [ARIA roles categorization](https://www.w3.org/TR/wai-aria/roles#roles_categorization)

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![High][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![High][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Medium][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![High][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] Google Analytics is installed and correctly configured.
* [ ] **Headings logic:** ![Medium][medium_img] Heading text helps to understand the content in the current page.
* [ ] **sitemap.xml:** ![High][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).
* [ ] **robots.txt:** ![High][high_img] The robots.txt is not blocking webpages.

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)

---

## Front-End Checklist Badge

If you want to show you are following the rules of the Front-End Checklist, put this badge on your README file!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `maitre`

La branche consiste dans ce fichier `README.md` automatiquement créé depuis le site [Front-End Checklist](http://frontendchecklist.com/) .

#### 2. `developpeurs`

Cette branche sera utilisé pour faire des changements significatifs à la structure si besoin. Il est préférable d'utiliser la branchemaitre pour corriger des petites erreurs ou pour ajouter un nouvel élément.

### Contributeurs

[contributeurs](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Support

If you have any question or suggestion, don't hesitate to use Gitter or Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Auteurs

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**
**Traduction FR: [Yohann Nizon](https://www.gameandme.fr)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ Retour en haut](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
