# LLM Project

## Project Task
The goal of this project is to fine-tune a pre-trained language model to summarize lengthy news articles into concise summaries. The project focuses on delivering high-quality summaries for a multitude of topics.
Link to trained model: https://huggingface.co/natanea/llm-summarization-project
## Dataset
I used the Multi-News dataset, which contains multi-document news summaries. Each sample includes a collection of related articles and a corresponding human-written summary. The dataset was preprocessed to truncate inputs and ensure compatibility with the token length limitations of our chosen model.

## Pre-trained Model
We fine-tuned the BART-large CNN model from Hugging Face. BART is a transformer-based encoder-decoder architecture designed for text generation tasks, making it well-suited for abstractive summarization.

## Performance Metrics
The model's performance was evaluated using:
- Validation Loss: Monitored during training to assess generalization.
- Human Evalutation: Ensured that generated summaries are factual and understandable.

Key Results:
- Training Loss: 1.824000
- Validation Loss: 1.747170
## Hyperparameters
- Learning Rate: Set to 2e-5 for fine-tuning stability.
- Batch Size: Used a small batch size of 4 per device with gradient accumulation for hardware efficiency.
- Epochs: Training completed in 1 epoch for computational cost and time constraints.
- Max Token Length: Limited input to 1024 tokens and output to 128 tokens for compatibility with hardware constraints and model design.

## Future Changes
1. **Increase Training Resources**  
   Limited access to computational resources on Colab restricted the ability to train and test the model effectively. Future work would involve:  
   - Using more powerful hardware to handle larger datasets and longer training periods.

2. **Train for More Epochs**  
   The current training was limited to 1 epoch due to computational constraints. Increasing the number of epochs while monitoring for overfitting would likely improve the model’s performance.

3. **Implement Early Stopping**  
   Adding a stop-loss hyperparameter would enable the training process to halt automatically when validation loss plateaus, optimizing both time and resources.

4. **Enhance Generalization**  
   The model struggles to generalize well on unseen data. This could be addressed by:  
   - **Augmenting the dataset** with more diverse and balanced samples.  
   - **Data Filtering** to remove noisy or irrelevant training samples.  
   - Applying **regularization techniques**, such as dropout or weight decay, during training.

