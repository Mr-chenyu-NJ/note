[TOC]



# LangChain相关地址

- **官网**：https://www.langchain.com/
- **GitHub 地址**：https://github.com/langchain-ai
- **中文文档地址**：https://docs.langchain.org.cn/oss/python/langchain/overview
- **英文文档地址**：https://docs.langchain.com/oss/python/langchain/overview
- **API 文档查询地址**：https://reference.langchain.com/python/langchain/



# 为什么需要LangChain

## 单一的大模型的局限性

- 知识受限于旧数据
- 无法和外部系统交互（API 数据库等）
- 不具备保持状态的能力



## LangChain的定位

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788670777.png)

## LangChain的应用场景

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788403913297-dc94d44c-cac8-456a-837d-cba2cc037b8e.png)

## LangChain主要模块（V1.2）

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788670778.png)

## LangChain家族

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788403995268-8bad8537-802a-4f0f-8f6a-897ef4dbee85.png)

## python虚拟环境配置

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788404039301-e954ba70-ad33-4ef2-8439-61dc07c71834.png)

## macbook配置conda

<font color="orange">环境初始化：</font>

```bash
## 下载conda
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh\nbash Miniconda3-latest-MacOSX-arm64.sh
conda env list
## 安装隔离环境
cnoda create --name langchain1.2 python=3.13.12
## 初始化环境 
conda init
conda env list
## 切换到对应的隔离环境
conda activate langchain1.2
## 验证环境
python --version
```

<font color="orange">安装相关依赖：</font>

✅ 优先conda install 然后pip install

```shell
conda install langchain=1.2.12
## 从特定渠道下载依赖 上面默认的下载会找不到
conda install -c conda-forge langchain==1.2.12
## 用pip装 conda要求严格 上面的会有版本错误
pip install langchain==1.2.12
```

<font color="orange">安装所有的依赖：</font>

 [requirements.txt](../file/requirements.txt) 

⚠️ 要切换到对应的环境

```shell
conda activate langchain1.2
pip install -r ./requirements.txt
```





# 大模型应用场景

## RAG（检索生成增强）

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788671189.png)



![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788671197.png)

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788671210.png)

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788671225.png)

## Agent开发

✅ 利用LLM的推理决策能力，通过规划、记忆和工具调用的能力，构造一个能独立思考，逐步完成给定目标的Agent（智能体）。

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788404890253-effef19e-f332-46d9-94f0-5256ea8d0fc6.png)



## 大模型应用开发的4个场景

纯Prompt

✅ 问一句答一句

![2f8960f4-cddd-4b16-9a7e-808e1bc2f694.png](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788671260.png)



Agent + Function Calling

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406804790-7bc1c7ba-5f41-43bc-a7f4-a7f4b9dc5c90.png)



RAG（检索生成增强）

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406826108-55d339e0-4c09-400b-878c-14de54a5914b.png)



Fine-tuning（精调\微调）

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406841933-1659de8b-39b6-49ca-a823-f760007cd452.png)



技术选型路线

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406875108-196d117a-5c39-4c70-a87f-434bada4ea70.png)





# 模型初始化

## 在线模型

**<font color="blue" size="5px">deepseek</font>**

1. 安装依赖（前面已经靠txt文件初始化了）
   ![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406956177-3d7c8c73-3a89-4644-9f76-a7d68c89a695.png)
2. 在pycharm里注意要选择对应的解释器 (在右下角可以选择对应的解释器 一定一定不要选错 选成默认的canda环境！！！)
3. 常用的参数设置
   ![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788406996330-7fe0d210-1f72-4ddb-b483-4bf689d6f376.png)

## 本地模型

✅ LangChain也支持使用ollama、vllm等框架启动的本地大模型。

## 模型调用

<font color="blue">invoke()</font>

✅ invoke方法非常灵活，支持三种形式的输入： 文本输入 、 字典列表 、 消息对象列表 （可以携带多轮对象，携带记忆）。 

✅ invoke的返回值

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788670784.png)

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788407081916-c8433e37-3c75-4073-9232-2e34772854c4.png)



<font color="blue">stream()</font>

✅ 相应速度快

✅ 交互更流畅



<font color="blue">batch()</font>

✅ 一次性接收所有的请求



<font color="blue">同步和异步调用</font>

## 模型初始化完整参数

**<font color="red">以deepseek为例：</font>**

入参：

```python
from langchain_deepseek import ChatDeepSeek
print(ChatDeepSeek.model_fields.keys())
```

出参：

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788407183995-b6d99d90-d685-4d6d-9f32-091b3135e87d.png)

> 🚀比较重要的:model_kwargs , extra_body
>

## 动态参数

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788407271093-fd4c1d46-45d6-438b-b94c-b839e69c903e.png)

| 配置项          | 类型                      | 描述                                                         |
| --------------- | ------------------------- | ------------------------------------------------------------ |
| run_name        | str                       | 为当前运行设置一个可读的名称。如在 LangSmith 追踪系统中快速定位和识别不同的运行任务。 |
| tags            | List[str]                 | 为运行设置标签，用于分类和过滤。如在 LangSmith 追踪系统中快速定位和识别不同的运行任务。 |
| callbacks       | List[BaseCallbackHandler] | 设置回调处理器，在运行的不同阶段（开始、流输出、结束等）触发。与一些监控平台（如 LangSmith）集成进行深度追踪和调试。 |
| metadata        | Dict[str, Any]            | 附加任意的键值对元数据。记录本次调用的业务上下文，如 {"user_id": "123", "session_id": "abc"} |
| max_concurrency | int                       | 限制当前可运行对象的最大并发运行数。防止对 API 接口或本地资源造成过大压力，实现简单的速率限制。 |
| recursion_limit | int                       | 限制运行时递归调用的最大深度。主要在复杂的工作流（如 Agent 执行多步工具调用）中，防止出现无限递归循环。 |
| configurable    | Dict[str, Any]            | 一个万能字典，用于传递其他可配置参数。实现更高级的动态行为，如配置可替代的模型或组件。 |



# LangSmith

✅ LangSmith是Langchain生态中专门用于LLM应用调试、监控、评估和管理的平台。





# 消息和提示词模板

✅ **Message（消息）是模型交互的最基本单元**

LangChain 在 1.0 中提供了跨模型统一的 Message 标准。无论你使用的是 OpenAI、Anthropic、Gemini 还是本地模型，这一标准都能保持一致的行为。好处：

- 兼容性强 ：不同模型的消息格式自动对齐。
- 可扩展性高 ：方便添加多模态内容或自定义字段。
- 可追踪性好 ：为 LangSmith 等调试工具提供一致的上下文数据结构。



