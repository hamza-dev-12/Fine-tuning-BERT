# Fine Tuning BERT

BERT (Bidirectional Encoder Representations from Transformers) is one of the most important large language models in Natural Language Processing, widely used for various sequence-to-sequence tasks. In this project, we fine-tune BERT for text classification on the Twitter Tweets Sentiment dataset from Kaggle.

## About Dataset

The dataset contains various columns, but for this project, we focused on the text (containing sentences) and the sentiment (consisting of three sentiments: positive, negative, and neutral). The model is trained to detect the sentiment of a given input sentence.

## Model Fine-Tuning Process

The model is fine-tuned using the Adam Optimizer with a very low learning rate. Due to the large number of parameters, training on limited GPUs is challenging. To address this, we employed LoRA (Low Rank Adaptation), a widely recognized technique in Parameter Efficient Fine Tuning (PEFT). This method adds adapters to the pretrained models while freezing the rest of the parameters, significantly reducing the number of trainable parameters. To further accelerate the training process, floating-point-16 mixed precision was used. This approach updates weights using 16-bit precision instead of 32-bit, thereby reducing memory consumption and speeding up training. However, this comes with some trade-offs in terms of potential loss of information.

## Results

After fine-tuning for several epochs, the accuracy on the test dataset was about 90%. This high accuracy was achieved by fine-tuning the model with very few trainable parameters.

