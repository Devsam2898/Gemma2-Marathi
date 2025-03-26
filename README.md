# Gemma2 9B Fine-Tuned for English-Marathi Translation

## Overview
This project fine-tunes Unsloth's Gemma2 7B model for high-quality English-to-Marathi translations. Leveraging Gemma2's robust architecture, the model was trained on a custom dataset to handle diverse linguistic challenges, including long-context paragraphs, idiomatic expressions, and noisy inputs.

## Model Features
- **Base Model:** Gemma2 9B
- **Architecture:** 42 transformer layers, optimized for multilingual tasks.
- **Precision:** 4-bit quantization (BitsAndBytes) for efficient fine-tuning and inference.
- **Token Support:** Up to 8,192 tokens with a vocabulary of 256,000 tokens.
- **Key Enhancements:** Rotary embeddings for improved attention and context retention.

## Dataset Description
The model was fine-tuned on a custom dataset available on Hugging Face:

- **Dataset:** [English-Marathi Complex Sentences](https://huggingface.co/datasets/Devavrat28/English-Marathi_Complex_Sentences)
- **Size:** ~X English-Marathi sentence pairs.
- **Domains:**
  - Historical narratives
  - Conversational phrases
  - Literary excerpts and idiomatic expressions
- **Challenges Addressed:**
  - Long-context paragraphs
  - Code-mixed sentences (English + Marathi)
  - Noisy inputs with typos or informal language

## Fine-Tuning Process
- **Framework:** TRL (Transformers Reinforcement Learning) library
- **Trainer:** SFTTrainer for supervised fine-tuning
- **Key Hyperparameters:**
  - Learning Rate: 2e-6
  - Gradient Accumulation Steps: 4
  - Warmup Steps: 5
  - Epochs: 3
  - Scheduler: Cosine decay
  - Optimization: AdamW (8-bit) for memory efficiency
- **Hardware:** Kaggle environment with multi-GPU support

## Evaluation Metrics
The model was evaluated using industry-standard metrics for machine translation:

- **BLEU Score:** 0.66
- **CHRF Score:** 0.3059

## Inference Examples
### Direct Translation:
- **Input:** "The golden age of the Peshwas brought prosperity to Maharashtra."
- **Output:** "पेशव्यांच्या सुवर्णकाळाने महाराष्ट्रात भरभराट घडवली."

### Long Context Translation:
Handles paragraphs with up to 8,192 tokens while retaining context.

### Noisy Input:
- **Input:** "The rapid advancement of artificial intelligence has the potential to revolutionize industries, from healthcare to finance, but it also raises ethical concerns regarding job displacement and algorithmic bias."
- **Output:** "कृत्रिम बुद्धिमत्तेच्या वेगाने प्रगतीने औद्योगिक क्षेत्रांमध्ये क्रांती घडवण्याची क्षमता आहे, आरोग्यसेवांपासून ते वित्तपर्यंत, परंतु त्यात नोकरीच्या जागांच्या विस्थापित होण्याबद्दल आणि अल्गोरिथमच्या पूर्वाग्रहाबद्दलही नैतिक चिंता आहे."

## Applications
- **Historical Text Translation:** Translating historical records for research.
- **Conversational AI:** Enhancing multilingual chatbots.
- **Localization:** Adapting English content for Marathi-speaking audiences.

## Future Work
- Expand training data with more domain-specific sentences.
- Fine-tune further for Marathi-English reverse translation.
- Explore integration with other Marathi NLP tools.

## Acknowledgments
Special thanks to Unsloth for providing the Gemma2 model and the Kaggle community for computational resources.

