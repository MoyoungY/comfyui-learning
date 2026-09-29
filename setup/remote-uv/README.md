# Remote uv project bootstrap

Target: Ubuntu x86_64, Python 3.11, NVIDIA driver 535.183.01. Proposed introductory stack: ComfyUI v0.3.40 and PyTorch 2.7.1 CUDA 11.8. This is an older learning setup; current ComfyUI/model support must be revisited for advanced lessons. Remote resolution and execution have not yet been tested.

Copy pyproject.toml beside (not inside) a fresh ComfyUI checkout in ~/comfyui-course on the remote server. The initial manifest contains only the pinned PyTorch packages. Importing ComfyUI requirements is required before running the app:

```bash
cd ~/comfyui-course
git clone --branch v0.3.40 --depth 1 https://github.com/Comfy-Org/ComfyUI.git ComfyUI
uv python pin 3.11
uv add --no-sync -r ComfyUI/requirements.txt
uv lock
uv sync --locked
uv run --locked python -c "import torch; print(torch.__version__); print(torch.version.cuda)"
```

If ComfyUI already exists, inspect the checkout rather than replacing it. Stop and inspect any dependency resolution error before changing pins. uv sync reconciles the project .venv exactly, so this directory should hold a dedicated course environment. The requirements import is a snapshot; future changes to upstream requirements are not automatically imported.

After successful setup, retain pyproject.toml, uv.lock, .python-version, and the result of `git -C ComfyUI rev-parse HEAD`. The lockfile tracks Python dependencies, not the application checkout or model weights.

When a GPU is available, run from the wrapper directory:

```bash
uv run --locked python ComfyUI/main.py --cuda-device 0 --listen 127.0.0.1 --port 8188
```

If using a different GPU, select its available device ID. Keep uv project commands in the wrapper directory to avoid selecting ComfyUI's own project metadata. Register later custom-node requirements through uv add before syncing.
