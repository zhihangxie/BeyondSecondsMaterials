# Existing Models

| Model | Year | Task | Languages | Speech Encoder | Speech Frame Rate | Modality Adapter | Modality Fusion | Output Frame Rate | LLM Decoder | SpeechLLM Size | Training Duration | Testing Duration |
|---|---:|---|---|---|---|---|---|---|---|---:|---|---|
| SpeechLLM-XL [102] | 2025 | ASR | EN | Enformer | 25 Hz | MLP | Prepending | 25 Hz | Llama2 | 0.2B | 30s | 5m |
| Audio Flamingo2 [15] | 2025 | ASR, QA/SQA, TTS | EN | CLAP | 100 Hz | MLP | Cross-Attention | 100 Hz | Qwen2.5-3B | 3B | 5m | 5m |
| Audio Flamingo3 [16] | 2025 | ASR, QA/SQA, TTS, Vision, Others | EN | WhisperV3 | 50 Hz | Pooling | Cross-Attention | 25 Hz | Qwen2.5-7B | 7.8B | 10m | 10m |
| VLAT-SALMONN [72] | 2025 | QA/SQA | EN | WhisperV2 | 50 Hz | WQ-Former | Prepending | 3 Hz | Vicuna-7B | 8.5B | 2m | 10m |
| VLAT-Qwen2-Audio [72] | 2025 | QA/SQA | EN | WhisperV3 | 50 Hz | Pooling | Prepending | 25 Hz | Qwen-7B | 7.8B | 2m | 10m |
| Qwen2.5-Omni [74] | 2025 | ASR, MT/ST, TTS, Vision | 8+ | WhisperV3 | 50 Hz | Pooling | Prepending | 25 Hz | Qwen2.5-7B | 7.8B | 20m | 20m |
| KIT [103] | 2025 | ASR, MT/ST, TTS, QA/SQA | 4 | SeamlessM4T | 50 Hz | Q-Former | Prepending | 50 Hz | Llama3.1-8B | 9B | 23m | 27m |
| FastLongSpeech [33] | 2025 | ASR, QA/SQA | 8+ | WhisperV3 | 50 Hz | Iterative | Prepending | Dynamic | Qwen-7B | 8B | 15m | 40m |
| Qwen3-Omni [50] | 2025 | ASR, MT/ST, TTS, Vision | 19 | Transformer | 12.5 Hz | MLP | Prepending | 12.5 Hz | Qwen3-30B | 30B | 40m | 40m |
| Voxtral [17] | 2025 | ASR, MT/ST, TTS | 13 | WhisperV3 | 50 Hz | MLP | Prepending | 12.5 Hz | Mistral 3B/24B | 4.7B/24.3B | 40m | 40m |
| MGM-Omni [75] | 2025 | ASR, TTS, Vision | 2 | Dual WhisperV3 | 50 Hz | MLP | Prepending | 50 Hz | Qwen2.5-7B | 8.5B | NA | 60m |
| Phi4-Multimodal [51] | 2025 | ASR, MT/ST, QA/SQA, TTS, Vision | 8 | Conformer | 12.5 Hz | MLP | Prepending | 12.5 Hz | Phi4-Mini-3B | 3.8B | 30m | 168m |
| FastSLM [73] | 2026 | ASR, MT/ST, TTS, QA/SQA | 2 | WhisperV3 | 50 Hz | HFQ-Former | Prepending | 1.67 Hz | Qwen3-4B | 4.7B | 15m | 480m |
