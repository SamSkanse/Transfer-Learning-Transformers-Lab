# Transfer-Learning-Transformers-Lab
This is a lab for my deep learning 2 class. I will be taking a pre-trained transformer and transfer learning using a sequential dataset of my choosing

## Environment Setup

This project supports GPU acceleration on both Windows (CUDA) and macOS (M1 Pro with Metal Performance Shaders).

### Prerequisites
- Python 3.10 or higher
- pip package manager

### Step 1: Create Virtual Environment

Create a virtual environment in the project directory:

```bash
python -m venv .venv
```

### Step 2: Activate Virtual Environment

**On macOS:**
```bash
source .venv/bin/activate
```

**On Windows (PowerShell):**
```powershell
.venv\Scripts\Activate.ps1
```

**On Windows (Command Prompt):**
```cmd
.venv\Scripts\activate.bat
```

### Step 3: Install Dependencies

**For macOS (M1 Pro with Metal Performance Shaders):**
```bash
pip install torch torchvision torchaudio
pip install -r requirements.txt
```

**For Windows (CUDA-enabled GPU):**
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install -r requirements.txt
```

**For Development (optional):**
```bash
pip install -r requirements-dev.txt
```
This installs additional tools: `nbstripout` (strips Jupyter metadata), `black` (code formatter), `flake8` (linter), and `pytest` (testing framework).

### Step 4: Verify GPU Access

**For macOS:**
```python
import torch
print(torch.backends.mps.is_available())  # Should return True if M1/M2/M3+ available
```

**For Windows (CUDA):**
```python
import torch
print(torch.cuda.is_available())  # Should return True if CUDA available
print(torch.cuda.get_device_name(0))  # Shows GPU name
```

### VS Code Configuration

The project is configured to use the virtual environment's Python interpreter. When you open the project:
1. The Python interpreter is automatically set to `.venv/bin/python` (macOS) or `.venv/Scripts/python.exe` (Windows)
2. Newly opened terminals automatically execute in the file's directory
3. VS Code will prompt you to select the interpreter if not already configured
