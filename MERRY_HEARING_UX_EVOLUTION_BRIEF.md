# Merry Hearing Now-first UX Evolution Brief

Last updated: 2026-06-02

Prototype entry:

- Version board: https://panstudiollrl-dev.github.io/merry-now-first-prototype/
- v1 prototype: https://panstudiollrl-dev.github.io/merry-now-first-prototype/v1.html
- v2 prototype: https://panstudiollrl-dev.github.io/merry-now-first-prototype/v2.html

This document summarizes the current two web prototype versions and the design thinking behind the shift from v1 to v2. It is intended as context for another AI/design collaborator before generating the next iteration.

---

## 1. Product Framing

Merry Hearing is not being designed as a technical hearing-aid control dashboard.

The core product direction is:

> A calm, now-first hearing support companion for people who open the app when something feels wrong.

The assumed user is often older, may be anxious, may not want to read much, and may open the app only when:

- speech is unclear
- one or both devices are not connected
- sound feels sharp, noisy, or uncomfortable
- they need a real human/audiologist to help

The first screen should therefore reduce panic and decision load. It should not ask the user to inspect technical controls, interpret complex sound charts, or understand hearing-aid configuration concepts before receiving help.

---

## 2. Shared Design Principles So Far

### Problem-first, not feature-first

The user should start from a felt problem:

- I can’t hear clearly
- Won’t connect
- Noise or hiss
- Ask someone

They should not be forced to choose from feature names such as Sound Compass, acoustic analysis, directional microphone, device tuning, or technical logs.

### Low interruption, high reassurance

The app should feel alive and supportive, but not noisy.

Good Merry behavior:

- notices relevant changes quietly
- uses small icon-led cues
- explains why something matters only when needed
- suggests one next action
- confirms what happened after the action

Bad Merry behavior:

- flooding the user with text
- making everything look urgent
- forcing onboarding before use
- creating fake buttons that do not perform actions
- turning passive information into button-shaped visual elements

### Icon first, text second

The user may not want to read long copy. Icons, color, layout, and motion should carry meaning before text does.

Text should be short and functional:

- what Merry noticed
- why it matters
- what the next action is
- what happened after the action

### Stable home base

The Now screen should remain stable. Even if future personalization is added, the first-layer structure should not constantly rearrange in a way that harms user confidence.

Recommendations can be visually emphasized, but should avoid making the user feel that the interface has become unfamiliar.

### Help near the operation area

Guidance, feedback, and error messages should appear near the place where the user is acting. The user should not need to remember where they are, what layer they are in, or where to look for the result.

### Progressive disclosure

Only reveal more detail when the user asks for it or when the next step requires it.

The design should support both:

- first-time or anxious users who need guidance
- experienced users who want fast action

---

## 3. v1 Summary

URL:

https://panstudiollrl-dev.github.io/merry-now-first-prototype/v1.html

### v1 Main Goal

v1 focused on proving the now-first interaction model:

> The user taps a problem card, and the app reveals the relevant next action directly on the same Now surface.

This version intentionally moved away from an earlier confirm-button approach. The problem card itself became the action entry.

### v1 Key Screens / Sections

1. Now / Default
2. Problem card selected state
3. Expanded solution panel
4. Comfort volume control
5. Nearby sound card
6. Care package flow
7. Sent confirmation
8. Care-related support content
9. More / less frequent tools

### v1 Interaction Model

The first layer is built around four large problem cards:

- I can’t hear clearly
- Won’t connect
- Noise or hiss
- Ask someone

When a card is selected:

- the problem list can collapse or give way to a solution card
- the selected card visually changes
- the user can return to the problem list if they tapped the wrong problem
- the user does not need to press an extra “Confirm problem” button

### v1 Important Decisions

#### Remove the confirm problem button

An earlier design used a large button such as:

> Confirm: I can’t hear clearly

This caused confusion because it looked like a CTA but only restated the card selection. The user could not tell why the information was button-shaped.

v1 corrected this by making the problem card itself the selection/action trigger.

#### Keep Sound Compass indirect

Nearby sound remains present, but not as a standalone feature tab. It is framed as environmental awareness:

> Merry is watching nearby speech and noise.

The user should not need to inspect directional sound as a feature.

#### Bring Care into the Now flow

Human help should be reachable without forcing the user into a separate technical care dashboard.

The Ask someone card can package:

- sound environment
- device state
- battery status
- safe setting parameters

### v1 Strengths

- Strong now-first direction
- Clear problem-card model
- Lower decision load than a feature dashboard
- Good brand-feeling visual direction
- Good start on comfort volume and device status
- Care package concept is understandable

### v1 Weaknesses

- Still somewhat flat and static
- Not enough sense that Merry is actively observing and responding
- Some guidance is still text-heavy
- Device reconnect flow is not concrete enough
- Care tab / care package flow can feel like a separate place rather than part of the current need
- Nearby sound is informative, but not yet truly actionable
- Personalization and usage records are not yet represented

