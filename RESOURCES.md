# ComfyUI Resources

Reviewed 2026-09-29. Recheck implementation-sensitive details when teaching them.

## Knowledge

- [Comfy-Org SD1.5 FP16 checkpoint](https://huggingface.co/Comfy-Org/stable-diffusion-v1-5-archive/blob/main/v1-5-pruned-emaonly-fp16.safetensors)
  Official introductory checkpoint download, file size, and published SHA256; selected for first basic workflow.

- [uv: PyTorch integration](https://docs.astral.sh/uv/guides/integration/pytorch/)
  Named explicit CUDA indexes and tool.uv.sources for project-based dependency management.
- [uv: Locking and syncing](https://docs.astral.sh/uv/concepts/projects/sync/)
  Lockfile generation, exact environment synchronization, and locked execution.

- [uv: Using environments](https://docs.astral.sh/uv/pip/environments/)
  Creating a Python-version-specific venv and explicitly targeting its interpreter with uv pip.

- [Official guide: Nodes](https://docs.comfy.org/basic-concepts/nodes)
  Node operations, ports, types, and connections. Primary reading for lesson 0001.
- [Official guide: Text to Image](https://docs.comfy.org/tutorials/basic/text-to-image)
  Standard Stable Diffusion example and roles of its components; useful for the first full workflow.
- [Official guide: First Generation](https://docs.comfy.org/get_started/first_generation)
  Loading example workflows, model placement, and first-run troubleshooting. Use once setup is known.
- [ComfyUI source: nodes.py](https://github.com/Comfy-Org/ComfyUI/blob/master/nodes.py)
  Inspect INPUT_TYPES and RETURN_TYPES for KSampler, VAEDecode, and SaveImage. Source resolves details simplified in prose: EmptyLatentImage creates zeros; random noise is prepared in the sampling path. The tutorial's description of an empty latent as pure noise is imprecise.

- [Official guide: Manual installation](https://docs.comfy.org/installation/manual_install)
  Environment isolation, dependencies, and server launch. Match PyTorch selection to the actual driver before installing.
- [Official guide: Server overview](https://docs.comfy.org/development/comfyui-server/comms_overview)
  Browser frontend and Python execution server architecture.
- [ComfyUI source: CLI arguments](https://github.com/Comfy-Org/ComfyUI/blob/master/comfy/cli_args.py)
  Verify listen address, port, and GPU selection flags for remote operation.
- [OpenSSH manual: ssh](https://man.openbsd.org/ssh)
  Primary reference for local port forwarding with -L and tunnel-only sessions with -N.

- [PyTorch official previous versions](https://pytorch.org/get-started/previous-versions/)
  Verified matching torch 2.7.1, torchvision 0.22.1, torchaudio 2.7.1 CUDA 11.8 wheels for the proposed introductory environment.
- [NVIDIA CUDA compatibility](https://docs.nvidia.com/deploy/cuda-compatibility/minor-version-compatibility.html)
  Driver compatibility and caveats; CUDA 13 requires driver branch 580 or newer, older CUDA binaries benefit from driver backward compatibility.
- [ComfyUI v0.3.40 source](https://github.com/Comfy-Org/ComfyUI/tree/v0.3.40)
  Proposed older introductory version for this server; dependencies and runtime still require validation. Current main has different GPU requirements.

## Wisdom (Communities)


- [Official ComfyUI repository](https://github.com/Comfy-Org/ComfyUI)
  Maintainer issue discussions for reproducible implementation problems; search existing reports before filing. Community participation is optional and no preference has been stated.

## Gaps

- Select model-specific primary sources for LoRA, ControlNet, character consistency, and video when those lessons become relevant.
- Verify installation and remote deployment instructions against the learner's actual environment.
