# JFXAI4DIA — Open-Source Alternative Integration Architecture

> **Project focus:** Physics-Driven AI for Industrial Design Automation  
> **Architecture goal:** reorganize the alternatives listed in the JFXAI4DIA source description into a modular, open and replaceable architecture for AI-assisted design, CAD generation, multidisciplinary optimization, CFD/FEA, aerospace and marine conceptual design, geometry interoperability, simulation, and engineering validation.

---

## 1. Source Project Direction

The source repository defines **JFXAI4DIA** as:

> **Physics-Driven AI for Industrial Design Automation**

The source compendium spans five major families:

1. **AI-assisted and generative design**
2. **CAD / geometry / interoperability**
3. **Aerospace and marine conceptual design**
4. **Physics simulation and multidisciplinary optimization**
5. **Engineering workflow orchestration and validation**

The source also preserves the project engineering lifecycle:

```text
MBSE → CAD → CAM → CAS
```

with Arcadia/Capella concepts for system architecture, CAD for computer-aided design, CAM for manufacturing/assembly, and CAS for end-to-end simulation and performance analysis.

---

# 2. Recommended Architecture Principle

The listed projects should not be deployed as a single monolithic application.

The preferred architecture is a **federation of replaceable engineering services** behind open interfaces:

```text
Engineering Requirements
        ↓
MBSE / System Architecture
        ↓
AI Design Intent
        ↓
Parametric / Generative CAD
        ↓
Geometry & Schema Normalization
        ↓
Discipline Analysis
        ↓
Multidisciplinary Optimization
        ↓
Physics Verification
        ↓
Design Decision
        ↓
Manufacturing / CAS
```

The governing principle is:

> **AI proposes and orchestrates design alternatives; physics-based solvers, parametric constraints, and engineering validation determine whether those alternatives are acceptable.**

---

# 3. High-Level Alternative Integration Architecture

```text
┌────────────────────────────────────────────────────────────────────────────┐
│                     ENGINEERING EXPERIENCE LAYER                           │
│ Web UI | FreeCAD | Engineering Console | Notebook | 3D Viewer            │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                                   v
┌────────────────────────────────────────────────────────────────────────────┐
│                    AI DESIGN & ORCHESTRATION LAYER                         │
│ AI-Arch | Aedifex | CADAM | CQAsk | FreeCAD AI | AgentSCAD              │
│ Natural Language → Requirements → Geometry → Simulation Jobs              │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                  ┌────────────────┼─────────────────┐
                  │                │                 │
                  v                v                 v
┌────────────────────────┐ ┌────────────────────┐ ┌──────────────────────────┐
│ GENERATIVE / PARAMETRIC│ │ GEOMETRY & CAD     │ │ ENGINEERING SCHEMAS      │
│ Rostok                 │ │ FreeCAD            │ │ IFC / IfcOpenShell       │
│ PhysiOpt               │ │ AeroShape          │ │ CPACS                    │
│ ShipHullGAN            │ │ Mechatronic WB     │ │ Parametric geometry      │
│ C-ShipGen              │ │ FreeCAD MCP        │ │                          │
└────────────┬───────────┘ └─────────┬──────────┘ └─────────────┬────────────┘
             │                       │                           │
             └───────────────────────┼───────────────────────────┘
                                     v
┌────────────────────────────────────────────────────────────────────────────┐
│                 CONCEPTUAL / MULTIDISCIPLINARY DESIGN                      │
│ SUAVE | openCDT | CEASIOMpy | FAST-OAD | GPkit | ADAO/SALOME            │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                    ┌──────────────┼─────────────────┐
                    │              │                 │
                    v              v                 v
┌────────────────────────┐ ┌──────────────────┐ ┌────────────────────────────┐
│ AERODYNAMICS / CFD     │ │ STRUCTURES / FEA │ │ FLIGHT / DYNAMICS          │
│ OpenSBLI               │ │ MAST             │ │ QPlane                     │
│ OpenFOAM / FEniCS      │ │ sensitivity      │ │ Ptera Software             │
│ AutoCFD                │ │ multiphysics     │ │                            │
│ CFL3D*                 │ │                  │ │                            │
└────────────┬───────────┘ └─────────┬────────┘ └────────────┬───────────────┘
             │                       │                       │
             └───────────────────────┼───────────────────────┘
                                     v
┌────────────────────────────────────────────────────────────────────────────┐
│                    MULTIDISCIPLINARY OPTIMIZATION                          │
│ MACH-Aero | ADAO | GPkit | PhysiOpt | Design-space exploration          │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                                   v
┌────────────────────────────────────────────────────────────────────────────┐
│                 VERIFICATION / CAS / DIGITAL ENGINEERING                   │
│ Solver comparison | Sensitivities | Constraints | UQ | Regression Tests  │
│ CAD ↔ Physics ↔ Optimization traceability                                 │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                                   v
┌────────────────────────────────────────────────────────────────────────────┐
│                           CAM / DOWNSTREAM                                 │
│ Validated geometry | Manufacturing preparation | Digital thread           │
└────────────────────────────────────────────────────────────────────────────┘
```

