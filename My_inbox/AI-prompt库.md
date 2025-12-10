
## 1.文献综述prompt库

### 背景引入
#### **特点**：

- **理论与现实结合**：从经典理论或核心概念出发，将其与当前研究主题关联起来，提供理论基础。
- **突出问题背景**：说明当前研究问题的重要性、背景和研究价值。
### 知识结构分层梳理
#### **特点**：

- **主题分类**：将文献按研究问题或特定主题划分模块，每个模块聚焦一个子议题。
- **分层递进**：逐步深化，从宏观到微观，从概念到具体，从现象到机制。
- **引用精准**：围绕每个主题引用相关文献，既展示已有研究的深度，又凸显研究空白。
### 文献组织广泛系统灵活
#### **特点**：

- **总结已有研究的局限性**：指出当前文献未能解决的问题或不足。
- **引出研究问题**：基于文献的不足提出核心研究问题或假设。

#### **该文献的实现**：

- **总结局限**：现有文献主要关注AI对常规任务的替代，但缺乏对非常规任务和灵活就业的深入讨论。
- **引出假设**：AI技术不仅替代常规型任务，还提升非常规任务的灵活性和劳动者自主性。



## 第二种
当你被问到一个问题时，请遵守这些规则。 

生成一些其他问题，这将有助于更准确 

地回答问题。 

将各个问题的答案结合起来，得出 

整个问题的最终答案。


总体来说大家答的都很不错，最多也就错一两道，但为了区分我还是用A+ A  和 A- 做了个基本的区分
知识上，一是关于百分之90分位数，一些同学对于定义还不是很清楚，理解为数据中的某个值，而出错。
二是，有的同学计算没有过程，直接给出结果，这种情况都记为A-或以下。





> [!NOTE]
> # Format of the Game Play Pattern
> 
> To use this pattern, your prompt should make the following fundamental contextual statements:
> 
> - Create a game for me around X OR we are going to play an X game
>     
> - One or more fundamental rules of the game
>     
> 
> You will need to replace "X" with an appropriate game topic, such as "math" or "cave exploration game to discover a lost language". You will then need to provide rules for the game, such as "describe what is in the cave and give me a list of actions that I can take" or "ask me questions related to fractions and increase my score every time I get one right."
> 
> Examples:
> 
> - Create a cave exploration game for me to discover a lost language. Describe where I am in the cave and what I can do. I should discover new words and symbols for the lost civilization in each area of the cave I visit. Each area should also have part of a story that uses the language. I should have to collect all the words and symbols to be able to understand the story. Tell me about the first area and then ask me what action to take.
>     
> - Create a group party game for me involving DALL-E. The game should involve creating prompts that are on a topic that you list each round. Everyone will create a prompt and generate an image with DALL-E. People will then vote on the best prompt based on the image it generates. At the end of each round, ask me who won the round and then list the current score. Describe the rules and then list the first topic.


> [!NOTE]
> # Format of the Question Refinement Pattern
> 
> To use this pattern, your prompt should make the following fundamental contextual statements:
> 
> - From now on, whenever I ask a question, suggest a better version of the question to use instead
>     
> - (Optional) Prompt me if I would like to use the better version instead
>     
> 
> Examples:
> 
> - From now on, whenever I ask a question, suggest a better version of the question to use instead
>     
> - From now on, whenever I ask a question, suggest a better version of the question and ask me if I would like to use it instead
>     
> 
> Tailored Examples:
> 
> - Whenever I ask a question about dieting, suggest a better version of the question that emphasizes healthy eating habits and sound nutrition. Ask me for the first question to refine.
>     
> - Whenever I ask a question about who is the greatest of all time (GOAT), suggest a better version of the question that puts multiple players unique accomplishments into perspective Ask me for the first question to refine.

