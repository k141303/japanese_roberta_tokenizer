# japanese_roberta_tokenizer
Tokenizer for
- [liat-nakayama/japanese-roberta-base-20201221](https://huggingface.co/liat-nakayama/japanese-roberta-base-20201221) 
- [liat-nakayama/japanese-roberta-base-20220905](https://huggingface.co/liat-nakayama/japanese-roberta-base-20220905)

registered in hagging face hub. 

If you use japanese-roberta-base-**20201221**, need to change branch.

```
git checkout 20201221
```

## How to use

### Install python pakages

~~~bash
pip install -r japanese_roberta_tokenizer/requirements.txt
~~~

### Import and Tokenize

~~~python:hoge.py
from japanese_roberta_tokenizer import JapaneseRoBERTaTokenizer

tokenizer = JapaneseRoBERTaTokenizer()

tokens = tokenizer.tokenize("本日は晴天なり")
input_tokens = [tokenizer.cls_token] + tokens + [tokenizer.sep_token]
input_ids = tokenizer.convert_tokens_to_ids(input_tokens)

print(input_tokens) # => ['<s>', '本@@', '日', 'は', '晴@@', '天', 'なり', '</s>']
print(input_ids) # => [0, 329, 31, 8, 6467, 1481, 113, 2]
~~~
