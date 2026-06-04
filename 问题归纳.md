1、prompt和context engineering：
前者可以提到cot思维链以及fewshot样本示范，激发模型的已有的知识；
后者能提到rag检索增强生成，窗口压缩和记忆问题，通过标准的外部信息注入窗口

a、promt稳定性问题
可以用自动化优化DSPy，将prompt视为可编译的参数，代码自动搜索。
还有幻觉的问题，cot+self-consistency强制逐步思考，进行多次推理迭代
b、context的质量问题
可以采取re-ranking重排序的策略，将优质的信息检索，放置到promt的开头或结尾；
self-refine自我反思进行清洗，让模型先判断检索内容是否有效，剔除之后进行回答

2、