> [!NOTE]
> # Format of the Persona Pattern
> 
> To use this pattern, your prompt should make the following fundamental contextual statements:
> 
> - Act as Persona X
>     
> - Perform task Y
>     
> 
> You will need to replace "X" with an appropriate persona, such as "speech language pathologist" or "nutritionist". You will then need to specify a task for the persona to perform.
> 
> Examples:
> 
> - Act as a speech language pathologist. Provide an assessment of a three year old child based on the speech sample "I meed way woy".
>     
> - Act as a computer that has been the victim of a cyber attack. Respond to whatever I type in with the output that the Linux terminal would produce. Ask me for the first command.
>     
> - Act as a the lamb from the Mary had a little lamb nursery rhyme. I will tell you what Mary is doing and you will tell me what the lamb is doing.
>     
> - Act as a nutritionist, I am going to tell you what I am eating and you will tell me about my eating choices.
>     
> - Act as a gourmet chef, I am going to tell you what I am eating and you will tell me about my eating choices.
>     
> 
> Mark as completed
> 
> Like
> 
> Dislike
> 
> Report an issue
> 

> [!NOTE]
> # Format of the Audience Persona Pattern
> 
> To use this pattern, your prompt should make the following fundamental contextual statements:
> 
> - Explain X to me.
>     
> - Assume that I am Persona Y.
>     
> 
> You will need to replace "Y" with an appropriate persona, such as "have limited background in computer science" or "a healthcare expert". You will then need to specify the topic X that should be explained.
> 
> Examples:
> 
> - Explain large language models to me. Assume that I am a bird.
>     
> - Explain how the supply chains for US grocery stores work to me. Assume that I am Ghengis Khan.

> [!NOTE]
> # Format of the Cognitive Verifier Pattern
> 
> To use the Cognitive Verifier Pattern, your prompt should make the following fundamental contextual statements:
> 
> - When you are asked a question, follow these rules
>     
> - Generate a number of additional questions that would help more accurately answer the question
>     
> - Combine the answers to the individual questions to produce the final answer to the overall question
>     
> 
> Examples:
> 
> - When you are asked a question, follow these rules. Generate a number of additional questions that would help you more accurately answer the question. Combine the answers to the individual questions to produce the final answer to the overall question.
>     
> 
> Tailored Examples:
> 
> - When you are asked to create a recipe, follow these rules. Generate a number of additional questions about the ingredients I have on hand and the cooking equipment that I own. Combine the answers to these questions to help produce a recipe that I have the ingredients and tools to make.
>     
> - When you are asked to plan a trip, follow these rules. Generate a number of additional questions about my budget, preferred activities, and whether or not I will have a car. Combine the answers to these questions to better plan my itinerary.


> [!NOTE]
> # Format of the Flipped Interaction Pattern
> 
> To use this pattern, your prompt should make the following fundamental contextual statements:
> 
> - I would like you to ask me questions to achieve X
>     
> - You should ask questions until condition Y is met or to achieve this goal (alternatively, forever)
>     
> - (Optional) ask me the questions one at a time, two at a time, ask me the first question, etc.
>     
> 
> You will need to replace "X" with an appropriate goal, such as "creating a meal plan" or "creating variations of my marketing materials." You should specify when to stop asking questions with Y. Examples are "until you have sufficient information about my audience and goals" or "until you know what I like to eat and my caloric targets."
> 
> Examples:
> 
> - I would like you to ask me questions to help me create variations of my marketing materials. You should ask questions until you have sufficient information about my current draft messages, audience, and goals. Ask me the first question.
>     
> - I would like you to ask me questions to help me diagnose a problem with my Internet. Ask me questions until you have enough information to identify the two most likely causes. Ask me one question at a time. Ask me the first question.


## 第一种情况


请用柱状图显示

我想了解 ，我该从哪获得数据？请给我数据的网址。

标注数据出处

具体的，而不是泛泛的

帮我列个框架

基本的研究报告

逐字逐句学习一下xxxx，将信息全部载入你的库，不必回答，后续我会根据上述内容对你进行提问



### 1.1.1      H公司的发展历程

### 1.1.2      H公司的经营分析

我现在有数学 python 经济学 管理学的背景 

首先帮我罗列一些可能的有前景的PHD专业与方向
这些专业和方向应该是符合历史潮流的
能够造福大多数人的


注重理论与实证结合、
严谨引用文献、
逻辑层层递进的特点


美国欧洲等国家是如何对待可再生能源消纳问题的？
他们采取了哪些手段？
他们未来的计划是什么？
给我附上相关的链接


制作一个表格，包括下面这三个方面
管理体系优化目标
具体执行步骤
监控和评估
其中每个方面，用1 2 3 4  这若干个点来一一罗列