`*` Components whose upstream license or distribution status is not established by the source README should be treated as **external/research candidates pending license verification**, not automatically as open-source core dependencies.

---

# 4. Category A — AI-Assisted Design Front Ends

## AI-Arch

**Source role:** automated building design optimization system.

### Best architectural role

```text
Building Requirements
       ↓
AI-Arch
       ↓
Candidate Building Designs
       ↓
IFC / Geometry Validation
       ↓
Physics / Optimization
```

### Strategic value

**4/5 — Domain-specific generative-design candidate**

Recommended for:

- building-layout exploration;
- architecture optimization;
- automated design alternatives;
- integration with IFC-based downstream workflows.

### Classification

**Strategic Architecture-AI Integration**

---

## Aedifex

**Source role:** open-source 3D architectural editor with AI design assistant.

### Strategic value

**5/5 — High-value interactive architecture/CAD candidate**

Best role:

- human-in-the-loop 3D editing;
- architectural design assistant;
- rapid iteration;
- front-end for building-design automation.

### Classification

**Primary Open Architectural AI Workbench Candidate**

---

## CADAM

**Source role:** open-source text-to-CAD web application.

### Strategic value

**5/5 — High-value natural-language CAD generation candidate**

Recommended pattern:

```text
Natural-Language Specification
            ↓
          CADAM
            ↓
       Parametric CAD
            ↓
Constraint / Physics Validation
```

### Classification

**Primary Text-to-CAD Candidate**

---

## CQAsk

**Source role:** LLM-based CAD model generation.

### Strategic value

**4/5 — Natural-language CAD research/integration candidate**

Best used as an alternative or complementary natural-language CAD interface to CADAM.

### Classification

**Strategic LLM-to-CAD Candidate**

---

## FreeCAD AI

**Source role:** AI assistant workbench for FreeCAD that generates and executes Python code.

### Strategic value

**5/5 — Strong desktop CAD copilot candidate**

Recommended for:

- scriptable geometry creation;
- repetitive CAD automation;
- design modifications;
- model inspection;
- engineering workflow assistance.

### Important boundary

Generated Python/macros should be reviewable and executed in a controlled environment.

### Classification

**Primary FreeCAD AI Automation Candidate**

---

# 5. Category B — AI CAD Orchestration

## AgentSCAD

**Source role:** engineering control room for CAD job orchestration.

### Strategic value

**5/5 — Strategic orchestration candidate**

Best position:

```text
Engineer / AI Agent
        ↓
AgentSCAD
        ↓
CAD Job Queue
  ┌─────┼──────────┐
  ↓     ↓          ↓
FreeCAD CADAM   Simulation
```

Potential responsibilities:

- CAD-job orchestration;
- asynchronous design generation;
- model/version tracking;
- solver-job coordination;
- artifact routing.

### Classification

**Primary CAD Workflow Orchestrator Candidate**

---

## FreeCAD MCP

**Source role:** simplified interface to FreeCAD.

### Strategic value

**5/5 — Strategic agent/CAD interoperability layer**

Recommended boundary:

```text
AI Agent
   ↓
MCP Client
   ↓
FreeCAD MCP
   ↓
Validated FreeCAD Operations
```

This is preferable to coupling an LLM directly to FreeCAD internals.

### Classification

**Strategic AI-to-CAD Tool Interface**

---

# 6. Category C — Generative & Parametric Design

## Rostok

**Source role:** open-source Python framework for generative design.

### Strategic value

**5/5 — Core generative-design candidate**

Best fit:

- topology/configuration exploration;
- parametric mechanism design;
- algorithmic generation;
- optimization-driven design.

### Classification

**Primary Generative Design Framework**

