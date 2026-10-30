# Wolfblood: Game Design Document

**Status:** Draft v0.1, awaiting Alex's review
**Last updated:** 2026-10-30

This document is the single source of truth for what Wolfblood is. If the game and this doc disagree, one of them gets fixed. Anything marked **🟡 Open question** still needs a decision from Alex; each one comes with a recommended default that we will use unless Alex says otherwise.

---

## 1. The pitch

A chainmail-clad shieldmaiden, a **Wolfblood**, is the sole survivor when her longship is ambushed. She washes ashore with nothing but her shield and has to fight her way home through a Norse world that has been touched by something old, cold, and wrong.

**Genre:** 2D side-scrolling action platformer with RPG mechanics, in the vein of Hollow Knight and Metroid, but more linear than Metroid.

**The feel in one line:** fast, aggressive, and punishing. She is fragile, her enemies are tough, and she wins by playing smart: combos, priming and detonating, perfect blocks, and choosing a good build.

### Pillars

These are the things every design decision should support.

1. **Kick in the front door.** Aggression is rewarded. Healing comes from hitting things, rage comes from fighting, and stealth is a bonus, never a requirement.
2. **Skill over stats.** She is fragile and enemies are resilient. Perfect blocks, smart combos, and positioning matter more than gear numbers.
3. **The shield is everything.** Her shield is her most important item and a core part of both defense and offense.
4. **A build, not a toolbox.** She can't use every ability at once. The player picks a loadout and changes it to suit the challenge.
5. **Norse myth, Lovecraftian dread.** Familiar Viking iconography twisted by cosmic horror.

---

## 2. Setting and tone

- **World:** Scandinavian and pagan mythology (draugr, jötnar, seiðr magic, runestones, the Nine Realms) bleeding into Lovecraftian horror: things from the deep sea and the void of Ginnungagap, cults that worship them, and people slowly changed by them.
- **Enemies:** humanoids, undead, cultists, monsters, and eldritch horrors. **No ordinary animals** as enemies. Wolf-, bear- and raven-themed things are the heroine's side.
- **Structure:** a journey home. Mostly a left-to-right path through connected regions, with side branches, secrets, and some backtracking when new abilities open routes. More linear than Metroid.
- **Story delivery:** light. A short opening, a few characters, item descriptions, and environmental storytelling. Who ambushed the longship, and why, is a mystery she uncovers on the way.

**Draft region list** (placeholder, to be refined):

| # | Region | Idea |
|---|---|---|
| 1 | The Wreck Shore | Tutorial. Beach, wreckage, sea caves, drowned things crawling out of the surf. |
| 2 | Rotwood | Dark pine forest, cultist camps, first stealth sections. |
| 3 | The Barrow Hills | Burial mounds full of draugr. Underground tunnels. |
| 4 | Frostspine Pass | Mountain climb, vertical platforming, jötunn-touched enemies. |
| 5 | The Drowned Fjord | A flooded town where the sea-things have taken hold. |
| 6 | Home | Her village, and whatever is waiting there. |

---

## 3. The heroine

- **Fragile.** She dies in a few hits from normal enemies. Most of her survival comes from blocking, parrying, and movement.
- **Resources** (see section 5): Health, Mana, Rage, and Block Charges.
- **Starts with:** her shield, and whatever she finds on the beach as her first weapon (recommended: a sword, since it is the easiest weapon to learn with).

---

## 4. Controls and movement

### Movement

Movement should feel tight and responsive, because the platforming is moderate to difficult.

- **Run** with quick acceleration and stopping.
- **Jump** with variable height (tap for short, hold for high). Includes standard forgiveness tricks that make platformers feel fair: a few frames of "coyote time" after running off a ledge, and remembering a jump press made just before landing.
- **Dash:** a quick burst in any of 8 directions, usable on the ground and once in the air. Short cooldown.
- **Backstep:** a quick hop backward while facing forward, for creating space without turning your back on an enemy.
- **No invincibility frames** on dash or backstep (see 🟡 Q1). Dodging is about getting out of the way, not phasing through attacks.
- **Later, from talents and items:** wall jump, air dash, double jump, dashing through enemies.

