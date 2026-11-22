# ⚡ 3D Industrial Sensor & Wiring Lab

An interactive, browser-based **3D Industrial Automation & Sensor Wiring Simulator** built with Three.js and Tailwind CSS. Designed for students, technicians, and automation engineers to practice wiring 24V DC industrial sensors, Festo-style relay modules, indicator units, and output loads using color-coded banana plug leads with real-time nodal circuit solving.

---

## ✨ Key Features

- **Interactive 3D Workbench & Dual DIN Rails**: Drag and drop or tap components from the palette to snap them onto two 35mm aluminum DIN rails.
- **3-Color Banana Plug Wiring System**: Connect terminal sockets using **Red (`+24V`)**, **Black (`Signal / Common`)**, and **Blue (`0V Negative`)** leads with realistic 3D catenary wire physics.
- **Live Nodal Circuit Solver & Short-Circuit Protection**:
  - Automatically propagates `+24V` and `0V` potentials across linked buses, relay contacts, and switches.
  - Detects direct `+24V` to `0V` faults and triggers an immediate short-circuit protection alert.
- **Live Probe Multimeter HUD**: Hover or tap any socket in the 3D scene to inspect real-time terminal states (`+24.0 V`, `0.0 V`, `OPEN`, or `FAULT!`).
- **Pre-Built Example Circuits**: Load 5 ready-to-test industrial circuits from the top **Presets** dropdown.
- **Undo / Redo & Workbench Reset**: Full action history (`Undo` / `Redo` with `Ctrl+Z` / `Ctrl+Y` shortcuts) plus a one-click `Reset` to clear the workbench.
- **Desktop, Tablet & Mobile Responsive Layout**:
  - Slide-over **Parts** and **Inspect** drawers for phones and tablets.
  - Dedicated **Pan L/R**, **Angle**, and **Zoom** camera sliders alongside **Wire & Drag** and **3D Orbit** touch modes.

---

## 🧰 Included 3D Components

### Power & Switching
| Component | Description | Terminals |
| :--- | :--- | :--- |
| **24V DC Power Supply** | Regulated 24V DC / 5A bench supply with mains rocker switch & status LED | `+24V DC`, `0V Common`, `Earth GND` |
| **Festo 3-Relay Module (`K1–K3`)** | 3 independent relay coils with 4 changeover contact sets each (`11/12/14` – `41/42/44`) | `A1`, `A2`, `COM (x1)`, `NC (x2)`, `NO (x4)`, `+24V`/`0V` pass-through |
| **Indicator Lamp & Buzzer Unit** | 8 illuminated indicator lamps (`1–8`), integrated buzzer, and linked `+24V` / `0V` buses | `L1–L8 (+/-)`, `Buzzer (+/-)`, `+24V` Bus, `0V` Common Buses |

### Industrial Sensors (Switchable `PNP +24V` / `NPN 0V` Output)
- **Inductive Proximity Sensor**: Detects ferrous metal targets placed in front of the sensing face.
- **Capacitive Proximity Sensor**: Detects non-metallic targets such as liquids, plastics, and glass.
- **Optical Proximity Sensor**: Diffuse optical sensor with sensing cone that detects any object brought near the lens.
- **Ultrasonic Distance Sensor**: Adjustable target distance slider (`5 cm – 100 cm`) with a `≤ 30 cm` trip threshold.
- **Mechanical Roller Limit Switch**: Dry-contact mechanical switch with `COM`, `NO`, and `NC` terminals.
- **Thermal Probe Switch**: Adjustable temperature probe (`10°C – 120°C`) with a `≥ 60°C` setpoint trigger.

### Output Loads
- **24V Pilot Tower Lamp**: High-visibility yellow beacon with 3D point-light illumination.
- **24V Alarm Buzzer**: Piezo alarm with animated vibrating plunger and synthesized Web Audio tone.

---

## 🔌 Standard 3-Wire Sensor Pinout

All 3-wire active sensors follow standard IEC / Festo terminal conventions:
1. **Left Socket (Red)**: `+24V DC` Supply (`Brown`)
2. **Middle Socket (Blue)**: `0V Negative` Return (`Blue`)
3. **Right Socket (Black)**: `Signal / Common OUT` (`Black`) — sources `+24V` in **PNP** mode or sinks to `0V` in **NPN** mode when triggered.

---

## 🎮 Controls & Shortcuts

| Action | Desktop | Mobile / Tablet |
| :--- | :--- | :--- |
| **Mount Component** | Drag from left palette onto DIN rail or click item | Tap **Parts** → Tap any component |
| **Connect Banana Wire** | Click source socket, then click destination socket | Tap source socket, then tap destination socket |
| **Disconnect Wire** | Click directly on any 3D wire | Tap directly on any 3D wire |
| **Trigger Sensor / Switch** | Click sensor on rail or use **Inspector** controls | Tap sensor on rail or open **Inspect** drawer |
| **Rotate / Pan / Zoom Camera** | Right-click drag (or switch to **3D Orbit**) & scroll wheel | Use **Pan L/R**, **Angle**, **Zoom** sliders or **3D Orbit** mode |
| **Undo / Redo** | `Ctrl + Z` / `Ctrl + Y` or top toolbar buttons | Tap `↶` / `↷` buttons in header |

---

## 🛠️ Tech Stack

- **3D Rendering & Physics**: [Three.js (r128)](https://threejs.org/) + `OrbitControls`
- **Styling & Responsive UI**: [Tailwind CSS](https://tailwindcss.com/)
- **Audio Feedback**: Native Web Audio API (synthesized relay clicks & alarm buzzer)
- **Architecture**: Zero-build, single-file static web application (`index.html` / `sensor_wiring_lab.html`) ready for GitHub Pages, Netlify, or Vercel.
