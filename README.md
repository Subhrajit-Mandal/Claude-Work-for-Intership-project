# Claude Work for Internship Project

Three interactive, single-file web apps: a **monthly spending planner**, a **parliamentary voting simulator**, and a **four-stroke piston engine explorer**.

Each one was built by **Claude** (Anthropic's AI assistant) from a plain-English prompt I wrote. Each is one self-contained `.html` file. There is nothing to install, no build step and no server. Download a file, open it in a browser, and it runs.

## Projects at a glance

| Project | File | Prompt | What it is |
|---|---|---|---|
| Next Month's Money Plan | [`Money spending.html`](Money%20spending.html) | [`Money Spending.txt`](Money%20Spending.txt) | Budget planner with projected vs. actual spending, duplicate detection and a savings-goal slider |
| Parliament Division Simulator | [`Parliment.html`](Parliment.html) | [`Parliament.txt`](Parliament.txt) | Simulates a parliamentary vote, from the seating chart to the result sheet |
| Pistonarium | [`pistonarium.html`](pistonarium.html) | [`pistonarium.txt`](pistonarium.txt) | Interactive 3D four-stroke engine with live graphs and multi-cylinder timing |

## How to run

1. Clone the repo, or download the files you want:
   ```bash
   git clone https://github.com/Subhrajit-Mandal/Claude-Work-for-Intership-project.git
   ```
2. Double-click any `.html` file. Use a recent version of Chrome, Edge, Firefox or Safari.

None of the files load external scripts, fonts or images, so they work offline.

---

## 1. Next Month's Money Plan

> *Plan it, track it, and find out whether future-you is thrilled or filing a complaint.*

**What it does.** You list your expected expenses for the month, then record what you actually spent. The app compares the two and tells you whether you hit your savings goal.

**How to use it**

1. **Add an expense.** Enter a name, pick a category, and fill in the projected and actual amounts (in ₹). Press **Add** or hit Enter.
2. **Set a savings goal.** The slider trims your projected spending by 0–60% (default 10%) to give you a goal-adjusted budget.
3. **Filter by category.** The dropdown in the Overview card limits the numbers to one category, or **All**.
4. **Read the results.** The Overview card shows:
   - Projected spending
   - Actual spending
   - Difference (projected minus actual; green is under, red is over)
   - Savings goal amount
   - Goal-adjusted budget
   - Total saving, or extra expenditure, against your goal
5. **Check the verdict.** A one-line summary tells you where you stand.
6. **Spot duplicates.** Entries with the same name and category (case-insensitive) are highlighted. **Remove duplicates** keeps the first one.
7. **Experiment.** **Load sample** fills in example data, and **Reset all** wipes everything after a confirmation prompt.

**Categories:** Housing, Food, Transport, Utilities, Health, Entertainment, Shopping, Education, Other.

**Your data.** Entries and the slider position are saved in your browser's `localStorage`, so they survive a refresh. They never leave your device. Clearing your browser data clears the plan too.

---

## 2. Parliament Division Simulator

> *Where motions are tabled, whips are cracked, and nobody reads the bill.*

**What it does.** You build a fictional legislature, give the Speaker a motion, and run a randomised vote. You can watch the chamber recolour from party colours to Aye, Nay and Abstain.

**How to use it**

1. **Set up the province.**
   - Name the legislature and set the total number of members (3–500).
   - Add up to 10 parties. Each has a colour, a name, a seat count and a **Govt** checkbox.
   - Party seats must add up to the total, or the **Convene** button stays disabled. **Auto-balance seats** fixes the arithmetic for you.
2. **Write the motion.** Type your own topic, or click **Surprise me** for a random one.
3. **Choose the rules.**
   - **Passing rule:** simple majority (Aye > Nay), absolute majority (more than half the House), or two-thirds of the House.
   - **Rebellion rate:** 0–50%, the chance that a member votes against their party's line.
   - **Free vote:** drops the whips, so every member votes at random.
4. **Convene the House.** This shows the province overview (members, parties, government vs. opposition seats, seats needed for a majority). It also shows the Speaker presenting your motion and a semicircular seating chart, with government benches on the left and opposition on the right.
5. **Call the division.** The seats pulse while the "bell rings", then the votes are cast.
6. **Read the result sheet.** It shows the verdict, an Aye/Nay/Abstain bar, and a per-party table of votes and rebels. Use the **Party colours** and **Vote colours** tabs to switch the chamber view.
7. **Go again.** **Re-run the vote** repeats the same motion with fresh randomness, and **New motion** takes you back to the topic box.

**How votes are decided.** Government members lean Aye and opposition members lean Nay. Every member has a 5% chance of abstaining, and the rebellion rate flips some votes. This is a simulation for fun and teaching, not a prediction of anything real.

---

## 3. Pistonarium

> *Where four-stroke cycles go to have a bang.*

**What it does.** It's an interactive 3D model of a four-stroke engine that you can rotate and take apart in the browser. It draws the pistons, connecting rods, crankshaft, valves, spark plug and the changing gas in each cylinder, with live graphs underneath.

**How to use it**

- **Look around.** Drag to orbit and use the mouse wheel or a pinch gesture to zoom. The **Front**, **Side** and **Iso** buttons snap to preset views.
- **Control time.** Play or pause the animation, step ±30°, or scrub the timeline from 0° to 720° (one full four-stroke cycle) to hand-crank the engine. A slider sets slow-motion speed.
- **Tweak the geometry:**
  - Stroke length (40–140 mm)
  - Connecting rod length (80–300 mm)
  - Bore, or piston diameter (50–110 mm)
  - Compression ratio (6:1 to 16:1)
- **Configure the engine:**
  - 1 to 8 cylinders
  - Bank angle from 0° (inline) through V-shapes to 180° (boxer)
  - Engine speed in rpm, which sets the numbers and not the animation
- **Play with timing.** Every cylinder has its own phase-offset slider. Presets are **Smooth** (an even firing order), **Even 1-2-3…**, **Unison**, **360° twins** and **Chaos**. The firing order is shown as you change it.
- **Read the graphs.** Switch between piston height, piston velocity, gas torque and the P–V loop. In the torque graph, white is the sum of all cylinders and the dashed amber line is the mean. The flatter the white line, the smoother the engine.
- **Inspect one cylinder.** Pick a cylinder to see its current stroke, cycle angle, height above bottom dead centre, piston speed, gas pressure and torque.
- **Check the numbers.** The side panel shows swept volume per cylinder, total displacement, compression ratio, rod ratio, bore/stroke ratio, mean piston speed, mean torque, ideal power and torque ripple.
- **Display toggles.** Show or hide cylinder walls, gas colours, valves and plug, X-ray pistons, TDC/BDC markers and auto-orbit.
- **Read the commentary.** A short note comments on your design choices, such as oversquare vs. undersquare, short vs. long rods, a crank that would hit the piston skirt, and torque ripple.

**About the physics.** The gas model is an idealised Otto cycle: polytropic compression and expansion, with instant combustion at top dead centre. Inertia, friction and heat loss are ignored. The piston kinematics, though, use the exact crank-slider equations, so the effect of rod length on piston motion is real. Treat the numbers as a learning aid, not engineering data.

**Tip:** it works best on a larger screen. On narrow screens the layout stacks vertically.

---

## How these were made

- **Code:** written by **Claude**, Anthropic's AI assistant, via claude.ai.
- **Prompts, direction and testing:** me. Each project started as one prompt asking for a complete, single-file HTML app. The exact prompts are in the `.txt` files next to each project, unedited.
- **Stack:** plain HTML, CSS and vanilla JavaScript. The Parliament chamber is drawn with SVG, Pistonarium with the HTML canvas. There are no frameworks, libraries or build tools.

## Repository structure

```
.
├── Money spending.html     # Spending planner
├── Money Spending.txt      # Prompt used
├── Parliment.html          # Parliament voting simulator
├── Parliament.txt          # Prompt used
├── pistonarium.html        # Piston engine explorer
├── pistonarium.txt         # Prompt used
└── README.md
```

## Credits

- **Code generation:** Claude (Anthropic)
- **Prompts, direction, testing and curation:** [@Subhrajit-Mandal](https://github.com/Subhrajit-Mandal)

## License

MIT License
