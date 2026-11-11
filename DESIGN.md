# Studio Chirurgico Ginecologico, Dott. Franco Alessandri: mock up

Mock up di restyling di https://www.alessandrifranco.com/ (oggi su Wix, template generico, link rotti). Deliverable: UN file `index.html` (CSS e JS inline), italiano, lingua `it`. Nessuna libreria, nessun embed, nessun CDN.

## Direzione (decisa, non cambiare)

`Direzione: clinico genovese sobrio, grotesque umanista con forte contrasto di peso (famiglia unica), ardesia / bianco calce freddo / ocra`

Scena: una donna, di sera o in pausa, dal telefono, cerca un ginecologo chirurgo di cui fidarsi e vuole sapere dove, come e chi. Luce del giorno, tema chiaro unico.
Register: brand. Riferimento reale: la carta intestata di uno studio medico stampata bene + le facciate ocra e i tetti in ardesia di Genova. Non copiare Wix, non fare "sanità teal e bianco", non fare editoriale crema+serif.

### Token (dichiarati a `:root`, niente colori letterali dopo)
- `--paper`  oklch(0.965 0.008 235)  fondo, bianco calce freddo
- `--panel`  oklch(0.915 0.016 240)  pannelli, slot foto
- `--ink`    oklch(0.25 0.035 255)   ardesia: testo, titoli, linee forti
- `--ink-2`  oklch(0.42 0.03 255)    testo secondario (contrasto AA su paper)
- `--ochre`  oklch(0.78 0.13 80)     UNICO accento: solo bottone primario e un segno firma. Testo su ocra = `--ink`
- Mai #000 / #fff. Nessun altro colore.
- Un solo raggio: 2px su tutto (bottoni, slot, pannelli). Niente ombre morbide, niente gradienti.

### Tipo
- Famiglia unica `Bricolage Grotesque` (display e testo), pesi 400 / 600 / 800 max. File woff2 NON presenti: dichiara `@font-face` con `src: url("fonts/BricolageGrotesque-var.woff2") format("woff2")`, `font-display: swap`, e stack di fallback `"Segoe UI Variable Display", "Segoe UI", system-ui, sans-serif`. Non scaricare font da terzi. Nel report elenca il file mancante.
- Scala rapporto 1.25 con clamp(). Corpo >= 17px, interlinea ~1.5, righe 60-70ch.
- Il nome "Franco Alessandri" in H1 è gigante (clamp fino a ~9rem), peso 800, tracking stretto, a sinistra. Contrasto di peso: "Dott." leggero 400.

## Contenuti REALI (usare solo questi; il resto = slot etichettato)

- Insegna: "Studio Chirurgico Ginecologico", Dott. Franco Alessandri
- Tagline originale del cliente: "Volere bene alla propria salute"
- Genova: Via Brigata Bisagno 4/19 (angolo S. Zita), 5° piano. Tel 010 543146
- Santa Margherita Ligure: Portofino Med, Via Partigiani d'Italia 31. Tel 010 543146
- Cellulare: 340 427 9206
- Email: studiofrancoalessandri@gmail.com
- Visite su appuntamento presso gli studi di Genova e di Santa Margherita Ligure. "Vi invitiamo a contattare la nostra segreteria per concordare la data più adatta alle vostre esigenze."
- Interventi chirurgici presso strutture private: Villa Montallegro (Genova), Villa Serena (Genova), e negli studi.
- Chirurgia oncologica: Policlinico S. Martino, IRCCS, centro di riferimento oncologico (il cliente scrive "ogni malato è seguito...": testo completo = slot).
- Convenzionato con tutte le principali Compagnie di Assicurazione.
- Virtual tour: https://tour.stefanoravera.it/tour/bJubQ8yWvfZylO-QIJZwM/Studio_Chirurgico_Ginecologico_Dr__Franco_Alessandri__Genova_ (link esterno, `rel="noopener"`)
- Blurb originali (troncati sul sito, usarli come sono e chiudere con slot):
  - Robotica: "La chirurgia robotica rappresenta l'ultima frontiera della chirurgia mini-invasiva" + `[TESTO COMPLETO DEL DOTTORE QUI]`
  - Isteroscopia diagnostica: "È una procedura che consente di esaminare la cavità dell'utero" + `[TESTO COMPLETO QUI]`
  - Uroginecologia: "La visita uroginecologica serve a verificare la presenza di un cedimento parziale o totale" + `[TESTO COMPLETO QUI]`
- Servizi ambulatorio (nomi): Visita ginecologica, Visita uroginecologica, Visita ostetrica, Pap test e HPV test, Tamponi vaginali, Colposcopia, Isteroscopia, Ecografia, Ecografia 3D.
- Servizi chirurgia (nomi): Chirurgia mini-invasiva, Chirurgia robotica, Laparoscopia single port, Isteroscopia operativa, Chirurgia oncologica, Embolizzazione fibromi uterini, Miomectomia, Isterectomia, Endometriosi, Prolasso ed incontinenza urinaria, Taglio cesareo.

NON inventare: titoli di studio, anni di esperienza, numeri di interventi, prezzi, orari, recensioni, descrizioni mediche aggiuntive, nomi di staff, testi legali. Foto: nessuna disponibile, solo slot.

## Obiettivo unico: chiamare lo studio

- CTA primaria, un'unica etichetta ovunque: **"Prenota una visita"** = `<a href="tel:+39010543146">`. Il numero 010 543146 è mostrato accanto.
- Il cellulare e l'email sono secondari (solo nei contatti/footer), nessun secondo bottone pieno.
- Mobile: barra fissa in basso (safe-area), bottone ocra min 48px, "Prenota una visita" + numero.

