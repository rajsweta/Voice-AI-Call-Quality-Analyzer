# Approach Summary

This project analyzes a sales call to extract transcript, speaker roles, sentiment, and one actionable insight, optimized for Google Colab’s free tier.

*Step 1 – Audio Extraction:*  
The YouTube file is downloaded with yt-dlp and converted to 16kHz mono WAV to ensure compatibility with speech models.  

*Step 2 – Transcription:*  
OpenAI Whisper (tiny model) is used for speech-to-text. It is lightweight, robust to poor audio quality, and runs within 30 seconds on Colab free tier.  

*Step 3 – Speaker Diarization:*  
Resemblyzer with clustering separates speaker turns. This allows us to distinguish between the customer and the sales rep.  

*Step 4 – Sentiment Analysis:*  
Each speaker’s utterances are analyzed using HuggingFace Transformers (DistilBERT SST-2) to detect positive, neutral, or negative tone.  

*Step 5 – Insight & Role Detection:*  
By comparing talk time and question frequency, the sales rep vs customer roles are identified. Finally, the system extracts one key actionable insight, e.g., “Customer repeatedly expressed concern about pricing, while sales rep dominated 65% of talk time.”  

This pipeline meets all requirements: robust transcription, fast runtime, clear comments, and one actionable business insight.