---

## PhysiOpt

**Source role:** Physics-Driven Shape Optimization for 3D Generative Models.

### Strategic value

**5/5 — Key differentiator for JFXAI4DIA**

This project is especially aligned with the project's title.

Architecture:

```text
Generated Shape
      ↓
Physics Constraint
      ↓
PhysiOpt
      ↓
Improved Geometry
      ↓
Solver Validation
```

### Classification

**Strategic Physics-Informed Generative Optimization Layer**

---

## CAD-Editor

**Source role:** Locate-then-Infill framework with ALDS.

### Strategic value

**4/5 — AI geometry editing research candidate**

Recommended role:

- local geometry repair/modification;
- constrained editing;
- selective geometry regeneration.

### Classification

**Research / Advanced CAD Editing Candidate**

---

# 7. Category D — Building / BIM Interoperability

## IfcOpenShell

**Source role:** open-source IFC toolkit.

### Strategic value

**5/5 — Core interoperability component**

Recommended role:

- IFC read/write;
- BIM normalization;
- geometry extraction;
- metadata;
- building digital thread.

Architecture:

```text
AI-Generated Building
       ↓
IFC
       ↓
IfcOpenShell
       ↓
Validation / Transformation
       ↓
Simulation / BIM Applications
```

### Classification

**Core BIM / IFC Interoperability Layer**

---

# 8. Category E — Aerospace Conceptual Design

## SUAVE

**Source role:** multi-fidelity conceptual-design environment.

### Strategic value

**5/5 — Strategic aircraft conceptual-design candidate**

Potential use:

- aircraft sizing;
- mission analysis;
- multidisciplinary conceptual design;
- design-space exploration.

### Classification

**Primary Multi-Fidelity Aerospace Candidate**

---

## openCDT

**Source role:** framework for conceptual aircraft design.

### Strategic value

**4/5 — Alternative conceptual-design framework**

Recommended as a replaceable alternative/comparison implementation to SUAVE and FAST-OAD.

---

## CEASIOMpy

**Source role:** conceptual aircraft design environment.

### Strategic value

**5/5 — Strategic aircraft MDO candidate**

Best use:

- CPACS-centered aircraft workflows;
- geometry/aerodynamic analysis;
- multidisciplinary aircraft design.

### Classification

**Strategic CPACS-Based Aircraft Design Component**

---

## FAST-OAD

**Source role:** open-source framework for rapid Overall Aircraft Design.

### Strategic value

**5/5 — Core aircraft overall-design candidate**

Architecture:

```text
Requirements
    ↓
FAST-OAD
    ↓
Aircraft Sizing
    ↓
Discipline Analysis
    ↓
Optimization
```

### Classification

**Primary Overall Aircraft Design Candidate**

---

# 9. Category F — Aerospace Data Schema

## CPACS

**Source role:** Common Parametric Aircraft Configuration Schema.

### Strategic value

**5/5 — Essential interoperability standard**

Recommended use:

```text
AI Design
   ↓
CPACS
   ↓
CEASIOMpy / FAST-OAD / Other Solvers
   ↓
Results
   ↓
Updated CPACS Model
```

### Classification

**Core Aerospace Data Contract**

This is strategically important because it allows JFXAI4DIA to connect multiple aircraft tools without making any single solver the master data model.

---

# 10. Category G — Aircraft Geometry

## AeroShape

**Source role:** robust 3D aircraft geometry modeling framework.

### Strategic value

**5/5 — Core geometry candidate for aerospace**

Best role:

- robust aircraft geometry;
- parameterized shape generation;
- analysis-ready geometry;
- bridge from CPACS/design variables to CFD/FEA.

### Classification

**Strategic Aerospace Geometry Kernel / Adapter**

---

# 11. Category H — Marine Generative Design

## ShipHullGAN

**Source role:** AI-driven ship-hull generation.

### Strategic value

**5/5 — High-value marine generative-design candidate**

Architecture:

```text
Hull Requirements
      ↓
ShipHullGAN
      ↓
Generated Hull Candidates
      ↓
Hydrodynamic / Geometric Validation
      ↓
Optimization
```

### Classification

**Strategic Marine Generative AI Candidate**

---

## C-ShipGen

**Source role:** conditional guided diffusion model for parametric ship-hull design.

### Strategic value

**5/5 — Advanced alternative to GAN-based hull generation**

Best use:

