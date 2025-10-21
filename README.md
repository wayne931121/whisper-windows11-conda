# Run Whisper in Windows11

# My ENV
https://github.com/wayne931121/whisper-windows11-conda/blob/main/env.yml

(the important thing is python=3.13.0 and so on...)

# My Device Info
- Windows 11
- Miniforge Conda
- CUDA 12.1 & 13.0 & 11.0

# Usage
## CLI
```sh
(C:\Users\TEST\sdp) C:\Users\TEST\sdp\content\real-time-voice-translator>python -m whisper
usage: __main__.py [-h] [--model MODEL] [--model_dir MODEL_DIR] [--device DEVICE] [--output_dir OUTPUT_DIR]
                   [--output_format {txt,vtt,srt,tsv,json,all}] [--verbose VERBOSE] [--task {transcribe,translate}]
                   [--language {af,am,ar,as,az,ba,be,bg,bn,bo,br,bs,ca,cs,cy,da,de,el,en,es,et,eu,fa,fi,fo,fr,gl,gu,ha,haw,he,hi,hr,ht,hu,hy,id,is,it,ja,jw,ka,kk,km,kn,ko,la,lb,ln,lo,lt,lv,mg,mi,mk,ml,mn,mr,ms,mt,my,ne,nl,nn,no,oc,pa,pl,ps,pt,ro,ru,sa,sd,si,sk,sl,sn,so,sq,sr,su,sv,sw,ta,te,tg,th,tk,tl,tr,tt,uk,ur,uz,vi,yi,yo,yue,zh,Afrikaans,Albanian,Amharic,Arabic,Armenian,Assamese,Azerbaijani,Bashkir,Basque,Belarusian,Bengali,Bosnian,Breton,Bulgarian,Burmese,Cantonese,Castilian,Catalan,Chinese,Croatian,Czech,Danish,Dutch,English,Estonian,Faroese,Finnish,Flemish,French,Galician,Georgian,German,Greek,Gujarati,Haitian,Haitian Creole,Hausa,Hawaiian,Hebrew,Hindi,Hungarian,Icelandic,Indonesian,Italian,Japanese,Javanese,Kannada,Kazakh,Khmer,Korean,Lao,Latin,Latvian,Letzeburgesch,Lingala,Lithuanian,Luxembourgish,Macedonian,Malagasy,Malay,Malayalam,Maltese,Mandarin,Maori,Marathi,Moldavian,Moldovan,Mongolian,Myanmar,Nepali,Norwegian,Nynorsk,Occitan,Panjabi,Pashto,Persian,Polish,Portuguese,Punjabi,Pushto,Romanian,Russian,Sanskrit,Serbian,Shona,Sindhi,Sinhala,Sinhalese,Slovak,Slovenian,Somali,Spanish,Sundanese,Swahili,Swedish,Tagalog,Tajik,Tamil,Tatar,Telugu,Thai,Tibetan,Turkish,Turkmen,Ukrainian,Urdu,Uzbek,Valencian,Vietnamese,Welsh,Yiddish,Yoruba}]
                   [--temperature TEMPERATURE] [--best_of BEST_OF] [--beam_size BEAM_SIZE] [--patience PATIENCE]
                   [--length_penalty LENGTH_PENALTY] [--suppress_tokens SUPPRESS_TOKENS]
                   [--initial_prompt INITIAL_PROMPT] [--carry_initial_prompt CARRY_INITIAL_PROMPT]
                   [--condition_on_previous_text CONDITION_ON_PREVIOUS_TEXT] [--fp16 FP16]
                   [--temperature_increment_on_fallback TEMPERATURE_INCREMENT_ON_FALLBACK]
                   [--compression_ratio_threshold COMPRESSION_RATIO_THRESHOLD] [--logprob_threshold LOGPROB_THRESHOLD]
                   [--no_speech_threshold NO_SPEECH_THRESHOLD] [--word_timestamps WORD_TIMESTAMPS]
                   [--prepend_punctuations PREPEND_PUNCTUATIONS] [--append_punctuations APPEND_PUNCTUATIONS]
                   [--highlight_words HIGHLIGHT_WORDS] [--max_line_width MAX_LINE_WIDTH]
                   [--max_line_count MAX_LINE_COUNT] [--max_words_per_line MAX_WORDS_PER_LINE] [--threads THREADS]
                   [--clip_timestamps CLIP_TIMESTAMPS]
                   [--hallucination_silence_threshold HALLUCINATION_SILENCE_THRESHOLD]
                   audio [audio ...]
__main__.py: error: the following arguments are required: audio

(C:\Users\TEST\sdp) C:\Users\TEST\sdp\content\real-time-voice-translator>
```
## Python
### You know language
```py
import whisper
model = whisper.load_model(r"C:\Users\TEST\sdp\content\real-time-voice-translator\large-v3-turbo.pt")
result = model.transcribe(wname,no_speech_threshold=0.6,language="en")
```
### Auto Detect
```py
import whisper
model = whisper.load_model(r"C:\Users\TEST\sdp\content\real-time-voice-translator\large-v3-turbo.pt")
result = model.transcribe(wname,no_speech_threshold=0.6)
```
### See more transcribe options
https://github.com/wayne931121/whisper-windows11-conda/blob/main/whisper/transcribe.py

