# From Overfitting to Information Loss: The Dilemma of Block Size in Causal Language Models


Alternative Heading: Understanding the Trade-offs of Sequence Length in Fine-Tuning Pre-trained Language Models


GPU: A100

- At first, I experimented with different values of the learning rate, i.e. 7e-5, 2e-5, and 1e-5, and 1e-5 seemed to perform the best.
- Perplexity(7e-5) ~ 33
- Perplexity(2e-5) ~ 16
- Perplexity(1e-5) ~ 11.18

After figuring out that 1e-5 helped in yielding the best results, we'll experiment with different values of block_sizes

block_size = 256 ---> 11.65
block_size = 512 --> CUDA OOM
