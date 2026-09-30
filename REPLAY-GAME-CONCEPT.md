# REPLAY

## Working Title

**REPLAY**

Previous concept name: **Echo**

The new title better reflects the defining mechanic:

> **Every physical gesture the player performs is recorded and later repeats automatically.**

This document focuses especially on the key design question:

> How can this mechanic remain interesting for an entire game instead of being a clever five-minute novelty?

---

# 1. Concept Summary

REPLAY is a physics-action puzzle game in which the player directly influences objects with simple gestures.

The twist is that every gesture becomes part of the world's future behaviour.

A swipe performed now is replayed after a fixed delay.

Then it repeats again.

And again.

The player's previous actions gradually become an automated machine.

The player is therefore doing two things at once:

1. solving the immediate physical problem
2. programming future behaviour through their own gestures

The core fantasy is:

> **Build a machine out of your own past actions.**

---

# 2. Core Interaction

The initial prototype should use one extremely simple gesture:

## Swipe

A swipe creates a directional force through the world.

Objects intersecting that swipe receive an impulse.

Examples:

- swipe upward beneath a ball to knock it upwards
- swipe sideways to deflect a moving object
- swipe through several objects to affect all of them

The game records:

- swipe path
- direction
- timing
- strength

After a fixed replay period, the gesture occurs again automatically as a visible **ghost gesture**.

The ghost gesture then continues repeating at the same interval.

---

# 3. Fundamental Rule

Suppose the repeat interval is **4 seconds**.

The player performs:

- 1.0s: swipe right
- 2.3s: swipe up

The world subsequently performs:

- 5.0s: automatic right swipe
- 6.3s: automatic up swipe
- 9.0s: automatic right swipe
- 10.3s: automatic up swipe
- 13.0s: automatic right swipe
- 14.3s: automatic up swipe

The player is creating a repeating physical programme.

---

# 4. Why This Can Become More Than a Gimmick

The game must not simply accumulate infinite gestures.

That would eventually become noisy, incomprehensible and impossible to balance.

Long-term depth comes from treating recorded gestures as **limited programmable resources**.

The game gradually evolves through three stages:

## Stage 1 — React

The player uses swipes to solve immediate problems.

The first repeat is surprising and useful.

## Stage 2 — Plan

The player deliberately places gestures knowing they will recur.

They start thinking:

> “I want an upward push here every four seconds.”

## Stage 3 — Compose

The player builds small repeating systems.

The challenge becomes arranging several repeating gestures so the world keeps functioning with minimal intervention.

This is the long-term game.

---

# 5. The Replay Track

The player should have a small, readable sequence of active recorded gestures.

For example:

- maximum 3 active echoes early
- maximum 4 later
- perhaps 5 in advanced challenges

Never allow unlimited recordings in the main game.

When the limit is reached, creating a new gesture either:

- replaces the oldest
- requires the player to choose one to remove
- or is temporarily blocked

Which behaviour is best should be tested.

The player must always be able to understand:

- what gestures are active
- where they occur
- when they will repeat next

---

# 6. Ghost Communication

Every recorded gesture has a persistent but subtle world-space preview.

A ghost line can indicate:

- path
- direction
- next activation
- sequence number

Shortly before replay:

- the ghost brightens
- a small pulse travels along the path
- optional haptic/audio cue warns the player

The game must never surprise the player because a gesture became invisible or impossible to remember.

The challenge should come from managing consequences, not from forgetting hidden state.

---

# 7. Primary Game Structure

A level is a small physical machine.

The player must get payloads through it by combining:

- live swipes
- previously recorded swipes
- environmental systems
- timing

The best levels should reach a point where the player can **stop touching the screen** and watch their sequence successfully operate.

That moment is the equivalent of watching a solved Rube Goldberg machine.

---

# 8. Core Objectives

Possible objectives include:

- keep a ball airborne
- route payloads to a goal
- deliver multiple objects in sequence
- keep a machine functioning for a target duration
- strike several switches in the correct order
- protect a fragile object
- maintain a repeating production cycle

The objectives should favour periodic behaviour.

That makes replaying gestures naturally useful.

---

# 9. Environmental Systems

These should interact with recorded gestures rather than becoming separate mechanics.

## 9.1 Trampolines

Recorded swipes can repeatedly knock payloads onto trampolines.

Useful for establishing cycles.

## 9.2 Wrap Holes

Objects can leave one side of the chamber and re-enter elsewhere.

This allows an object to repeatedly cross the same ghost swipe.

## 9.3 Leaf Blowers

Continuous force modifies paths between replay events.

