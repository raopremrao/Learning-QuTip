I'll explain how squeezed states revolutionized gravitational wave detection in LIGO. This is a beautiful example of fundamental quantum mechanics enabling one of the most precise measurements in human history.

---

## **The Core Problem: The Standard Quantum Limit**

LIGO measures gravitational waves by detecting **tiny changes in arm length** — we're talking about displacements of:

$$\Delta L \sim 10^{-19} \text{ meters} = \frac{1}{10,000} \times \text{ proton radius}$$

### **Where does noise come from?**

| Noise Source | Origin | Frequency Dependence |
|-------------|--------|---------------------|
| **Shot noise** (photon counting) | Laser light is quantized | Dominates at **high frequencies** (>100 Hz) |
| **Radiation pressure** | Photon momentum kicks mirrors | Dominates at **low frequencies** (<100 Hz) |
| **Seismic noise** | Ground vibrations | Below ~10 Hz (filtered out) |

These two quantum noises are **conjugate** — they arise from the **Heisenberg uncertainty principle** applied to light.

---

## **The Quantum Noise Picture**

### **Interferometer Basics:**

```
        Laser
          ↓
    ┌─────┴─────┐
    │  50/50    │ ← Beam splitter
    │   BS      │
    └─────┬─────┘
          │
    ┌─────┴─────┐
    │           │
   ↓│           │↓
  [M1]←──dL──→[M2]  ← Test masses (mirrors, 40 kg each!)
    │           │
    └─────┬─────┘
          ↓
      Detector
          ↓
    Photodiode (measures interference)
```

### **What the photodiode measures:**

