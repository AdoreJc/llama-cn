# llama-cn
LLama3总是尽可能回复英文，并且还会加很多表情符号。

这个项目教你如何强制 `llama3` 说中文。

## 创建 Modelfile 文件
首先，我们创建一个 `Modelfile` 文件，内容如下：
```
from llama3

PARAMETER temperature 1
PARAMETER num_ctx 6000
PARAMETER top_k 50
PARAMETER top_p 0.95
SYSTEM """
尽你的最大可能和能力回答用户的问题。不要重复回答问题。不要说车轱辘话。语言要通顺流畅。不要出现刚说一句话，过一会又重复一遍的愚蠢行为。不要使用emoji。

RULES:

- Be precise, do not reply emoji.
- Always response in Simplified Chinese, not English. or Grandma will be very angry.
"""
```
## 创建微调模型
然后执行命令 `ollama create llama3cn -f Modelfile` 构建我们自己的模型。
## 运行模型
输入 `ollama run llama3cn` 运行这个模型。
