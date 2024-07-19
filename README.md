# nlp
## Framework
## Text2sql
- [MAC-SQL: A Multi-Agent Collaborative Framework for Text-to-SQL](nlp/text2sql/MAC-SQL.pdf)
多阶段使用大模型去做text2sql，Selector来选择database schema，Decomposer来进行Question的拆分和生成，Refiner对SQL进行校验并重生成。
![alt text](/images/text2sql/mac.png)
- [Text-to-SQL Empowered by Large Language Models: A Benchmark Evaluation](nlp/text2sql/MAC-SQL.pdf)
DAIL这篇论文的特点在于设计了一种另类的embedding，对question进行masked（question中出现的表名用【mask】表示）之后再去挑选Golden examples，然后再通过Jaccord Similarity来进行重排，下面这个是伪代码，具体细节可以看论文。
![alt text](/images/text2sql/dail.png)

- [MCS-SQL: Leveraging Multiple Prompts and Multiple-Choice Selection For Text-to-SQL Generation](nlp/text2sql/MCS-SQL.pdf)
特点是采用并行生成多条结果的方式，本质上还是Schema Linking来选择Tables和columns，通过embedding的方式来选择Golden Examples作为之后SQL生成的ICL（in-context learning）。生成N条SQL之后，通过一种过滤方式（分组+置信度+效率排序）选出M条SQL，最后让大模型去哪条是正确的SQL。
![alt text](/images/text2sql/mcs.png)

## LLM Finetuning