The **phase quadrature** $\hat{P}$ (which carries the gravitational wave signal) and the **amplitude quadrature** $\hat{X}$ (which doesn't, but has noise).

---

## **The Heisenberg Bottleneck**

For **coherent state** (ordinary laser light):

$$\Delta X = \Delta P = \frac{1}{\sqrt{2}} \quad \text{(in natural units where $\hbar = 1$)}$$

The **Standard Quantum Limit (SQL)** arises because:

$$\text{Signal-to-Noise} \propto \frac{\text{Displacement Signal}}{\sqrt{(\Delta X)^2 + (\Delta P)^2}}$$

| Quadrature | Role | Noise Impact |
|-----------|------|-------------|
| $\hat{X}$ (amplitude) | Intensity fluctuations | Creates **radiation pressure noise** on mirrors |
| $\hat{P}$ (phase) | Phase/interference | Creates **shot noise** in detection |

You can't reduce both simultaneously — **they're conjugate variables**!

---

## **Enter Squeezed States: The Quantum Fix**

### **The Idea:**

Instead of a **coherent state** (circular uncertainty):

```
        ΔP ↑
           │
           │    ╭──╮
           │   (    )  ← Coherent state: ΔX = ΔP
           │    ╰──╯
           └────────→ ΔX
```

Use a **squeezed state** (elliptical uncertainty):

```
        ΔP ↑
           │
           │   ╭────╮
           │  (      )  ← Squeezed: ΔP < 1/√2, ΔX > 1/√2
           │   ╰────╯
           └────────→ ΔX
              (stretched)
```

---

## **How LIGO Uses Squeezing**

### **Frequency-Dependent Squeezing (Advanced LIGO):**

| Frequency Regime | Dominant Noise | Squeezing Strategy |
|-----------------|----------------|------------------|
| **Low freq** (~10-100 Hz) | Radiation pressure | Squeeze **amplitude** (reduce $\Delta X$) |
| **High freq** (~100-1000 Hz) | Shot noise | Squeeze **phase** (reduce $\Delta P$) |

But you can't do both at once classically... unless you use **filter cavities**!

### **The Breakthrough: Frequency-Dependent Squeezing**

```
    Squeezed Light Source (Optical Parametric Oscillator)
              ↓
    ┌─────────────────┐
    │  Filter Cavity  │ ← Tunes squeezing angle vs. frequency
    │  (long optical  │
    │   resonator)    │
    └─────────────────┘
              ↓
    ┌─────────────────┐
    │   Main LIGO     │ ← Interferometer
    │  Interferometer │
    │  (4 km arms)    │
    └─────────────────┘
              ↓
         Detection
```

### **Physics of the Filter Cavity:**

The squeezing parameter $\zeta$ rotates in phase space as light propagates. By choosing the **filter cavity length and finesse**, you make:

$$\theta_{\text{squeeze}}(\omega) = \arctan\left(\frac{\omega_{\text{cavity}}}{\omega}\right)$$

| Frequency | Effective Squeezing Angle | Quadrature Squeezed |
|-----------|--------------------------|---------------------|
| $\omega \ll \omega_c$ | ~90° | **Amplitude** (reduce radiation pressure) |
| $\omega \gg \omega_c$ | ~0° | **Phase** (reduce shot noise) |

This creates a **rotation** that tracks the noise curve!

---

## **Quantitative Impact**

### **Sensitivity Improvement:**

| Configuration | Strain Sensitivity | Range Improvement |
|--------------|-------------------|-------------------|
| No squeezing (SQL) | $h \sim 10^{-23}/\sqrt{\text{Hz}}$ | Baseline |
| 10 dB squeezing | $h \sim 3 \times 10^{-24}/\sqrt{\text{Hz}}$ | **~3× farther** |
| LIGO O3 (actual) | ~3 dB squeezing | ~40% more volume |

### **What "10 dB squeezing" means:**

$$10 \log_{10}\left(\frac{(\Delta P_{\text{coh}})^2}{(\Delta P_{\text{sq}})^2}\right) = 10 \text{ dB}$$

$$\Rightarrow \Delta P_{\text{sq}} = \frac{1}{\sqrt{10}} \Delta P_{\text{coh}} \approx 0.32 \times \frac{1}{\sqrt{2}}$$

**Phase uncertainty reduced by factor of ~3!**

---

## **The Squeezed State in LIGO's Math**

### **Input to interferometer:**

$$|\psi_{\text{in}}\rangle = \hat{S}(\zeta)\hat{D}(\alpha)|0\rangle$$

Where:
- $\alpha \sim 10^{21}$ (macroscopic coherent amplitude, ~1 kW laser power!)
- $\zeta = r e^{i\theta}$ with $r \approx 1.15$ (10 dB squeezing)

### **Interaction with gravitational wave:**

The GW modifies the **phase quadrature**:
$$\hat{P}_{\text{out}} = \hat{P}_{\text{in}} + \frac{2\omega_0}{c} h(t) \hat{X}_{\text{in}} \cdot L$$

Where:
- $h(t)$ = gravitational wave strain
- $\omega_0$ = laser frequency
- $L$ = arm length (4 km)
- The second term is the **signal**

### **Signal-to-noise with squeezing:**

$$\text{SNR} \propto \frac{h(t)}{\Delta P_{\text{sq}}} = \frac{h(t)}{e^{-r}/\sqrt{2}} = \sqrt{2} e^r h(t)$$

For $r = 1.15$ (10 dB): **SNR improves by factor of ~3.2**

---

## **Real LIGO Results**

### **Observing Run Timeline:**

| Run | Years | Squeezing? | Binary Merger Range |
|-----|-------|-----------|-------------------|
| O1 | 2015-2016 | No | ~1.3 Gpc (first GW150914!) |
| O2 | 2016-2017 | No | ~1.9 Gpc |
| O3 | 2019-2020 | Yes (3-6 dB) | ~2.7 Gpc |
| O4 | 2023-2025 | Yes (6+ dB) | ~3.5+ Gpc |
| O5 (A+) | ~2027+ | Yes (10+ dB, filter cavities) | ~5+ Gpc |

### **Key Detections Enabled:**

| Event | What | Squeezing Role |
|-------|------|---------------|
| GW150914 | First black hole merger | Proved concept (pre-squeezing era) |
| GW170817 | Neutron star merger + gamma rays | Would have been marginal without improvements |
| GW190521 | Most massive binary BH (150+150 $M_\odot$) | High-mass, low-frequency; squeezing crucial |
| Recent events | Daily detections in O4 | Squeezing increases detection rate ~10× |

---

## **The Quantum Optics Hardware**

### **How to Make Squeezed Light:**

```
    Pump Laser (green, 532 nm)
           ↓
    ┌──────────────┐
    │  Nonlinear   │ ← Periodically-poled KTP crystal
    │   Crystal    │   (χ⁽²⁾ optical parametric oscillator)
    └──────────────┘
           ↓
    Squeezed Vacuum (at 1064 nm, LIGO wavelength)
           ↓
    ┌──────────────┐
    │  Filter Cavity│ ← 300 m optical resonator (tunes frequency response)
    └──────────────┘
           ↓
    Injected into interferometer's dark port
```

### **The Squeezing Generation Process:**

$$\hat{H}_{\text{int}} = i\hbar \chi^{(2)} (\hat{a}_{\text{pump}} \hat{b}^\dagger \hat{c}^\dagger - \text{h.c.})$$

- Pump photon → creates **correlated photon pair** in signal ($\hat{b}$) and idler ($\hat{c}$) modes
- Below threshold: **squeezed vacuum** (sub-Poissonian statistics)
- The correlation reduces uncertainty in specific quadratures

---

## **Why This Matters: The Physics**

### **The Uncertainty Principle is NOT a Limit — It's a Resource!**

Classical thinking:
> "Quantum noise limits precision. We can't beat it."

Quantum thinking:
> "The uncertainty principle says $\Delta X \cdot \Delta P \geq \frac{1}{2}$. It does NOT say $\Delta X = \Delta P = \frac{1}{\sqrt{2}}$. We can **redistribute** uncertainty!"

$$\Delta X_{\text{new}} = e^{+r}/\sqrt{2}, \quad \Delta P_{\text{new}} = e^{-r}/\sqrt{2}$$

$$\Delta X_{\text{new}} \cdot \Delta P_{\text{new}} = \frac{1}{2} \checkmark \text{ (saturates uncertainty bound)}$$

**We trade increased amplitude noise for decreased phase noise — exactly what LIGO needs!**

---

## **Summary: The Big Picture**

```
┌─────────────────────────────────────────────────────────┐
│  GRAVITATIONAL WAVE                                     │
│       ↓ h(t) ~ 10⁻²¹                                    │
│  ┌─────────────────┐                                    │
│  │  Space-time     │ ← stretches one arm, compresses    │
│  │  strain         │   other by ΔL = h × L ~ 10⁻¹⁸ m  │
│  └─────────────────┘                                    │
│       ↓                                                 │
│  ┌─────────────────┐                                    │
│  │  LIGO Arms      │ ← 4 km × 2, Fabry-Perot cavities  │
│  │  (4 km each)    │   (light bounces ~300×)            │
│  └─────────────────┘                                    │
│       ↓                                                 │
│  ┌─────────────────┐                                    │
│  │  Interference   │ ← phase shift φ = (2π/λ) × 2ΔL     │
│  │  at beam splitter│                                    │
│  └─────────────────┘                                    │
│       ↓                                                 │
│  ┌─────────────────┐                                    │
│  │  SQUEEZED LIGHT │ ← REDUCES ΔP below SQL             │
│  │  (ΔP = e⁻ʳ/√2) │   by factor eʳ ~ 3 (10 dB)         │
│  └─────────────────┘                                    │
│       ↓                                                 │
│  ┌─────────────────┐                                    │
│  │  Photodiode     │ ← detects phase quadrature         │
│  │  (shot noise    │   with improved SNR                │
│  │   reduced!)     │                                    │
│  └─────────────────┘                                    │
│       ↓                                                 │
│  SIGNAL DETECTED! (above noise floor)                   │
└─────────────────────────────────────────────────────────┘
```

---

## **Your Code Connection**

Remember your tutorial code?
```python
epsilon = 0.5j    # Squeezing parameter
S = (0.5 * np.conj(epsilon) * a * a - 0.5 * epsilon * a.dag() * a.dag()).expm()
```

This $\hat{S}(\zeta)$ with $\zeta = 0.5i$ is **exactly the operator** LIGO uses — just with much larger $r$ (1.15 instead of 0.5) and frequency-dependent rotation via filter cavities!

The Wigner function you plotted shows the **elliptical uncertainty** that, when oriented correctly, pushes noise out of the signal quadrature and into the unused one.

---

Want me to derive the **frequency-dependent squeezing angle** from the filter cavity transfer function, or explain how **quantum entanglement** between the two LIGO arms could enable even better sensitivities (quantum dense metrology)?