- conditioned hull generation;
- multiple design constraints;
- comparative generative-model research.

### Classification

**Strategic Diffusion-Based Marine Design Candidate**

---

# 12. Category I — Aerodynamic / Shape Optimization

## MACH-Aero

**Source role:** aerodynamic shape optimization framework.

### Strategic value

**5/5 — Core physics optimization candidate**

Recommended flow:

```text
Geometry
   ↓
CFD
   ↓
Adjoint / Sensitivity
   ↓
MACH-Aero
   ↓
Updated Geometry
```

### Classification

**Primary Aerodynamic Shape Optimization Candidate**

---

## GPkit

**Source role:** Python package for defining and manipulating geometric-programming models.

### Strategic value

**5/5 — Strong optimization layer**

Recommended for:

- aircraft sizing;
- system-level design;
- analytic design constraints;
- convex/geometric optimization.

### Classification

**Strategic System Optimization Component**

---

# 13. Category J — Data Assimilation & Optimization

## ADAO — SALOME Module

**Source role:** data assimilation and optimization.

### Strategic value

**5/5 — Strategic calibration / inverse-problem candidate**

Useful for:

- parameter estimation;
- model calibration;
- data assimilation;
- design optimization;
- digital-twin synchronization.

Architecture:

```text
Measured / Reference Data
          +
Simulation Model
          ↓
        ADAO
          ↓
Estimated Parameters
          ↓
Updated Engineering Model
```

### Classification

**Strategic Optimization & Data Assimilation Component**

---

# 14. Category K — CFD Code Generation

## OpenSBLI

**Source role:** open-source code-generation system for CFD.

### Strategic value

**5/5 — High-value automated CFD candidate**

Best role:

```text
PDE / CFD Problem
      ↓
OpenSBLI
      ↓
Generated Solver Code
      ↓
HPC Execution
      ↓
Flow Solution
```

This fits particularly well with AI-assisted engineering because a high-level agent can configure a solver workflow while OpenSBLI remains the deterministic numerical backend.

### Classification

**Primary Open CFD Code-Generation Candidate**

---

# 15. Category L — AI for CFD

## AutoCFD

**Source role:** fine-tuning a large language model for automating CFD simulations.

### Strategic value

**5/5 — Directly aligned AI-CFD research component**

Recommended architecture:

```text
Natural-Language CFD Intent
           ↓
AutoCFD-style Agent
           ↓
Case Configuration
           ↓
Validation Rules
           ↓
OpenFOAM / OpenSBLI
           ↓
Results
           ↓
AI Explanation
```

### Classification

**Strategic AI-to-CFD Automation Candidate**

AI-generated CFD cases should be validated before execution and results should never be accepted solely because the LLM configured them.

---

# 16. Category M — FreeCAD CFD

## FreeCAD CFD + OpenFOAM + FEniCS

**Source role:** CFD for FreeCAD using OpenFOAM and FEniCS solvers.

### Strategic value

**5/5 — Strong open CAD-to-physics bridge**

Recommended architecture:

```text
FreeCAD Geometry
       ↓
CFD Workbench / Adapter
       ↓
OpenFOAM / FEniCS
       ↓
Results
       ↓
FreeCAD Visualization / Optimization
```

### Classification

**Primary Open CAD-to-CFD Integration**

---

# 17. Category N — CFL3D

The source describes **CFL3D** as a structured-grid, cell-centered, upwind-biased RANS code.

The source README does **not** establish its license status.

Therefore it should not automatically be classified as part of the open-source core.

### Classification

**External / Research CFD Reference — License Verification Required**

Recommended architecture:

```text
Common CFD Case Definition
        |
        +---- OpenFOAM
        +---- OpenSBLI
        +---- optional CFL3D adapter
```

This avoids vendor/tool lock-in and keeps the primary reproducible CFD path open.

---

# 18. Category O — Multiphysics Structural Analysis

## MAST

**Source role:** Multidisciplinary-design Adaptation and Sensitivity Toolkit; sensitivity-enabled multiphysics FEA.

### Strategic value

**5/5 — Core structural/multiphysics optimization candidate**

Best use:

- finite-element analysis;
- structural sensitivities;
- multidisciplinary design;
- coupled optimization;
- shape/design derivatives.

### Classification

**Strategic Multiphysics FEA / Sensitivity Component**

---

# 19. Category P — Flight Simulation

## QPlane

**Source role:** fixed-wing flight-simulation environment.

