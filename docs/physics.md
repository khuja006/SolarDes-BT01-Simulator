# Open Thermodynamic & Heat Transfer Equations (`docs/physics.md`)

> **Note:** The equations below are standard textbook thermodynamics used to maintain internal physical consistency in the training simulator. Empirical fouling and mass-transfer correlations are proprietary and represented only by illustrative placeholders.

## 1. Saturation Vapor Pressure — Antoine Equation

Water vapor saturation pressure $P_{\text{sat}}$ as a function of temperature $T$ ($^\circ\text{C}$):

$$\log_{10}(P_{\text{mmHg}}) = A - \frac{B}{C + T}$$

Where for water ($1\text{–}100^\circ\text{C}$):
- $A = 8.07131$
- $B = 1730.63$
- $C = 233.426$
- $P_{\text{sat}}[\text{kPa}] = P_{\text{mmHg}} \times 0.133322368$

### Operating Point Verification
- At chamber pressure $P_1 = 25.0\text{ kPa}$, the saturation boiling temperature is:
  $$T_{\text{sat}}(25.0\text{ kPa}) = 65.0^\circ\text{C}$$
- At absorber surface temperature $T_{\text{surf}} = 65.5^\circ\text{C}$ ($+0.5\text{ K}$ overheat):
  $$P_{\text{sat}}(65.5^\circ\text{C}) = 25.52\text{ kPa} > P_1 (25.0\text{ kPa})$$
  Because $P_{\text{sat}}(T_{\text{surf}}) > P_{\text{chamber}}$, net interfacial evaporation is thermodynamically favorable.

## 2. Latent Heat of Vaporization ($\lambda$)

Linearized correlation around operating temperature ($T_{\text{surf}} = 65.5^\circ\text{C}$):

$$\lambda(T) = 2500.8 - 2.36 \cdot T \quad [\text{kJ/kg}]$$

At $T_{\text{surf}} = 65.5^\circ\text{C}$:
$$\lambda_{65.5} = 2346.2\text{ kJ/kg}$$

## 3. Evaporative Heat Flux ($q_{\text{evap}}$) & Effective Heat Transfer Coefficient ($h_{\text{eff}}$)

Given mass evaporation flux $J = 1.84\text{ kg/(m}^2\cdot\text{h)}$ and active area $A = 0.5\text{ m}^2$:

$$\dot{m}_{M1} = J \cdot A = 1.84\text{ kg/(m}^2\cdot\text{h)} \times 0.5\text{ m}^2 = 0.92\text{ kg/h} = 2.5556 \times 10^{-4}\text{ kg/s}$$

$$q_{\text{evap}} = \frac{J}{3600} \cdot (\lambda \times 1000) = \frac{1.84}{3600} \times 2.3462 \times 10^6 = 1199\text{ W/m}^2$$

With bulk seawater temperature $T_{\text{bulk}} = 45.2^\circ\text{C}$, the driving temperature difference is:

$$\Delta T = T_{\text{surf}} - T_{\text{bulk}} = 65.5 - 45.2 = 20.3\text{ K}$$

The effective evaporative heat transfer coefficient (without hidden geometry fudge factors) is:

$$h_{\text{eff}} = \frac{q_{\text{evap}}}{\Delta T} = \frac{1199}{20.3} = 59.06\text{ W/(m}^2\cdot\text{K)} = 0.0591\text{ kW/(m}^2\cdot\text{K)}$$
