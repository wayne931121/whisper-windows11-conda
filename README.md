# Run Whisper in Windows11

# My ENV
https://github.com/wayne931121/whisper-windows11-conda/blob/main/env.yml

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
