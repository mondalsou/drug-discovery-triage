# Contributing to Drug Discovery Triage

Thank you for your interest in contributing! This project welcomes contributions from the community.

## 🎯 Project Goals

- **Scientific Accuracy**: All methods must be peer-reviewed
- **Transparency**: Predictions should be interpretable
- **Performance**: Fast response times (<100ms)
- **User Experience**: Clean, intuitive interface
- **Education**: Help users understand drug discovery

## 🚀 Getting Started

### Prerequisites
- Python 3.11+
- Node.js 20+
- Docker (optional)

### Setup
```bash
# Clone the repository
git clone https://github.com/mondalsou/drug-discovery-triage.git
cd drug-discovery-triage

# Backend
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload

# Frontend (in new terminal)
cd frontend
npm install
npm run dev
```

## 🔧 Development Workflow

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

## 📝 Pull Request Guidelines

### Before Submitting
- [ ] Code follows the project style
- [ ] All tests pass
- [ ] Documentation updated (if needed)
- [ ] Scientific methods cited (if applicable)

### PR Description Should Include
- What problem does this solve?
- How was it tested?
- Any breaking changes?
- Screenshots (for UI changes)

## 🧪 Testing

### Backend
```bash
cd backend
python -c "from app.chemistry import analyze_molecule; print(analyze_molecule('CCO', []))"
```

### Frontend
```bash
cd frontend
npm run build
```

## 📚 Areas for Contribution

### High Priority
- [ ] Batch processing (CSV upload)
- [ ] Export results (PDF/CSV)
- [ ] Additional ADMET endpoints
- [ ] Test coverage improvement

### Medium Priority
- [ ] 3D conformation generation
- [ ] Substructure search
- [ ] User authentication
- [ ] Molecule history

### Low Priority
- [ ] Dark/Light theme toggle
- [ ] Additional example molecules
- [ ] Keyboard shortcuts
- [ ] Mobile app (React Native)

## 🔬 Scientific Contributions

### Adding New Prediction Methods

When adding a new ADMET prediction:

1. **Research**: Find peer-reviewed literature
2. **Implement**: Add function to `backend/app/chemistry.py` or `backend/app/admet.py`
3. **Document**: Add docstring with reference
4. **Test**: Validate with known drugs
5. **Cite**: Add reference to documentation

**Example:**
```python
def _predict_new_property(mol: Chem.Mol) -> Dict:
    """
    Predict new property using validated method.

    Reference: Author et al., Journal 2020, 10, 123-456
    """
    # Implementation
    return {"property": value}
```

## 🎨 UI/UX Contributions

### Design Principles
- **Dark theme** (primary)
- **Material-UI components**
- **Responsive** (mobile-friendly)
- **Tooltips** for all metrics
- **Color-coded** (green/yellow/red)

### Adding New UI Components
```tsx
// Use existing patterns
<PropertyCard
  label="New Property"
  value={data.newProperty}
  tooltip="Description with citation"
  color={getColor(data.newProperty)}
/>
```

## 📖 Documentation

### Code Comments
- Use docstrings for all functions
- Explain WHY, not WHAT
- Cite scientific references

### README Updates
- Keep live demo link updated
- Add new features to features list
- Update screenshots

## 🐛 Bug Reports

### Good Bug Report Includes
- Browser/OS version
- Steps to reproduce
- Expected vs actual behavior
- SMILES string (if applicable)
- Screenshots

### Example
```
**Bug**: QED score shows NaN for caffeine

**Environment**: Chrome 120, macOS Sonoma

**Steps**:
1. Enter SMILES: CN1C=NC2=C1C(=O)N(C(=O)N2C)C
2. Click Analyze
3. See QED card shows NaN

**Expected**: QED score ~0.45
```

## 💡 Feature Requests

### Good Feature Request Includes
- Problem statement
- Proposed solution
- Use case / benefit
- Scientific reference (if applicable)

### Example
```
**Feature**: Add pKa prediction

**Problem**: Users need to know ionization state

**Solution**: Implement Marvin pKa algorithm

**Reference**: ChemAxon, J. Chem. Inf. Model. 2020

**Benefit**: Better solubility predictions
```

## 🤝 Code of Conduct

### Be Respectful
- Professional communication
- Constructive feedback
- Inclusive language
- Credit others' work

### Focus on Science
- All methods must be validated
- Cite original papers
- Question with data
- Peer review mindset

## 📫 Contact

Questions? Reach out:
- GitHub Issues: [Create issue](https://github.com/mondalsou/drug-discovery-triage/issues)
- Email: mondalsou@gmail.com

## 📜 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for making Drug Discovery Triage better! 🚀
