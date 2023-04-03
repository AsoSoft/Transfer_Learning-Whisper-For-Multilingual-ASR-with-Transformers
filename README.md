## Transfer_Learning-Whisper-For-Multilingual-ASR-with-Transformers
ئەم لەلایان تیمی ئاسۆسفت ئامادە کراوە, بۆ یەکەمین جار کۆستەمایزکردنی زمانی نوێ لە Whisper کە پێشتر نەکرابوو.
ئێمە توانیمان کۆستەمایزی بکەین بۆ زمانی کوردی بەم چەند گۆرانکاریەی خوارەوە:
١-لەشوێن بەکارهێنانی تۆکەنایزەری Pretrain, زیاد کردنی تۆکەنایزەری نوێ.
tokenizer = WhisperTokenizer(vocab_file='/content/ckb/vocab.json',
                            merges_file='/content/merges.txt',
                             unk_token='',
                             bos_token= '<|endoftext|>',
                             pad_token= '<|endoftext|>',
                             model_max_length = 1024,
                            task='transcribe')
٢-لابردنی لایەری کۆتای Decoder لە مۆدێڵێ Pretrain و دوبارە دروست کردنەوەی لە scratch بۆ زمانی نوێ.
model.config.decoder_layerdrop=1
