# llm-resource-meter
Estimate the real-world resource consumption of LLM usage, including tokens, energy, water, and carbon impact. The project helps users understand the environmental cost of their AI interactions and estimate consumption across individual sessions, days, months, or years.

# Architecture
                    ┌─────────────────────┐
                    │       User          │
                    │ prompts / tokens    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Usage Input      │
                    │ input + output      │
                    │ tokens + model      │
                    └──────────┬──────────┘
                               │
                               ▼
              ┌──────────────────────────────┐
              │     Resource Estimation      │
              │                              │
              │ Token Calculator              │
              │ Energy Estimator              │
              │ Water Estimator               │
              │ Carbon Estimator              │
              └──────────────┬───────────────┘
                             │
                             ▼
                    ┌─────────────────────┐
                    │   Usage Result      │
                    │                     │
                    │ tokens              │
                    │ Wh / kWh            │
                    │ liters              │
                    │ g / kg CO₂e         │
                    └──────────┬──────────┘
                               │
                    ┌──────────▼──────────┐
                    │     API / CLI       │
                    └──────────┬──────────┘
                               │
                         ┌─────▼─────┐
                         │ Dashboard │
                         └───────────┘
                         
## repository structure
llm-resource-meter/
│
├── src/
│   └── resource_meter/
│       ├── models.py
│       ├── tokens.py
│       ├── energy.py
│       ├── water.py
│       ├── carbon.py
│       └── estimator.py
│
├── tests/
│   └── test_estimator.py
│
├── examples/
│   └── basic_estimate.py
│
├── README.md
├── pyproject.toml
└── LICENSE