A repeated swipe may only work because airflow bends the object back into place.

## 9.4 Buttons

A repeated swipe can periodically knock an object onto a switch.

## 9.5 Hatches

Open and close according to button state or timers.

This produces phase-based puzzles.

## 9.6 Rotating Arms

Recorded pushes can synchronise with rotating machinery.

## 9.7 Moving Platforms

A gesture only affects something when its repeat timing coincides with the platform position.

## 9.8 Fragile Objects

Prevent indiscriminate swiping.

A recurring gesture that once helped may later become dangerous.

---

# 10. Long-Term Difficulty Model

The game should become harder through **temporal interaction**, not by simply increasing speed.

Difficulty dimensions:

- number of active echoes
- longer sequence before success
- environmental motion
- multiple payloads
- phase differences
- different object masses
- temporary switches
- dangerous old gestures
- narrower safe timing windows
- multiple simultaneous objectives

The player is effectively solving both:

- space
- time

---

# 11. Campaign Progression

## World 1 — Meet Your Past

Goal: understand repetition.

### Level 1
One ball.

One swipe sends it into a goal.

The level ends before replay occurs.

### Level 2
Same idea, but the goal requires the swipe to occur a second time.

The ghost repeats automatically.

The player understands the mechanic.

### Level 3
Player must position the first swipe so both its immediate and replayed versions are useful.

### Level 4
Two swipes.

### Level 5
First situation where a replay can hurt the player.

---

## World 2 — Build a Rhythm

Introduce small repeating systems.

### Example
A ball moves around a square chamber.

The player creates:

- upward swipe
- right swipe
- downward swipe

Their repeating sequence keeps the ball circulating.

The puzzle succeeds when the player maintains the cycle long enough.

The player learns:

> My gestures can become machinery.

---

## World 3 — Timing

Introduce moving platforms, hatches and pulsed fans.

The same ghost gesture now behaves differently depending on where the environment is in its cycle.

Players learn phase relationships.

---

## World 4 — Multiple Objects

Introduce two payloads.

A swipe may help one object while endangering another.

The player begins composing gestures that serve several purposes.

---

## World 5 — Editing the Past

Introduce deliberate echo management.

The player can remove one active recorded gesture.

This is not merely an emergency power.

It becomes part of puzzle solving.

Example:

1. create an upward swipe to lift a payload
2. allow it to repeat three times
3. once the payload reaches the upper chamber, remove that swipe
4. record a new sideways gesture
5. continue the machine

This prevents the game becoming permanently cluttered.

---

## World 6 — Programmes

Levels require stable repeating sequences.

The player's goal is no longer simply to get one ball somewhere.

They create an automated routine.

Example:

- feeder releases a ball every four seconds
- ghost swipe launches it
- blower bends its path
- second ghost swipe redirects it
- trampoline sends it through a tunnel
- third ghost swipe lands it in the goal

Once configured correctly, the machine repeatedly succeeds.

---

## World 7 — Interference

Introduce deliberately conflicting echoes.

A gesture is useful at one moment but dangerous at another.

The player must exploit:

- shielding
- movement timing
- temporary barriers
- phase offsets
- echo removal

---

## World 8 — Composition

Late game becomes closer to physical programming.

The player sees complex moving environments and must design a repeating gesture sequence.

Success comes from making the whole system stable.

---

# 12. Solving the Long-Term Problem

The central risk is obvious:

> If every action repeats forever, eventually the game becomes chaos.

The design should solve this with **bounded complexity**.

## Rule 1 — Limited Active Echoes

Only a small number exist simultaneously.

Three or four is likely enough for substantial depth.

## Rule 2 — Explicit Editing

Players can deliberately remove or replace echoes.

## Rule 3 — Short Repeat Cycles

The repetition interval should be short enough that players can mentally understand it.

Approximately 3–6 seconds should be explored during prototyping.

## Rule 4 — Stable Levels

Environmental systems should be deterministic.

The player must be able to learn the machine.

## Rule 5 — Echoes Are World-Space Objects

They remain visibly represented.

Nothing important is hidden inside a timeline menu.

## Rule 6 — Campaign Levels Have End States

A puzzle ends before accumulated complexity becomes exhausting.

The endlessly growing version belongs only in a separate challenge mode.

---

# 13. Potential Advanced Mechanic: Delay

Later levels may let the player choose between a small number of predefined repeat intervals.

For example:

- fast: every 3 seconds
- normal: every 5 seconds
- slow: every 8 seconds

Do not introduce this early.

Different periods create richer emergent patterns because gestures fall in and out of phase.

Example:

