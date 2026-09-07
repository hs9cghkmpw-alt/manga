# FLUX-Ready Prompts (panel-by-panel, English)

Written specifically for **free FLUX tools (FLUX.1-schnell / FLUX.1-dev via free UIs)**,
which in most free deployments accept **one single prompt box and no negative-prompt field**,
and generate **one image per call**.

This changes the production approach from the page-level prompts in
`scripts/image_prompts.md` / `image_prompts_en.md`:

- **Generate one panel at a time**, not a full multi-panel page in one shot. Multi-panel
  consistency (same character, same page layout) is not reliable from a single diffusion call.
- **Fold every "must not" constraint into the positive prompt itself** (no separate negative
  prompt field assumed). `scripts/negative_prompts.md` stays useful as a manual checklist when
  reviewing FLUX output, but do not rely on pasting it into a negative-prompt box that may not
  exist.
- **Assemble the page afterward**: crop/arrange the generated panel images into the panel layout
  described in `scripts/full_script.md` (a comic-page compositing step — e.g. Photopea, GIMP,
  Canva, or an HTML/CSS grid rendered to an image), then typeset the Japanese text on top with a
  proper font, per `scripts/00_style_guide.md` §8. Do not expect FLUX to lay out multiple comic
  panels with correct reading order in one image.

## How to use this file

Each panel line below is written to be combined as:

```
[GLOBAL] + [ERA TAG block for that panel's character(s)] + [PANEL line]
```

Copy GLOBAL once, copy the matching ERA block, then copy the one PANEL line you need, and paste
all three together as a single prompt into FLUX. A fully worked example is given after GLOBAL.

---

## GLOBAL (prepend to every single prompt, no exceptions)

```
Full-color Japanese educational-manga illustration, single panel, in the style of Japanese
"Shinken Zemi"-style learning manga: clean medium-weight digital linework, digital cel-style
coloring, character always placed inside a fully rendered, specific background/scene (never a
floating icon portrait, never a plain gradient background), expressive but natural facial
expression and posture, believable human proportions, no text, no lettering, no speech bubbles,
no Japanese or English writing anywhere in the image, not a photo, not 3D render, not a
PowerPoint-style graphic, not a medical brochure illustration, not chibi/gag-manga exaggeration,
not a close-up icon portrait, high detail, clean composition, single consistent light source.
```

## Worked example (P00, panel 1)

```
Full-color Japanese educational-manga illustration, single panel, in the style of Japanese
"Shinken Zemi"-style learning manga: clean medium-weight digital linework, digital cel-style
coloring, character always placed inside a fully rendered, specific background/scene (never a
floating icon portrait, never a plain gradient background), expressive but natural facial
expression and posture, believable human proportions, no text, no lettering, no speech bubbles,
no Japanese or English writing anywhere in the image, not a photo, not 3D render, not a
PowerPoint-style graphic, not a medical brochure illustration, not chibi/gag-manga exaggeration,
not a close-up icon portrait, high detail, clean composition, single consistent light source.
Adult Japanese man, early-to-mid 30s, short neat dark brown hair, calm oval face with a firm
jawline, straight eyebrows, warm but slightly tired eyes, wearing plain casual clothes (soft
knit sweater, neutral color), average athletic build, standing by a window indoors, looking out
thoughtfully with a calm expression, a faint translucent light film subtly overlaying one side of
his face like a soft veil, warm subdued color palette, medium-wide shot showing him and the
window/room around him.
```

---

## ERA / CHARACTER TAG BLOCKS

Append the block(s) matching who appears in the panel, right after GLOBAL.

### [CHILD] Yuta, age ~7-9
```
A Japanese boy, about 7 to 9 years old, short black hair, round soft facial features, average
child build, wearing simple casual Japanese children's clothes (t-shirt and shorts or a simple
home outfit).
```

### [ELEM] Yuta, elementary school
```
A Japanese boy, about 9-11 years old, short black hair, oval face starting to lengthen from a
child's roundness, wearing a casual elementary-school outfit or home clothes, energetic posture.
```

### [JHS] Yuta, junior high school
```
A Japanese teenage boy, about 13-14 years old, short-to-medium black hair slightly messy, lean
build, wearing a Japanese junior-high boys' school uniform (dark gakuran-style buttoned jacket).
```

### [CADET] Yuta, Ground SDF technical high school / young SDF member
```
A young Japanese man, late teens to early 20s, short regulation-cut dark hair, fit athletic
build, alert posture, wearing a Japan Ground Self-Defense Force cadet or duty uniform (khaki/
olive-green working uniform), no visible insignia detail needed.
```

