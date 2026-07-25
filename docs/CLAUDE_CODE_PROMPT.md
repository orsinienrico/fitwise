You are a senior creative technologist and product designer working on a premium mobile-first HTML demo for a fashion intelligence app called Fitwise.

I am giving you an existing single-file HTML/CSS/JS app: `index.html`.

Your task: refine it directly in `index.html`. Do not create a framework. Do not create React, Next.js, package.json, Tailwind or external dependencies. Keep everything as one standalone HTML file.

PRODUCT CONTEXT
Fitwise is not a shopping app and not a generic AI outfit rater.
Fitwise answers the real user question: “Posso uscire così?”
The user uploads or takes a photo of their outfit, selects an occasion, adds optional notes, and receives a verdict on whether the look fits the context.

Core philosophy:
“L'eleganza è contesto.”
An outfit is not right or wrong in absolute terms. It can be perfect for one context and wrong for another.
Fitwise judges style choices, never the body or the person.

BRAND
Name: Fitwise
Tagline: Sapere prima di uscire.
Main brand statement: L'eleganza è contesto.
Tone: Italian only, elegant, direct, premium, editorial.
Avoid generic AI language such as “AI outfit analyzer”, “Occhio sartoriale AI”, “Intelligenza di stile”.

Visual direction:
Premium, fashion/editorial, mobile-first, refined, dark, sensual, not SaaS.
References: Gucci digital atelier, Prada editorial, Apple Vision Pro, Vogue, Saint Laurent, Spotify Wrapped for share card.

Palette:
- Ink Black: #050505
- Ivory: #F7F0E4
- Champagne Gold: #D7BD83
- Oxblood: #541B27
- Sage: #8D9572

REQUIRED CHANGES

1. Fix the hero headline on iPhone.
The current question mark in “Posso uscire così?” is clipped or disappears on Safari iPhone.
Do not keep the question mark inside italic inline text.
Use this two-line headline instead:

```html
<h1 class="headline">
  Posso uscire così
  <span class="headlineQuestion">Davvero?</span>
</h1>
```

Suggested CSS:

```css
.headline {
  font-family: Georgia, serif;
  font-size: clamp(54px, 15vw, 72px);
  line-height: 1.02;
  letter-spacing: -0.06em;
  overflow: visible;
}

.headlineQuestion {
  display: block;
  font-style: italic;
  color: transparent;
  background: linear-gradient(90deg, #fff2d2, #d7bd83, #8c6127);
  -webkit-background-clip: text;
  background-clip: text;
  padding-bottom: 0.12em;
}
```

2. Replace home slogan.
Do not use “Occhio sartoriale AI”.
Use:

```text
L'eleganza è contesto
```

3. Replace home copy with:

```text
Fitwise analizza il tuo outfit, l'occasione e i dettagli per dirti se il look è davvero nel posto giusto — con un verdetto chiaro, consigli di stile e upgrade concreti.
```

4. Keep the result page rich and premium.
It must include:
- hero image with verdict
- score /100
- style ratings with stars and bars
- diagnostic boxes: Punto forte, Punto critico, Matching, Rischio
- section “Verdetto”
- section “Consigli di stile” with summary and 3 detailed advice cards
- section “Per un upgrade” with 3 alternatives
- section “Preview consigliata” with conceptual before/after preview

5. Fix share button.
The current share can produce a black screen on iPhone. Do not use the uploaded user photo inside the share canvas.
Generate a native Fitwise share card entirely in canvas without the user photo.

Canvas size: 1080x1920.

Share card content:
- FITWISE
- Sapere prima di uscire
- verdict
- score /100
- ratings: Armonia colori, Occasione, Tessuti, Consistenza
- quote: “L'eleganza è contesto.”
- CTA: “Prova Fitwise: carica il tuo outfit, scegli l'occasione e scopri se puoi uscire così.”

Share logic:
- create canvas without external images
- canvas.toBlob
- create File `fitwise-verdetto.png`
- if `navigator.canShare({ files: [file] })` works, share the image file
- else if `navigator.share` works, share text
- else copy text to clipboard
- never leave the user with black screen
- show toast feedback

6. Update the top-right `?` modal.
It must open the true positioning and disclaimer.
Use this Italian content:

FITWISE

Sapere prima di uscire.

Fitwise non giudica le persone.
Giudica soltanto le scelte di stile.

Un outfit non è giusto o sbagliato in assoluto.
Può essere perfetto per un contesto e fuori posto per un altro.

Fitwise analizza foto, occasione e dettagli per stimare:
- armonia dei colori
- coerenza dei tessuti
- livello di formalità
- adeguatezza al contesto
- rischio di sembrare fuori luogo

e restituisce un verdetto chiaro, consigli pratici e possibili upgrade.

L'obiettivo non è seguire la moda.
L'obiettivo è sentirsi nel posto giusto.

Disclaimer:
Questa demo fornisce valutazioni automatizzate a scopo informativo e di intrattenimento.
Le analisi non costituiscono consulenza professionale di stile.
La preview consigliata è una simulazione concettuale e non modifica realmente la foto.

© Orsini&Co. Tutti i diritti riservati.

7. Keep everything Italian only.
No English UI labels.

8. Keep it single-file HTML/CSS/JS, optimized for iPhone Safari.
Use safe-area-inset. Touch targets must be at least 44px. Avoid clipped text.

OUTPUT
Modify `index.html` directly and return the full updated file. Also summarize exactly what changed.