## 认识消息

### 消息的内部结构

✅ LangChain的消息（Message）对象包含三种字段

- Role：消息所属的角色或类型，如 system、 user 、 assistant 。
- Content：消息内容
- Metadata：（可选）元数据，存储额外信息。如：消息ID、响应时间、token消耗量、消息标签

等



### 消息的类型

✅ LangChain定义了很多消息类型，通过 role 区分。常用的有四种。

```json
{"role": "system","content": "你是个精通编程的软件架构师"}
{"role": "user","content": "你好啊~"}
{"role": "assistant","content": "我也很高兴认识你"}
{"role": "tool","content": "今天天气很好","tool_call_id":"call_00_nUD2NC9QRN5Cg1GaoIkBJQ4s"}
```



### 消息格式

1. JSON格式
2. 对象格式 







# 工具调用

## 概述

✅ 在LangChain中，工具（Tools）实际上是指明确定义了输入和输出的 可调用函数 。因此， 工具调用(Tool Calling) 也被称为 函数调用(Function Calling)。

✅ 整体流程入下

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788670785.png)

✅ 细节流程如下

<font color="orange">步骤1</font>：模型绑定工具 ：通过model.bind_tools([...])绑定一个或者多个工具。

<font color="orange">步骤2</font>：模型生成工具调用请求 ：用户输入问题，调用模型（比如invoke()）。如果需要调用工具，模型返回包含工具调用信息（如工具名称和参数）的AIMessage。

<font color="orange">步骤3</font>：开发者手动执行工具 ：用户从响应中提取工具调用信息并手动调用对应的工具（比如工具.invoke()）。

<font color="orange">步骤4</font>：将工具执行结果ToolMessage传递给模型生成最终结果 ：将之前用户提问内容和手动执行工具结果ToolMessage返回模型，模型最终生成回复。



## 工具的定义

### 不使用@tool（不推荐）

```python
from langchain_core.utils.function_calling import convert_to_openai_tool
from rich import print as rprint
def get_weather(dt: str, city: str="北京"):
    """
    天气查询工具
    Args:
        dt: 日期
        city: 城市名称
    """
    return f"{city}天气晴朗"
rprint(convert_to_openai_tool(get_weather))
```



### 使用@tool（推荐）

```python
class weatherSchema(BaseModel):
    city: str = Field(default="北京", description="城市名称")
    if_forecast: bool = Field(default=False, description="是否包含明天天气预报")
    
@tool("get_weather_and_forecast", description="查询当天天气，可以包含明天天气", args_schema=weatherSchema)
def get_weather(city: str, if_forecast: bool):
    res = f"{city}今天天气不错"
    if if_forecast:
        res += "\n明天天气也不错"
    return res
```





# 结构化输出

## 概述

### 什么是结构化输出

✅ 要求模型最终返回一个符合预定义结构的数据对象，例如固定字段的JSON、Pydantic 模型、TypedDict，而不再是无格式的自然语言文本。它的核心目标是把“ 自然语言回答”变成“ 程序可以稳定消费的数据”



### 结构化输出

```python
# 一步到位
structured_llm = model.with_structured_output(Person)
person = structured_llm.invoke("张三是一名 30 岁的软件工程师")
# ✅ 自动解析、验证、创建对象
```



### 结构化输出模式

目前LangChain 1.x 支持多种Schema与结构化输出方式：

- Pydantic（字段校验、描述、嵌套结构，功能最丰富）
- TypedDict（轻量类型约束）
- JSON Schema（与前后端/跨语言接口最通用）
- dataclass

模型对象可以调用 with_structured_output() 绑定输出模式（schema）。



## 四种结构化输出

### Pydantic

✅ 它通过在运行时强制执行类型提示，确保数据的正确性和一致性，是 生产场景首选 。

✅  需要满足的几个要素：

- 所有结构化输出的数据模型都必须继承 BaseModel
- 使用 类型提示 。Pydantic 支持丰富的字段类型：str 、int、float、List[xxx]、Optional[xxx]等
- 使用 Field() 添加字段默认值和描述，帮助 LLM 理解字段含义



<font color="orange">基本使用</font>

```python
from pydantic import BaseModel, Field, SecretStr

class MovieModel(BaseModel):
    """
    电影的详细信息
    """
    title: str = Field(description="电影标题")
    year: int = Field(description="电影上映年份")
    director: str = Field(description="导演")
    rating: float = Field(description="电影评分，满分十分")
    
model_with_structure = model.with_structured_output(MovieModel)
response = model_with_structure.invoke("给出盗梦空间的信息")
print(response)
print(type(response))
```





<font color="orange">详细过程</font>

![image.png](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788673059.png)



### TypedDict

✅ TypedDict 是 Python 3.8+ 引入的一种类型提示工具，即带有类型声明的字典结构。适合需要快速定义字典结构且无需 Pydantic 重量级功能的场景。



<font color="orange">基本使用</font>

```python
from typing import TypedDict, List, Annotated

# 使用TypedDict定义嵌套结构
class Actor(TypedDict):
    """演员情况"""
    name: Annotated[str,"演员姓名"]
    role: Annotated[str,"饰演的角色"]
    
    
class Movie(TypedDict):
    """电影情况"""
    title: Annotated[str,"电影标题"]
    year: Annotated[int,"上映年份"]
    director: Annotated[str,"导演"]
    cast: Annotated[List[Actor],"演员列表"] # 嵌套列表定义
    rating: Annotated[float,"评分"]
    
# 设置模型结构化输出
structured_llm = model_with_closeai.with_structured_output(Movie)
# 调用模型并获取结构化输出
resp = structured_llm.invoke("给我介绍下电影《盗梦空间》")
# 访问嵌套数据
print(f"电影名: {resp['title']}")
print(f"上映年份: {resp['year']}")
print(f"导演: {resp['director']}")
print(f"演员列表:{resp['cast']}")
print(f"评分: {resp['rating']}")
```

### JSON Schema

✅ 这种方式需要按照JSON Schema规范拼接JSON字符串，比较繁琐，并且缺少校验机制。不推荐。



<font color="orange">基本使用</font>

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788430072731-8868a361-2cc8-4aa0-aa68-bfdb0e0ed258.png)



### @dataclass

✅ @dataclass是 Python 标准库 dataclasses 提供的类装饰器，用于简化“以字段为核心”的数据类定义。给类加上 @dataclass 后，Python 会根据字段声明自动生成常用方法，例如：

- __init__
- __repr__
- __eq__

因此，从对象行为上看， @dataclass 创建的类，常常 近似于 手写这些方法的普通类。



