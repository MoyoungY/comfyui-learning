# Teaching notes

## Current status (supersedes setup-pending notes below)

- Lesson 0016 mini-project complete by user report (LR-0032): flowers appeared in panel 2, matched pixel-art surroundings, fox visually unchanged. Finish with saving both original PNGs, regular workflow JSONs, and relevant reference/mask inputs; backup not yet confirmed. Pause at this milestone rather than immediately adding another quiz. Guided integration demonstrated; independent reconstruction and cross-pose identity remain untested. Scarf issue remains intentionally deferred.

- Mini-project plan checkpoint passed (LR-0031): user chose inpainting and has a suitable first pixel-art fox image. Next create panel 2 in a copy of the successful inpainting graph, load panel 1, mask bare ground away from fox, add PixelArtRedmond MODEL/CLIP branches at 0.8/0.8, direct text conditioning to sampler without Canny control for this local edit. Flower-focused pixel-art prompt; denoise 1, seed 43 fixed, CFG 7, 20 steps, euler/normal. Await flowers/style/boundary observations.

- User accepted a two-image mini-project. Lesson 0016: same-view pixel-art story, fox beneath tree with bare ground, then yellow flowers in a small patch; focus style and controlled local change, no scarf or strict identity requirement. First ask learner to choose between full regeneration and inpainting for panel 2, with reasoning. Await plan and images. Prior “ok” did not explicitly verify JSON/reference backup; do not mark it confirmed.

- PNG restoration and visually matching rerun succeeded by user report (LR-0030). Next finish lesson 0015 by exporting regular editable workflow JSON and retaining the original reference image alongside output PNG. Export/backup not yet confirmed. Do not claim fresh deterministic computation or cross-machine reproducibility; same-session caching possible.

- User explicitly chose to stop scarf-placement troubleshooting; respect that choice and do not resume it without request. Lesson 0015 practices restoring a preferred result from original PNG workflow metadata, exporting regular workflow JSON, and retaining reference input. Await restoration/rerun report; no reproducibility success established yet.

- User says scarf may shift elsewhere, not just change folds. Treat as possible accessory-placement failure, not confirmed visual diagnosis. Next compare at seed 45 with a more explicit prompt: blue scarf wrapped snugly around neck directly below chin, small knot at front. Keep reference and strengths unchanged. Existing Canny map came from original scarf-free fox and provides no scarf-location outline; prompt refinement is a test, not a placement guarantee.

- Scarf comparison reported (LR-0029): blue scarf remains in seed-45 result, but placement may vary relative to seed 44. Next distinguish minor changes in knot/hanging ends from displacement off the neck before proposing edits. Do not treat positional variation as automatically unacceptable or claim full character consistency.

- Blue scarf appeared by user report after positive prompt edit (LR-0028). Next save seed-44 result and compare seed 45 with identical scarf prompt, reference, and other settings; inspect scarf presence/color/location. Do not infer identity consistency from one generated marker or silently count scarf generation as persistence.

- Identity assessment corrected (LR-0027 supersedes LR-0026): selected details were fox pose/tree shape, and user says fox is mostly white with few visible details. Only style/structure consistency is established; identity remains unclear. Next add one observable design attribute (blue scarf) in the combined workflow with current seed/settings held fixed, then inspect whether it appears. A shared accessory alone will not prove full character identity; ControlNet may constrain the edit.

- Lesson 0014 comparison completed by user report (LR-0026): both seeds produced pixel-art style, similar layout, and unchanged chosen identity details. Details were not named; do not invent them. Next name the two details to make the evaluation reusable, then test a changed composition/reference for comic-panel transfer. Current evidence covers only one composition and two seeds.

- User correctly selected LoRA branch for missing style with retained layout (LR-0025), but gave no independent explanation. Lesson 0014 tests the combined workflow across seeds 43/44 and asks for separate style/layout/identity observations. Await results; this is a same-composition consistency check, not yet a multi-panel character-consistency achievement.

- Lesson 0013 complete by user report (LR-0024): LoRA-enabled result looked more pixel-art while following fox outline/tree placement with Canny control held fixed. Next use a short independent diagnosis/retrieval exercise before adding more tools; user has followed guided construction, but independent debugging and delayed retention are not established. Save combined workflow/result; do not equate structural similarity with character consistency.

- Outline-versus-identity checkpoint passed (LR-0023). Lesson 0013 combines PixelArtRedmond with the working Canny graph: control strength fixed 0.8, same pixel-art trigger prompt both runs, LoRA 0/0 versus 0.8/0.8. Await combined results; no claim that style and structure controls are independent or guarantee identity.

- ControlNet comparison passed by user report (LR-0022): strength 0.8 followed fox outline/tree position more closely than 0. Lesson 0012 execution complete; model loading is supported by reported effect, though exact settings not inspected. Apply ControlNet optional VAE was clarified as unnecessary for this SD1.5 Canny workflow; decoder still requires VAE. Next integrate previously tested pixel-art LoRA with Canny while holding ControlNet fixed, after a brief transfer prediction. Character identity remains untested.

