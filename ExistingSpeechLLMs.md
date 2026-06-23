# Existing Long-form SpeechLLMs

| Index | Model | Year | Task | Languages | Speech Encoder | Speech Frame Rate | Modality Adapter | Modality Fusion | Output Frame Rate | LLM Decoder | SpeechLLM Size | Training Duration | Testing Duration |
|-------|-------|:----:|:----:|:---------:|:--------------:|:-----------------:|:----------------:|:---------------:|:-----------------:|:-----------:|:--------------:|:-----------------:|:----------------:|
|  1 |     SpeechLLM-XL | 2025 | ASR                                               | EN |       Enformer |   25 Hz |        MLP |      Prepending |   25 Hz |         Llama2 |       0.2B | 30s |   5m |
|  2 | Audio Flamingo-2 | 2025 | ASR,        QA/SQA,                        others | EN |           CLAP |  100 Hz |        MLP | Cross-Attention |  100 Hz |     Qwen2.5-3B |         3B |  5m |   5m |
|  3 | Audio Flamingo-3 | 2025 | ASR,        QA/SQA,           TTS,         others | EN |      WhisperV3 |   50 Hz |    Pooling | Cross-Attention |   25 Hz |     Qwen2.5-7B |       7.8B | 10m |  10m |
|  4 |     VLAT-SALMONN | 2025 |             QA/SQA                                | EN |      WhisperV2 |   50 Hz |  WQ-Former |      Prepending |    3 Hz |      Vicuna-7B |       8.5B |  2m |  10m |
|  5 | VLAT-Qwen2-Audio | 2025 |             QA/SQA, SUM/SSUM, TTS, Vision, others | EN |      WhisperV3 |   50 Hz |    Pooling |      Prepending |   25 Hz |        Qwen-7B |       7.8B |  2m |  10m |
|  6 |          KIT+CMU | 2026 | ASR, MT/ST, QA/SQA, SUM/SSUM,              others |  4 |      WhisperV3 |   50 Hz |    Pooling |      Prepending |   50 Hz |     Qwen2.5-7B |       7.8B | 15m |  15m |
|  7 |              FBK | 2026 | ASR, MT/ST, QA/SQA, SUM/SSUM,              others |  4 |    SeamlessM4T |   50 Hz |        MLP |      Prepending |   50 Hz |       Qwen3-4B |       4.7B | 25m |  15m |
|  8 |     Qwen2.5-Omni | 2025 | ASR, MT/ST,                   TTS, Vision         | 8+ |      WhisperV3 |   50 Hz |    Pooling |      Prepending |   25 Hz |     Qwen2.5-7B |       7.8B | 20m |  20m |
|  9 |              KIT | 2025 | ASR, MT/ST, QA/SQA, SUM/SSUM                      |  4 |    SeamlessM4T |   50 Hz |  WQ-Former |      Prepending |   50 Hz |    Llama3.1-8B |         9B | 23m |  27m |
| 10 |   FastLongSpeech | 2025 | ASR,        QA/SQA                                | 8+ |      WhisperV3 |   50 Hz |  Iterative |      Prepending | Dynamic |        Qwen-7B |         8B | 15m |  40m |
| 11 |       Qwen3-Omni | 2025 | ASR, MT/ST,                   TTS, Vision         | 19 |    Transformer | 12.5 Hz |        MLP |      Prepending | 12.5 Hz |      Qwen3-30B |        30B | 40m |  40m |
| 12 |          Voxtral | 2025 | ASR, MT/ST,                   TTS                 | 13 |      WhisperV3 |   50 Hz |        MLP |      Prepending | 12.5 Hz | Mistral 3B/24B | 4.7B/24.3B | 40m |  40m |
| 13 |         MGM-Omni | 2025 | ASR,                          TTS, Vision         |  2 | Dual WhisperV3 |   50 Hz |        MLP |      Prepending |   50 Hz |     Qwen2.5-7B |       8.5B |  NA |  60m |
| 14 |  Phi4-Multimodal | 2025 | ASR, MT/ST, QA/SQA, SUM/SSUM,      Vision         |  8 |      Conformer | 12.5 Hz |        MLP |      Prepending | 12.5 Hz |   Phi4-Mini-3B |       3.8B | 30m | ~~168m~~ |
| 15 |          FastSLM | 2026 | ASR, MT/ST, QA/SQA, SUM/SSUM                      |  2 |      WhisperV3 |   50 Hz | HFQ-Former |      Prepending | 1.67 Hz |       Qwen3-4B |       4.7B | 15m | ~~480m~~ |


