# ComfyUI Resources

Reviewed 2026-09-29. Recheck implementation-sensitive details when teaching them.

## Knowledge

- [Apply ControlNet Advanced](https://docs.comfy.org/built-in-nodes/ControlNetApplyAdvanced)
  Positive/negative conditioning ports, control model and image inputs, strength and active interval. Reviewed 2026-09-30 for lesson 0012.

- [Built-in Canny node](https://docs.comfy.org/built-in-nodes/Canny)
  IMAGE input/output, threshold ranges and defaults (0.4/0.8), edge preview troubleshooting. Reviewed 2026-09-30 for lesson 0011; current official documentation, pinned source fetch unavailable.

- [ControlNet v1.1 SD1.5 Canny model card](https://huggingface.co/lllyasviel/control_v11p_sd15_canny)
  Original model family and expected Canny-edge conditioning. [ComfyUI maintainer FP16 file](https://huggingface.co/comfyanonymous/ControlNet-v1-1_fp16_safetensors/blob/main/control_v11p_sd15_canny_fp16.safetensors): 723 MB and published SHA256. Selected for introductory SD1.5 exercise, reviewed 2026-09-30.

- [Maintainer ControlNet examples](https://github.com/comfyanonymous/ComfyUI_examples/blob/master/controlnet/README.md)
  Control images must match the ControlNet type; application does not automatically extract edges/depth. Model directory and model sources. Reviewed 2026-09-30 for lesson 0010.

- [PixelArtRedmond SD1.5 model card](https://huggingface.co/artificialguybr/pixelartredmond-1-5v-pixel-art-loras-for-sd-1-5)
  Creator's SD1.5 adapter and trigger words “pixel art, PixArFK”; selected for introductory style comparison, reviewed 2026-09-30. [File and published SHA256](https://huggingface.co/artificialguybr/pixelartredmond-1-5v-pixel-art-loras-for-sd-1-5/blob/main/PixelArtRedmond15V-PixelArt-PIXARFK.safetensors). Creator reports training on Liberte, an SD1.5 variant; results with the learner's vanilla checkpoint remain untested.

- [Official guide: LoRA](https://docs.comfy.org/tutorials/basic/lora)
  Load LoRA ports, installation directory, and model/CLIP strength controls; reviewed 2026-09-30 for lesson 0009. Choose the actual adapter only after checking its base-model compatibility and creator instructions.

- [Official guide: Inpainting](https://docs.comfy.org/tutorials/basic/inpaint)
  Mask editor, VAE Encode (for Inpainting), and comparison of general SD1.5 versus specialized inpainting models. Reviewed 2026-09-30 for lesson 0008.

- [Official guide: Image to Image](https://docs.comfy.org/tutorials/basic/image-to-image)
  Input-image workflow and denoise comparison for lesson 0007. Reviewed 2026-09-30; use pinned nodes.py for VAE Encode port types and avoid treating the guide’s simplified full-noise analogy as exact implementation detail.

- [Classifier-Free Diffusion Guidance — Ho and Salimans](https://arxiv.org/abs/2207.12598)
  Primary research on guidance strength and the tradeoff between sample fidelity and diversity; introduced for lesson 0006. Reviewed 2026-09-30.

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
