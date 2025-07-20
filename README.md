# 🔩 Truss Force Analysis Using Method of Joints (Mathematica)

## 📘 Project Description

This Mathematica-based tool performs **static analysis of a 2D truss structure** using the **Method of Joints**. It allows the user to define external forces applied at nodes and then computes:

- Support reactions at roller and fixed supports
- Internal axial forces in all members
- Classification of each member force as **Tension**, **Compression**, or **Zero Force**
- A **color-coded truss diagram** with labels and directional arrows

---

## 🚀 Features

- Predefined truss structure with 8 nodes and 13 members
- User input for external forces in simple text format
- Symbolic solution for internal forces using equilibrium equations
- Automatic classification and visualization:
  - 🔴 Red → Tension
  - 🟢 Green → Compression
  - ⚫ Black → Negligible Force
- Vector-based diagram with numeric labels and a legend

---

## 🏗️ Truss Configuration

- **Nodes:** A, B, C, D, E (bottom) and F, G, H (top)
- **Members:** Includes horizontal, vertical, and diagonal connections
- **Supports:**
  - **A**: Roller (vertical reaction only)
  - **E**: Fixed (horizontal and vertical reactions)

---

## 🧮 How It Works

1. **Define Geometry:**
   - Hardcoded node coordinates and member connections

2. **User Inputs Loads:**
   - Enter external loads in format:  
     ```
     Node Fx Fy Node Fx Fy ...
     ```
     Example:  
     ```
     B 0 -30 C 0 -30 D 0 -90
     ```

3. **Compute Reactions:**
   - Uses ∑Fx = 0, ∑Fy = 0, and ∑Moments = 0 to find Ay, Ex, and Ey

4. **Apply Method of Joints:**
   - Sets up and solves force balance at each node using symbolic math
   - Forces in each member are determined

5. **Visualize:**
   - Members are drawn with color-coded forces
   - Reaction forces shown as arrows
   - Forces labeled in Newtons (N)

---

## 📈 Output Example

Here’s a sample truss analysis result for external loads applied at nodes **B (0, -30 kN)**, **C (0, -30 kN)**, and **D (0, -90 kN)**:

### 🔹 Internal Member Forces

| Member | Force (N) | Nature      |
|--------|------------|-------------|
| AB     | +60.000    | Tension     |
| BC     | +67.500    | Tension     |
| CD     | +67.500    | Tension     |
| DE     | +90.000    | Tension     |
| AF     | −84.853    | Compression |
| BF     | +40.000    | Tension     |
| FG     | −63.246    | Compression |
| CG     | +30.000    | Tension     |
| BG     | −12.500    | Compression |
| DG     | +37.500    | Tension     |
| GH     | −94.868    | Compression |
| DH     | +60.000    | Tension     |
| HE     | −127.280   | Compression |

### 🔹 Support Reactions


At A (Roller): Reaction = (0, +60.000) N  
At E (Fixed):  Reaction = (0, +90.000) N

### 🖼️ Truss Force Diagram

![Truss Force Diagram](/example_output.png)

- 🔴 Red: Tension  
- 🟢 Green: Compression  
- ⚫ Black: Near-zero force  
- Black arrows: Reaction forces
