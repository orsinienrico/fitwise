# Fitwise — Implementation Notes

## Stato attuale

Il file `index.html` è una demo HTML/CSS/JS standalone.

È già presente:

- schermata home
- upload/scatto foto da iPhone
- selector occasione
- note opzionali
- analisi simulata lato client
- step animati di analisi
- schermata risultato
- voti di stile
- box diagnostici
- sezione “Verdetto”
- sezione “Consigli di stile”
- sezione “Per un upgrade”
- sezione “Preview consigliata”
- pulsanti Copia / Condividi / Nuovo look
- modal del `?`

## Vincoli

Mantenere tutto in un singolo file:

```text
index.html
```

Non usare:

- React
- Next.js
- Tailwind
- pacchetti npm
- immagini remote
- font remoti
- backend
- API esterne

## Target primario

Safari su iPhone.

## Upload foto

L'input usa:

```html
<input type="file" accept="image/*" capture="environment" />
```

## Analisi

L'analisi è simulata. Varia in base a:

- occasione selezionata
- parole nelle note come “troppo”, “dubbio”, “casual”, “scarpe”, “colore”, “giacca”, “jeans”, “sbagliato”

## Share

La condivisione deve essere robusta su iPhone.

Non usare la foto caricata nel canvas di share.

Usare una card generata interamente da canvas con gradient e testo, per evitare schermo nero.

## Preview consigliata

La preview è concettuale. Non deve promettere vera modifica AI della foto.

Testo corretto:

```text
Preview concettuale: mostra come cambierebbe la percezione del look applicando i consigli, non modifica realmente la foto.
```