<font color="orange">基本使用</font>

```python
from pydantic import Field

@dataclass
class Movie():
    """
    电影的详细信息
    """
    title: str = Field(description="电影标题")
    year: int = Field(description="电影上映年份")
    director: str = Field(description="导演")
    rating: float = Field(description="电影评分，满分十分")
    
structured_model = model.with_structured_output(Movie)
response = structured_model.invoke("给出盗梦空间的信息")
print(response)
print(type(response))
```



### 重点小结

✅ 用Pydantic定义schema，在接收到响应后会进行校验，字段不匹配则抛出异常，其余三种方式不校验。

这里只展示Pydantic如下：

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788430734172-0192e8ad-d0a5-43cc-bc45-6b2906634741.png)



## 获取结构化结果方式

### 使用with_structured_output

代码如下

```python
class Movie(BaseModel):
    """电影信息"""
    title: str = Field(description="电影标题")
    year: int = Field(description="上映年份")
    director: str = Field(description="导演")
    rating: float = Field(description="评分（10分制）")
    
# 设置模型结构化输出
model_with_structure = model.with_structured_output(Movie,include_raw=True)
```



### 使用输出解析器(不推荐)

✅ 这种方法更传统，依赖于在提示词中明确指示模型输出特定格式的文本，然后使用解析器进行转换。其流程是： 提示词指导 (引导生成指定类型）→模型生成文本→解析器转换 。

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788431013837-11a5c82b-7c97-4c2c-b04c-ae57bad5c07c.png)



# 智能体

## 理解 Agents

### 概述

✅ 在大模型应用开发中，智能体通常指一种以 大语言模型为推理与决策核心 ，结合 记忆 、 工具调用 与环境交互能力，能够进行 规划决策 并执行 复杂任务 以达成目标的软件系统。

✅ 核心组件：

