# ComfyUI Glossary

Terms demonstrated in the lesson 0001 checkpoint. Scope: the standard Stable Diffusion workflow studied so far.

## Terms

**CLIP**:
The loaded text-encoder model supplied to CLIP Text Encode, distinct from the encoded prompt data it produces.

**CLIP Text Encode**:
The operation that takes a CLIP model and prompt text and produces CONDITIONING for the sampler.

**LATENT**:
Latent-space data, such as KSampler's sampled output, which requires decoding to become pixel image data.

**IMAGE**:
Pixel image data accepted by Save Image, distinct from LATENT data.

**VAE input**:
The loaded VAE model, including learned weights and decoding functionality, supplied to VAE Decode separately from the latent samples.

**Data dependency**:
A relationship established by connected inputs and outputs; changing a node's canvas position alone does not change it.