### [SDF-COMMS] Yuta, SDF communications duty
```
A young Japanese man in his early-to-mid 20s, short regulation-cut dark hair, fit build, wearing
a Japan Ground Self-Defense Force working uniform, focused expression, standing near
communications equipment (racks, cables, a control panel) in an indoor technical facility.
```

### [ADULT] Yuta, present day
```
An adult Japanese man in his early-to-mid 30s, short neat dark brown hair, calm oval face with a
firm jawline, warm but sometimes tired eyes, average-to-athletic build, wearing plain modern
casual or business-casual clothing appropriate to the scene.
```

### [MOTHER]
```
An adult Japanese woman, generic warm and tired appearance appropriate to a mother in her 30s-40s
for the era shown, simple modest clothing, no invented distinguishing details beyond what the
scene requires.
```

### [BROTHERS]
```
Three young Japanese boys, younger than the protagonist, simple casual children's clothes,
playing energetically, generic child appearance without invented distinguishing details.
```

### [STEPFATHER]
```
An adult Japanese man, generic plain appearance appropriate to the era, neutral/tense expression,
simple everyday clothing, no invented distinguishing details.
```

### [SUPERVISOR-KIND]
```
An older Japanese adult in a Japan Ground Self-Defense Force uniform appropriate to a supervising
officer, warm patient expression, approachable posture.
```

### [SUPERVISOR-HARSH]
```
An older Japanese adult in a Japan Ground Self-Defense Force uniform appropriate to a supervising
officer, stern impatient expression, arms crossed or pointing posture.
```

### [WIFE-CHILD]
```
An adult Japanese woman (Yuta's wife) with a warm gentle expression in simple modern casual
clothes, and a young Japanese child, both in a warm home setting, generic appearance without
invented distinguishing details.
```

### [SUPPORT-FIGURE]
```
An adult Japanese support professional (visiting nurse or employment-support staff), calm
attentive expression, simple professional casual clothing, warm but composed posture, keeping a
respectful physical distance.
```

---

## PANEL LIST (page → panel → tag + line)

Format: `Page / panel — [TAG(s)] panel description line (append after GLOBAL + TAG block).`

### P00 — Title
1. [ADULT] — see Worked Example above.
2. [CHILD] — Small silhouette-style scene hinting at a lonely childhood memory, backlit, low
   detail, mostly silhouette.
3. [CADET] — Small silhouette-style scene of military training, backlit, mostly silhouette.
4. [ADULT] [WIFE-CHILD] — Small silhouette-style scene of a warm present-day family moment,
   backlit, mostly silhouette.

### P01 — Childhood among brothers
1. [CHILD] [BROTHERS] — Lively Japanese family living room, Yuta playing energetically on the
   floor with his three younger brothers, warm indoor lighting, toys scattered around.
2. [CHILD] [MOTHER] — Mother scolding Yuta with a stern but ordinary parental expression, Yuta
   looking down with a slightly unhappy face, home interior background.
3. [CHILD] [BROTHERS] — One younger brother affectionately clinging to Yuta's arm, both smiling
   faintly, home interior background.

### P02 — Age 7, the first separation
1. [CHILD] [MOTHER] — A peaceful family dinner table with both parents and grandparents present,
   warm but slightly desaturated flashback tone, traditional Japanese home dining room.
2. [CHILD] — Yuta peeking around a hallway corner at blurred adult figures talking with serious
   postures in the next room, dim hallway lighting, focus on Yuta's worried face.
3. [CHILD] — Yuta's small figure seen from behind, standing alone in front of an unfamiliar
   elementary school gate, overcast cool-toned sky.
4. [CHILD] — Yuta sitting at a desk in an unfamiliar classroom full of blurred unfamiliar
   classmates, looking down, cool desaturated palette.

### P03 — Elementary school, what he's good at
1. [ELEM] — Classroom scene, Yuta raising his hand eagerly and confidently during a math lesson,
   chalkboard with simple math shapes in the background (no legible text).
2. [ELEM] — Yuta at a desk at home late at night, deeply focused on a workbook, a wall clock
   showing a late hour, warm desk lamp lighting.
3. [ELEM] [MOTHER] — A family member gently telling Yuta to go to sleep, Yuta smiling sheepishly,
   warm home interior at night.

### P04 — Elementary school, struggles and workaround
1. [ELEM] — Yuta panicking in his bedroom in the morning, searching frantically through papers on
   his desk and floor, messy room, morning light.
