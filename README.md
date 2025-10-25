# VSD-RISC-V-SoC-Tapeout-Program-Week-5

> *Transitioning from Transistor-Level Design to Full Physical Implementation*

---

## 🚀 Overview

This week’s task focuses on **setting up OpenROAD Flow Scripts** and executing the **Floorplan** and **Placement** stages of a standard **Physical Design flow**.
You’ll move from SPICE-level design (Week 4) to actual **chip layout generation**, bridging theory and practice in VLSI backend design.

---

## 🧩 Objective

* Set up **OpenROAD Flow Scripts** on Linux.
* Run and verify **Floorplan** and **Placement** stages only.
* Understand how RTL is converted into a **physical representation** on silicon.

---

## 🧱 Why This Task Is Important

This task connects your transistor-level understanding with real-world chip implementation.
You’ll learn:

✅ How **core area** and **die dimensions** are defined
✅ How **standard cells** are arranged to optimize **timing, area, and congestion**
✅ How **floorplanning and placement** decisions influence overall **chip performance**

---

## 📚 Repository Reference

🔗 **OpenROAD Flow Scripts Reference**
[https://github.com/spatha0011/spatha_vsd-hdp/blob/main/Day14/README.md](https://github.com/spatha0011/spatha_vsd-hdp/blob/main/Day14/README.md)

---

## 🛠️ Setup & Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts.git
cd OpenROAD-flow-scripts
```

### Step 2: Install Prerequisites

Install dependencies (on Ubuntu/Debian):

```bash
sudo apt-get update
sudo apt-get install build-essential python3 python3-venv cmake git
```

### Step 3: Build the Flow

```bash
./setup.sh
make
```

✅ **Expected Output:**
“OpenROAD environment successfully set up.”

### Step 4: Launch OpenROAD

```bash
flow.tcl
```

---

## 🧮 Execution Steps

### 1️⃣ Floorplan

* Defines **core area**, **die boundaries**, and **placement rows**.
* Establishes **power grid** and **IO ring** positions.

Command example:

```bash
./flow.tcl -design <design_name> -to floorplan
```

**Key Output Files:**

* `floorplan.def`
* `floorplan.log`
* `floorplan.png`

---

### 2️⃣ Placement

* Standard cells are placed **legally** (non-overlapping).
* Aims to **minimize wirelength** and **optimize timing**.

Command example:

```bash
./flow.tcl -design <design_name> -from floorplan -to placement
```

**Key Output Files:**

* `placement.def`
* `placement.log`
* `placement.png`

---

## 🖼️ Example Outputs

📸 **Expected Screenshots for Submission**

* Terminal showing commands & successful installation
* Floorplan view (core + die outlines)
* Placement layout (standard cells visible)

---

## 📝 Deliverables

| Deliverable        | Description                                |
| ------------------ | ------------------------------------------ |
| 🖥️ Terminal Proof | Screenshots of installation & OpenROAD run |
| 📸 Layout Images   | Floorplan + Placement visual outputs       |
| 🧾 Short Summary   | 3–4 lines on steps & challenges faced      |

---

## 🧠 Quick Notes (Concept Simplifier)

| Concept            | Description                                           | Why It Matters                                            |
| ------------------ | ----------------------------------------------------- | --------------------------------------------------------- |
| **Floorplan**      | Defines chip’s physical boundaries and layout regions | Determines chip size, power grid, and cell placement area |
| **Core Area**      | Active area containing logic cells                    | Impacts die size and yield                                |
| **Placement**      | Arranges standard cells legally                       | Reduces wirelength and congestion                         |
| **Congestion Map** | Visualization of routing difficulty                   | Helps optimize timing and reduce DRC errors               |
| **DEF File**       | Design Exchange Format (physical representation)      | Used for verification and routing stages                  |
| **GDSII**          | Final mask layout format                              | Fabrication-ready output                                  |

---

## 🔍 Comparison Corner (CMP)

| Step                  | What Happens                          | Tool Used        | Output                        |
| --------------------- | ------------------------------------- | ---------------- | ----------------------------- |
| **Week 4 (Ngspice)**  | Simulated transistor-level circuits   | Ngspice          | Analog plots                  |
| **Week 5 (OpenROAD)** | Converts gate-level netlist to layout | OpenROAD         | Floorplan + Placement layouts |
| **Next Steps**        | Routing + GDSII generation            | OpenROAD + Magic | Fabrication-ready file        |

---

## 💡 Common Issues & Fixes

| Issue                         | Cause                         | Fix                                   |
| ----------------------------- | ----------------------------- | ------------------------------------- |
| `flow.tcl: command not found` | Environment not sourced       | Run `source env.sh` before executing  |
| `Permission denied`           | Missing executable permission | Run `chmod +x setup.sh`               |
| `No module named 'yaml'`      | Python dependency missing     | `pip install pyyaml`                  |
| Layout not visible            | Missing viewer                | Use `klayout` or `magic` to visualize |

---

## ❓ Q&A Section

**Q1: Why stop at placement and not proceed to routing?**
➡️ Because routing is part of the next stage. Week 5 focuses only on *physical structure organization* before wires are connected.

**Q2: Can OpenROAD handle large designs?**
➡️ Yes! It supports both academic and industrial-scale designs.

**Q3: What’s the difference between Floorplan and Placement?**
➡️ Floorplan defines *where* cells can go; Placement decides *exactly where* each cell will go.

**Q4: What is “Legalization” in placement?**
➡️ It’s the process of adjusting cells to non-overlapping positions without violating rules.

**Q5: What’s next after Placement?**
➡️ Clock Tree Synthesis (CTS), Routing, and Signoff.

---

## 🧭 Summary

By completing this task, you have:

* Installed and launched **OpenROAD Flow Scripts**
* Executed **Floorplan** and **Placement**
* Observed how logical designs become **physically structured layouts**

🧩 You’re now ready to move towards **Routing**, **CTS**, and **Timing Closure** — the next stages in backend design!

---

## 🤝 Credits

* **Instructor Reference:** [spatha_vsd-hdp Day14 README](https://github.com/spatha0011/spatha_vsd-hdp/blob/main/Day14/README.md)
* **Tool:** [OpenROAD Project](https://github.com/The-OpenROAD-Project)
* **Student:** *Shaili Sahu (Amrita Vishwa Vidyapeetham, Bengaluru)*

---

## 🎯 Final Tip

💬 *“Understanding placement is like playing chess — every move affects timing.”*