- Canny preview checkpoint passed (LR-0021): recognizable fox/tree edges reported. Lesson 0012 wires Apply ControlNet (Advanced) into both conditioning branches of a basic SD1.5 text-to-image graph, with Load Image/Canny as a separate control branch. Await wiring; model selector visibility remains implicit, actual loading unverified. First comparison strength 0 versus 0.8, start 0/end 1, fixed seed and settings; LoRA excluded for this first isolated test.

- User acknowledged ControlNet installation instructions with “ok”; download/selection not explicitly confirmed. Lesson 0011 prepares a standalone Load Image → Canny → Preview Image graph, built-in Canny thresholds 0.4/0.8 as documented defaults. Await edge visibility and node availability; this preview does not verify ControlNet model loading. Pinned nodes_canny.py could not be fetched; settings verified against current official node documentation, not pinned source.

- Remote controlnet directory contains only put_controlnets_and_t2i_here. Selected control_v11p_sd15_canny_fp16.safetensors from comfyanonymous/ControlNet-v1-1_fp16_safetensors (723 MB). Published SHA256 8932b66e15aae835b3490dbf989f56c253104cee08a88bf21283762f557c9f10. Download, checksum, selector visibility, and actual loading remain unconfirmed. Next after discovery: prepare and preview the fox edge map using available Canny node, then wire control conditioning.

- Lesson 0010 input-type checkpoint passed: user chose extracted edge map for Canny ControlNet (LR-0020). Next request remote ComfyUI/models/controlnet directory listing to discover an SD1.5-compatible Canny model. No model availability, preprocessing, wiring, or execution confirmed yet.

- LoRA comparison-control checkpoint passed (LR-0019). Lesson 0010 introduces matching a ControlNet to its control-image type, starting with Canny edges of the fox for composition. Await concept prediction and remote models/controlnet inventory; no ControlNet model installed/selected or workflow executed yet. Avoid human-pose preprocessing for this fox exercise.

- First LoRA comparison succeeded by user report (LR-0018): user chose strengths 0.8/0.8 as stronger pixel-art style versus 0/0. This supports actual adapter use, superseding installation-pending uncertainty for the reported experiment; hash and exact settings remain unverified. Next assess why both prompts included trigger words to isolate adapter contribution. Do not infer MODEL/CLIP effects separately or character consistency.

- User acknowledged download instructions with “ok”; installation/selection are not explicitly confirmed. Next conditional test is PixelArtRedmond strengths 0/0 versus 0.8/0.8, same pixel-art fox prompt with PixArFK, seed 43 fixed, CFG 7, steps 20, euler/normal, denoise 1, 512 square batch 1. Await results; strengths are experimental starting values.

- Remote loras directory contains only put_loras_here. Selected PixelArtRedmond15V-PixelArt-PIXARFK.safetensors (27.2 MB) from artificialguybr/pixelartredmond-1-5v-pixel-art-loras-for-sd-1-5 for a visibly distinct style experiment. Creator documents SD1.5 family, trained on Liberte, triggers “pixel art, PixArFK”; vanilla SD1.5 result not yet tested. Published SHA256 b770d01002510180cd03b5f8c8199fdb41d924c51d4980fc86298d0e4cdf7953. Download, selection, wiring, and generation remain unconfirmed. No numerical strength recommendation found on reviewed card; label future initial strength as experimental, not author-prescribed.

- Lesson 0009 output-type checkpoint passed: user identified adjusted MODEL and CLIP objects (LR-0017). Next request remote ComfyUI/models/loras inventory; no adapter selected and wiring not confirmed. Check creator model card for SD1.5 compatibility, trigger words, and recommended strengths before execution.

- Lesson 0009 introduces Load LoRA on a copy of the original text-to-image graph. Await identification of its MODEL/CLIP outputs and available SD1.5 LoRA files; none selected or installed yet. Do not assume the tutorial's example LoRA or its strengths are suitable for the user's existing checkpoint.

- Lesson 0008 complete by user report (LR-0016): user says result now looks good and is finished with review questions; earlier reported fox visually unchanged. Stop boundary troubleshooting. No final adjustment was specified, so do not infer which remedy worked. Next suitable progression: save the successful workflow/result, then introduce LoRA for reusable style control; no LoRA lesson delivered or model selected yet.

- User reports final flower patch blends somewhat unnaturally while fox looks unchanged. Next distinguish a visible patch boundary from mismatched color/lighting/watercolor style before selecting a remedy. Do not assume a hard-mask seam or recommend mask expansion/feathering without identifying the observed issue.

- Inpainting succeeded by user report (LR-0015): mask preview had a white patch, masked area changed on initial run, and flowers appeared after switching positive prompt to “a cluster of small yellow wildflowers, green stems and leaves, watercolor painting”. Other inputs were instructed unchanged, not independently verified. Next assess whether user can distinguish working mask from prompt/content failure; final fox preservation and boundary quality remain unchecked.

