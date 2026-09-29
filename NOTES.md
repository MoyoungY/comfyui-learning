# Teaching notes

## Current status (supersedes setup-pending notes below)

- User confirms SD1.5 filename now appears in checkpoint selector. Discovery succeeded; actual loading and hash verification were not separately reported. Lesson 0003 completes graph wiring; await predictions before GPU launch/generation. GPU availability remains unknown.

- User found only ComfyUI/models/checkpoints/put_checkpoints_here. Default checkpoint directory is empty. Next download Comfy-Org SD1.5 v1-5-pruned-emaonly-fp16.safetensors (2.13 GB), verify published SHA256 e9476a13728cd75d8279f6ec8bad753a66a1957ca375a1464dc63b37db6e3916, refresh node definitions, select it. Download and selection not yet confirmed.

- User verified torch 2.7.1+cu118 / CUDA build 11.8 and confirmed the local browser editor loads after remote CPU-mode launch and SSH forwarding instructions. GPU execution and model installation remain unverified.
- Lesson 0002 prompt-branch checkpoint passed: user distinguished CLIP model from generated data and identified CLIP Text Encode with CLIP/text inputs. See LR-0004. Next establish available model filenames, then complete sampler inputs. GPU availability question remains unanswered.

- Teach in English, matching the user's request.
- User clarified they want full uv project dependency management: pyproject.toml, uv.lock, uv add/sync/run, not merely uv venv or uv pip. Use a wrapper project outside the ComfyUI checkout, import its requirements into that project, and explicitly source the pinned torch trio from the CUDA 11.8 index. Installation and dependency resolution remain unverified.
- User's verification reported torch 2.14.0+cu130 and CUDA build 13.0, differing from the proposed pinned cu118 environment. Cause unknown: inspect actual working directory, pyproject.toml, interpreter and torch path before changing packages. Successful import does not verify GPU execution. Next diagnostic uses uv run --no-sync to avoid altering state.
- Diagnosis confirmed from user output: remote project is /mnt/mnt1/myy/projects/courses/comfyui-course and interpreter/torch are in its .venv. Actual manifest has torch>=2.14.0, torchvision>=0.29.0, torchaudio>=2.11.0, requires-python>=3.11, and no tool.uv source/index configuration. Correct those declarations to exact 2.7.1/0.22.1/2.7.1 pins and explicit cu118 sources, narrow Python to 3.11, then uv lock and uv sync --locked. Preserve all other imported dependencies. Fix not yet verified; use actual remote path in future instructions.
- User subsequently verified torch 2.7.1+cu118 and runtime build 11.8 after the correction. Package version check passed; GPU computation, ComfyUI startup, and browser connection remain unverified. Next step: start pinned ComfyUI via wrapper uv run --locked with --cpu on server loopback, establish local SSH forwarding, verify editor loads without generating. Recheck GPU availability before switching to GPU mode.
- Mission supplied explicitly by the user; no further mission interview needed.
- Teach causal explanations; connect to Python and deep learning where useful.
- Ask for predictions before revealing answers. Revisit earlier material in later sessions for retention.
- Never equate lesson delivery or quiz self-checks with demonstrated mastery.
- ComfyUI is not installed. Remote Ubuntu server, SSH works, Python 3.11.5, NVIDIA driver 535.183.01 (nvidia-smi CUDA 12.2), two 24 GiB RTX 3090 GPUs. User wants local browser editing with remote execution. At 2026-09-29 17:19 both GPUs were 99–100% utilized by ESMNet_py39 jobs, about 14 GiB each; GPU 1 reported 92 C. Availability must be rechecked before generation.
- Propose isolated Python 3.11 venv and torch 2.7.1+cu118 as a driver-preserving introductory setup, with ComfyUI v0.3.40 planned (not installed or tested). Current upstream README now requires cu130+ for NVIDIA 20-series and newer, incompatible with this driver; do not blindly clone current main for this older stack. Explain old-release limitation and revisit modern setup for advanced workflows. No server commands have been executed by the agent.
- Lesson 0001 checkpoint passed: user explained LATENT versus IMAGE, decoder data and model inputs, and dependency independence from visual layout. See learning record 0002. No ComfyUI execution has been verified; durable retention remains to be checked later.
- Proposed progression (adapt to evidence): typed graph reading → full minimal text-to-image and execution → controlled experiments and debugging → image-to-image → LoRA → ControlNet → character consistency and comics → video/animation → remote operation and automation. Bring remote setup forward if needed to run initial exercises.
- Before subsequent lessons, read MISSION.md, learning-records, and assets. Start with one retrieval question from a previous lesson.
- Promote terms to GLOSSARY.md only after the learner demonstrates understanding. Initial terms promoted after lesson 0001 checkpoint.