### Controls

Both controller and mouse + keyboard are supported from the start. Buttons will be rebindable.

| Action | Controller (Xbox layout) | Keyboard + mouse |
|---|---|---|
| Move / aim | Left stick | A / D (W / S to aim up and down) |
| Jump | A | Space |
| Attack | X | Left mouse |
| Block / parry | LB (hold to block) | Right mouse |
| Dash | RB | Shift |
| Backstep | B | Ctrl |
| Weapon ability | Y | Q |
| Spell 1 / 2 | LT + face button | E / R |
| Throw | RT | Middle mouse or F |
| Rage form | Click both sticks | V |
| Mead horn | D-pad down | H |
| Menu / map | Start / Back | Esc / Tab |

---

## 5. Resources

| Resource | What it does | How you get it back |
|---|---|---|
| **Health** | Run out and you die. | Damaging enemies (main way), mead horn, some spells. |
| **Mana** | Pays for spells. | Slowly over time, faster while hitting enemies. |
| **Rage** | Builds while fighting. Higher rage means more damage but less defense. At full, she can transform. Also pays for weapon abilities (see 🟡 Q3). | Dealing and taking damage. Slowly drains outside combat. |
| **Block Charges** | Each normal block or parry uses one. Start with 3. | Regenerate over time. |

### Rage: the berserker meter

- Fighting fills the rage bar. Hitting enemies fills it most, taking hits fills it a little.
- **The more rage, the more damage** she deals with attacks and spells, **and the more damage she takes.** Running hot is powerful and risky.
- Rage drains slowly when she is out of combat.
- **At full rage, she can trigger a Rage Form** for a limited time (see section 9).

### Healing

