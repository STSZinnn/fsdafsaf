# FrostPVP Reborn v4.1.0-beta1 (source / test release)

**Requirements:** Paper 1.21.11, Java 21, Gradle 8.14.

This project builds on the user's v4.0 beta source. Combat abilities live in
`FrostRebornCombat.java`; server events and shared utilities remain in the legacy
classes to preserve items, event behavior, and trust permissions.

## Controls

- Press **F** with a Frost weapon in the main hand to activate its unique active.
- For Frozen Shield or Frozen Totem in the offhand, **F** activates them when the
  main hand has no Frost ability (main-hand weapon takes priority).
- Bow and Crossbow: **F** prepares the next normal projectile; shoot normally.
- Loyalty Trident: **F** prepares a Harpoon throw; press **F** again after hitting
  a target to pull them, even while the trident is still flying/returning.
- Fishing Rod: cast normally; **F** grapples toward an anchored solid block.
  Jump to disengage and keep momentum.
- Frozen Pickaxe: **F** toggles Fortune V/Silk Touch, **Shift+F** toggles 3x3/1x1.
- Twin Blades: equip one in each hand; **F** triggers Eclipse Dance.

## Selected reworks

Sword: Winter's Dance (3 steerable dashes and fast ice crescents on melee hits).
Battleaxe: Glacier Crusher / Fractured Armor.
Spear: Northern Impalement / Arctic Precision.
Bow: Crystal Bloom / Crystalline Arrows.
Crossbow: Shattered Ricochet / Frost Reflection.
Loyalty Trident: Glacial Harpoon / Frozen Tether.
Depths Trident: Stormwake / Static Current.
Firework: Skyhunter's Barrage / Frostflare.
Shield: Glacial Reprisal / Frozen Resilience.
Totem: Frost Sanctuary / Winter's Blessing (does NOT revive).
Fishing Rod: Icebound Grapple / Arctic Landing.
Goat Horn: Call of the Frostbound / Commander's Presence.
Pickaxe: 2 utility mode switches / Miner's Momentum.

Twin Blades are new: Dayblade (gold sword; heavy solar damage, slower, breaks
shields, daytime knockback immunity) and Nightblade (iron sword; speed and extra
reach at night). Eclipse Dance needs both equipped and has a shared cooldown.

## Armor

- Helmet: sneak 5 seconds to reveal nearby players with Glowing for 10 seconds,
  10-block radius, 120-second cooldown.
- Chestplate: +10 maximum health (five hearts).
- Leggings: Fire Resistance.
- Boots: Speed II, +10% movement speed on snow/ice, powder-snow protection.
- Complete set: below 40% health, Winter's Awakening grants Speed III for 5
  seconds and a 3-heart (6 health-points before armor) damaging knockback burst;
  90-second cooldown.

## Existing servers / configuration migration

Back up your **config.yml**, `trusted.yml`, world, and player data first.
On enable, v4.1 retains events, visuals, HUD, trust data and new `reborn.*`
settings, and removes legacy ability settings from config.yml.
You will not find Snowball, Wind Charge, TNT or Flint-and-Steel weapons in the menu.
Their old special attacks are not part of Reborn.

Existing PDC-marked Frost weapons keep their identification tags. Item tooltip
lore is refreshed on player join or through `/frost restyle`.

## Resource pack

Use `FrostPVP_Reborn_v4.1_Combined_Animated_Pack.zip` to see the animated
Frost weapon/armor tooltip backgrounds, Dayblade/Nightblade, and the Sovereign
SMP tooltips/particles. Resource pack is separate from the plugin source ZIP.

## Build with GitHub Actions

Create `.github/workflows/build.yml` in your repository, using the complete
YAML included in this ZIP and repeated in the assistant's reply. Go to Actions,
Run workflow, then download the built JAR from Artifacts.

**Testing status:** Java syntax parsed; YAML and ZIP structure validated.
This environment cannot resolve the Paper API Maven repository, so no complete
Gradle compile or actual Paper server test has been performed. Treat this as a
beta, check the Actions build log, and test on a separate server before upgrading.
