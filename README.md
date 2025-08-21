**U.S. Airways Preferred Customer Service – Queueing & Solver Optimization**

This project models and optimizes staffing for a call center dedicated to Preferred Customers. Using a queueing approach and Excel Solver, it compares service targets of 30s vs 45s average hold time, then designs a cost-efficient hybrid schedule of full-time and part-time agents.

🧭 Problem & Objectives

- Improve response speed and quality for preferred customers while controlling cost. 
- Targets: reduce average hold time from 45s to 30s; compute minimum agents; design an efficient staffing schedule. 

📊 Approach

1. **Queueing model** to estimate minimum agents by time block/day. Parameters include:
- Processing time 𝑝 = 6.41 min, utlization 𝑈 = 𝑝/(𝑎⋅𝑚), 𝐶𝑉𝑎^2 = 𝐶𝑉𝑝^2 = 1, hold-time target 𝑇𝑞 ∈ {30𝑠,45𝑠}.
2. **Excel Solver** to create an optimized weekly schedule:
- 8.5-hour full-time shifts (4-1-4), 4-hour part-time shifts, wage $14/hr + 25% benefits = $17.50/hr. 

✅ Key Results

- Total weekly cost: $37,412 (45s) vs $39,019 (30s) → +$1,607 (~4.3%) for 30s target. 
- Staffing (sample, 30s) totals to 355 agents across the week (FT/PT mix). 
- Staffing (sample, 45s) totals to 342 agents. 
- Peak demand occurs Thu–Fri; weekends are lighter. 

📅 Proposed Weekly Schedules (excerpt)

**30s target** – daily totals (FT + PT):

Sun 50, Mon 54, Tue 50, Wed 50, Thu 57, Fri 56, Sat 38 → **Total 355.** 

**45s target** – daily totals (FT + PT):

Sun 46, Mon 52, Tue 48, Wed 49, Thu 55, Fri 56, Sat 36 → **Total 342.**

🔁 How to Reproduce (Excel)

1. Open the provided Excel files in /data.
2. Verify input tables for **arrival rates by hour/day** and the **service-time parameter p.**
3. Use the queueing sheet to compute **minimum agents** per time block for **30s** and **45s** targets (as defined above). 
4. Open the **Solver** configuration and optimize staffing subject to:
- shift rules (FT 8.5h, PT 4h), integer agent counts, coverage ≥ required agents. 
5. Compare weekly totals and cost outputs; confirm **~$1,607** delta and **~4–5%** increase under the 30s target. 

🧠 Assumptions

- 𝐶𝑉𝑎^2 = 𝐶𝑉𝑝^2 = 1 (exponential inter-arrival and service).
- Hourly wage **$17.50** (incl. 25% benefits).
- Hybrid staffing: FT covers base demand; PT flexes to peaks. 

🔍 Insights

- **Better CX vs Cost Trade-off:** 30s improves service but raises weekly cost by ~4–5%. 
- **Peaks:** Thu–Fri need the most agents; weekends are off-peak. 

🛠️ Tools

Microsoft Excel (Queueing calculations + **Solver**)
