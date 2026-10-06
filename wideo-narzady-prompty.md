# 3 nowe wideo „Te napoje wspierają Twoje narządy" – zestaw promptów

Wzorzec: oryginalne nagranie (6 narządów: oczy, mózg, płuca, wątroba, nerki, serce).
Zmiana: każde wideo ma **max 3 narządy**, a w kolejnych wideo są **nowe narządy** (bez powtórek z oryginału i między sobą).

## Parametry wspólne
- Format: pion 9:16 (oryginał 1206×2622), ok. 6 s, 24–30 fps
- Tło: ciemny, matowy, wilgotna faktura, kontrastowe światło
- Układ: po lewej narząd (duży, makro, realistyczny), po prawej szklanka napoju + świeże składniki
- Środek: biała etykieta z nazwą narządu (PL) i mały podpis napoju (EN), cienka linia łącząca
- Animacja: miniaturowi robotnicy w żółtych kaskach i granatowych kombinezonach czyszczą narząd (gąbki, szczotki, myjki ciśnieniowe). Brudny, ciemny narząd stopniowo staje się czysty i jasny. W napoju unosi się para lub bąbelki, a składniki lekko się poruszają
- Tytuł u góry: „Te napoje wspierają…", dół: „Zadbaj o swoje narządy!!"
- Uwaga: bez twierdzeń typu „leczą" ani „detoks". To napoje wspierające, nie leki.

## Prompt bazowy (wklej do Sora / Runway / Kling / Veo)
> Vertical 9:16, 6 seconds, dark moody studio background. Left: a macro, photorealistic, initially dirty and dull {NARZĄD}; tiny miniature construction workers in yellow helmets and navy overalls scrub it with sponges and brushes, it gradually turns clean and glowing. Right: a {NAPÓJ} in a glass with fresh ingredients, gentle steam/bubbles. A white label "{NAZWA PL}" with a small caption "{NAPÓJ EN}" between them. Repeat the same layout for each of the three rows, top to bottom, cleaning progress in sync. Cinematic lighting, shallow depth of field, tilt-shift miniature look.

## Wideo 1 – układ trawienny
| Rząd | Narząd (etykieta) | Napój (podpis) | Składniki |
|---|---|---|---|
| 1 | Żołądek | Chamomile Tea | rumianek, miód |
| 2 | Jelita | Kefir | kefir, borówki |
| 3 | Trzustka | Cinnamon Tea | laski cynamonu, jabłko |

Tytuł: „Te napoje wspierają trawienie"

## Wideo 2 – skóra i odpływ
| Rząd | Narząd (etykieta) | Napój (podpis) | Składniki |
|---|---|---|---|
| 1 | Skóra | Cucumber Mint Water | ogórek, mięta |
| 2 | Pęcherz | Cranberry Juice | żurawina |
| 3 | Tarczyca | Green Smoothie | szpinak, spirulina, kiwi |

Tytuł: „Te napoje wspierają Twoje ciało"

## Wideo 3 – ruch i krążenie
| Rząd | Narząd (etykieta) | Napój (podpis) | Składniki |
|---|---|---|---|
| 1 | Stawy | Golden Milk | kurkuma, imbir, pieprz |
| 2 | Śledziona | Nettle Tea | pokrzywa, cytryna |
| 3 | Tętnice | Hibiscus Tea | kwiat hibiskusa, lód |

Tytuł: „Te napoje wspierają krążenie i ruch"

## Montaż (po wygenerowaniu klipów)
Jeśli narzędzie generuje tylko krótkie klipy, wygeneruj każdy rząd osobno (3 klipy na wideo) i złóż je pionowo w jednym kadrze:
```
ffmpeg -i r1.mp4 -i r2.mp4 -i r3.mp4 -filter_complex "[0][1][2]vstack=inputs=3" -t 6 wideo1.mp4
```