### Strategic value

**4/5 — Flight dynamics validation candidate**

Recommended for:

- flight dynamics;
- control studies;
- conceptual aircraft validation;
- AI-generated design evaluation.

---

## Ptera Software

**Source role:** open-source package for flapping-wing flight analysis.

### Strategic value

**4/5 — Specialized bio-inspired / flapping-wing analysis**

Recommended for:

- ornithopters;
- MAV/UAV research;
- unsteady flapping-wing aerodynamics.

### Classification

**Specialized Aerospace Simulation Candidate**

---

# 20. FreeCAD Mechatronic Workbench

**Source role:** Mechatronic Workbench for FreeCAD.

### Strategic value

**4/5 — Mechatronic CAD extension candidate**

Useful for:

- multidisciplinary product models;
- electromechanical assembly;
- system integration;
- CAD-based engineering workflows.

### Classification

**Optional Mechatronic Design Integration**

---

# 21. Recommended Open Integration Backbone

The strongest cross-domain architecture from the source list is:

```text
                    AI DESIGN INTENT
                          |
       +------------------+------------------+
       |                                     |
       v                                     v
  CADAM / CQAsk                       FreeCAD AI
       |                                     |
       +------------------+------------------+
                          |
                    FreeCAD MCP
                          |
                          v
                PARAMETRIC GEOMETRY
              Rostok / AeroShape
                          |
        +-----------------+-----------------+
        |                 |                 |
        v                 v                 v
       IFC              CPACS         Native CAD/BREP
 IfcOpenShell       Aerospace        FreeCAD
        |                 |                 |
        +-----------------+-----------------+
                          |
                          v
                 PHYSICS SERVICES
      OpenFOAM / OpenSBLI / MAST / QPlane
                          |
                          v
                OPTIMIZATION SERVICES
         MACH-Aero / ADAO / GPkit / PhysiOpt
                          |
                          v
                 VERIFIED DESIGN
```

---

# 22. Cross-Domain Design Profiles

## Profile A — Open Building Design Automation

```text
Requirements
    ↓
AI-Arch / Aedifex
    ↓
CADAM
    ↓
IFC
    ↓
IfcOpenShell
    ↓
Physics / Optimization
    ↓
Validated BIM
```

Best for:

- architectural automation;
- generative building design;
- BIM-oriented workflows.

---

## Profile B — AI-Driven Aircraft Design

```text
Mission Requirements
       ↓
FAST-OAD / SUAVE
       ↓
CPACS
       ↓
AeroShape
       ↓
CEASIOMpy
       ↓
OpenFOAM / OpenSBLI
       ↓
MACH-Aero
       ↓
QPlane
       ↓
Validated Aircraft Concept
```

Best for:

- conceptual aircraft design;
- MDO;
- aerodynamic optimization;
- flight validation.

---

## Profile C — AI-Driven Ship Hull Design

```text
Hull Requirements
      ↓
ShipHullGAN
      OR
C-ShipGen
      ↓
Parametric Geometry
      ↓
Physics Evaluation
      ↓
PhysiOpt / Optimizer
      ↓
Validated Hull Family
```

Best for:

- generative marine geometry;
- comparative GAN/diffusion research;
- physics-driven hull refinement.

---

## Profile D — Natural-Language CAD + Physics

```text
Engineer Prompt
      ↓
CADAM / CQAsk / FreeCAD AI
      ↓
FreeCAD MCP
      ↓
FreeCAD Geometry
      ↓
OpenFOAM / FEniCS / MAST
      ↓
ADAO / GPkit
      ↓
Engineering Report
```

Best for:

- general industrial design;
- interactive engineering assistants;
- design automation.

---

## Profile E — AI-CFD Automation

```text
Engineering Question
      ↓
AutoCFD
      ↓
Case Definition
      ↓
Validation Rules
      ↓
OpenSBLI / OpenFOAM
      ↓
Solver Execution
      ↓
Post-processing
      ↓
AI Explanation
```

Best for:

- CFD workflow automation;
- training;
- rapid design exploration.

---

# 23. Multidisciplinary Optimization Loop

The preferred JFXAI4DIA loop is:

```text
          DESIGN VARIABLES
                ↓
         Geometry Generator
                ↓
     ┌──────────┼───────────┐
     ↓          ↓           ↓
Aerodynamics  Structures   Mission
OpenSBLI     MAST         QPlane
OpenFOAM
     └──────────┼───────────┘
                ↓
            Objectives
           + Constraints
                ↓
   MACH-Aero / ADAO / GPkit
                ↓
         Updated Design
                ↺
```