- swipe A repeats every 3 seconds
- swipe B repeats every 5 seconds

They align every 15 seconds.

This creates deep timing puzzles with very little additional content.

---

# 14. Potential Advanced Mechanic: One-Shot Echo

Some levels may provide a limited echo that repeats only once.

Useful for:

- onboarding
- special challenge design
- reducing complexity

This should be treated as a modifier, not the default mechanic.

---

# 15. Endless Mode

The main campaign should be handcrafted.

A separate replayable mode could provide long-term engagement.

## Endless Machine

Payloads continuously enter the chamber.

The player maintains a limited set of active echoes.

They can:

- overwrite an existing echo
- rescue mistakes with live gestures
- optimise a stable repeating machine

Difficulty increases through:

- faster spawn cadence
- multiple object types
- hazardous payloads
- shifting environmental phases
- additional destinations

The aim is not to accumulate infinite echoes.

The challenge is:

> Keep improving a tiny repeating programme while the workload rises.

That is far more sustainable.

---

# 16. Scoring

Possible scoring dimensions:

## Completion
Solve the level.

## Automation
How long can the puzzle run without additional live input?

## Efficiency
How few active echoes are required?

## Stability
Can the machine process several payloads consecutively?

## Challenge Conditions
Examples:

- solve with only two echoes
- no manual input after the first cycle
- never delete an echo
- process five payloads consecutively
- protect the fragile object

This supports meaningful replay without requiring random level generation.

---

# 17. Daily Challenge

A daily deterministic chamber could work well.

Everyone receives:

- identical layout
- identical physics
- identical payload sequence

Competitive metrics could include:

- longest stable run
- fewest echoes
- least manual intervention
- fastest solution

This naturally rewards mastery.

---

# 18. Failure and Retry

Failure must be fast and informative.

Examples:

- collision
- payload loss
- incorrect delivery
- fragile object destroyed
- machine jams

Retry immediately resets:

- physics state
- active echoes
- timing phase

Players should be able to replay a puzzle within roughly one tap.

---

# 19. Game Feel

Recorded gestures should feel like physical entities.

## Live Gesture

- follows finger precisely
- force is immediate
- short haptic confirms impact

## Recording

- swipe leaves a ghost trail
- trail settles into the world
- subtle tick confirms it has entered the loop

## Before Replay

- ghost trail brightens
- directional pulse moves along it
- optional quiet cue indicates activation is imminent

## Replay

- ghost hand or energy sweep follows the original path
- same force is applied
- physics response is immediate

The replay must feel like:

> “My old action just happened again.”

Not like a hidden script fired.

---

# 20. Prototype Scope

The first prototype should prove whether repeated gestures become satisfying rather than annoying.

## Implement

1. swipe-to-impulse
2. recording
3. one fixed repeat interval
4. maximum three active echoes
5. visible ghost paths
6. manual echo deletion
7. one payload ball
8. walls
9. goal
10. trampoline
11. wall-wrap tunnel
12. leaf blower
13. button
14. hatch
15. fast restart

## Prototype Levels

Build approximately 12–15 test chambers.

Suggested sequence:

1. first replay surprise
2. repeated upward push
3. two-gesture rhythm
4. dangerous replay
5. delete an echo
6. trampoline timing
7. wall-wrap interaction
8. blower interaction
9. button
10. timed hatch
11. two active payloads
12. three-echo automation
13. stable repeating machine
14. limited manual intervention challenge
15. difficult composition puzzle

---

# 21. Prototype Questions

The prototype must answer:

1. Is replaying a gesture immediately understandable?
2. Does watching a useful echo repeat feel satisfying?
3. Can players mentally track three active echoes?
4. Is four too many?
5. What repeat interval feels best?
6. Does deleting/replacing echoes create strategy or feel like administration?
7. Can players deliberately build stable machines?
8. Do they naturally retry to improve them?
9. Does the mechanic remain interesting after 15–20 minutes?
10. Does it generate surprising interactions without becoming unreadable?

---

# 22. Success Criteria

Continue development only if:

- players quickly understand that gestures repeat
- players begin intentionally planning future repetitions
- they can reason about a small set of active echoes
- they enjoy watching a machine operate without touching it
- failure usually produces an immediate idea for improvement
- later puzzles gain depth from timing and interaction rather than extra rules
- the game remains enjoyable after the initial novelty disappears

The critical transformation is:

> **Early game:** “My swipe happened again.”

to:

> **Mid game:** “I need a swipe here every four seconds.”

to:

> **Late game:** “I have programmed this whole machine with three gestures.”

If the prototype achieves that progression, REPLAY has the potential to support a full game.