## Struttura pagina (>=4 famiglie di layout, mobile e desktop diversi)

1. **Header**: una riga, 64-72px. Sinistra: "Dott. Franco Alessandri" (wordmark testuale, nessun logo). Desktop: link ancora Visite, Chirurgia, Dove, Curriculum + CTA. Mobile: wordmark + tel button icona/testo, niente hamburger (ancore in una riga scorrevole o assenti).
2. **Hero** (asimmetrico, nessun testo centrato): H1 "Dott. Franco Alessandri" gigante; sotto una frase: "Chirurgia e ginecologia a Genova e Santa Margherita Ligure." (<=20 parole nel sottotitolo); CTA primaria + numero. Lato destro desktop (sotto il H1 su mobile): slot ritratto `[FOTO DEL DOTTORE QUI]` in `--panel`, proporzione 4:5, con didascalia "Studio Chirurgico Ginecologico". Segno firma in ocra: UNA linea spessa (6px) sotto "Dott." che si disegna in 600ms al caricamento (transform scaleX), unico movimento hero; reduced-motion = statica.
3. **Visite** (ambulatorio): titolo a sinistra sticky su desktop, a destra tre gruppi in colonne: "Visite" (ginecologica, uroginecologica, ostetrica), "Esami" (Pap test e HPV test, Tamponi vaginali, Colposcopia, Isteroscopia), "Ecografia" (Ecografia, Ecografia 3D). Uroginecologia e Isteroscopia hanno `<details>` inline con il blurb originale + slot. Leggibile senza JS (details nativo). Frase "Visite su appuntamento..." come testo corrente. Niente numerazioni, niente card identiche.
4. **Chirurgia**: pannello `--panel` a tutta larghezza, layout diverso dalla sezione 3: grande frase di apertura (Robotica, blurb originale) a sinistra, a destra elenco raggruppato in 3 colonne di testo: "Mini-invasiva" (Chirurgia mini-invasiva, Chirurgia robotica, Laparoscopia single port, Isteroscopia operativa), "Patologie" (Embolizzazione fibromi uterini, Miomectomia, Isterectomia, Endometriosi, Prolasso ed incontinenza urinaria), "Oncologia e ostetricia" (Chirurgia oncologica con nota Policlinico S. Martino IRCCS, Taglio cesareo). Sotto: "Dove si opera" = Villa Montallegro, Villa Serena, Policlinico S. Martino, in una riga grande di testo ardesia.
5. **Chi è**: slot `[BIO DEL DOTTORE QUI]` + link `[CURRICULUM PDF QUI]` (href="#", chiaramente slot, non deve sembrare finito). Layout: citazione-tagline "Volere bene alla propria salute" come H2 grande a sinistra + slot a destra. Sezione corta.
6. **Dove** (contatti): due indirizzi grandi in tipografia (non card), affiancati su desktop, impilati su mobile, ognuno con via, tel, link "Apri nella mappa" (link a `https://www.google.com/maps/search/?api=1&query=` URL-encoded, nessun iframe). Sotto: email, cellulare, link Virtual tour, riga assicurazioni. Qui compare ancora la CTA primaria (stessa etichetta).
7. **Footer**: nome, indirizzi corti, `[P.IVA / DATI LEGALI QUI]`, `[PRIVACY POLICY QUI]`, nota "Mockup di restyling, non è il sito ufficiale" (piccola).

Eyebrow maiuscolo tracciato: massimo 1 in tutta la pagina. Niente middle-dot chain, niente freccia "→" sui link, niente emoji, icone solo se servono (una famiglia, SVG inline, stroke uniforme; preferire nessuna icona).

## Immagini
Nessuna foto reale disponibile e nessuna generata che mostri persone/luoghi. Gli slot foto sono parte del design: rettangoli `--panel` con etichetta `[FOTO ... QUI]` in testo ink-2, ben proporzionati, `role="img"` + `aria-label`. Niente picsum.

## Vincoli tecnici
Vanilla, mobile-first da 360px, `overflow-x: clip` su html e body, `min-height: 100dvh`, container max ~1200px, griglie con `minmax(0,1fr)`. Spaziatura multipli di 8px. Un H1. Focus visibile (outline 3px ink con offset), link "Vai al contenuto". Target >=44px. Movimento solo transform/opacity, 150-400ms (la linea ocra 600ms è l'unica eccezione dichiarata), una sola easing `cubic-bezier(0.16, 1, 0.3, 1)`, `prefers-reduced-motion` rispettato. Mai `transition: all`. Niente fade-up sulle sezioni. Testo senza em dash né en dash. Etichetta CTA uguale ovunque.
`<title>`, meta description, lang="it", Open Graph minimo. JSON-LD `Physician`/`MedicalBusiness` solo con dati reali sopra (nome, indirizzi, telefono, email), senza orari.
Peso pagina < 150 KB.

## Definition of done
- `index.html` apre da file e da http-server, nessun errore in console, nessuna richiesta di rete esterna (solo il 404 atteso del font mancante).
- Hero H1 + frase + CTA visibili a 1280x800 e a 390x844 senza scroll.
- A 390px la pagina non scrolla in orizzontale e la barra CTA fissa non copre il contenuto finale (padding-bottom).
- `grep` di `QUI]` mostra tutti gli slot attesi e solo quelli.
- Nessun colore o font-family letterale dopo il blocco `:root`.