2. [ELEM] — A teacher gently pointing out a forgotten item to Yuta in a classroom, ordinary
   everyday tone, not harsh.
3. [ELEM] — Yuta stuffing an overstuffed school backpack completely full of textbooks, backpack
   visibly bulging, bedroom setting.
4. [ELEM] — Yuta walking to school with a slightly proud confident expression, backpack full,
   morning street background.

### P05 — Junior high, lively days and reading the real rules
1. [JHS] — Classroom scene, Yuta making several classmates laugh with an animated expression and
   gesture, lively classroom background.
2. [JHS] — Yuta sitting at his desk in front of a stack of unsubmitted assignment papers, relaxed
   unconcerned expression.
3. [JHS] — Yuta leaning over to copy from a friend's notebook quickly at a desk, tense hurried
   posture, classroom background.
4. [JHS] — Yuta checking a wristwatch with a confident smirk, hallway background, morning light.
5. [JHS] — A friend energetically waking Yuta up who is still half asleep in bed, bedroom
   background, morning light.

### P06 — Age 12, the second separation
1. — Tense, dim home interior, a broken teacup or plate on the floor implying an argument just
   happened, no people directly shown, unsettling empty composition, cool desaturated tones.
   (Deliberately avoid depicting any person or violent action directly.)
2. [JHS] [MOTHER] — A young teenage Yuta standing protectively in front of his mother, determined
   worried expression, dim home interior, cool desaturated tones.
3. [MOTHER] — Mother and a young teenage figure walking away from a house at night, seen from
   behind, streetlights, quiet residential street.
4. [JHS] — Close-up of young teenage Yuta's complicated expression, a mix of relief and unresolved
   pain, cool desaturated tones, plain background.

### P07 — The broken father-son attempt
1. [JHS] [STEPFATHER] — Young teenage Yuta awkwardly approaching an adult male figure, hesitant
   body language, plain home interior.
2. [JHS] — Close-up of young teenage Yuta's face, mouth slightly open, trying and failing to say
   a word, conflicted expression.
3. [JHS] [STEPFATHER] — A silent, cold dinner table with two place settings, no eye contact
   implied by empty chairs/posture, subdued lighting.
4. [JHS] — Yuta's back, walking away carrying a bag/suitcase toward a new school building in the
   distance, overcast sky.

### P08 — "I have to hold it together" — the mask begins
1. [JHS] [MOTHER] — A large, quiet panel: mother's face with a strained, exhausted expression,
   speaking softly to young teenage Yuta who faces her, dim indoor lighting, emotionally weighty
   composition.
2. [JHS] — Close-up of young teenage Yuta's face receiving those words, a flicker of childlike
   softness draining from his expression into a more composed, guarded look.
3. [JHS] — Young teenage Yuta's reflection in a window or mirror, a faint translucent light-film
   "mask" effect subtly overlaying half of his reflected face, quiet moody lighting.

### P09 — Struggling with self-management, and a system that fits
1. [ADULT] — A messy desk covered with papers, Yuta flustered and searching, realizing he forgot
   something, home or office setting.
2. [ADULT] — Yuta carefully pushing a coin into a metal can with the lid taped shut, close-up on
   hands and can, warm domestic lighting.
3. [ADULT] — A small still-life time-lapse-style panel: the same can shown fuller and heavier,
   coins visible through a slot, simple warm-lit composition.

### P10 — Ground SDF technical high school, enrollment
1. [CADET] — A line of nervous young cadets in uniform standing at attention in front of a school
   gate, Yuta among them, overcast institutional atmosphere, khaki/gray palette.
2. [CADET] [SUPERVISOR-HARSH] — Early morning roll call, a strict instructor shouting orders at a
   row of standing cadets, hard-edged lighting, khaki/gray palette.
3. [CADET] — Physical training scene, cadets including Yuta doing push-ups or running in
   formation, sweat and effort visible, hard-edged khaki/gray palette.

### P11 — The structure of shared responsibility
1. [CADET] — A group of cadets reacting urgently to a discovered mistake, several figures moving
   into action together, institutional interior.
2. [CADET] — Yuta's own mistake being covered by fellow cadets working together, cooperative body
   language, institutional interior.
3. [CADET] — A group of tired but satisfied cadets including Yuta after solving a problem
   together, camaraderie visible in relaxed posture and small smiles.

### P12 — How he relates to rules
1. [CADET] — Yuta calmly and precisely following a regulation-based task (folding gear, checking
   equipment), focused composed expression.