This preserves physics-based authority while allowing AI to manage the workflow.

---

# 24. Proposed Complementary Open AI Layer

The following are **proposed integrations**, not components asserted by the source README.

| Component | Proposed role |
|---|---|
| LangGraph | Agent/workflow state machine |
| MCP | Tool interoperability |
| FastAPI | Engineering service APIs |
| Qdrant | Engineering-document RAG |
| PostgreSQL | Job/state/metadata storage |
| Open WebUI | Optional engineering copilot UI |
| Ollama / llama.cpp | Local model runtime |
| vLLM | Private high-throughput inference |
| MLflow | Experiment/model tracking |
| OpenTelemetry | Distributed traces/metrics |

Open-weight local models can be exposed through a provider-neutral model gateway, while deterministic engineering solvers remain independent.

---

# 25. Engineering Agent Architecture

```text
Engineer
   |
   v
Engineering Copilot
   |
   +----- Requirements Agent
   +----- CAD Agent
   +----- CFD Agent
   +----- Optimization Agent
   +----- Validation Agent
   |
   v
Tool Gateway / MCP
   |
   +---- FreeCAD MCP
   +---- CADAM
   +---- IfcOpenShell
   +---- CPACS services
   +---- OpenSBLI
   +---- OpenFOAM
   +---- MAST
   +---- MACH-Aero
   +---- ADAO
   +---- QPlane
```

Recommended agent responsibilities:

- interpret design requirements;
- generate candidate parameter sets;
- invoke bounded CAD operations;
- configure simulation jobs;
- compare results;
- summarize sensitivities;
- identify constraint violations;
- create traceable engineering reports.

Agents should **not** override solver validity checks or engineering acceptance criteria.

---

# 26. Stable Integration Contracts

To minimize coupling:

| Boundary | Preferred contract |
|---|---|
| MBSE → design | requirements IDs + architecture model |
| Building design → BIM | IFC |
| Aircraft design → analysis | CPACS |
| CAD → geometry services | STEP / BREP / mesh formats |
| Agent → FreeCAD | MCP / bounded API |
| CFD configuration → solver | normalized case schema |
| Solver → optimization | objective/constraint API |
| Analysis → data layer | structured JSON/Parquet/HDF5 |
| Optimization → CAD | parameter vector + geometry update |
| AI → engineering tools | bounded service API / MCP |
| V&V → release | signed result/traceability record |

Actual format support must be checked against each upstream implementation.

---

# 27. Open-Core Prioritization

## Priority 1 — Architecture Backbone

- FreeCAD
- FreeCAD MCP
- IfcOpenShell
- CPACS
- OpenSBLI
- MAST
- MACH-Aero
- ADAO
- GPkit

These provide the strongest open interoperability, simulation and optimization backbone.

---

## Priority 2 — AI / Generative Design

- CADAM
- Aedifex
- Rostok
- PhysiOpt
- ShipHullGAN
- C-ShipGen
- FreeCAD AI
- CQAsk
- AgentSCAD

---

## Priority 3 — Aerospace Specialization

- FAST-OAD
- CEASIOMpy
- SUAVE
- openCDT
- AeroShape
- QPlane
- Ptera Software

---

## Priority 4 — Specialized / Research

- AI-Arch
- CAD-Editor
- Mechatronic Workbench
- AutoCFD

---

## Priority 5 — External / Verify Before Open-Core Inclusion

- CFL3D — source README does not establish license
- any project whose exact upstream repository/license cannot be uniquely resolved

---

# 28. Value & Role Matrix

