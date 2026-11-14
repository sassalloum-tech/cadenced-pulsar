# Cadenced Pulsar: The universe pulses. So do we.

**Powered by ASCIS (Autonomous Space Care Intelligence System)**
NASA International Space Apps Challenge 2026 · Challenge: *Create Health Monitoring Software for Astronauts on Space Missions* · Team: La Luz de las Estrellas

Cadenced Pulsar is an offline-first, visual health companion for astronauts. On a Mars mission a radio message can take up to about 22 minutes each way, so the crew has to act alone. The prototype shows a 3D body twin, judges every vital against that astronaut's own baseline, tells apart a heart attack, a panic attack and an environmental cause such as high CO2, and keeps a heart cause open until it is properly checked. A human confirms every medication step. A morning check-in and a mountain-trail learning game keep health knowledge fresh when the radio is silent.

**All vitals in this prototype are simulated. It is not a medical device and has not been clinically validated. The clinical content is a draft for physician review.**

## Files

- `index.html`: the monitoring screen (open this one).
- `summit-trail.html`: the Summit Trail snakes-and-ladders learning game.
- `libs/` (optional): local copies of `three.min.js` and `GLTFLoader.js` (three.js r128). If present, the 3D views work with no internet. If absent, the page loads them from jsDelivr.

## How to run it offline

Download the repository, keep `index.html` and `summit-trail.html` together (plus `libs/` for 3D without internet), and open `index.html` in a browser. Fonts fall back to system fonts when offline.

## NASA data and resources used

- NASA medical requirements documents (MRIDs): EVA medical monitoring MEDB 6.1/6.2, resting ECG MEDB 1.6, 24-hour ECG MEDB 1.7, bone densitometry MEDB 1.11, strength and conditioning MEDB 5.2, cycle ergometer N3.07, arm ergometry MEDB 6.3, exercise treadmill MR006L, infection screening MEDB 2.3, 2.4 and MR021S (provided in the challenge resources).
- NASA Human Research Program risk summaries: cardiovascular, immune, microbes, hypoxia and sensorimotor.
- NASA OCHMO Medical Technical Brief OCHMO-MTB-007, Venous Thrombosis in Spaceflight (January 2026).
- NASA working group report on decompression sickness, venous thromboembolism and patent foramen ovale (August 2026).
- NASA OCHMO page: Risk of Venous Thromboembolism During Spaceflight.
- Norsk P, Asmar A, Damgaard M, Christensen NJ. Fluid shifts, vasodilatation and ambulatory blood pressure reduction during long duration spaceflight. J Physiol 2015;593:573-584.
- Stahn AC et al. Increased core body temperature in astronauts during long-duration space missions. Scientific Reports 2017;7:16180.

These sources shaped what the system measures (ECG, heart rate, suit and cabin pressure, CO2 and oxygen, radiation), how personal baselines are used, how bone and muscle status is estimated from exercise logs, and the spaceflight clot pathway. The stop criteria in the NASA test documents are for supervised exercise tests and are used only as inspiration for alerts, not as diagnostic rules.

## Use of Super Intelligence (AI) tools

- **Concept and clinical logic:** by the team physician.
- **AI assistance (Claude, Anthropic):** drafting and refinement of interface code, simulation logic, text and ideas, reviewed by the team.
- **AI-generated images and 3D models (Meshy, and an image generator):** the mountain board artwork, the 3D anatomical body, the blood pressure monitor, thermometer, pulse oximeter and astronaut bust. Each is labeled "AI-generated" in the interface.
- No NASA logos, flags or mission identifiers are used in generated content.

## Third-party resources

- three.js r128 (MIT license) and its GLTFLoader.
- Nunito font by Google Fonts (SIL Open Font License).
- Meshy-generated 3D models and images (see Meshy terms for the plan used).

## Limits

Simulated data only. Projections are labeled as projections, not diagnoses. Medication doses are intentionally left to the physician protocol. Not clinically validated.
