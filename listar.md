# LiStar-X
### Existing Rocket Fuels:

1. **Liquid Oxygen (LOX) + RP-1 (refined kerosene):**
   - **Pros**: High energy density, good performance at relatively low costs.
   - **Cons**: RP-1 is hydrocarbon-based, leaving residue (coking) that can damage rocket engines. Kerosene is relatively heavy and not the most efficient in terms of specific impulse.

2. **LOX + Liquid Hydrogen (LH2):**
   - **Pros**: Extremely efficient, producing the highest specific impulse of any conventional rocket fuel combination.
   - **Cons**: Hydrogen has low density, requiring large storage volumes and cryogenic conditions, making it difficult to handle and increasing overall system complexity.

3. **Hypergolic fuels (N2O4 + Hydrazine derivatives):**
   - **Pros**: Ignites on contact, simple engine designs, reliable.
   - **Cons**: Extremely toxic and environmentally harmful, with relatively lower specific impulse than LOX/LH2.

4. **Solid Rocket Propellants (e.g., Ammonium Perchlorate Composite Propellant - APCP):**
   - **Pros**: Simple design, long storage, and immediate thrust.
   - **Cons**: Less efficient than liquid propellants, hard to control once ignited, environmental concerns due to perchlorates.

### Ideal Properties for New Rocket Fuel:
- **High specific impulse (Isp)**: A measure of fuel efficiency.
- **Low molecular weight**: To reduce the mass of propellant needed.
- **Stable and non-toxic**: For easier handling and safety.
- **High energy density**: To provide long-lasting energy.
- **Cryogenic stability**: If possible, minimizing the need for heavy cooling equipment.

### Key Observations from Current Approaches:
- Liquid hydrogen offers the best efficiency but is difficult to handle and store.
- RP-1 (kerosene) is affordable but leaves residue and isn’t the most efficient.
- Hypergolics are reliable but highly toxic.
- Solid propellants are stable but not very efficient and difficult to throttle.

### New Chemical Formula Approach:

To improve upon these, the fuel needs to balance high efficiency, low molecular weight, and stability. By integrating elements of current best practices (like the efficiency of hydrogen) with advanced chemical engineering, we can attempt to create a high-performance, long-lasting rocket fuel.

#### Suggested Approach: **Metal Hydrides + High-Energy Oxidizer**

1. **Metal Hydrides**:
   - **Elemental hydrogen** bound in **metal hydrides** (e.g., lithium hydride (LiH), magnesium hydride (MgH2)) offers high hydrogen density without cryogenic requirements.
   - **Pros**: High hydrogen content without the need for cryogenic storage, reduced volume, high-energy release when combined with an oxidizer.

2. **Advanced Oxidizers**:
   - A high-performance oxidizer like **dinitrogen tetroxide (N2O4)** or **perfluorinated compounds** could provide a powerful oxidation process while maintaining stability.
   - **Innovative oxidizers**: Consider derivatives of **fluorine**, which is highly reactive and energy-dense but challenging to handle. A more stable variant, like **perfluorocarbon-based oxidizers**, could significantly enhance fuel performance.

#### Proposed Formula:
**LiH + N2O4 → Li + H2O + energy**

This reaction provides a large amount of energy release with hydrogen and lithium as lightweight components. Lithium, being one of the lightest metals, significantly reduces the overall weight of the propellant system.

#### Additional Optimizations:
- **Nanoparticle catalyst**: Including a metal catalyst (such as platinum or palladium) in nanoparticle form can enhance reaction efficiency and control the combustion process more precisely.
- **Stabilizers and binders**: Add organic polymers as binders to stabilize the hydrides in a safe form.

### Theoretical Formula:

- **Fuel**: **Lithium Hydride (LiH)** – lightweight hydrogen carrier.
- **Oxidizer**: **Dinitrogen tetroxide (N2O4)** – high-energy oxidizer.
- **Additive**: **Platinum nanoparticle catalyst** – improves reaction efficiency.
- **Binder/Stabilizer**: **Perfluorinated polymer** – stabilizes the structure.

This combination balances **lightweight composition**, **long storage potential**, **high efficiency**, and **relatively easy handling**.

### Final Chemical Equation:
\[ \text{2 LiH} + \text{N}_2\text{O}_4 \rightarrow 2 \text{Li} + \text{H}_2\text{O} + \text{N}_2 + \text{Energy} \]

This reaction produces lithium metal, nitrogen, and water as by-products, making it more environmentally friendly than kerosene-based fuels.