| Component | Domain | Strategic Value | Recommended Role |
|---|---|---:|---|
| AI-Arch | Architecture AI | 4/5 | Building design optimization |
| Aedifex | Architecture/CAD AI | 5/5 | Interactive AI design workbench |
| SUAVE | Aerospace | 5/5 | Multi-fidelity conceptual design |
| CADAM | AI CAD | 5/5 | Text-to-CAD |
| Rostok | Generative Design | 5/5 | Parametric/generative design |
| AgentSCAD | CAD Orchestration | 5/5 | CAD-job orchestration |
| openCDT | Aerospace | 4/5 | Conceptual design alternative |
| IfcOpenShell | BIM | 5/5 | IFC interoperability |
| CAD-Editor | AI CAD Editing | 4/5 | Localized AI geometry editing |
| Ptera | Flight Physics | 4/5 | Flapping-wing analysis |
| CEASIOMpy | Aerospace MDO | 5/5 | CPACS-based analysis |
| PhysiOpt | Physics-Driven AI | 5/5 | Shape optimization |
| ADAO | Optimization | 5/5 | Data assimilation / calibration |
| FAST-OAD | Aircraft Design | 5/5 | Overall aircraft design |
| ShipHullGAN | Marine AI | 5/5 | Generative hull design |
| C-ShipGen | Marine AI | 5/5 | Diffusion hull generation |
| CQAsk | LLM/CAD | 4/5 | Natural-language CAD generation |
| GPkit | Optimization | 5/5 | Geometric programming |
| OpenSBLI | CFD | 5/5 | CFD code generation |
| FreeCAD AI | CAD AI | 5/5 | FreeCAD copilot |
| QPlane | Flight Simulation | 4/5 | Fixed-wing validation |
| CPACS | Aerospace Schema | 5/5 | Interoperability contract |
| AeroShape | Aircraft Geometry | 5/5 | Robust geometry |
| MACH-Aero | Aero Optimization | 5/5 | Shape optimization |
| CFL3D | CFD | 3/5 open-core fit | External/verify license |
| MAST | FEA/Multiphysics | 5/5 | Sensitivity-enabled FEA |
| FreeCAD MCP | Agent/CAD | 5/5 | AI tool interface |
| Mechatronic WB | Mechatronics | 4/5 | CAD extension |
| AutoCFD | AI/CFD | 5/5 research value | CFD automation |
| OpenFOAM/FEniCS CFD | CFD | 5/5 | Primary open CFD path |

---

# 29. Recommended MVP

The MVP should prove one complete **AI → CAD → Physics → Optimization** loop.

```text
Engineering Requirement
        ↓
CADAM / FreeCAD AI
        ↓
FreeCAD MCP
        ↓
FreeCAD Geometry
        ↓
OpenFOAM / OpenSBLI
        ↓
ADAO / GPkit
        ↓
Validated Design Alternative
        ↓
Engineering Report
```

### MVP capabilities

- natural-language design request;
- parameterized CAD generation;
- human review of geometry;
- automated mesh/case preparation;
- physics simulation;
- objective/constraint extraction;
- optimization iteration;
- result comparison;
- complete traceability.

---

# 30. Aerospace MVP Extension

```text
Mission Requirements
       ↓
FAST-OAD
       ↓
CPACS
       ↓
AeroShape
       ↓
CEASIOMpy
       ↓
OpenSBLI / OpenFOAM
       ↓
MACH-Aero
       ↓
QPlane
```

This is the strongest source-derived path for a dedicated aircraft-design demonstrator.

---

# 31. Marine MVP Extension

```text
Hull Requirements
      ↓
ShipHullGAN / C-ShipGen
      ↓
Generated Geometry
      ↓
Physics Validation
      ↓
PhysiOpt
      ↓
Candidate Hull Portfolio
```

The generative model should produce candidate geometry; downstream physics determines acceptance.

---

# 32. MBSE → CAD → CAM → CAS Mapping

```text
MBSE
Arcadia / Capella
requirements and system architecture
        ↓
CAD
CADAM / FreeCAD / Aedifex / AeroShape
        ↓
CAM
validated geometry for downstream manufacturing
        ↓
CAS
OpenSBLI / OpenFOAM / FEniCS
MAST / QPlane / CEASIOMpy
MACH-Aero / ADAO / PhysiOpt
        ↓
Engineering Verification
```

This makes CAS the **physics and multidisciplinary validation layer** rather than merely a visualization stage.

---

# 33. Recommended Repository Structure