- First inpainting run reported: flowers did not appear; fox stayed visually similar. Cause unknown. Next inspect Load Image.MASK via Convert Mask to Image → Preview Image to confirm nonempty mask and intended polarity/location before changing prompt, CFG, or seed. Do not infer mask success merely from fox preservation.

- Inpainting checkpoint passed: user chose the background as the edit region and confirms saved mask and wiring (LR-0014). Next run the lesson 0008 flower prompt at denoise 1.0, seed 43 fixed, CFG 10, 20 steps, euler/normal, grow_mask_by 6. Await result before claiming successful inpainting.

- Lesson 0008 introduces background-patch inpainting with existing SD1.5 checkpoint and VAE Encode (for Inpainting). Await mask-location prediction and wiring confirmation before first inpaint. Use a small background patch away from fox, grow_mask_by 6, denoise 1.0 for the cleared-region workflow; do not transfer the prior 0.3 setting blindly or promise exact unmasked-pixel preservation.

- Lesson 0007 checkpoint complete: user chose denoise 0.3 for a small adjustment preserving the fox illustration (LR-0013). Next suitable lesson: inpainting for editing a selected region, contrasting edit location with denoise strength. No inpainting lesson delivered yet; revisit denoise versus brightness later without assuming mastery.

- Image-to-image results reported (LR-0012): 0.3 stayed closer; pose, shape, watercolor style did not noticeably change in the compared results. User reported brighter fur/background at 1.0; interpreted brief “yes” as an extra 1.0 test, but run sequence is ambiguous. Next check distinction between denoise permitting changes and directly controlling brightness; do not teach a monotonic denoise-brightness rule.

- Lesson 0007 prediction passed: user chose denoise 0.3 for closer pose preservation and reports wiring complete (LR-0011). Next run 0.3 versus 0.7 with the same original fox input, seed 43 fixed, CFG 10, unchanged prompts and remaining settings. Await results; do not treat wiring report as successful image-to-image execution.

- Lesson 0007 introduces image-to-image using the preferred saved fox image, Load Image → VAE Encode → KSampler. Await wiring confirmation and prediction for denoise 0.3 versus 0.7; no image-to-image execution or understanding established yet. Preserve the text-to-image workflow as a separate saved copy.

- Lesson 0006 checkpoint passed: user distinguished stronger guidance from guaranteed quality and preferred CFG 10 over 3 for watercolor style (LR-0010). Keep CFG 10 as the current workflow preference, not a universal default. Seed, prompt, and CFG comparisons are complete by user report; next suitable topic is image-to-image with VAE Encode and denoise, using the preferred saved fox image. That lesson has not yet been delivered.

- User identified changing the seed as the extra factor when asked why changing seed and prompt together complicates attribution; full causal explanation was supplied by the teacher, so independent mastery is not established. Lesson 0006 introduces CFG via a fixed-seed comparison at 3 and 10. Await prediction and observations; do not record CFG mastery from lesson delivery.

- Fixed-seed red-to-white fox prompt comparison completed by user report (LR-0009): color changed; pose and position stayed close. User rejected guaranteed color-only change; causal explanation remains to be checked. Next ask why changing both seed and prompt would make attribution harder. Do not imply fixed seed guarantees composition or that this pair demonstrates character consistency.

- Lesson 0005 comparison reported: sitting red fox stayed similar; fox position and shape changed (LR-0008). Next predict changing only positive prompt “red fox” to “white fox” while retaining seed 43 and all other settings. Elicit whether pose/position must stay identical before running; prompt-change behavior and character-identity control remain untested.

- Seed-change prediction passed (LR-0007): user explained that changing noise while retaining prompt guidance should produce a different image broadly following the same prompt. Lesson 0005 tests this with seeds 42 and 43; await observations before claiming experimental understanding or advancing to character-consistency conclusions.

- First generation succeeded by user report: image appeared and matched fox/tree/watercolor prompt. User correctly recalled VAE Decode (LR-0006); lesson 0004 checkpoint passed. Next elicit a prediction about changing only seed 42 to 43 before running a controlled comparison. Exact baseline settings and generated image have not been independently inspected; seed effects and character consistency are not yet demonstrated.

- User reports successful ComfyUI GPU startup. Lesson 0004 provides first-generation baseline; await actual image or error before recording successful inference. GPU startup alone does not establish checkpoint loading or sampling success.

- User reports both GPUs are now idle. Proceed with GPU 0 launch by replacing --cpu with --cuda-device 0 in the working server command, preserving loopback binding and SSH forwarding. Await CUDA startup confirmation before first generation; no GPU execution has yet been demonstrated.

- Lesson 0003 checkpoint answered correctly: destination port determines positive role; Empty Latent Image does not create seed-dependent noise. User reports wiring complete (LR-0005). Next request current nvidia-smi output before choosing a GPU and restarting from CPU mode; actual model loading and first generation remain unverified.

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