# Download Model
https://github.com/wayne931121/whisper-windows11-conda/blob/main/whisper/__init__.py#L17C1-L32C2

<pre>
_MODELS = {
    "tiny.en": "https://openaipublic.azureedge.net/main/whisper/models/d3dd57d32accea0b295c96e26691aa14d8822fac7d9d27d5dc00b4ca2826dd03/tiny.en.pt",
    "tiny": "https://openaipublic.azureedge.net/main/whisper/models/65147644a518d12f04e32d6f3b26facc3f8dd46e5390956a9424a650c0ce22b9/tiny.pt",
    "base.en": "https://openaipublic.azureedge.net/main/whisper/models/25a8566e1d0c1e2231d1c762132cd20e0f96a85d16145c3a00adf5d1ac670ead/base.en.pt",
    "base": "https://openaipublic.azureedge.net/main/whisper/models/ed3a0b6b1c0edf879ad9b11b1af5a0e6ab5db9205f891f668f8b0e6c6326e34e/base.pt",
    "small.en": "https://openaipublic.azureedge.net/main/whisper/models/f953ad0fd29cacd07d5a9eda5624af0f6bcf2258be67c92b79389873d91e0872/small.en.pt",
    "small": "https://openaipublic.azureedge.net/main/whisper/models/9ecf779972d90ba49c06d968637d720dd632c55bbf19d441fb42bf17a411e794/small.pt",
    "medium.en": "https://openaipublic.azureedge.net/main/whisper/models/d7440d1dc186f76616474e0ff0b3b6b879abc9d1a4926b7adfa41db2d497ab4f/medium.en.pt",
    "medium": "https://openaipublic.azureedge.net/main/whisper/models/345ae4da62f9b3d59415adc60127b97c714f32e89e936602e85993674d08dcb1/medium.pt",
    "large-v1": "https://openaipublic.azureedge.net/main/whisper/models/e4b87e7e0bf463eb8e6956e646f1e277e901512310def2c24bf0e11bd3c28e9a/large-v1.pt",
    "large-v2": "https://openaipublic.azureedge.net/main/whisper/models/81f7c96c852ee8fc832187b0132e569d6c3065a3252ed18e56effd0b6a73e524/large-v2.pt",
    "large-v3": "https://openaipublic.azureedge.net/main/whisper/models/e5b1a55b89c1367dacf97e3e19bfd829a01529dbfdeefa8caeb59b3f1b81dadb/large-v3.pt",
    "large": "https://openaipublic.azureedge.net/main/whisper/models/e5b1a55b89c1367dacf97e3e19bfd829a01529dbfdeefa8caeb59b3f1b81dadb/large-v3.pt",
    "large-v3-turbo": "https://openaipublic.azureedge.net/main/whisper/models/aff26ae408abcba5fbf8813c21e62b0941638c5f6eebfb145be0c9839262a19a/large-v3-turbo.pt",
    "turbo": "https://openaipublic.azureedge.net/main/whisper/models/aff26ae408abcba5fbf8813c21e62b0941638c5f6eebfb145be0c9839262a19a/large-v3-turbo.pt",
}
</pre>
