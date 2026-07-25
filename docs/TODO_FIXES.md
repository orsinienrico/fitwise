# Fitwise — TODO e Fix Prioritari

## 1. Headline: il punto interrogativo è problematico su iPhone

Problema corrente: nella headline iniziale il `?` di “Posso uscire così?” viene tagliato o sparisce su Safari iPhone.

### Fix richiesto

Non usare più il punto interrogativo nella stessa riga italic.

Soluzione preferita:

```html
<h1 class="headline">
  Posso uscire così
  <span class="headlineQuestion">Davvero?</span>
</h1>
```

CSS suggerito:

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

Obiettivo: niente testo tagliato su Safari iPhone.

---

## 2. Slogan home

Eliminare definitivamente:

```text
Occhio sartoriale AI
```

Usare:

```text
L'eleganza è contesto
```

---

## 3. Copy home

Usare copy più premium:

```text
Fitwise analizza il tuo outfit, l'occasione e i dettagli per dirti se il look è davvero nel posto giusto — con un verdetto chiaro, consigli di stile e upgrade concreti.
```

---

## 4. Condividi: evitare schermo nero

Problema: la share card attuale può diventare nera su iPhone se prova a usare la foto caricata dentro un canvas.

### Fix richiesto

Non includere la foto utente nella card condivisa.

Generare invece una card nativa Fitwise in canvas con solo:

- background gradient premium
- brand Fitwise
- Sapere prima di uscire
- verdetto
- score
- metriche
- frase “L'eleganza è contesto.”
- CTA marketing

Dimensione consigliata:

```text
1080 x 1920
```

### Share fallback

Implementare:

1. canvas senza foto utente
2. `canvas.toBlob`
3. `new File([blob], 'fitwise-verdetto.png', { type: 'image/png' })`
4. se `navigator.canShare({ files: [file] })` funziona, condividere immagine
5. altrimenti `navigator.share` solo testo
6. altrimenti clipboard
7. mai lasciare schermo nero

---

## 5. Modal del bottone `?`

Il `?` in alto deve aprire il posizionamento vero dell'app e il disclaimer.

Testo da usare:

```text
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
```

---

## 6. Risultato finale desiderato

La demo deve essere:

- single-file `index.html`
- mobile-first iPhone
- tutto in italiano
- premium/fashion/editoriale
- senza dipendenze esterne
- senza React/Next
- pronta per GitHub Pages/Vercel/Netlify

