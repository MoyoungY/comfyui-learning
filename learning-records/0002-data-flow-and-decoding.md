# Typed data flow and decoding understood

The user correctly explained that KSampler produces latent data requiring decoding before image saving, distinguished the sampled latent input from the loaded VAE model and its learned weights, and explained that moving a node without changing wires leaves data dependencies unchanged. This establishes immediate understanding of the output-stage graph and supports introducing the upstream inputs of a minimal text-to-image workflow; hands-on execution and longer-term retention have not yet been demonstrated.