---

## 4. v2 Summary

URL:

https://panstudiollrl-dev.github.io/merry-now-first-prototype/v2.html

### v2 Main Goal

v2 keeps the v1 Now-first foundation, but adds companion-like responsiveness:

> Merry should notice context, explain the next step, and give calm, icon-led guidance without overwhelming the user.

### v2 Key Additions

1. Merry noticed cue cards
2. Icon-led dynamic hints
3. Scene-aware safety suggestions
4. Guided reconnect animation
5. More explicit v1-to-v2 explanation
6. Personal Listening Space concept
7. Survey placeholder for future user feedback

### v2 Merry Noticed Cues

Merry can surface small, low-interruption observations such as:

- Right aid seems weak.
- Speech is nearby.
- Busy street detected.

These cues are not alarms. They are quiet invitations to act.

Each cue should ideally include:

- a clear icon
- a short headline
- one reason or implication
- one next action

### v2 Guided Reconnect

The Won’t connect flow now includes a lightweight animated guide.

The goal is to simulate a real Bluetooth/hearing-aid reconnect scenario without overwhelming the user.

Current 1-3 step model:

1. Bring both hearing aids close to the phone
2. Wake the right aid / open the case / restart only if needed
3. Merry confirms both aids are linked

The interaction is intentionally staged:

- selecting Won’t connect reveals the guide
- pressing Start guided reconnect starts the sequence
- the guide gives feedback as it progresses
- the final state says both aids are linked

This is based on common consumer Bluetooth troubleshooting patterns:

- keep device close
- check power/battery
- wake or reset the accessory
- reconnect or re-pair only if needed

### v2 Scene-aware Sound

v2 starts to explore場域辨識:

- busy street
- busy table / restaurant
- clinic / counter speech
- home sound

The point is not just “detect a scene,” but to translate the scene into a safer listening choice.

Example:

> Busy street detected. Merry should keep traffic sounds audible while softening harsh background noise.

This is important because hearing support should not only optimize comfort; it must preserve safety cues.

### v2 Personal Listening Space

Inspired by the usefulness of spatial arrangement in audio tools, v2 introduces a softer and more original concept:

> Personal Listening Space

Instead of copying another product’s “drag people around a spatial audio map” pattern, Merry can explore:

- keeping front speech close
- placing harsh noise farther away
- preserving traffic/safety sounds
- showing the user what Merry is protecting

This should remain hearing-health oriented, not gaming/chat oriented.

### v2 Strengths

- More alive and responsive than v1
- Stronger sense of care and companionship
- Better use of icons and motion
- Better explanation of what changed from v1
- Reconnect flow is more concrete
- Scene-aware safety starts to connect hearing aid value to real life
- Maintains low-interruption tone

### v2 Weaknesses

- Still based mostly on design reasoning, not real user data
- Personalization is conceptual only
- Usage-record-driven recommendations are not implemented
- The survey is only a placeholder
- Some icon language still needs refinement and testing
- Guided reconnect is a simulated flow, not connected to real Bluetooth/device APIs
- Need more evidence from hearing-aid users, clinicians, and app usage records

---

## 5. From v1 to v2: What Changed

### v1 was about task structure

v1 asked:

> Can the app stop being a control panel and become a problem-first help surface?

The key design move was to make the four problem cards the primary entry.

### v2 is about perceived support

v2 asks:

> Can Merry feel like it is noticing, caring, and guiding without becoming intrusive?

The key design move is adding contextual cues and guided feedback around the same stable problem-card base.

### v1 reduced decision load

v1 removed unnecessary confirmation and made actions more direct.

### v2 reduces interpretation load

v2 uses icons, motion, and short feedback so users do not need to interpret technical states.

### v1 made help reachable

v1 included the Care Package concept.

### v2 makes help feel situated

v2 tries to show why help is needed now:

- right aid is weak
- speech is nearby
- street sound should remain audible

### v1 treated Nearby sound as awareness

v1 made Nearby sound less like a standalone Sound Compass feature.

### v2 treats scene awareness as care

v2 reframes environment detection as:

- protect the front voice
- soften harsh background
- keep traffic audible
- help the user understand what Merry is doing

---

## 6. Research / Book Principles Integrated So Far

The current direction is influenced by universal design and self-service interface principles:

### Users differ by experience, not only age

Do not design only for “older users” or only for “new users.”

Users may be:

- first-time users
- anxious users
- occasional users
- experienced users
- clinician-supported users
- users with low technical confidence

The interface must support a shared core path while allowing shortcuts or deeper tools later.

### Memory load must be reduced

The user should not need to remember:

- what layer they are in
- what they selected earlier
- what a technical term means
- where to find the next action