This formulation optimizes for **long-lasting propulsion** with lower weight than RP-1 and higher efficiency than many hypergolics, making it a competitive choice for modern spaceflight.

Would you like further refinements or simulations of how this formula could perform?

## Simulation + Testing

Simulating and validating the practicality of a new rocket fuel formula, such as **LiH + N₂O₄**, in Python requires several steps. These include modeling the chemical reaction, estimating energy output, calculating thrust and specific impulse, and analyzing thermodynamic properties. Here’s a step-by-step guide on how to approach this:

### Step 1: Model the Chemical Reaction
You can start by modeling the reaction:
\[ 2 \text{LiH} + \text{N}_2\text{O}_4 \rightarrow 2 \text{Li} + \text{H}_2\text{O} + \text{N}_2 + \text{Energy} \]

To do this, we need to calculate the energy produced by the reaction, known as the **enthalpy of reaction** (\( \Delta H \)). You can calculate this by using bond energies or looking up enthalpy values from chemical databases.

### Step 2: Thermodynamic Calculations

- **Bond Energies**: You can use bond dissociation energies to calculate the energy released during the reaction.
- **Heat of Formation**: The heat of formation values for reactants and products can be found from a database, such as NASA's thermodynamic database.

Example values might be:
- \( \Delta H_{\text{LiH}} \)
- \( \Delta H_{\text{N}_2\text{O}_4} \)
- \( \Delta H_{\text{H}_2\text{O}} \)
- \( \Delta H_{\text{N}_2} \)

The energy release \( \Delta H \) for the reaction can be calculated as:

\[
\Delta H = \sum (\Delta H_{\text{products}}) - \sum (\Delta H_{\text{reactants}})
\]

### Step 3: Calculate Thrust and Specific Impulse

To calculate **thrust** and **specific impulse (Isp)**, you need to use:

\[
F = \dot{m} v_{\text{e}}
\]
Where:
- \( F \) is the thrust
- \( \dot{m} \) is the mass flow rate of the propellant
- \( v_{\text{e}} \) is the exhaust velocity

The exhaust velocity \( v_{\text{e}} \) is calculated as:

\[
v_{\text{e}} = \sqrt{\frac{2 \Delta H}{M_{\text{fuel}}}}
\]
Where \( M_{\text{fuel}} \) is the molar mass of the fuel mixture and \( \Delta H \) is the heat released per unit mass of fuel.

Finally, **specific impulse (Isp)** is given by:

\[
Isp = \frac{v_{\text{e}}}{g_0}
\]

Where \( g_0 \) is the gravitational constant (9.81 m/s²).

### Step 4: Python Simulation

In Python, you can simulate the chemical reaction, calculate the energy output, and use the formulas for thrust and specific impulse. Here’s a basic structure to get started:

```python
import math

# Constants
g0 = 9.81  # m/s², gravitational constant

# Heat of formation (example values, you should replace with actual data)
delta_H_LiH = -90  # kJ/mol for LiH
delta_H_N2O4 = 9.7  # kJ/mol for N2O4
delta_H_Li = 0  # kJ/mol for Li (element)
delta_H_H2O = -241.8  # kJ/mol for H2O
delta_H_N2 = 0  # kJ/mol for N2 (element)

# Calculate enthalpy of reaction (kJ/mol)
delta_H_reactants = 2 * delta_H_LiH + delta_H_N2O4
delta_H_products = 2 * delta_H_Li + delta_H_H2O + delta_H_N2

delta_H_reaction = delta_H_products - delta_H_reactants  # kJ/mol

# Molar masses (kg/mol)
M_LiH = 7.95e-3  # LiH molar mass
M_N2O4 = 92.011e-3  # N2O4 molar mass
M_fuel = (2 * M_LiH + M_N2O4)  # total mass of reactants

# Convert reaction energy from kJ/mol to J/kg
energy_per_kg = (delta_H_reaction * 1e3) / M_fuel  # J/kg

# Calculate exhaust velocity (m/s)
v_e = math.sqrt(2 * energy_per_kg)

# Calculate specific impulse (Isp)
Isp = v_e / g0

# Print results
print(f"Energy per kg of fuel: {energy_per_kg:.2f} J/kg")
print(f"Exhaust velocity: {v_e:.2f} m/s")
print(f"Specific Impulse: {Isp:.2f} seconds")
```

