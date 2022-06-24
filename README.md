# competition_heritage_culture

### 遗址文化领域知识抽取与问答挑战赛 PL-Marker baseline
赛题地址：https://challenge.xfyun.cn/topic/info?type=heritage-culture&option=stsj

#### 运行步骤
**1** 通过`run_mydataset_ner.py`下面的脚本得到ner的预测

**2** 运行 `process.ipynb`里的代码处理ner预测结果
``` processed_f = open('../datasets/my_dataset_processed/ner_pred_result.json', 'w', encoding='utf8')
with open('./bert_models/PL-Marker-roberta-zh-10/ent_pred_test.json','r', encoding = 'utf8') as f:
    for line in f:
        processed_f.write(json.dumps(json.loads(line), ensure_ascii=False)+'\n')

processed_f.close()
```

**3** 运行`run_mydataset_re.py`下面的脚本得到关系预测的结果

**4** 通过`process.ipynb`中的代码进行后续处理，和结果统计