The app should make the next step visible and predictable.

### Too many options should be grouped or hidden

Common options should remain visible. Less common options should move to More or advanced areas.

However, hiding options must not make minority users unable to complete their task.

### Recommendations can reduce cognitive load

Recommendations are useful when users do not know what they need.

But recommendations should:

- be based on behavior/context when possible
- not overtake the whole interface
- not rearrange stable elements too aggressively
- visually belong to the same design family as normal options

### Dynamic prompts can create companionship

Dynamic prompts can make the app feel alive and supportive.

But they should be:

- timely
- quiet
- near the relevant operation
- visually clear
- dismissible or ignorable
- not constantly alarming

### Icons and images need validation

Icons are not automatically understandable. They should be tested with multiple users.

An icon should not replace text unless it is extremely familiar. The best pattern is often:

> icon + short label + brief outcome

---

## 7. Open Questions for Future Versions

### 1. Should Merry ask onboarding questions at first use?

Potentially yes, but not as a forced long wizard.

Better direction:

- minimal first-use setup
- optional guided setup
- ask only what improves immediate support
- allow skipping
- progressively collect preferences through use

Possible first-use questions:

- What situations are hardest for you?
- Do you often need help in restaurants, streets, clinics, or home?
- Do you prefer Merry to suggest changes automatically or ask first?
- Who can Merry contact when you need help?

Avoid:

- long medical-feeling questionnaire
- asking for data before the user experiences value
- making the user feel tested

### 2. Can Merry use Apple Health or device data?

This may be valuable but requires privacy/legal/product review.

Potentially useful data:

- age range
- hearing-related settings
- mobility or activity context
- location category, if allowed
- device usage records

Design principle:

> Do not depend on external data for the core experience. Use it only to improve recommendations when permission exists.

### 3. How should usage records affect the UI?

The strongest future direction is behavior-driven personalization:

- frequently used help cards can be recommended
- repeated scenes can become shortcuts
- repeated care-package sends can become easier
- common sound adjustments can become suggested profiles

But the stable Now screen should remain recognizable.

### 4. How do we avoid functional fixedness?

Users may expect the app to behave like previous control panels. The design should not trap them in old concepts such as:

- tabs as feature categories
- Sound Compass as a feature to inspect
- manual tuning as the main action

The app should teach a new pattern:

> Tell Merry what feels wrong; Merry guides the safest next step.

### 5. How should expert users move faster?

Possible expert paths:

- saved listening presets
- frequent action shortcuts
- advanced sound controls under More
- clinician/debug details behind Care or More

But expert paths should not dominate the first screen.

---

## 8. Suggested Direction for v3

v3 should not simply add more screens.

It should test whether Merry can become more useful while staying calm.

Recommended v3 themes:

### Adaptive cue priority

Show no more than 1-3 Merry noticed cues at a time.

Prioritize by:

- safety
- device failure
- speech importance
- repeated user behavior

### Icon system refinement

Create a coherent icon language for:

- device connection
- battery
- speech
- noise
- traffic
- care / audiologist
- safe setting
- learning / guide

Each icon should pair with a short label and outcome.

### Guided micro-flows

Build small flows like:

- reconnect right aid
- make front speech clearer
- soften harsh noise
- send care package
- keep traffic audible

Each flow should:

- show the current step
- show what Merry is checking
- show success/failure feedback
- allow returning to Now

### Non-intrusive personalization

Add a small “Merry often helps you with…” recommendation area.

Example:

> Merry often helps you in busy streets. Keep traffic sounds audible?

This should be visually softer than the main problem cards.

### Feedback collection

Add survey questions after prototype use:

- Did the app feel supportive?
- Did Merry interrupt too much?
- Could you find what you needed?
- Did the icons help before reading text?
- Did you understand what would happen after tapping?
- Would you trust Merry to suggest a safer setting?

---

## 9. Guidance for Claude / Next Collaborator

Please do not turn this into:

- a medical dashboard
- a technical tuning console
- a playful game UI
- a generic health app
- a marketing landing page

Please preserve:

- low-interruption tone
- mature premium health-product feeling
- Merry brand colors
- large readable controls
- stable Now-first structure
- icon-led short guidance
- user confidence and reversibility

When proposing changes, evaluate them against:

1. Does this reduce cognitive or memory load?
2. Does this make the next action more predictable?
3. Does this help both anxious first-time users and experienced users?
4. Does this avoid unnecessary reading?
5. Does this make Merry feel caring without being noisy?
6. Does this preserve safety in real-world listening scenes?
7. Does this avoid making passive information look like a button?
8. Does this keep the user in control?

---

## 10. One-sentence Evolution Summary

v1 proves that Merry can be a problem-first help surface; v2 begins turning that surface into a quiet companion that notices context, guides the next step, and supports the user without overwhelming them.
