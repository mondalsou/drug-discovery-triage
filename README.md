# 💊 Drug Discovery Triage

<div align="center">

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-drug--discovery--triage-blue?style=for-the-badge)](https://drug-discovery-triage-hx7j.vercel.app)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)

**Production-ready web application for preliminary drug candidate screening with comprehensive ADMET predictions**

[Live Demo](https://drug-discovery-triage-hx7j.vercel.app) • [Documentation](#documentation) • [Tech Stack](#tech-stack) • [Features](#features)

</div>

---

## 🎯 Overview

**Drug Discovery Triage** is a modern web application that helps medicinal chemists and researchers rapidly assess drug-likeness and ADMET properties of small molecules. Built with transparency and scientific rigor in mind, it uses validated rule-based methods to predict:

- **Drug-likeness scores** (QED, Lipinski, Lead-likeness)
- **ADMET properties** (Solubility, BBB penetration, GI absorption, CNS MPO)
- **Toxicity alerts** (10 PAINS patterns, CYP450 metabolism)
- **Stereochemistry analysis** with educational context

### 🌟 Why This Project Stands Out

- ✅ **Production-ready**: Full-stack deployment with CI/CD
- ✅ **Scientifically validated**: All methods peer-reviewed (ESOL, Lipinski, CNS MPO, Murcko scaffolds)
- ✅ **Transparent**: Rule-based predictions (no black-box ML)
- ✅ **Modern UI/UX**: Dark-themed Material-UI with responsive design
- ✅ **Fast**: <100ms prediction time, instant results
- ✅ **Educational**: Explains WHY stereoisomers differ in biology

---

## 🚀 Live Demo

**Try it now:** [https://drug-discovery-triage-hx7j.vercel.app](https://drug-discovery-triage-hx7j.vercel.app)

### Example Molecules to Test:

| Molecule | SMILES | Expected Results |
|----------|--------|------------------|
| **(S)-Ibuprofen** | `CC(C)Cc1ccc([C@H](C)C(=O)O)cc1` | QED: 0.72, BBB+, High CNS |
| **Aspirin** | `CC(=O)OC1=CC=CC=C1C(=O)O` | QED: 0.58, Lead-like |
| **Caffeine** | `CN1C=NC2=C1C(=O)N(C(=O)N2C)C` | BBB+, CNS active |

---

## ✨ Key Features

### 🧪 Comprehensive ADMET Predictions

<table>
<tr>
<td width="50%">

**Absorption & Distribution**
- Aqueous solubility (ESOL equation)
- GI absorption (Lipinski + Veber)
- BBB penetration (multi-parameter)
- CNS MPO score (Pfizer method)

</td>
<td width="50%">

**Metabolism & Toxicity**
- CYP450 substrate predictions
- 10 PAINS/structural alerts
- Clinical toxicity risk
- FDA approval likelihood

</td>
</tr>
</table>

### 📊 Drug-likeness Metrics

- **QED Score**: Quantitative Estimate of Drug-likeness (0-1 scale)
- **Lipinski Rule-of-Five**: Oral bioavailability assessment
- **Lead-likeness**: Rule of 3 for fragment screening
- **Scaffold Analysis**: Murcko scaffold extraction

### 🔬 Stereochemistry Analysis

- Identifies chiral centers (R/S configuration)
- Educational context explaining enantiomer differences
- Visual structure comparison
- Historical examples (Thalidomide, Ibuprofen)

### 🎨 Modern User Interface

- Dark-themed Material-UI design
- Real-time predictions (<100ms)
- Interactive property cards with tooltips
- Responsive layout (mobile-friendly)
- Copy SMILES functionality

---

## 🛠️ Tech Stack

### Backend
- **FastAPI** - High-performance Python API framework
- **RDKit** - Cheminformatics toolkit for molecular descriptors
- **Pydantic** - Data validation and settings management
- **Uvicorn** - ASGI server

### Frontend
- **React 19** - Modern UI library
- **TypeScript** - Type-safe JavaScript
- **Material-UI 7** - Component library
- **Vite** - Fast build tool

### Deployment
- **Vercel** - Frontend hosting with edge functions
- **Railway/Render** - Backend API hosting
- **Docker** - Containerization for reproducibility
- **GitHub Actions** - CI/CD pipeline

---

## 📚 Documentation

### Quick Start

```bash
# Clone the repository
git clone https://github.com/mondalsou/drug-discovery-triage.git
cd drug-discovery-triage

# Run with Docker Compose (easiest)
docker-compose up --build

# Access the application
# Frontend: http://localhost:3000
# Backend API: http://localhost:8000
# API Docs: http://localhost:8000/docs
```

### Local Development

**Backend:**
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

---

## 🔬 Scientific Validation

All prediction methods are based on peer-reviewed literature:

| Method | Reference | Year |
|--------|-----------|------|
| ESOL Solubility | Delaney, *J. Chem. Inf. Comput. Sci.* | 2004 |
| Lipinski RO5 | Lipinski et al., *Adv. Drug Deliv. Rev.* | 2001 |
| CNS MPO | Wager et al., *ACS Chem. Neurosci.* | 2010 |
| Lead-likeness | Congreve et al., *Drug Discovery Today* | 2003 |
| Murcko Scaffolds | Bemis & Murcko, *J. Med. Chem.* | 1996 |
| PAINS | Baell & Holloway, *J. Med. Chem.* | 2010 |

---

## 📊 Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     User Browser                        │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              Frontend (React + Vite)                    │
│              Hosted on Vercel                           │
│  • Material-UI components                               │
│  • TypeScript for type safety                           │
│  • Responsive design                                    │
└────────────────────┬────────────────────────────────────┘
                     │ REST API
                     ▼
┌─────────────────────────────────────────────────────────┐
│            Backend (FastAPI + RDKit)                    │
│            Hosted on Railway/Render                     │
│  • Molecular descriptor calculation                     │
│  • ADMET predictions                                    │
│  • Structure rendering                                  │
└─────────────────────────────────────────────────────────┘
```

---

## 🎯 Use Cases

### For Medicinal Chemists
- Rapid compound prioritization
- SAR analysis with scaffold extraction
- ADMET liability identification
- Stereochemistry education

### For Researchers
- Virtual screening preparation
- Compound library profiling
- Lead optimization guidance
- Drug-likeness assessment

### For Educators
- Teaching medicinal chemistry concepts
- Demonstrating ADMET principles
- Stereochemistry visualization
- Property-based design

---

## 🚢 Deployment

### Docker Compose (Self-Hosted)
```bash
docker-compose up --build
```

### Vercel (Frontend)
```bash
cd frontend
vercel --prod
```

### Railway (Backend)
```bash
cd backend
railway up
```

See [DEPLOYMENT_GUIDE.md](DEPLOYMENT_GUIDE.md) for detailed instructions.

---

## 🤝 Contributing

Contributions are welcome! This project is designed to be:
- **Educational**: Clear, well-documented code
- **Extensible**: Easy to add new prediction methods
- **Scientific**: All methods must be peer-reviewed

### Areas for Enhancement
- [ ] Batch processing (CSV upload)
- [ ] Export results (PDF/CSV)
- [ ] Additional ADMET endpoints
- [ ] 3D conformation generation
- [ ] Substructure search

---

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Sourav Mondal**

- GitHub: [@mondalsou](https://github.com/mondalsou)
- LinkedIn: [Sourav Mondal](https://www.linkedin.com/in/sourav-mondal)

---

## 🙏 Acknowledgments

- **RDKit** community for the excellent cheminformatics toolkit
- **FastAPI** for the modern Python web framework
- **Material-UI** for the beautiful component library
- Scientific literature authors for validated ADMET methods

---

## 📈 Project Stats

- **Lines of Code**: ~3,500 (Python + TypeScript)
- **Prediction Time**: <100ms per molecule
- **Docker Image Size**: ~500MB (optimized)
- **Test Coverage**: Core chemistry functions validated
- **Deployment**: Automated CI/CD with GitHub Actions

---

<div align="center">

### ⭐ Star this repo if you find it useful!

**Built with ❤️ for the drug discovery community**

[Live Demo](https://drug-discovery-triage-hx7j.vercel.app) • [Report Bug](https://github.com/mondalsou/drug-discovery-triage/issues) • [Request Feature](https://github.com/mondalsou/drug-discovery-triage/issues)

</div>
