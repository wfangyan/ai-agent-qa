1、prompt和context engineering：
前者可以提到cot思维链以及fewshot样本示范，角色扮演等，激发模型的已有的知识；
后者能提到rag检索增强生成，窗口压缩和记忆问题，通过标准的外部信息注入窗口。

a、promt稳定性和幻觉问题
可以用自动化优化DSPy，将prompt视为可编译的参数，代码自动搜索。
还有幻觉的问题，cot+self-consistency强制逐步思考，进行多次推理迭代。

b、context的质量问题，即中间迷失和噪声
可以采取re-ranking重排序的策略，将优质的信息检索，放置到promt的开头或结尾；
self-refine自我反思进行清洗，让模型先判断检索内容是否有效，剔除之后进行回答。

未来可以融合fusion，动态调整prompt以及自动管理context。

2、为何transformer架构在处理超长的上下文的时候会变慢？瓶颈在哪？怎么解决？
自注意力机制，每个token都要和序列中的其他所有的token进行交互，time&space = O(N^2)
总结就是计算会二次方爆炸、显存瓶颈导致数据搬运慢、外推性差超过了使用训练样本的一般长度，ppl飙升

全栈优化方案：
a、IO 感知注意力优化，flash attention在高速缓存中一次计算完
b、kv cache压缩技术，让多个query头共享同一组key和value
c、显存碎片管理，借鉴操作系统的虚拟内存分页，将存储放在非连续的显存
d、位置编码延伸，通过数学插值欺骗模型，让文本还在训练过的长度

3、rag系统怎么进行query改写？











