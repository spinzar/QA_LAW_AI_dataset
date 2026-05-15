language:
- ar
- ps
license: apache-2.0
task_categories:
- question-answering
tags:
- egyptian-arabic
- legal
- qa
- law
- arabic-nlp
- pashto-translation
size_categories:
- 1K<n<10K
pretty_name: "د مصري عامیانه عربي حقوقي پوښتنو او ځوابونو ډېټاسیټ"
dataset_info:
  features:
  - name: question
    dtype: string
  - name: answer
    dtype: string
  - name: source_topics
    dtype: string
  splits:
  - name: train
    num_bytes: 2186295
    num_examples: 3725
  download_size: 871442
  dataset_size: 2186295
configs:
- config_name: default
  data_files:
  - split: train
    path: data/train-*
---

# د مصري عامیانه عربي حقوقي پوښتنو او ځوابونو ډېټاسیټ (پښتو ژباړه)

## د ډېټاسیټ تشریح

دا ډېټاسیټ د **۳،۷۲۵** پوښتنو او ځوابونو جوړه لري چې په **مصري عامیانه عربي (Egyptian Arabic)** ژبه چمتو شوي او پر **حقوقي موضوعاتو** تمرکز کوي. دا ډېټاسیټ د عربي ژبې د پروسس (NLP) ماډلونو د پراختیا لپاره یوه ارزښتناکه سرچینه ده، په ځانګړي ډول د هغو غوښتنلیکونو لپاره چې د مصر په محلي کلتور او قانوني سیسټم پورې اړه لري.

### کلیدي ځانګړتیاوې

- **ژبه**: مصري عامیانه عربي (العامية المصرية)
- **برخه (Domain)**: قانون/حقوق (القانون)
- **کچه**: ۳،۷۲۵ نمونې
- **موضوعات**: ۷۴۵ بې ساري حقوقي کټګورۍ
- **فارمت**: د پوښتنې او ځواب جوړې (Q&A) له موضوعي کټګورۍ سره

## د ډېټاسیټ جوړښت

### د ډېټا کالمونه

- **`question`**: حقوقي پوښتنې چې په مصري عامیانه عربي ډیالیکټ لیکل شوي دي.
- **`answer`**: اړوند جامع ځوابونه چې په مصري عامیانه ژبه ورکړل شوي دي.
- **`source_topics`**: حقوقي کټګورۍ چې محتوا طبقه بندي کوي.

### نمونه (Example)

```json
{
  "question": "څوک کولی شي د دې درغلۍ راپور ورکړي یا د ماشوم (قاصر) د ساتنې لپاره قانوني ګامونه پورته کړي؟",
  "answer": "هر هغه څوک چې د ماشوم په ساتنه کې ګټه ولري، لکه د لومړۍ درجې خپلوان (لکه مور که چیرې پلار وصي وي، یا کاکا او ماما)، یا خپله څارنوالي کولی شي مداخله وکړي که چیرې ورته راپور ورسیږي. همدارنګه، هغه شورا (المجلس الحسبي) چې د ماشومانو پر اموالو څارنه کوي هم مداخله کولی شي. دوی کولی شي محکمې ته دعوه وړاندې کړي ترڅو وصي لیرې کړي او د ماشوم حقونه بیرته ترلاسه کړي.",
  "source_topics": "د وصي یا ولي لخوا پر ماشوم درغلي"
}

```

### د ډېټاسیټ بارول (Loading)

```python
from datasets import load_dataset

# د ډېټاسیټ لوډ کول
dataset = load_dataset("Omar-youssef/QA_LAW_Egyptian_dataset")

# د ټریننګ برخې ته لاسرسی
train_data = dataset['train']

# د ډېټا د لاسرسي نمونه
for example in train_data.select(range(3)):
    print(f"پوښتنه: {example['question']}")
    print(f"ځواب: {example['answer']}")
    print(f"موضوع: {example['source_topics']}")
    print("-" * 50)

```

## احصایوي معلومات

* **ټولې نمونې**: ۳،۷۲۵
* **بې ساري حقوقي موضوعات**: ۷۳۸
* **د پوښتنې اوسط اوږدوالی**: تغیر کوي (طبیعي محاوره يي عربي)
* **د ځواب اوسط اوږدوالی**: په مصري عامیانه ژبه کې جامع تشریحات
* **د فایل اندازه**: نږدې ۲.۲ ام بي (خلاص شوی)

## د ډېټا کیفیت

دا ډېټاسیټ لاندې ځانګړتیاوې لري:

* د طبیعي مصري عامیانه عربي کارول.
* جامع حقوقي تشریحات.
* د متنوع حقوقي موضوعاتو تر پوښښ لاندې نیول.
* حقیقي حقوقي سناریوګانې او پوښتنې.

## ماخذ (Citation)

که تاسو دا ډېټاسیټ په خپله څېړنه کې کاروئ، هیله ده دا لاندې حواله وکاروئ:

```bibtex
@dataset{omar_youssef_egyptian_legal_qa,
  author = {Omar Youssef},
  title = {Egyptian Arabic Legal QA Dataset},
  year = {2025},
  publisher = {Hugging Face},
  url = {[https://huggingface.co/datasets/Omar-youssef/QA_LAW_Egyptain_dataset](https://huggingface.co/datasets/Omar-youssef/QA_LAW_Egyptain_dataset)}
}

```

## جواز (License)

دا ډېټاسیټ د **Apache 2.0** جواز تر چتر لاندې خپور شوی دی.

```

---