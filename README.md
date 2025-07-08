# vishal-infrastructure-project

Material Fatigue Life Estimator for Railway Station Construction
Author: Purvasha Mathur
Institute: IIT Jodhpur
Domain: Applied Physics + Structural AI + Civil Infrastructure

✨ Project Aim
To estimate the realistic fatigue lifespan of various construction materials used in infrastructure projects like the reconstruction of Jodhpur Railway Station. This tool is intended to help engineers, researchers, and construction firms assess long-term safety using physics-backed fatigue models.

🤔 Research Questions & Answers
1. How can we accurately predict the fatigue life of materials used in a railway station over decades of repetitive loading?
Answer:
By applying physics-backed fatigue models (Basquin, Civil Log, Barrett-Foschi, Glass fracture laws) customized for each material type, this simulator estimates the number of cycles to failure under specified stress amplitudes.

Output:
S-N curves (Stress vs. Cycles) are plotted to visualize fatigue life at different stress levels. Civil engineers can interactively adjust stress to see real-time life predictions.

2. Which mathematical fatigue models best suit different construction materials used in Vishal Infrastructure’s railway station project?
Answer:
Each material is matched to the most accurate fatigue model based on its mechanical behavior:

Metals (Steel, Aluminum): Basquin's law

Concrete, Brick, Stone, PVC: Civil Log model

Glass: Brittle power-law fracture

Timber: Barrett-Foschi model

Output:
The simulator dynamically switches formulas based on material selection.

3. Can we design a practical simulator that civil engineers at Vishal Infrastructure can use for real-world decision making?
Answer:
Yes. The tool uses Streamlit for interactivity, enabling:

Graphical S-N visualization

Adjustable sliders

CSV export

Custom material definition

Output:
"What-if" simulations like:

“How long will 25 MPa concrete last with 300 cycles/day?”

“Will timber survive 10 years at 20 MPa cyclic loading?”

4. What are the safety and economic implications if fatigue life predictions are inaccurate in public projects like Jodhpur Railway Station?
Answer:

Underestimation → Overdesign → Higher costs

Overestimation → Risk of failure → Safety hazards

Output:
Fatigue life is displayed in both years and cycles, aiding in design validation (e.g., 30+ years target lifespan).

📊 Fatigue Formulas Used
🔧 Civil Formula
cpp
Copy
Edit
log10(N) = A - B * (σ / f_c)
🔧 Basquin Formula (Metals)
ini
Copy
Edit
N = A * σ^(-b)
🔧 Glass Formula (Brittle)
ini
Copy
Edit
N = (1 / A) * (f_c / σ)^B
🔧 Barrett-Foschi Formula (Timber)
cpp
Copy
Edit
log10(N) = a - b * (σ / σ_u)^m
📚 Material Properties Table
Material	Formula Type	Constants	Use Case
RCC (Concrete + Steel)	Civil	A=14.5, B=3.7, f_c=32 MPa	Beams, slabs, columns
Brick Masonry	Civil	A=12.2, B=4.1, f_c=12 MPa	Wall framework
Stone	Civil	A=11.8, B=3.9, f_c=30 MPa	Cladding, façade
Mild Steel Beam	Basquin	A=3e12, b=0.08	Trusses, structural support
Stainless Steel Rail	Basquin	A=2.5e11, b=0.1	Handrails, braces
Aluminium Frame	Basquin	A=5e9, b=0.12	Doors, windows
Glass Panel	Glass	A=8e-7, B=19.5, f_c=0.72 MPa	Glazing, panels
PVC Pipe	Civil	A=8.3, B=3.7, f_c=6 MPa	Water and waste piping
Fiber Cement Board	Civil	A=9.0, B=5.2, f_c=14 MPa	Partitions, cladding
Timber	Barrett-Foschi	a=6.6, b=1.1, m=4.8, σ_u=58 MPa	Woodwork, support

🖼️ Sample Output: S-N Curve
Material	Stress Amplitude (σ)	Cycles to Failure
RCC	20 MPa	~1.2 million
Glass	0.5 MPa	~0.2 million
Mild Steel	50 MPa	~2 million
Timber	25 MPa	~0.4 million

(Plots are generated automatically in the Streamlit interface.)

🎓 Features
Fatigue simulation using sliders

S-N curve plotting

Add custom materials

Export fatigue data as CSV

🏛 Intended Use Case
This tool was developed for Vishal Infrastructure Pvt. Ltd. for use in the Jodhpur Railway Station reconstruction. It provides:

Accurate material fatigue evaluation

Support for structural safety and cost efficiency

Design optimization based on physics

Engineer-friendly usability

✏️ Future Scope
Add environmental stressors (temperature, humidity)

Crack visualization (Paris’ Law)

BIM and FEM integration

Host as a web-based decision support app

🎨 Developed By
Purvasha Mathur
Bachelor's in Artificial Intelligence and Data Science
IIT Jodhpur