- **Main healing comes from dealing damage**, so the way to survive is to attack.
- **🟡 Q5: How exactly?** Recommended default: every hit heals a small amount, and detonations and finishers heal more. This keeps the pace fast and never asks her to stop and heal mid-fight. (The alternative is Hollow Knight's approach: hits fill a meter, then you hold a button to spend it on healing.)
- **Mead horn:** a reliable emergency heal with a few charges that refill at rest points. Drinking takes a moment, so it is risky mid-fight.
- **Healing spells** may exist but should be rare and part of a build choice.

---

## 6. Combat

### Core idea

Enemies are **much** tougher than she is. Hitting an enemy over and over with a basic attack works, but slowly and dangerously. **Efficient combat comes from combos and from priming and detonating.**

### Basic attacks and combos

- Each weapon has a basic attack chain (for example, a 3-hit combo), plus up, down, and air variations.
- Mixing in abilities, throws, and spells at the right time builds bigger damage than any single move.

### Priming and detonating

Some attacks **prime** a target with a status effect. Other attacks **detonate** that status for a big payoff. How it detonates depends on the weapon type that sets it off.

**First example: Static**
- **Prime:** a lightning javelin does little damage but applies **Static** to the enemy, which slows them.
- **Detonate with a hammer:** area damage that hits everything nearby.
- **Detonate with a sword or spear:** high single-target damage.

More prime types will follow the same pattern. Ideas: **Bleed** (stacks of bleed that can be ripped open), **Frost** (chill that can be shattered), **Rune marks** (seiðr magic).

### Damage types and armor

| Damage type | Rule |
|---|---|
| **Physical** | Reduced by armor. The normal case. |
| **Blunt** (hammers) | Ignores some armor. Extra damage to shields. |
| **Bleed** | Ignores all armor. Damage over time. |
| **Lightning** | Deals **bonus** damage the more armor the target has. |

### Stagger (proposed)

**🟡 Q6.** Recommended default: enemies have a hidden **stagger** meter that combos and heavy hits fill up. When it fills, the enemy is briefly stunned and takes extra damage. This makes "tough enemies" feel like a puzzle to crack rather than a sponge to chip away at, and gives hammers and bear-style attacks a clear job.

### Blocking and parrying

Her shield, and to a lesser extent her weapon, can block and parry.

- **Block:** hold the block button to raise the shield. A blocked hit does reduced damage and uses **1 block charge.**
- **Parry:** tap block just as an attack lands to deflect it. Reduced damage, uses **1 block charge,** and briefly opens the enemy up.
- **Perfect block / perfect parry:** hit the timing exactly right and she takes **no damage.** (Whether a perfect one uses a charge is 🟡 Q2.)
- **Block charges:** start at 3 and regenerate over time. With no charges, she can't block; hits go straight through.
- **The trade-off:** each shield and weapon has a damage reduction value and a perfect window.
  - **High reduction** (heavy shield) means a **smaller** perfect window. Safe for normal blocks, hard to perfect.
  - **Low reduction** (light buckler) means a **larger** perfect window. Risky if you miss, rewarding if you're good.

### Shields on enemies

- Shielded enemies block her attacks from the front.
- **Spear in the shield:** throwing a spear into an enemy's shield sticks it there, and the weight stops them blocking for a few moments. This works by default, no talent needed.
- Hammers do extra damage to shields. Getting behind a shielded enemy also works.

### Throwing

- Spears and axes can be thrown as well as used in melee.
- **🟡 Q7: Does she lose her weapon when she throws it?** Recommended default: no. She carries a few spare javelins or throwing axes matching her weapon type, shown as **throw charges** (say, 2) that regenerate over time. Her main weapon stays in her hand. This keeps throws a regular part of combos without awkward weapon pickups.

### Ranged versus melee

Weapons and spells are tagged **ranged** or **melee** so talents can reference them (for example, *Opening Volley*: damaging an enemy with a ranged attack or spell increases the critical strike chance of your next melee attack or spell against them).

- **🟡 Q4: Can ranged attacks be used in melee range?** Recommended default: yes, at first. We playtest it and only add a restriction if point-blank throwing turns out to be the best move every time.

### Stealth (minor)

- Enemies have a visible **field of view** cone.
- Reaching an enemy while unseen allows a **sneak attack** that does heavy damage or opens with a big stagger.
- Some places (tall grass, shadows, alcoves) let her **hide.**
- Stealth is always optional. She is a kick-in-the-front-door kind of fighter.

---

## 7. Equipment

### Slots

| Slot | Role |
|---|---|
| **Weapon** | Main damage. Sets her attack style and grants a weapon ability. |
| **Shield** | Block reduction, perfect window, block charges, shield bash. Her most important item. |
| **Cloak** | Movement and stealth (e.g. hiding, air control). |
| **Pauldrons** | Defense and rage. |
| **Gauntlets** | Attack speed, throws, combos. |
| **Greaves** | Dash and jump. |
| **Amulet** | Magic and special effects. |

Items have different stats, and some have **special abilities** (e.g. a shield that releases a shockwave on perfect block).

### Weapon types

| Weapon | Speed | Damage | Special |
|---|---|---|---|
| **Sword** | Fast | Lower | Best mobility while attacking. Detonates for big single-target damage. |
| **Spear** | Medium | Medium | Long reach. Throwable. Detonates for single-target damage. Pins shields. |
| **Axe** | Medium | Medium-high | Throwable. Leans toward bleed. |
| **Hammer** | Slow | High | Ignores some armor, wrecks shields, detonates in an area. |

### Build limits

She can't have everything active at once. **Recommended default loadout:**

- 1 weapon (with its ability) and 1 shield
- 2 spell slots
- 1 rage form
- Her 5 armor pieces

All of these can be swapped at rest points. These numbers are a starting point for playtesting.

---

## 8. Spells

Spells cost mana and are tagged ranged or melee. **Starting examples:**

- **Lightning Javelin** (ranged): low damage, applies Static (primes).
- **Thunderclap** (melee): short-range burst that detonates Static.
- **Blood Rune** (melee): next few hits apply Bleed.
- **Seiðr Ward** (self): brief shield bubble, or a small heal.

More spells will come with the talent trees.

---

## 9. Rage forms

When the rage bar is full, she can transform for a limited time. Only one form is equipped at a time.

| Form | Fantasy | Plays like |
|---|---|---|
| **Wolf** (the default) | She becomes a giant wolf. | Fast, mobile, lunges, bleeds, dashes through enemies. |
| **Bear** | A huge, tanky bear. | Slow, very tough, big knockback hits, ignores crowd control. |
| **Valkyrie** | No shapeshift. She is wreathed in lightning and wings. | Her own weapons and spells are empowered. For players who don't want to transform. |

The **Wolf** form is available from the start. Bear and Valkyrie are unlocked later (via talents or story).

---

## 10. Talents and leveling (reserved for later)

**Not in the first playable versions.** The game will be built so these can be added cleanly later.

- **Talent points** come from defeating bosses and from exploration (hidden shrines, etc.).
- **Four small trees with high-impact talents,** rather than lots of small number tweaks:

| Tree | Theme |
|---|---|
| **Wolf** | Mobility, bleeds, slows, dashing through enemies. |
| **Bear** | Damage reduction, slow hard-hitting attacks, knockback and stun, crowd-control resistance. |
| **Valkyrie** | Lightning magic. |
| **Raven** | Aerial mobility: wall jumps, air dash, etc. |

- Rage forms tie into the trees (the Bear tree improves the Bear form, and so on).
- **Example talent:** *Opening Volley* (see section 6).
- **🟡 Q8: Leveling.** Does she also gain levels and stats from XP, or are talent points the only progression? Recommended default: talent points and gear only, no XP levels. It fits "skill over stats" and keeps balance simpler. We can revisit when the trees are designed.

---

## 11. Enemies

| Tier | Description |
|---|---|
| **Weak** | Fodder. Die to a short combo. Often come in groups. |
| **Normal** | Tougher than her. Need real combos or tactics. |
| **Elite** | Mini-bosses: special moves, big health, guard areas. |
| **Boss** | Region bosses with multiple phases. Give talent points. |

Each enemy type has clear strengths and weaknesses (armored, shielded, fast, flying, ranged, magic-resistant), so different builds handle them differently.

**Starter enemy ideas:**

- **Drowned Thrall** (weak): shambling sea-corpse.
- **Shieldbearer Draugr** (normal): blocks from the front. Teaches the spear-in-shield trick.
- **Cult Seer** (normal): ranged caster who hangs back.
- **Barnacled Huscarl** (elite): heavily armored. Teaches lightning and hammers.
- **First boss:** something big that crawled out of the sea and sank her ship.

---

## 12. Death, checkpoints, and saving

- **🟡 Q9.** Recommended default: **runestone shrines** act as checkpoints. Resting at one refills health, mead and mana, lets you change your loadout, and respawns normal enemies. On death, she returns to the last shrine with no other penalty for now. A Hollow Knight-style "recover what you lost" penalty can be added later if the game needs more stakes.
- The game autosaves at shrines.

---

## 13. Art, audio and UI

- **Style:** retro pixel art, 16-bit to 32-bit inspired (think SNES or GBA, with a bit more animation).
- **Resolution:** the game is drawn at a low fixed resolution (recommended **480×270**) and scaled up with crisp pixels. That size scales perfectly to 1080p and 4K.
- **UI:** clean and minimal. Health, mana, rage and block charges in a corner, with no clutter.
- **During early milestones** everything uses simple placeholder shapes and colors. Real art comes once the game feels good to play.
- **Audio:** placeholder sound effects early. Music and proper sound later.

---

## 14. Tech stack (recommended)

The goal is a game Alex can **play in a web browser by clicking a link,** that works with a controller or a keyboard and mouse, and that Claude can build and test directly.

| Part | Choice | Why |
|---|---|---|
| Game engine | **Phaser 3** | A mature, free 2D game engine for the browser, with built-in physics, controller support, animation and tile maps. |
| Language | **TypeScript** | JavaScript with type checking, which catches mistakes early in a big project. |
| Build tool | **Vite** | Fast, simple bundling and a local preview. |
| Level editor | **Tiled** | A free, popular map editor. Levels can be drawn visually, and Alex could even edit them. |
| Hosting | **GitHub Pages** | Free. Every update to the main branch rebuilds the game at a link like `palexanderemmerson-glitch.github.io/Woolfblood`. |
| Pixel art | Aseprite or free asset packs | Later, once mechanics are solid. |

**The alternative considered:** Godot 4, a full game engine with a visual editor that can also export to the web. It is excellent, but its web builds are heavier and it is built around clicking through an editor, which suits a hands-on developer more than a prompt-driven workflow. Phaser keeps everything in code, so Claude can build, test and screenshot the game directly.

---

## 15. Roadmap

Small steps, each ending in **something you can play at the link.** Each milestone gets its own thread and pull request.

| # | Milestone | You can play... |
|---|---|---|
| **M0** | **Setup** | An empty game screen at the public link, with controller and keyboard detected. |
| **M1** | **Movement** | A test room with run, jump, dash and backstep, tuned to feel tight. |
| **M2** | **First blood** | Sword combo, a training dummy and a Drowned Thrall, health, damage, healing-on-hit, death and respawn. |
| **M3** | **The shield** | Block, parry, perfect block and parry, block charges, and the Shieldbearer Draugr. |
| **M4** | **Rage and throwing** | The rage bar, throw charges, spear-in-shield, and the full HUD. |
| **M5** | **Prime and detonate** | Lightning Javelin and Static, sword and hammer detonations, armor and damage types, stagger. |
| **M6** | **Gear and builds** | Equipment slots, item stats, the loadout screen at shrines. |
| **M7** | **The Wreck Shore** | The first real level: shrines, stealth basics, three enemy types and an elite. |
| **M8** | **First boss and the Wolf** | The first boss fight and the Wolf rage form. |
| Later | | Talent trees and leveling, Bear and Valkyrie forms, more regions, the art and audio pass, story. |

---

## 16. Open questions, with recommended defaults

Unless Alex says otherwise, we go with the recommendation.

| # | Question | Recommended default | Why |
|---|---|---|---|
| Q1 | Should dash or backstep give invincibility frames? | **No.** Dodging means moving out of the way. Talents can add "dash through enemies," but not invulnerability. | Keeps the shield as the main defense and makes perfect blocks the skill to master. |
| Q2 | Does a perfect block or parry use a block charge? | **No, it's free by default.** A low-level talent could make perfect blocks *restore* a charge or give extra rage. | She is fragile and the game is hard, so mastering timing should always pay off. |
| Q3 | Weapon abilities: stamina or rage? | **Rage. No stamina bar.** | One fewer bar to watch, and it creates a real choice: spend rage on abilities now, or save it for a rage form. Spending rage also lowers her rage, which brings her defense back up. |
| Q4 | Can ranged attacks be used in melee range? | **Yes for now.** Revisit after playtesting. | Easier to add a restriction later than to guess now. |
| Q5 | How does healing from damage work? | **Each hit heals a little; detonations and finishers heal more.** | Fast pace, no stopping to heal. |
| Q6 | Do enemies have a stagger meter? | **Yes.** | Makes tough enemies feel like puzzles, and gives heavy weapons a clear role. |
| Q7 | Does she lose her weapon when she throws it? | **No.** She carries spare throwing weapons as regenerating throw charges. | Keeps throws in combos without fiddly pickups. |
| Q8 | XP levels, or only talent points? | **Only talent points and gear.** | Fits "skill over stats" and keeps balance simpler. |
| Q9 | What happens on death? | **Back to the last shrine, no other penalty for now.** | Simple to start; more stakes can be added later. |
| Q10 | Tech stack? | **Phaser 3 + TypeScript, hosted on GitHub Pages.** | Playable at a link, controller support, fully buildable by Claude. |