# Findings

- **Language and task coverage**

  Existing long-form SpeechLLMs remain largely English-centered, although recent systems extend to multilingual settings and broader tasks such as ST, SQA, SSUM, TTS, and multimodal reasoning.

- **Speech encoders**

  Many systems inherit Whisper-style encoders trained on fixed 30-second windows, while newer models train encoders with stronger temporal reduction or more efficient long-sequence attention.

- **Modality adapters**

  Adapter design determines how speech representations are compressed and fused into the LLM input space, mediating the trade-off between information retention and decoder-side computational cost.

- **LLM decoders**

  Decoder self-attention and KV-cache growth become major bottlenecks as input duration increases, and long-form performance depends on effective context use rather than supported context length alone.

- **Model compression**

  Memory and computation grow with both parameter count and sequence length, making compression, batching strategies, and hardware capacity important for long-form SpeechLLM training and deployment.

- **Training strategies**

  Most systems follow multi-stage pipelines involving representation alignment, supervised finetuning, PEFT methods such as LoRA, and long-form extension on longer recordings.

- **Evaluation protocols**

  Current evaluations emphasize maximum supported duration and task accuracy, but often lack standardized stress tests that analyze effective context use over progressively longer recordings.


# References

| Index | Short Title | Year | Author | Title |
|-------|-------------|-------|--------|------|
|  1 |     SpeechLLM-XL | 2025 |           Jia, Junteng and others  | Efficient Streaming LLM for Speech Recognition |
|  2 | Audio Flamingo-2 | 2025 |           Ghosh, Sreyan and others | Audio Flamingo 2: An Audio-Language Model with Long-Audio Understanding and Expert Reasoning Abilities |
|  3 | Audio Flamingo-3 | 2025 |           Goel, Arushi and others  | Audio Flamingo 3: Advancing Audio Intelligence with Fully Open Large Audio Language Models |
|  4 |     VLAT-SALMONN | 2025 |     Chaichana, Yuatyong and others | Extending Audio Context for Long-Form Understanding in Large Audio-Language Models |
|  5 | VLAT-Qwen2-Audio | 2025 |     Chaichana, Yuatyong and others | Extending Audio Context for Long-Form Understanding in Large Audio-Language Models |
|  6 |        KIT + CMU | 2026 |        Ugan, Enes Yavuz and others | Multilingual Long-form Speech Instruction Following: KIT's Submission to IWSLT 2026 |
|  7 |              FBK | 2026 |            Xie, Zhihang and others | FBK's Long-form SpeechLLMs to IWSLT 2026 Instruction Following |
|  8 |     Qwen2.5-Omni | 2025 |                 Xu, Jin and others | Qwen2.5-Omni Technical Report |
|  9 |              KIT | 2025 |             Koneru, Sai and others | KIT's Offline Speech Translation and Instruction Following Submission for IWSLT 2025 |
| 10 |   FastLongSpeech | 2025 |            Guo, Shoutao and others | FastLongSpeech: Enhancing Large Speech-Language Models for Efficient Long-Speech Processing |
| 11 |       Qwen3-Omni | 2025 |                 Xu, Jin and others | Qwen3-Omni Technical Report |
| 12 |          Voxtral | 2025 |          Liu, Alexander and others | Voxtral |
| 13 |         MGM-Omni | 2025 |          Wang, Chengyao and others | MGM-Omni: Scaling Omni LLMs to Personalized Long-Horizon Speech |
| 14 |  Phi4-Multimodal | 2025 | Abouelenin, Abdelrahman and others | Phi-4-Mini Technical Report: Compact yet Powerful Multimodal Language Models via Mixture-of-LoRAs |
| 15 |          FastSLM | 2026 |            Lee, Junseok and others | FastSLM: Hierarchical Frame Q-Former for Effective Speech Modality Adaptation |
