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
- Mie ACS Registry, Circulation Journal 2025 (Prehospital Vital Signs, Including SpO2, and Mortality in Acute Myocardial Infarction): Simple Risk Index of 34 or more together with SpO2 of 94% or lower, hazard ratio 3.98 for 30-day death. Simple Risk Index formula from the InTIME II substudy (Morrow et al., Lancet): heart rate x (age/10)^2 / systolic blood pressure. It is a risk marker in patients having a heart attack, not a diagnostic test.
- NASA Integrated Medical Model, Acute Coronary Syndrome Clinical Finding Form (CliFF, 2023): diagnostic and treatment capability scope for acute coronary syndrome (troponin, ECG, ultrasound; antiplatelet and fibrinolytic therapy, nitroglycerin, oxygen).
- ISS common medication list (2023 packaging data): aspirin 325 mg tablet and nitroglycerin 0.4 mg tablet.
- Reference doses in the heart attack screens (weight-based tenecteplase, enoxaparin with a clot-dissolving drug, aspirin, clopidogrel loading): TNKase (tenecteplase) prescribing information, and the STEMI dosing table in Vascular Health and Risk Management 2009;5:249-256. Height is not used. The physician confirms every dose, and the screens are simulated.
- Stahn AC et al. Increased core body temperature in astronauts during long-duration space missions. Scientific Reports 2017;7:16180.

These sources shaped what the system measures (ECG, heart rate, suit and cabin pressure, CO2 and oxygen, radiation), how personal baselines are used, how bone and muscle status is estimated from exercise logs, and the spaceflight clot pathway. The stop criteria in the NASA test documents are for supervised exercise tests and are used only as inspiration for alerts, not as diagnostic rules.

## Use of Super Intelligence (AI) tools

- **Concept and clinical logic:** by the team physician.
- **AI assistance (Claude, Anthropic):** drafting and refinement of interface code, simulation logic, text and ideas, reviewed by the team.
- **AI-generated images and 3D models (Meshy, and an image generator):** the mountain board artwork, the 3D anatomical body, the blood pressure monitor, thermometer, pulse oximeter and astronaut bust. Each is labeled "AI-generated" in the interface.
- **Spoken prompts:** use the browser's built-in text-to-speech (synthetic voice, a soft female voice when the device has one). Voice is off by default and is switched on with the Voice button.
- **Concept image:** the stabilization web image in Evacuation mode is AI-generated and labeled as a concept that has not been built.
- No NASA logos, flags or mission identifiers are used in generated content.

## Third-party resources

- three.js r128 (MIT license) and its GLTFLoader.
- Nunito font by Google Fonts (SIL Open Font License).
- Meshy-generated 3D models and images (see Meshy terms for the plan used). The thermometer, oxygen analyzer and astronaut bust pictures are AI-generated and labeled in the interface.

## Emergency protocol (draft by the team physician, simulated)

Voice and pop-up questions run only for five demo buttons: **CO₂ rising**, **Subtle ECG change**, **ST elevation**, **Cardiac arrest** and **Panic at rest**. Rest, Exercise and Neck swelling are silent.

1. **Check the signal:** triggers include raised cabin or suit CO2, SpO2 of 94% or lower together with a Simple Risk Index of 34 or more, systolic pressure below 80, fast heart rate and ECG change. The signal is checked against the personal baseline and artifacts are held back until the signal is clean. The astronaut is told to stop and attach to the stabilization web, and the emergency proxy (a designated crewmate) answers the plain-language symptom questions.
2. **Tests:** point-of-care troponin and ultrasound are requested even without symptoms.
3. **Suspected but unconfirmed (preventive):** the only preventive medicine is **aspirin**, one 325 mg tablet chewed and given by the crew after the proxy agrees. It is not offered with an aspirin allergy, G6PD deficiency or signs of aortic dissection. Calming breathing follows, and the voice stops when the aspirin is given.
4. **Active heart attack (ST elevation or rising troponin):** implied emergency consent applies (a design proposal, shown in the reasoning panel). The voice repeats "Stop all physical activity". Aspirin comes first, then the treating medicines are added through the pump after a 10-second countdown (STOP cancels, Confirm starts now): tenecteplase by weight, and enoxaparin as a proposed addition. Clopidogrel (or ticagrelor with a gene-based switch) and nitroglycerin are given by the crew. Then: prepare manual CPR, proceed with evacuation, attach the CPR patches, calming breathing. The vitals return to normal on screen and a post-therapy plan opens.
5. **Cardiac arrest:** the automatic CPR device counts down and starts, with the AED prompts and the oxygen mask. The pulse returns in the simulation, the vitals normalize and the post-therapy plan opens.
6. **Panic at rest:** after the tests show very low concern for the heart, the emergency proxy is asked about **Ativan** (lorazepam), one 1 mg tablet from the ISS medical kit, with safety checks (heart tests, air and oxygen, other sedatives or opioids, allergy). The astronaut is guided through breathing until Crewmate B reports he feels better.

Within NASA's acute coronary syndrome capability list (2023): antiplatelet therapy, fibrinolytic therapy for a STEMI, nitroglycerin and oxygen. That list names no anticoagulant, so enoxaparin is a proposed addition. Aspirin 325 mg, nitroglycerin 0.4 mg, lorazepam (Ativan) 1 mg, metoprolol XL 50 mg and lisinopril 10 mg are on the ISS medication list. NASA's form also assigns removal to definitive care for every acute coronary syndrome case.

The pump, the consent flow and the implied-emergency-consent rule are design proposals that need ethical and clinical validation. They are simulated here. A loose-sensor demo shows how artifacts are held back, and a genes demo switches clopidogrel to ticagrelor.

## Limits

Simulated data only. Projections are labeled as projections, not diagnoses. Medication doses are intentionally left to the physician protocol. Not clinically validated.