```text
jfxai4dia/
├── README.md
├── docs/
│   ├── architecture/
│   ├── compendium/
│   ├── ai-design/
│   ├── interoperability/
│   ├── aerospace/
│   ├── marine/
│   ├── cfd/
│   ├── optimization/
│   └── validation/
│
├── MBSE/
│   ├── Capella/
│   ├── CAD/
│   ├── CAM/
│   └── CAS/
│
├── ai/
│   ├── cadam/
│   ├── cqask/
│   ├── freecad-ai/
│   ├── agentscad/
│   └── agents/
│
├── cad/
│   ├── freecad/
│   ├── freecad-mcp/
│   ├── ifc/
│   └── parametric/
│
├── aerospace/
│   ├── cpacs/
│   ├── fast-oad/
│   ├── ceasiompy/
│   ├── suave/
│   ├── aeroshape/
│   └── qplane/
│
├── marine/
│   ├── shiphullgan/
│   └── c-shipgen/
│
├── physics/
│   ├── opensbli/
│   ├── openfoam/
│   ├── fenics/
│   └── mast/
│
├── optimization/
│   ├── mach-aero/
│   ├── adao/
│   ├── gpkit/
│   └── physiopt/
│
└── tests/
    ├── geometry/
    ├── solver/
    ├── optimization/
    └── integration/
```

---

# 34. Roadmap

## Phase 1 — Open CAD Backbone

- FreeCAD;
- FreeCAD MCP;
- normalized geometry contracts;
- engineering artifact registry.

## Phase 2 — AI CAD

- CADAM;
- FreeCAD AI;
- CQAsk;
- AgentSCAD.

## Phase 3 — Physics

- OpenFOAM/FEniCS;
- OpenSBLI;
- MAST;
- validation harness.

## Phase 4 — Optimization

- ADAO;
- GPkit;
- PhysiOpt;
- multidisciplinary objective/constraint contracts.

## Phase 5 — Aerospace

- CPACS;
- FAST-OAD;
- CEASIOMpy;
- AeroShape;
- MACH-Aero;
- QPlane.

## Phase 6 — Marine

- ShipHullGAN;
- C-ShipGen;
- physics-driven hull validation.

## Phase 7 — BIM / Architecture

- Aedifex;
- AI-Arch;
- IFC;
- IfcOpenShell.

## Phase 8 — AI Engineering Platform

- RAG;
- engineering agents;
- model routing;
- audit;
- observability;
- experiment tracking.

---

# 35. Final Strategic Architecture

```text
                        JFXAI4DIA
                            |
                   AI ENGINEERING COPILOT
                            |
                 REQUIREMENTS / MBSE
                            |
          +-----------------+------------------+
          |                                    |
          v                                    v
      AI CAD                               DOMAIN AI
CADAM / CQAsk / FreeCAD AI       ShipHullGAN / C-ShipGen
          |                         AI-Arch / PhysiOpt
          +-----------------+------------------+
                            |
                            v
                    GEOMETRY LAYER
        FreeCAD / AeroShape / IfcOpenShell
                            |
              +-------------+-------------+
              |                           |
              v                           v
             IFC                        CPACS
          Buildings                   Aerospace
              |                           |
              +-------------+-------------+
                            |
                            v
                     PHYSICS LAYER
      OpenSBLI / OpenFOAM / FEniCS / MAST
                            |
                            v
                  OPTIMIZATION LAYER
         MACH-Aero / ADAO / GPkit / PhysiOpt
                            |
                            v
                  VERIFICATION / CAS
                            |
                            v
                    VALIDATED DESIGN
```

---

# 36. Strategic Recommendation

For a genuinely open and replaceable integration architecture, the strongest backbone is:

```text
FreeCAD
   +
FreeCAD MCP
   +
IfcOpenShell / CPACS
   +
OpenSBLI / OpenFOAM / FEniCS
   +
MAST
   +
ADAO / GPkit
   +
MACH-Aero / PhysiOpt
```

with the generative and AI front end selected per domain:

```text
General CAD  → CADAM / FreeCAD AI / CQAsk
Buildings    → Aedifex / AI-Arch
Aircraft     → FAST-OAD / CEASIOMpy / AeroShape
Ships        → ShipHullGAN / C-ShipGen
```

This avoids making an LLM, generative model, CAD system, solver, or optimizer the universal center of the platform.

Instead, **open schemas and validated physics form the integration backbone**.

---

# 37. Disclaimer

This document is a proposed engineering integration architecture derived from the alternatives explicitly listed in the JFXAI4DIA source README.

It does not claim that all listed projects are already integrated, mutually compatible, actively maintained, or distributed under identical open-source licenses.

Where the source description does not establish licensing or exact upstream identity, the component is marked as an external or verification-required candidate.

AI-generated geometry, optimization results, CFD cases, structural models, aircraft or ship concepts, and other engineering outputs require independent verification and validation before operational, manufacturing, or safety-critical use.
