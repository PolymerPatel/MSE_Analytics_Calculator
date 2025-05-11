# Identifying a Material with a Binary Phase Diagram - Usage Guide Brainstorming

This tool will assist Materials Scientists and Engineers to easily match a literature referenced binary phase diagrams with material thermal properties to identify a material or alloy.



## User Interface

Protocol for application:

At start of application, the program should create the (empty) materials lists
The program should offer a menu for the user to select from
The program should perform the user’s selected task
The program should offer the menu in a loop until the user enters “q”

Backend integration checklist items:

Create a data table or database to pull the information from. 
Building a database in lists or APIs from critical materials will be an uphill challenge.
Develop and organize the chatbot's database with research-backed information. - Langchain and hugging face

Positioning to showcase its value.
Finding users to test it out as a decision-making or educational resource for a sustainable material management system.




## Installation: This example use-case was generated with AI and serves as a brainstorming session with a volunteer

```bash
# Clone the repository or download the script
git clone https://github.com/your-username/binary-phase-diagram-generator.git
cd binary-phase-diagram-generator

# Install required dependencies
pip install matplotlib numpy
```

## Quick Start

### Generate a Pre-configured Tin-Bismuth Example

```bash
python binary_phase_diagram.py --example --output tin_bismuth_diagram.png
```

### Generate a Custom Diagram Using a Configuration File

```bash
python binary_phase_diagram.py --config your_config.json --output custom_diagram.png
```

## Configuration Options

Create a JSON configuration file with the following parameters:

| Parameter | Description | Example |
|-----------|-------------|---------|
| `material_a` | Symbol for first material | "Cu" |
| `material_b` | Symbol for second material | "Ni" |
| `material_a_melting_point` | Melting point of material A | 1085.0 |
| `material_b_melting_point` | Melting point of material B | 1455.0 |
| `eutectic_temperature` | Temperature of eutectic point | 1000.0 |
| `eutectic_composition` | Composition at eutectic point (% of B) | 35.0 |
| `title` | Diagram title | "Binary Phase Diagram" |
| `x_label` | Label for x-axis | "Atomic Percent" |
| `show_weight_percent` | Show secondary axis with weight percent | true |
| `temp_unit` | Temperature unit | "°C" |
| `references` | List of literature references | ["ASM Handbook Vol 3 (2016)"] |
| `alpha_phase_temp` | Temperature for allotropic transformation | 13.2 |
| `alpha_phase_comp_limit` | Composition limit for allotropic phase | 93.0 |
| `phase_regions` | List of phase region labels | [{"x": 50, "y": 300, "label": "α+L"}] |
| `custom_points` | List of custom points to highlight | [{"composition": 40, "temperature": 800}] |

## API Usage in Python

You can also use the generator programmatically in your Python code:

```python
from binary_phase_diagram import BinaryPhaseDiagramGenerator

# Method 1: Using a configuration file
generator = BinaryPhaseDiagramGenerator(config_file="your_config.json")
generator.generate_diagram(output_file="output.png")

# Method 2: Direct parameter configuration
generator = BinaryPhaseDiagramGenerator(
    material_a="Al",
    material_b="Si",
    material_a_melting_point=660.3,
    material_b_melting_point=1414.0,
    eutectic_temperature=577.0,
    eutectic_composition=12.6,
    references=["ASM Handbook Vol. 3 (2016)"]
)
generator.generate_diagram(output_file="al_si_diagram.png")

# Method 3: Use the built-in example
BinaryPhaseDiagramGenerator.create_tin_bismuth_example(output_file="example.png")
```

## Scalable Phase Diagram Systems

Eutectic Systems (e.g., Tin-Bismuth)
A map that has a liquid transform directly to two solid phases at the eutectic point - that point where the curves intersect.

Peritectic Systems (e.g., Iron-Carbon up to 6.67% C)
A map where liquid and solid phases react to form a new solid phase. 
Commonly found Iron-Carbon alloys due to the properties of adding Carbon to the system.


## Adding Thermodynamic Data

The generator can be extended to calculate and display thermodynamic parameters:

- Gibbs free energy curves
- Activity coefficients
- Entropy of mixing
- Heat of formation

## Citing

When using this tool for academic publications, please cite:

```
Binary Phase Diagram Generator
https://github.com/PolymerPatel/binary-phase-diagram-tool
```

And the relevant references for the material system data you've used.

## References

For accurate binary phase diagram data, consult:

1. ASM Handbook, Volume 3: Alloy Phase Diagrams
2. Massalski, T.B., Binary Alloy Phase Diagrams, ASM International
3. NIST Phase Diagram Database
4. Journal of Phase Equilibria and Diffusion
