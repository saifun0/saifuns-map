# Saifun's Map

**A fast, minimalist, clean-room Minimap & Fullscreen World Map built specifically for Minecraft 1.7.10 and GT: New Horizons (GTNH 2.9+).**

Zero Mixins · Angelica & Shaders Ready · Java 8 & Java 17–25 (LWJGL3ify) · Full English, Russian & Simplified Chinese (`en_US` / `ru_RU` / `zh_CN`) Localization · `LGPL-3.0`

![Saifun's Map World Map with GTNH Ore Veins](docs/worldmap_gtnh_ores.png)

| World Map & Entity Radar | Quick Menu (`Y`) & Minimap HUD |
| :---: | :---: |
| ![World Map & Entity Radar](docs/worldmap_terrain.png) | ![Quick Menu & Minimap HUD](docs/quickmenu_hud.png) |

---

## Highlights

- **Crisp, True-Color Terrain Engine**
  - Samples actual top-face block PNG textures directly through Minecraft's `IResourceManager` (fully Angelica-safe and resource-pack-aware — fixes inaccurate vanilla `MapColor` hues on modded blocks such as BoP Ash Block or RWG stained clay).
  - Directional NW→SE topographic shading, cast cliff/tree shadows, ambient occlusion, transparent water depth gradients, and compressed `.smap` disk caching.
  - **Dimension-Aware GTNH Scanning:** stable height-independent Nether & bedrock-roofed cavern scanning (with disk persistence and lava shoreline shading), clean open-sky scanning for The End, Galacticraft/GalaxySpace planets & orbital stations, and smart ceiling-based Cave Mode for Overworld & Twilight Forest.
- **Native GTNH Integrations (Zero Mixins)**
  - **GTNH Navigator (`1.1.x`):** full support for **VisualProspecting** (Ore Veins, Underground Fluids), **TCNodeTracker** (Thaumcraft Nodes), and **ServerUtilities** (Chunk Claims & Chunk Loading) with tactical focus dimming, ore tooltips, double-click tracking, `Delete` depletion/unclaim, NEI `R`/`U`, and right-click context actions.
  - **Tracked Target Icons & 3D Beacons:** tracked GTNH ore veins and Thaumcraft nodes display their **exact native overlay icon** with a golden beacon column in 3D and on the minimap, while background waypoints dim cleanly out of the way.
  - **ShareWhereIAm & JourneyMap Compatible:** bidirectional chat sharing with clean in-place clickable `[Save] [Edit] [Beacon]` cards and one-click JourneyMap waypoint import.
- **Minimalist Waypoints & 16 Crisp GTNH Pixel-Art Icons**
  - 16 original `11×11` (`9×9` + 1px dark outline) Minecraft-style icons tailored for GTNH (Pin, Home, Pickaxe, Sword, Portal, Flag, Star, Chest, Farm, Death Skull, Oil Spout, Power, Factory Gear, Thaumcraft Node, Diamond, Rubber Tree), interactive HSV Color Picker, and exact timestamped automatic Death waypoints (`Death (HH:mm:ss)`).
  - User-created custom groups with inline `+` creation, LMB filter, RMB instant group visibility toggle, live search, distance/name/date sorting, and two-click **Clear Deaths**.
  - Right-click any waypoint on the World Map to Teleport, Edit, Hide, Share, or Delete.
- **Hybrid Multiplayer & Quick 3D Pings (`acceptableRemoteVersions = "*"`)**
  - **Client-only friendly:** works on any server without requiring server installation (bridges through ShareWhereIAm/chat).
  - **Server-assisted bonus:** installing the same jar on the server unlocks long-range teammate radar (no FairPlay restrictions), native animated 3D Quick Pings with soft sound chime & countdown, and 1-click waypoint group sharing.
- **Zero-Clutter Controls & Async PNG Export**
  - Compact **Quick Menu (`Y`)** toggles every map overlay & setting with live minimap preview, keeping your keyboard free.
  - Full Settings screen with smooth sliders and live minimap preview.
  - Asynchronous PNG map exporter (`/smap export` or Settings → *Export Map PNG*) saves tight-cropped explored dimension maps to `screenshots/saifunsmap/` with a clickable chat link.

---

## Default Keybindings

Only essential keys are bound by default; every other toggle remains available in **Controls → Saifun's Map** (unbound by default) and inside the **Quick Menu (`Y`)**:

| Action | Default Key |
|---|---|
| Open World Map | `J` |
| Quick Map Menu | `Y` |
| Quick Add Waypoint | `B` |
| Open Waypoints Menu | `U` |
| Enlarge Minimap (Smooth) | `Z` |
| Minimap Zoom In / Out | `=` / `-` |
| Quick 3D Ping | *(Unbound — bind in Controls, or RMB on World Map)* |

## Client Commands

- `/smap share [name]` — Share your current location in chat.
- `/smap export` — Export the explored map of your current dimension to PNG (`screenshots/saifunsmap/`).

## Installation

1. Drop `saifunsmap-<version>.jar` into your `.minecraft/mods/` folder (works cleanly alongside or in place of JourneyMap).
2. *(Optional)* Place the same jar in the server's `mods/` folder to enable long-range teammate radar, native 3D pings, and 1-click group sharing.

## Building from Source

```bash
./gradlew build
```

Built jars are output to `build/libs/saifunsmap-<version>.jar`.

---

## Русская версия (Краткое описание)

**Saifun's Map** — быстрая, минималистичная мини-карта и полноэкранная карта мира для **Minecraft 1.7.10** и **GT: New Horizons (2.9+)** без единого Mixin (полная совместимость с **Angelica**, шейдерами и **Java 8 / 17–25**).

### Основные возможности
- **Точные цвета блоков и рельеф:** прямое считывание PNG-текстур блоков через `IResourceManager` (корректные цвета для BoP, RWG, GregTech и ресурспаков даже под Angelica), направленные тени, прозрачность воды, стабильный скан Незера и корректная работа в Энде, Twilight Forest и космосе Galacticraft / GalaxySpace.
- **Полная интеграция с GTNH:** нативная поддержка слоёв **VisualProspecting** (рудные жилы, жидкости, `Delete` для пометки выкопанной жилы, двойной клик / ПКМ для отслеживания с 3D-маяком и родной иконкой руды), **TCNodeTracker** (ноды Thaumcraft с иконкой аспекта), **ServerUtilities** (приват и прогрузка чанков) и **ShareWhereIAm**.
- **Минималистичные метки:** 16 чётких пиксельных иконок `11×11` в стилистике Minecraft и GTNH (булавка, дом, кирка, меч, портал, флаг, звезда, сундук, ферма, череп смерти, нефть, энергия, шестерня завода, узел Thaumcraft, алмаз, дерево/гевея), точное время в метках смерти, пользовательские группы с вкл/выкл по ПКМ, живой поиск, сортировка, «Удалить смерти», контекстное меню ПКМ на карте мира и импорт меток из JourneyMap.
- **Гибридный мультиплеер:** работает на любом сервере без установки на сервер; при установке на сервер дополнительно включаются дальний радар друзей, анимированные быстрые 3D-пинги со звуком и шаринг целой группы меток в 1 клик.
- **Удобство:** быстрое меню по **`Y`**, карта мира по **`J`**, слайдеры настроек с живым превью и асинхронный экспорт карты в PNG (`/smap export`).

---

## License

This project is licensed under the **GNU Lesser General Public License v3.0 (LGPL-3.0)** — see [LICENSE](LICENSE).