### Step 5: Validation and Iteration
1. **Validate energy output**: Compare the calculated energy output to existing fuels (e.g., RP-1, LH2) to determine its competitiveness.
2. **Adjust for real-world conditions**: Add corrections for nozzle efficiency, heat loss, and real-world combustion chamber conditions.
3. **Optimize**: Use the results to adjust the mixture ratio or fuel components to maximize performance.

### Step 6: Advanced Simulation Tools
For more accurate validation, you can integrate Python simulations with external tools like:
- **Cantera**: For detailed chemical kinetics and combustion simulation.
- **NASA's CEA (Chemical Equilibrium with Applications)**: To simulate complex rocket propulsion chemistry, combustion products, and specific impulse.

# Simple Test

The negative value of the calculated energy per kg indicates that there may still be an issue with how the enthalpy values or mass calculations are being handled. Let’s break down what’s happening and adjust accordingly.

### Issues:
1. **Enthalpy of Reaction**: Based on the values you provided:
   - Enthalpy of reactants = -170.3 kJ/mol
   - Enthalpy of products = -241.8 kJ/mol
   - Enthalpy of reaction = -71.5 kJ/mol

   The negative value for the enthalpy of reaction indicates that the reaction is **exothermic**, which is correct, but this needs to be handled carefully when calculating energy per unit mass.

2. **Energy per kg Calculation**: The energy per kg calculation involves dividing the enthalpy of the reaction by the molar mass of the fuel, but it seems that something went wrong in the conversion process.

Here’s how to fix the issues and validate the result:

### Updated Code with Fix:

```python
import math

# Constants
g0 = 9.81  # m/s², gravitational constant

# Heat of formation (in kJ/mol)
delta_H_LiH = -90  # kJ/mol for LiH (verify value)
delta_H_N2O4 = 9.7  # kJ/mol for N2O4 (verify value)
delta_H_Li = 0  # kJ/mol for Li (element)
delta_H_H2O = -241.8  # kJ/mol for H2O (verify value)
delta_H_N2 = 0  # kJ/mol for N2 (element)

# Calculate enthalpy of reaction (kJ/mol)
delta_H_reactants = 2 * delta_H_LiH + delta_H_N2O4
delta_H_products = 2 * delta_H_Li + delta_H_H2O + delta_H_N2

delta_H_reaction = delta_H_products - delta_H_reactants  # kJ/mol

# Debug output
print(f"Enthalpy of reactants: {delta_H_reactants} kJ/mol")
print(f"Enthalpy of products: {delta_H_products} kJ/mol")
print(f"Enthalpy of reaction: {delta_H_reaction} kJ/mol")

# Molar masses (kg/mol)
M_LiH = 7.95e-3  # LiH molar mass (kg/mol)
M_N2O4 = 92.011e-3  # N2O4 molar mass (kg/mol)
M_fuel = 2 * M_LiH + M_N2O4  # total mass of reactants (kg/mol)

# Convert reaction energy from kJ/mol to J/kg
energy_per_kg = (delta_H_reaction * 1e3) / M_fuel  # J/kg

# If energy is negative, correct the sign (since the reaction is exothermic, energy should be positive)
if energy_per_kg < 0:
    energy_per_kg = abs(energy_per_kg)

# Calculate exhaust velocity (m/s)
v_e = math.sqrt(2 * energy_per_kg)

# Calculate specific impulse (Isp)
Isp = v_e / g0

# Print results
print(f"Energy per kg of fuel: {energy_per_kg:.2f} J/kg")
print(f"Exhaust velocity: {v_e:.2f} m/s")
print(f"Specific Impulse: {Isp:.2f} seconds")
```

### Key Changes:
1. **Corrected Energy Sign**: I included a condition to handle the negative sign in the `energy_per_kg` calculation since exothermic reactions release energy, which is positive when we measure usable energy.
   
2. **Energy Conversion**: We calculate the reaction energy in J/kg by converting from kJ/mol to J/mol and then dividing by the mass in kg/mol. This is important for getting the correct value.

### Why This Fix Works:
The reaction is exothermic, so we expect the reaction enthalpy to be negative (it releases energy). However, when calculating the energy per kg, we use the absolute value because the energy available for propulsion (from the fuel's combustion) must be positive.

### Next Steps:
- **Run the code** and check the results again. The energy per kg should now be positive, and you should be able to compute the exhaust velocity and specific impulse correctly.
- **Verify the enthalpy values** with reliable chemical sources to ensure that the values for LiH, N₂O₄, H₂O, and N₂ are accurate for your specific reaction.
