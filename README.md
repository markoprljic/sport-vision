# Sport Vision — AI Shopping Assistant (demo)

Mobile-first HTML demo for a Croatian voice-driven sports equipment shop. Speak in Croatian, get product results.

## Running locally

Open `index.html` in Chrome (desktop or Android). The Web Speech API requires Chrome — Safari/Firefox won't recognise the mic.

```
open index.html
```

For a slightly nicer dev experience (so the mic prompt isn't blocked on `file://`):

```
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying to GitHub Pages

1. Push this directory to a GitHub repo
2. Settings → Pages → deploy from `main` branch, root folder
3. Open the Pages URL in mobile Chrome and tap the red circle

## Demo scenarios

The three rehearsed scripts (speak them after tapping the red circle):

1. *"Imam trideset godina, konzervativnog sam stila, tražim muške hlače za trčanje, do sto eura, Nike ili Adidas."* → 4 men's running trousers
2. *"Pripremam se za maraton i trebam novi par tenisica za trčanje. Pokažite mi sve opcije koje imate."* → 8 running shoes
3. *"Želim početi igrati tenis, kakvu opremu trebam? Sve zajedno do dvjesto eura."* → follow-up (adult/child) → 4-item bundle, total 197,96 €

After results, refine via the floating mic button: *"samo crne"*, *"do osamdeset eura"*, *"veličina četrdeset dva"*, *"samo Nike"*, *"pokaži mi više"*.

## Without a microphone

Open the browser console and call:

```js
simulateSpeech('Pripremam se za maraton i trebam tenisice za trčanje.')
simulateRefine('Samo crne.')
```

## Stack

Single `index.html`, no build, no dependencies. Web Speech API for `hr-HR` recognition, CSS gradients for product imagery.
