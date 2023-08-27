# From Overfitting to Information Loss: The Dilemma of Block Size in Causal Language Models


Alternative Heading: Understanding the Trade-offs of Sequence Length in Fine-Tuning Pre-trained Language Models


GPU: A100

- At first, I experimented with different values of the learning rate, i.e. 7e-5, 2e-5, and 1e-5, and 1e-5 seemed to perform the best.
- Perplexity(7e-5) ~ 33
- Perplexity(2e-5) ~ 16
- Perplexity(1e-5) ~ 11.18

After figuring out that 1e-5 helped in yielding the best results, we'll experiment with different values of block_sizes


- 64 ---->14.9
- block_size = 256 ---> 11.65
- block_size = 512 --> CUDA OOM




Note: 
The token length distribution seems to vary significantly, with minimum lengths as low as 24 tokens and maximum lengths as high as 1140 tokens. The choice of block size ("sequence length" or "window size") can have a significant impact on the performance of model, as it determines how much context the model can consider for each prediction.

- Too Small: A block size that's too small may not provide enough context for the model to make meaningful predictions.

- Too Large: A block size that's too large may make the model harder to train because it may exceed hardware limitations (e.g., GPU memory), or it may overfit to the specific examples due to the long sequence.

Variable Length: If your framework allows for it, you might consider using variable-length sequences. This way, you're not limited by a fixed block size.