![img](https://cdn.nlark.com/yuque/0/2026/png/29329670/1788431768246-33f65677-f4fb-4aea-9c8a-cf124055fe5d.png)

实际开发中几个要素并不需要同时出现，一句话总结

- 必须的：行动（Action）
- 几乎总是存在的：工具（Tool）
- 有条件存在的：规划决策（Planning）
- 最容易被省略的：记忆（Memory）



### agent 的创建与调用

**<font color="red">历史上的调用：</font>**

在 LangChain 0.x 时代，框架内的 Agent 系统经历了“碎片化”阶段。当时的设计理念是 “针对场景设计特定 Agent”：

- 如果你要实现思维链推理（ReAct），就用 create_react_agent ；
- 如果需要结构化输出，就用 create_structured_chat_agent ；
- 要工具调用，则用 create_tool_calling_agent。

```python
# 3. 创建 agent
agent = create_react_agent(
    llm=model,
    tools=tools,
    prompt=prompt
)

# 4. 创建 executor
executor = AgentExecutor(
    agent=agent,
    tools=tools,
    verbose=True
)

# 5. 调用
result = executor.invoke({"input": "问题"})
```

⚠️  这种方式灵活，但也带来了三个明显问题：

1. 心智负担高——每种 Agent 都要单独记忆 API 与参数；
2. 可组合性差——多个 Agent 之间无法统一调度；
3. 生态碎片化——不同模块难以复用或协同演化。



**<font color="red">全新的调用：</font>**

✅ 统一为一个入口：create_agent()

```python
# 2. 创建 agent（一步完成）
agent = create_agent(
    model=model,
    tools=[tool1, tool2],
    system_prompt="Agent 的行为指令" # 可选
)
```

### 模型的传入方式

✅ 分为字符串和对象 比较简单 可以看代码



### 绑定工具

✅ 支持静态和动态绑定，后者需要中间件

<font color="blue">Langchain 内置的工具如下</font>

![img](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788670786.png)

### 工具调用流程分析

 ✅ Langchain的Agent会将模型和工具结合起来，在实现上由一个基于 LangGraph 的图结构来编排执行流程，如下所示。这与前文得到的 Agent 图结构是一致的，本质上就是经典的 ReAct 结构：一个具备<font color="blue">“ 思考-行动-观察”</font>不断循环的自主工作者。

![image-20260906232621599](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788708381.png)

> <font color="red">用户问题 → AI 思考 → 调用工具 → 观察结果 → 继续思考 → ... → 最终答案</font>

✅ 当用户提出一个复杂需求时，Agent会像人类一样，先<font color="blue">理解任务、规划步骤、使用合适的工具（如搜索网络、查询数据库、执行计算）获取信息</font>，Agent 会在一个循环中 反复调用模型和工具 ，直到某次模型输出中 <font color="blue">不再包含工具调用</font> 则结束，最后综合所有信息给出最终答案。

------

<font color="orange">举例</font>

用户问题：“找出当前最流行的无线耳机并检查库存”的任务。

![image-20260906233105302](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788708665.png)



### 重试机制

✅ Agent可以在工具调用结果不满足要求时，自主重试。

```python
messages = [
  SystemMessage("""
  你是一个天气助手。
  当工具返回以 'TEMP_UNAVAILABLE:' 开头的结果时，
  说明是临时故障，不要立即放弃；
  你应再次调用同一个工具，最多重试 3 次。
  如果 3 次后仍失败，再向用户说明服务暂时不可用。
  """),
  HumanMessage("你好，杭州今天的天气如何？")
]
```



## Agent高级用法

### 设置Agent名称

```python
agent = create_agent(
  model=model,
  name =
  "chat_assistant"
)
```

<font color="orange">使用场景</font>

1. 流式输出归因
2. 消息身份标记
3. 调试与trace可读性
4. 组件化封装
5. 前端展示与运行态可观测性
6. 作为稳定的运行时身份标识

> 讲白了就是给Agent设置身份id 方便溯源定位Agent



### 系统提示词

```python
agent = create_agent(
  model=model,
  tools=[get_weather],
  system_prompt=
  """你是天气助手。	
    工作流程：
    1. 理解用户的城市查询
    2. 使用 get_weather 工具获取数据
    3. 简洁清晰地回答
    输出格式：
    - 天气状况
    - 温度
    - 注意事项（如有）
  """
)
```

✅ 提示词设置有两种方式： <font color="blue">静态设置</font> 和 <font color="blue">动态设置</font> 。动态设置需要借助中间件，后续讲解。



### 结构化输出

| 维度     |                模型的结构化输出                | Agent 结构化输出                                |
| -------- | :--------------------------------------------: | ----------------------------------------------- |
| 操作对象 |  作用于 <font color="blue">大模型对象</font>   | 作用于 <font color="blue">Agent</font>          |
| 解析时机 |   每次模型调用 生成 AIMessage 时，进 行解析    | 仅在 Agent 决定"任务结束" 并输出最终 答案时解析 |
| 数据流转 |                模型 结构化对象                 | 模型 工具 反思 ... 结构化对象                   |
| 绑定方式 |          使用 with_structured_output           | 使用 response_format 参数                       |
| 适用场景 | 单次、确定性 的任务（如提取字段、翻 译、分类） | 多步、复杂推理 的任务（如查文档后汇 总报表）    |



 <font color="blue">四种策略</font>

```python
def create_agent(
  ...
  response_format: Union[
    ToolStrategy[StructuredResponseT],
    ProviderStrategy[StructuredResponseT],
    type[StructuredResponseT],
    None,
	]
)
```



------

① <font color="purple">ProviderStrategy</font>

​	使用模型提供商的 <font color="blue">原生结构化输出功能</font> 实现结构化输出。这里所说的“原生结构化输出”指的是大语言模型（LLM）提供商通过其API直接提供的、在模型响应阶段就强制保证 输出格式符合预定规范 的能力，这种能力能够在模型生成内容的源头确保结构化准确性。

​	适用于支持原生结构化输出的模型，比如OpenAI、Anthropic Claude或xAI Grok等。



② <font color="purple">ToolStrategy</font>

​	对于不支持原生结构化输出的模型，LangChain采用“ToolStrategy”工具调用的方式实现结构化输出。此策略兼容绝大多数 支持工具调用 的现代模型，其核心原理是动态创建一个<font color="blue">"虚拟工具"</font>，该工具的输入参数对应着期望的数据结构。

​	当模型需要生成最终答案时，<font color="blue">系统会引导模型"调用"这个虚拟工具</font> ，从而间接产生符合要求的结构化数据。



③ <font color="purple">type / AutoStrategy</font>

​	当我们直接传入一个定义类型时，LangChain会自动包装为AutoStrategy，触发<font color="blue">自动选择策略</font> ：如果模型支持原生结构化输出（如OpenAI、Anthropic Claude或xAI Grok），则优先使用ProviderStrategy；否则使用ToolStrategy。



④ <font color="purple">None</font>

​	默认配置，表示不以结构化输出，以 自然语言 响应用户问题。

> <font color="red">总结：在实际大模型Agent开发场景中，如果使用到了结构化输出，推荐使用 “ToolStrategy”策略 ，所以后续重点介绍这种策略方式结构化输出。</font>



### 流式输出及模式

| 模式             | 输出内容                                                     | 使用场景                                                     |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| values           | 每个步骤执行后，都会输出完整的状态 信息                      | 适用于每一步都要获取完整状态、状 态持久化场景                |
| updates（默 认） | 每个步骤执行后，只增量更新状态中发 生变化的内容              | 用于监控Agent 执行进度，例如观察 Agent决定调用工具、工具执行结果 等步骤 |
| messages         | 输出流式返回的Token以及相关的元数 据（如：来自哪个节点model/tool） | 实现类似ChatGPT 的打字机效果，为 聊天机器人等交互式应用提供最佳的 实时体验 |
| tasks            | 输出当前task任务开始和结束的时间， 包含任务的结果和错误信息  | 该模式用于监控任务的生命周期                                 |
| debug            | 与tasks模式类似，比task模式多输出 任务步骤、时间戳、task类型 （task/task_result） | 该模式用于调试、监控task任务的生 命周期                      |
| checkpoints      | 当检查点（checkpoint）被创建时会 触发输出，输出包含检查点中的状态 | 用于需要状态持久化、工作流恢复或 分布式执行跟踪的高级场景    |
| custom           | 通过get_stream_writer在工具或节点 内部自定义发送的数据       | 用于输出业务逻辑相关的进度信息 （如“已处理10/100条记录”）、自定 义日志或指标 |



<font color="orange">我们可以根据不同的目标来选择不同的输出模式。例如：</font>

- 实现 实时对话交互 ，优先选择messages模式；
- 观察Agent的 思考与执行步骤 ，优先选择updates模式；
- 需要查看 每一步状态 优先选择values/tasks/debug模式；
- 在工具执行时 输出自定义业务 日志优先选择custom模式。



## Agent实战

<font color="red">代码见仓库！</font>



# 中间件

## 概述

### 什么是中间件

✅ 在 create_agent() 的底层运行机制中，有几个重要的组件，分别是：

1. 模型(Model) ：Agent 的“大脑”，负责理解任务与决策推理。
2. 工具(Tools) ：Agent 的“手脚”，执行模型自己做不到的外部操作。
3. 系统提示词(System Prompt) ：Agent的“角色”，告诉模型该怎么想、参考什么上下文。
4. 中间件(Middleware) ：Agent的“中枢”，在执行流程的关键节点进行拦截、控制和增强。



✅ Middleware(中间件)，简单说就是Agent 执行过程中的<font color="blue">钩子函数</font>，是 LangChain 1.x 的“王牌”工程化能力。

<font color="orange">没有中间件的Agent架构</font>

![image-20260907001458063](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788711298.png)



<font color="orange">有中间件的Agent架构</font> <font color="red">非常重要！！！！！</font>

![image-20260907001556026](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260906_1788711356.png)



### 为什么需要中间件

> 用户输入 → 拼接提示词/消息 → 调用模型 → 如有需要调用工具 → 返回结果

这种方式对于简单场景已经足够，但一旦进入真实项目，往往会遇到很多额外需求，例如：

- 想根据问题复杂度动态 切换模型 ；
- 想 限制 某些用户只能调用部分工具；
- 想在工具报错时 自动重试 或返回兜底结果；
- 想在模型调用前 插入额外的系统提示 ；
- 想记录每一步的 执行日志 ，方便排查问题；
- 想在敏感信息出现时 阻断执行 ；
- 想在正式执行工具前增加 人工审批 。

​	这些需求有一个共同特点：它们不是<font color="blue">Agent 的核心业务逻辑，但又会影响 Agent 的执行过程</font>。中间件的价值就在于把这些与业务无关、但与执行过程强相关的横切逻辑，从 Agent 主流程中分离出来。让Agent 主体代码 聚焦业务 ，而借助中间件，实现<font color="blue">“ 拦截流程、修改流程、增强流程”</font>。

​	简言之，LangChain 1.x 的中间件能实现如下功能：

- 日志与分析 - 追踪行为、调试、性能监控
- 转换 - 修改提示词、工具选择、输出格式
- 容错 - 重试、降级、早期终止
- 安* - 限流、守护规则、PII 检测



### 中间件的分类

根据LangChain是否已经定义了来分类：

- 自定义中间件：允许开发者自定义，从而实现更加灵活的Agent行为管理
- 内置中间件：LangChain实现并提供的

模型供应商定制的中间件 ：依赖于特定模型服务的实现
和模型供应商无关的中间件 。LangChain提供的与供应商无关的中间件如下：
链接：https://docs.langchain.com/oss/python/langchain/middleware/overview



<font color="orange">供应商无关的中间件</font>

<font color="green">类型1：成本与资源控制类</font>
核心目标：控成本、控配额、避免无限调用
这类中间件主要解决“ Agent太贵、太能跑、停不下来”的问题。
包含：
- Model call limit：限制模型调用次数，防止一次任务反复请求 LLM，导致费用失控
- Tool call limit：限制工具调用次数，避免 Agent 无限试错、死循环调工具Summarization：在上下文快满时自动总结历史，减少 token 消耗
- Context editing：裁剪上下文、清理工具调用痕迹，本质上也是为了节省上下文成本
业务场景理解：适合生产环境的成本治理、配额治理、长会话优化、SaaS 产品控费。

<font color="green">类型2：稳定性与容错保障类</font>
核心目标：保证服务不中断、失败后尽量自动恢复
这类中间件主要解决“ 调用失败怎么办、模型挂了怎么办、工具超时怎么办”。
包含：

- Model fallback：主模型失败时切换备用模型
- Model retry：模型调用失败后自动重试
- Tool retry：工具调用失败后自动重试

业务场景理解：适合线上生产系统，尤其是多模型、多工具依赖的 Agent。本质上是在做 高可用、容灾、鲁棒性建设。



<font color="green">类型3：安全与合规风控类</font>
核心目标：让 Agent 可控、可审、合规
这类中间件主要解决“ Agent乱执行、泄露敏感信息、做危险操作”的问题。

包含：

- Human-in-the-loop：在关键工具调用前暂停，等人工审批
- PII detection：检测和处理个人敏感信息
- Model call limit / Tool call limit：某种意义上也可归到风控，因为它能防止异常滥用

业务场景理解：适合企业内部系统、客服系统、审批流、数据查询类 Agent。尤其是涉及：发邮件、调数据库、调财务/人事系统、导出敏感信息、执行外部动作等



<font color="green">类型4：决策增强与智能编排类</font>
核心目标：提升 Agent 的决策质量和任务拆解能力
这类中间件主要解决“ Agent不够聪明、不会规划、不会先筛工具”的问题。

包含：
- To-do list：给 Agent 增加任务规划、分步骤执行和状态跟踪能力
- LLM tool selector：当工具太多时，用子模型筛选最相关的几个工具交给主模型
- Subagent：允许生成子Agent，把复杂任务拆给不同角色处理

业务场景理解：适合复杂任务流，比如：研究型 Agent、多步骤分析、报告生成、多角色协作、长链路任务编排等。这类本质上是在增强 Agent的“脑子”与“组织能力”。



<font color="green">类型5：执行能力扩展类</font>
核心目标：给 Agent 更多“手脚”
这类中间件主要解决“ Agent只能聊天，不能真正操作环境”的问题。

包含：
- Shell tool：给 Agent 持久 shell，会执行命令
- File search：给 Agent 文件搜索能力，能做 Glob/Grep
- Filesystem：给 Agent 文件系统读写与长期存储能力

业务场景理解：适合工程 Agent、代码 Agent、本地自动化 Agent、运维 Agent。本质上是把 Agent 从“纯推理”扩展成“能操作环境的执行体”。



<font color="green">类型6：开发调试与测试辅助类</font>
核心目标：方便开发、测试、验证 Agent 行为
这类中间件主要不是直接服务业务，而是服务于 研发和调试阶段 。

包含：
- LLM tool emulator：用 LLM 模拟工具执行，便于测试（最典型）
- Summarization：有时也可辅助调试长会话表现
- Context editing：可用于测试上下文裁剪效果
- Human-in-the-loop：也常用于调试高风险步骤

业务场景理解：适合开发阶段快速验证流程、做 mock、减少真实工具依赖。

##  常用内置中间件

### SummarizationMiddleware中间件

✅ 对历史消息列表进行 <font color="blue">摘要&总结</font> ，达到 <font color="blue">压缩上下文</font> 的效果。在 <font color="blue">达到触发条件</font> 时，调用大模型对历史消息进行摘要， 将摘要的结果作为HumanMessage，放到消息列表最开始的位置。

### HumanInTheLoopMiddleware中间件

✅ HumanInTheLoopMiddleware（人在环中间件、人工审核中间件）在 工具调用前 中断Agent运行，等待用户对工具调用请求决策。可选的决策有： approve（同意执行） 、 edit（编辑调用配置后执行） 、 reject（拒绝执行） 。

### PIIMiddleware中间件

✅ 敏感信息保护。PII中间件用于检测和处理对话中的个人身份信息（Personally Identifiable Information，PII），支持自定义处理策略。



## 其他内置的中间件

ModelCallLimitMiddleware中间件

✅ 限制模型调用次数，避免无限循环，控制调用成本。

### ToolCallLimitMiddleware中间件

✅ 限制工具调用次数，可以 限制所有工具 调用的总次数，也可以 限制特定工具 的调用次数。

### ModelFallbackMiddleware中间件

✅ 用于故障转移，当主模型无法访问时，启用备用模型。

### LLMToolSelectorMiddleware中间件

✅ 智能工具筛选。当工具太多时，用于模型筛选最相关的几个工具。

### ToolRetryMiddleware中间件

✅ 基于指数退避算法，设置工具调用失败时的重试策略。

### ModelRetryMiddleware中间件

✅ 模型调用失败时重试，策略和工具调用的重试一样，都是基于指数退避算法。因此，本节案例不再重点观察指数退避算法，而是测试不同的退出模式。

### LLMToolEmulator中间件

✅ 某些情况下，工具尚未开发完成，我们希望先测试工具调用，可以用LLM tool emulator模拟工具。

### ContextEditingMiddleware中间件

✅ 上下文编辑中间件，该中间件提供了上下文管理的一种方式。通过更改发送给模型的消息列表来控制成本。注意：不会更改消息列表。因此我们只能通过token用量来推测是否对消息列表进行了裁剪。

### FilesystemFileSearchMiddleware中间件

✅ 基于系统的Glob和Grep检索工具，为Agent赋予本地文件搜索和分析的能力。

- Glob根据文件路径检索
- Grep根据文件内容检索

### Shell tool中间件

✅ 为Agent提供一个可以执行命令的Shell环境。Windows下无法测试。

### Filesystem中间件

✅ 这是源自deepagents（基于LangChain的另一个框架）的中间件内置了四个工具，分别用于查看目录、读文件、写文件和改文件。

### Subagent中间件

✅ 也是来自deepagents的中间件用于便捷地创建子Agent。

### 中间件顺序

✅ Middleware 可以叠加使用，那么多个中间件书写顺序非常重要！！！！



## 自定义中间件

✅ 无论是官方内置中间件、自定义中间件、还是下文提到的便捷装饰器中间件，通常都是通过实现其中的一个或多个hook来生效的。



### hook函数分类

✅ 官方将六个钩子函数按照风格分为两类

<font color="orange">类型1：Node-style hooks(节点风格钩子)</font>

顾名思义，它们在流程的 特定节点 运行。适合顺序逻辑，如记录日志、验证包括

- before_agent：在Agent开始运行之前执行。
- before_model：在模型调用之前执行。
- after_model：在模型调用之后执行。
- after_agent：在Agent流程全部完成后执行。

<font color="orange">类型2：Wrap-style hooks(包装风格钩子)</font>

顾名思义，它们在 模型或工具调用前后 运行。适合控制流，如重试、回退、缓存。包括

- wrap_model_call (包裹模型调用)
- wrap_tool_call (包裹工具调用)



### Node-style hooks

✅ 支持两种用法

- 装饰器是函数式挂载，把一个hook快速挂载到Agent的某个节点。
- 类写法是对象化中间件，把中间件封装为一个可配置、可复用、可扩展的组件。



<font color="green">基于装饰器</font>

```python
# 1. 定义 before_model 钩子
@before_model
def before_model_middleware(state: AgentState, runtime: Runtime) ->
dict[str, Any] | None:
	state["messages"][-1].content +="-> before_model <-"
	return None
```



<font color="green">基于类实现</font>

✅ 关键规则：

1. 必须继承 AgentMiddleware ← 这个固定
2. 方法名固定 ( before_model , after_model ) ← 这个固定
3. 类名随意 ← 这个不固定

LangGraph 只看：是否继承 AgentMiddleware？是否有 before_model / after_model 等方法？

```python
class MyMiddleware(AgentMiddleware):
	def __init__(self):
		super().__init__()
    
	def before_model(self, state: AgentState, runtime: Runtime) -> dict[str,
Any] | None:
		state["messages"][-1].content +="-> before_model <-"
		return None

	def after_model(self, state: AgentState, runtime: Runtime) -> dict[str,
Any] | None:
    state["messages"][-1].content +="-> after_model <-"
    return None

	def before_agent(self, state: AgentState, runtime: Runtime) -> dict[str,
Any] | None:
    state["messages"][-1].content +="-> before_agent <-"
    return None

def after_agent(self, state: AgentState, runtime: Runtime) -> None:
    state["messages"][-1].content +="-> after_agent <-"
    return None
```



<font color="green">参数说明</font>

Node-style hooks函数有两个参数

- state: 是一个AgentState实例，维护Agent运行过程中的状态，这类状态会随着Agent的运行而发生变化，包括 消息列表 。

- runtime: 是一个Runtime实例，维护Agent运行过程中的上下文环境，包括 上下文 、 长期记忆 等。



<font color="green">返回值说明</font>

返回 None：不修改状态（不修改Agent状态）

```python
def before_model(self, state, runtime):
  print("日志记录")
  return None # 不做任何修改，继续流程
```

返回字典：更新状态

```python
def after_model(self, state, runtime):
  count = state.get("count", 0)
  return {"count": count + 1} # 更新状态中的 count
```

返回 {"jump_to": "..."}：控制流程

```python
def before_model(self, state, runtime):
	if state.get("count", 0) > 10:
		return {"jump_to": "__end__"} # 跳过模型，直接结束
  return None # 不做任何修改，继续流程
```



**<font color="red">can_jump_to</font>**

✅ 这里就涉及到Node-style的四个hook函数可以接收额外参数 can_jump_to。钩子函数可以 改变Agent正常的运行轨迹 。比如：发现上下文窗口溢出，直接跳转至结尾，提前终止整个Agent。

- can_jump_to 决定了钩子函数可以直接跳转至流程的哪些位置，可取值如下：
- end：跳转至Agent流程末尾，或第一个after_agent钩子，直接终止整个流程。
- tools：跳转至工具节点。
- model：跳转至模型节点，或第一个before_model钩子。



> [!NOTE]
>
> 基于装饰器和基于类实现待实现！！！！



### Wrap-style hooks函数用法

![image-20260907232216681](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260907_1788794536.png)



![image-20260907232053541](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260907_1788794453.png)



<font color="green">基于装饰器</font>

✅ 原理类似



<font color="green">基于类实现</font>

✅ 原理类似



<font color="green">参数说明</font>

- request：被封装的请求对象，可以是模型或工具调用请求
- handler：处理器，用于处理请求并返回调用结果。



### 装饰器和类的选择

<font color="orange">情况1：中间件只用一个钩子函数，推荐用装饰器，需要多个钩子函数推荐类写法</font>

- 当一个中间件只需要实现一个钩子函数时，直接使用装饰器最简单。
- 当一个中间件需要实现多个钩子函数时，类写法更合适。

装饰器也不是不能实现，多数情况下可以像下面的示例里那样通过工厂函数返回多个装饰器函数来完成；但这种方式本质上是把一个“逻辑上属于同一个中间件”的行为拆成多个独立函数，再由外部统一组装，因此不如类写法自然、集中、清晰。

<font color="orange">情况2：复杂配置推荐用类实现</font>

装饰器当然也可以通过函数闭包传递参数，但在自省（运行时类型校验）、调试等方面天然不如类写法方便。

<font color="orange">情况3：跨项目复用推荐用类写法</font>

如果希望中间件成为一个可实例化、可封装、可测试的组件，类写法更加合适，因为这些本就是类擅长的场景，装饰器的闭包也能实现，但使用不友好。



### hook函数的执行顺序

分类讨论

- before_* 钩子函数：从前到后执行
- after_* 钩子函数：从后往前执行
- wrap_* 钩子函数：洋葱架构，前面的包裹后面的

这里的顺序并非定义顺序，而是创建Agent时传递中间件的顺序。



# 上下文和记忆

## 概述

### 为什么需要上下文

✅ 记忆是一种记住之前互动信息的系统

![image-20260907233418738](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260907_1788795258.png)



### 上下文工程

✅ 上下文工程(Context Engineering) 负责“合理组织”这些记忆和任务信息 ，让LLM的响应更连贯、更贴合需求。这也是Agent能实现 复杂多轮交互 的核心基础。

![image-20260907233929432](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260907_1788795569.png)



### 上下文类型及相关的API

✅ LangChain的上下文工程是基于Agent讨论的，而上下文工程是构建在LangGraph之上的。LangGraph 提供了三种管理上下文的方法，这些方法结合了可变性和生命周期维度：

| 上下文类型        | 描述                                                      | 可变 性 | 生命 周期 | 访问方法              |
| ----------------- | --------------------------------------------------------- | ------- | --------- | --------------------- |
| 动态运行时 上下文 | 在单次运行中会演变的可变数据                              | 动 态   | 单次 运行 | LangGraph state对象   |
| 动态跨会话 上下文 | 在对话间共享的持久数据。比如用户偏好、 历史洞察、知识条目 | 动 态   | 跨对 话   | LangGraph store对象   |
| 静态运行时 上下文 | 在启动时传入的用户元数据、工具、数据库 连接               | 静 态   | 单次 运行 | LangGraph context对象 |



### 记忆的分类

官方说明：https://docs.langchain.com/oss/python/concepts/memory

记忆分为短期记忆和长期记忆，对应不同的使用场景：

- 短期记忆（Short-term memory、会话级记忆、thread-scoped memory）：作用范围是<font color="blue">单个对话线程</font>（Thread）内，一旦开启新对话（更换 thread_id ），记忆即消失。
- 长期记忆（Long-term memory，跨会话级记忆 ）：在会话间存储用户特定或应用级数据， 并在<font color="blue">会话线程间共享</font> 。它可以随时在<font color="blue">任何线程中被调用</font>。记忆的范围是任意自定义命名空间，而不仅仅是单一线程 ID。

![image-20260907234348531](/Users/chenyu/Library/Application Support/typora-user-images/image-20260907234348531.png)



### 记忆的管理

✅ 在LangChain v0.x版本中，通过专用的xxxMemory类管理记忆。

✅ 在LangChain v1.x版本中，Agent是构建在LangGraph图结构之上的，通过上文提到的state和store构建记忆系统。使用更简单、功能更统一。

- state：短期记忆对象，以 会话 为单位组织，包含当前会话的所有消息记录以及自定义信息。
- store：长期记忆对象， 跨会话持久化 的数据，通常需要结合向量数据库或外部存储实现。

## 短期记忆

✅ LangChain1.x 的短期记忆是三者的组合：

State（会话内部状态） + Checkpointer（持久化机制） + Thread ID（会话作用域）

- State ：默认 存储历史消息列表messages ，通过State 管理历史消息
- Checkpointer ：负责将State 作为检查点持久化保存，检查点是某个时刻的State 快照
- Thread ID ：用于唯一标识State ，LangChain运行时会按照 thread_id 读写State快照

> 这就像玩 RPG 游戏时的“自动存档”：你不需要手动保存，系统在关键节点自动记录，下次进入游戏随时可以从上次的存档点继续。

### 基于内存的持久化器

```python
from langgraph.checkpoint.memory import InMemorySaver

checkpointer = InMemorySaver()

# 1. 创建 Agent 时添加 checkpointer
agent = create_agent(
  model=model,
  checkpointer=checkpointer # 添加内存管理
)
# 2. 调用时指定 thread_id
config = {
  "configurable": {
  "thread_id": "1"
  }
}

print("\n第一轮对话：")

response1 = agent.invoke({
  "messages": [HumanMessage("我叫张三")]},
  config=config # 传入 config
)

print(f"Agent: {response1['messages'][-1].content}")
print("\n第二轮对话：")
response2 = agent.invoke({
  "messages": [HumanMessage("我叫什么？")]},
  config=config # 使用相同的 thread_id
)
print(f"Agent: {response2['messages'][-1].content}")
```

说明：你只需传入 checkpointer 和 config，Agent 就能自然具备连续对话能力。



<font color="green">关键步骤说明</font>

<font color="orange">第1步：初始化记忆引擎：</font> checkpointer = InMemorySaver() ——创建一个内存级的记忆存储。

<font color="orange">第2步：绑定 Agent：</font>在 create_agent 时传入 checkpointer ，让 Agent 具备状态存储能力。

<font color="orange">第3步：设定会话 ID：</font>通过 config = {"configurable": {"thread_id": "1"}} 为每次调用指定线程标识。同一个 thread_id 共享记忆，不同 thread_id 完全隔离。

```python
# 会话 1
config1 = {"configurable": {"thread_id": "1"}}
agent.invoke({...}, config=config1)
# 会话 2
config2 = {"configurable": {"thread_id": "2"}}
agent.invoke({...}, config=config2)
# 两个会话完全独立
```

thread_id 是记忆管理的核心开关：在会话2里询问会话1的会话信息，Agent 会表示不知道——因为双方记忆空间完全隔离。



<font color="green">工作原理</font>

```python
agent.invoke({"messages": [{"role": "user","content": "你好"}]}, config)
# InMemorySaver 保存：
# {
#   "thread_id": "xxx"
#   "messages": [
#       HumanMessage("你好"),
#       AIMessage("你好！有什么可以帮助你的吗？")
#   ]
# }

agent.invoke({"messages": [{"role": "user","content": "天气"}]}, config)
# InMemorySaver 更新：
# {
#   "thread_id": "xxx"
#   "messages": [
#       HumanMessage("你好"),
#       AIMessage("你好！有什么可以帮助你的吗？"),
#       HumanMessage("天气"),
#       AIMessage("...")
#   ]
# }
```

 

<font color="green">常见的问题</font>



1. 为什么 Agent 不记得？

   检查：

   ✅ 是否添加了 checkpointer=InMemorySaver() ？

   ✅ 是否传入了 config 参数？

   ✅ 两次调用的 thread_id 是否相同？

   

2. InMemorySaver 只保存在内存中：

​	✅ 同一进程内有效（不支持跨进程共享）

​	❌ 程序重启后丢失（或进程重启后丢失）

​	❌ 不同进程无法共享

解决方案：持久化（SQLite、PostgreSQL）



3. 默认情况下，InMemorySaver 会保存所有消息。

问题：消息越来越多（无限增长，需要管理上下文）token消耗增加，甚至会超过模型的 token 限制响应速度变慢、成本增加

解决方案：上下文管理（修剪、摘要）



4. 如何清空某个会话的历史？

   目前 InMemorySaver 没有提供删除 API。临时方案：

   - 使用新的 thread_id

   - 或重新创建 Agent

### 基于外部存储介质的持久化器

✅ LangGraph提供的checkpointer后端列表如下https://docs.langchain.com/oss/python/langgraph/persistence#checkpointer-libraries

此处选择PostgreSQL作为持久化器。



```python
DB_URL =
"postgresql://langchain_user:abcd1234@118.195.128.47:5432/langchain_db?
sslmode=disable"
with PostgresSaver.from_conn_string(DB_URL) as checkpointer:
  # 初始化PostgreSQL数据库
  checkpointer.setup()
  agent = create_agent(
    model=model,
    checkpointer=checkpointer
  )
  config = {"configurable": {"thread_id": "1"}}
```

setup() 用于初始化PostgreSQL数据库，首次运行会创建必要的表，重复执行不会重新建表，底层逻辑是 Create IF Not Exists ，相关源码如下



### 记忆治理策略（上下文管理）

✅ 随着对话的进行，历史消息不断累积， state会持续增长 ，为模型带来挑战：

1. LLM的 上下文窗口是有限的 ，完整历史可能无法装入LLM的上下文窗口，导致上下文丢失或错

误。

2. 即便模型的上下文窗口够大，多数LLM在长上下文场景仍然表现不佳。模型会 被陈旧或离题的内容“分散注意力”。

3. 同时，会带来 高昂的token花费 。

此时需要对上下文进行管理：对历史记录进行压缩、清理、重组等。



<font color="oragne">消息剪裁</font>

✅ 目标是控制token用量，通常 保留系统初始消息和最近若干消息 ，或 按token数保留末尾内容 。适合成本敏感、对旧上下文依赖不强的场景。



<font color="oragne">消息删除</font>

✅ 消息裁剪强调“在 模型调用前裁剪 消息列表，控制模型可以看到的上下文范围”，而消息删除强调 模型调用完成后将某些消息从消息列表中移除 ，永久更改状态。适合明确要遗忘、清理、重置某些历史。



<font color="oragne">摘要</font>

![image-20260908115542884](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260908_1788839742.png)

```python
# 创建带摘要中间件的 Agent
agent = create_agent(
  model=model_out,
  tools=[],
  checkpointer=InMemorySaver(),
  middleware=[
		SummarizationMiddleware(
			model=model_in,
			trigger=[
				("tokens", 100), # 超过 100 tokens 就摘要
			],
			keep=("messages", 2),
			summary_prompt="对历史消息摘要，消息列表如下\n{messages}",
		)
	]
)
```



<font color="red">设置最大token数触发摘要的标准是啥？</font>

```
# 模型上下文窗口 4k → 设置 3000
# 模型上下文窗口 8k → 设置 6000
# 模型上下文窗口 16k → 设置 12000
# 留一些余量给工具调用和系统提示
```



<font color="oragne">自定义过滤策略</font>



### state的理解

✅ state的底层定义如下

```python
class AgentState(TypedDict, Generic[ResponseT]):
	"""State schema for the agent."""

	messages: Required[Annotated[list[AnyMessage], add_messages]]
	jump_to: NotRequired[Annotated[JumpTo | None, EphemeralValue,
PrivateStateAttr]]
	structured_response: NotRequired[Annotated[ResponseT, OmitFromInput]]
```



## 长期记忆

### 概述

#### 什么是长期记忆

✅ 短期记忆记录的是 会话级别（线程，Thread） 的数据， 会话间不共享 。

✅ 而长期记忆记录的是用户特定或应用级别的数据，任何会话都可以随时访问。

![image-20260908121039866](/Users/chenyu/Library/Application Support/typora-user-images/image-20260908121039866.png)



#### 分类

LangChain参考CoALA paper将长期记忆划分为三类：

| Memory Type                            | 存什么        |
| -------------------------------------- | ------------- |
| Semantic（语义记忆）                   | 事实          |
| Episodic（情景记忆）                   | 经验          |
| Procedural（程序性记忆） 规则/做事方法 | 规则/做事方法 |



#### 存储架构

✅ 长期记忆的存储是 <font color="blue">store -> namespace -> key -> value</font> 的四层架构。

<font color="orange">第1层：Store（记忆仓库）</font>

- Store是 langgraph.store.base.BaseStore 的子类实例，由全类名可知，store是由LangGraph提供的。常用实现类：

​		InMemoryStore ：将长期记忆存储在内存，适合测试

​		PostgresStore ：将长期记忆存储在外部的PostgreSQL数据库，适合生产环境

- 开发期可用 InMemoryStore；生产建议数据库后端，如 PostgresStore

<font color="orange">第2层：Namespace（命名空间）</font>

​	数据类型是由任意长度的 tuple[str, ...] 表示的 <font color="blue">层级路径</font>。作用上很像“文件路径 / 文件夹层级”，用于给长期记忆分组和隔离。数据类型为 字符串元组

<font color="orange">第3层：Key（键）</font>

是该 namespace 下的唯一标识，单条记忆的唯一键，数据类型为 字符串(str)

<font color="orange">第4层：Value（值）</font>

是存储的值，数据类型为 字典(dict[str, Any])

```python
namespace = ("users","user_123","preferences") # 元组类型
key ="profile" # 字符串类型
value = { # 字典类型
	"language": "zh-CN",
	"style": "short_direct",
	"likes": ["python","rag"]
}
store.put(namespace, key, value)
```



#### API使用



#### 在Agent运行图中访问长期记忆



#### 何时写入记忆

官方介绍了两种方式。

1. 在主流程里写（hot path）

也就是：用户发消息，AI 一边回答，一边决定要不要记下来。

优点：

​	立即生效

​	下一轮马上能用

​	用户可感知，透明

缺点：

​	增加延迟

​	逻辑变复杂

2. 在后台写（background）

就是先回答用户，记忆整理放到后台 异步 做。

优点：

​	主流程更快

​	记忆逻辑更独立

​	更适合批量整理

缺点：

​	不能立刻生效

​	要决定多久整理一次

​	触发时机不好选

工程上通常这么选：用户偏好、账号资料 ：可热路径写

对话摘要、经验沉淀、行为分析 ：更适合后台写





# RAG

✅ RAG（Retrieval-Augmented Generation，检索增强生成）是一种结合 信息检索 （Retrieval）与 文本生成 （Generation）的技术，旨在提升大语言模型在回答专业问题时的 准确性 和 可靠性 。

![image-20260908132716704](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260908_1788845236.png)

即：

![image-20260908132746905](https://raw.githubusercontent.com/Mr-chenyu-NJ/note/main/PIC/2026/09/upgit_20260908_1788845266.png)

