2. [CADET] — Yuta sternly pointing out a rule violation to another cadet, firm serious expression.
3. [CADET] [SUPERVISOR-HARSH] — Yuta arguing back logically and calmly against an older superior
   who looks visibly annoyed, tense confrontational composition.
4. [CADET] — Close-up of Yuta's frustrated, unconvinced expression after being scolded, plain
   institutional background.

### P13 — Communications work, a problem effort can fix
1. [SDF-COMMS] — Yuta focused intently on communications equipment (racks, cables, a control
   panel), technical indoor facility.
2. [SDF-COMMS] — Warning lights and urgent activity around communications equipment, a sense of
   trouble/incident, dramatic lighting.
3. [SDF-COMMS] — A small team of SDF members working together at the equipment to restore
   communications, cooperative focused postures.
4. [SDF-COMMS] — Yuta writing in a notebook afterward, a determined, slightly frustrated
   expression, equipment visible in the background.

### P14 — Reassignment, what wasn't handed down
1. [SDF-COMMS] — Yuta receiving a document (transfer order) from another uniformed figure,
   institutional office interior.
2. [SDF-COMMS] — Yuta standing alone in front of a desk stacked with incomplete handover
   documents, empty office around him, isolated feeling.
3. [SDF-COMMS] [SUPERVISOR-KIND] — An older supervising officer with a warm, patient expression
   showing Yuta something on equipment or paperwork, reassuring collaborative posture.

### P15 — Caught in the middle, the gears start to break
1. [SDF-COMMS] [SUPERVISOR-HARSH] — A new supervising officer taking over a desk/position, visibly
   different colder atmosphere compared to before, office interior.
2. [SDF-COMMS] [SUPERVISOR-HARSH] — The new supervisor pointing/speaking sternly at Yuta, who
   looks strained and unfairly pressured, tense office interior.
3. [SDF-COMMS] — A dim nighttime scene, Yuta on duty during a night shift, exhausted posture,
   institutional facility at night.
4. [SDF-COMMS] — Close-up of Yuta's deeply exhausted face, the translucent light-film "mask"
   effect visibly cracking/uneven across his face, dim lighting.

### P16 — The period of psychological breakdown
1. [ADULT] — A quiet, heavily desaturated panel: Yuta sitting alone on the floor or a chair,
   posture curled inward, plain dim room, low contrast muted colors.
2. [SDF-COMMS] — A semi-transparent, faded flashback-style panel echoing his earlier focused
   effort at communications equipment, ghostly overlay quality.
3. — (diagram/explanation panel — leave for later typeset overlay; if generating, use a plain
   muted abstract background with no figures and no text, suitable as a caption-box background.)

### P17 — What is "brain fatigue"? (explanation page)
1. — Abstract diagram-style panel: a simple head silhouette with soft glowing icons (a speech
   bubble shape, a calendar shape, two overlapping figures, a question mark) stacking up inside
   it, plain background, muted colors, no text, suitable as a background for a later text overlay.
2. [ADULT] — Yuta in a conversation with another person that has no clear resolution, his
   posture gradually more drained across the exchange, plain indoor setting.
3. [ADULT] — Close-up of Yuta's face near his limit, tired heavy-lidded eyes, muted lighting.
4. [ADULT] — A large panel with Yuta's figure small in frame and generous empty plain background
   space reserved for later emphasis lettering, subdued color, quiet heavy mood.

### P18 — Career after the SDF
1. [SDF-COMMS] — Small panel: Yuta doing communications/maintenance work in SDF uniform.
2. [ADULT] — Small panel: Yuta in business casual clothes listening attentively to a client across
   a table, notebook in hand, office setting.
3. [ADULT] — Small panel: Yuta teaching a beginner at a computer, pointing at a monitor, warm
   classroom/office setting.
4. [ADULT] — Small panel: Yuta doing technical work at outdoor telecom/network equipment (a base
   station or utility cabinet), practical work clothes.
5. [ADULT] — Small panel: Yuta in a counseling meeting at a table with another person, employment
   support office setting, listening posture.

### P19 — From supporting others to being supported
1. [ADULT] [SUPPORT-FIGURE] — Yuta, in a past employment-support staff role, sitting across a
   table from another person in a counseling posture, supportive attentive expression, office
   setting.
2. [ADULT] [SUPPORT-FIGURE] — Mirrored composition: now Yuta is the one sitting in the counseled
   seat, being listened to by another support staff figure, same style office setting.
3. [ADULT] — Close-up of Yuta's face registering quiet realization of this reversal, plain office
   background.

### P20 — Outlets, looking for a replacement
1. [ADULT] — A dim, warm-toned flashback bar/izakaya scene, a younger adult Yuta with a drink,
   contemplative rather than celebratory mood, other blurred patrons in background.
2. [ADULT] [WIFE-CHILD] — A present-day home scene overlapping visually with the memory (can be
   drawn as a simple side-by-side or faded transition composition), warm home lighting.
3. — Abstract diagram-style panel: simple icons (a closed eye, a pause symbol, an exhale motion
   line) arranged cleanly, plain muted background, no text, suitable as a caption-box background.
4. [ADULT] — Yuta looking out a window with an open, questioning expression, plain quiet
   background, soft lighting, deliberately unresolved mood.

### P21 — Family and hobbies
1. [ADULT] [WIFE-CHILD] — A warm family dinner table scene, Yuta with his wife and child, cozy
   home interior lighting.
2. [ADULT] — Night fishing scene at a harbor in Otaru, Yuta happily reeling in a fish under
   string lights or a lantern, dark blue night sky, sea in background.
3. [ADULT] — Yuta sitting at a shogi board across from another person, focused but slightly
   novice posture, quiet room setting.
4. [ADULT] — Yuta at a home desk working on a laptop/PC, sticky notes or a notebook with simple
   diagrams nearby (no legible text), warm desk lamp lighting.
5. [ADULT] — Small close-up panel of Yuta's thoughtful, slightly conflicted expression while
   looking at a phone or photo, implying thoughts of his mother, plain warm background.

### P22 — Understanding over caregiving
1. [ADULT] [SUPPORT-FIGURE] — Yuta politely waving off an offer of help with a determined
   independent expression, everyday setting.
2. [ADULT] — Yuta sitting alone, visibly overwhelmed and unable to speak or reach out, isolated
   posture, quiet room, muted lighting. (Avoid any depiction implying need for constant physical
   care.)
3. [ADULT] [SUPPORT-FIGURE] — A support professional standing at a respectful distance, calm
   attentive expression, warm but composed body language, everyday setting.
4. — Abstract diagram-style panel: five simple clean icons in a row (a speech bubble, a clock/wait
   symbol, a checklist, a calendar, an empty circle for "do nothing"), plain background, no text,
   suitable as a caption-box background.

### P23 — Things to keep thinking about together
1. [ADULT] [MOTHER] [SUPPORT-FIGURE] — A symbolic gathering around one table: Yuta, a family
   member, and a support/medical professional figure, warm collaborative atmosphere, home or
   office setting.
2. — Abstract diagram-style panel: a clean simple list-style layout of eleven small placeholder
   icons/blocks arranged in a grid, plain background, no text, suitable as a caption-box
   background for later typeset list.

### P24 — The future, living with understanding
1. [ADULT] [SUPPORT-FIGURE] — Yuta engaged positively at a support program/workplace setting,
   focused determined posture, warm lighting.
2. [ADULT] — A softly rendered, slightly lighter-toned imagined scene of Yuta explaining or
   advising another person at a desk, gentle "hoped-for future" quality to the lighting/color.
3. [ADULT] [WIFE-CHILD] [SUPPORT-FIGURE] — Large final panel: Yuta surrounded by family, a
   colleague, and a support figure in a warm gathering scene, natural relaxed unguarded
   expression, no mask light-film effect at all, the warmest, brightest palette in the whole set.

---

## Notes for the ChatGPT review step

This file, together with `scripts/full_script.md` (facts + dialogue) and
`scripts/00_style_guide.md` (style rules), is meant to be readable directly from GitHub for
review before any image is generated. When reviewing:

- Confirm each panel prompt matches the corresponding fact/scene in `scripts/full_script.md`.
- Confirm no prompt implies a fact not present in `CLAUDE.md` (e.g. no invented dialogue, no
  graphic violence, no "needs constant care" framing).
- Confirm no prompt asks FLUX to render Japanese text directly.

## Notes for page assembly after FLUX generation

1. Generate every panel image for a page individually with FLUX using the prompts above.
2. Arrange the panel images into the panel layout described in `scripts/full_script.md` for that
   page (panel sizes/order can be adapted for visual flow, per `scripts/00_style_guide.md` §5).
3. Overlay speech bubbles / narration boxes / captions and typeset the Japanese text from
   `scripts/full_script.md` using a proper Japanese font (never AI-rendered text).
4. Save the assembled page into `pages/draft/`, then run it through the review steps in
   `pages/draft/README.md` before promoting to `pages/final/`.
