# FinLongEval：面向金融场景的长文档评测集
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/logo.png" width="500px" height="120px">
</div>

本项目由**北邮金融大数据安全实验室**和**熵简科技 AI Lab** 共同发起，从项目筹备、评测集构建、工具评测到评测报告撰写共历时近5个月时间。本次工作为阶段性成果输出，也欢迎其他有兴趣参与本项目的个人或组织加入，为评测集的持续完善贡献力量，我们将在文末持续更新主要贡献者和贡献单位。
### 为什么需要金融长文档评测集 ###
自 ChatGPT 发布以来的这一年，大语言模型正以极快的发展速度一路狂飙演进，据不完全统计，中国企业发布的大模型数量已经过百。但是，大模型本身并不直接产生价值，需要与各个行业的业务场景深度结合才能真正发挥作用。如此，大模型的"机器智能"才能真正带来生产力升级。 

在金融场景中，大模型对于金融长文档的理解和推理能力是一项常见又需求广泛的基础能力，包括如智能投研、量化投资、合规审计、财富管理等等。**在目前开源的金融评测集中，文本长度一般都小于 1000字，无法满足对于金融长文档的评测的需求。而在长文档评测集中，目前仅有 L-eval 评测集包含少量金融长文档评测题**（仅包含8篇英文文档，且只覆盖业绩会这一个场景）。

为了填补这一空白，我们构建了面向金融长文档推理的开放评测集 **FinLongEval**，以提供衡量大模型在金融长文档处理的评估任务集及评估办法，推动大模型在金融场景下的落地。  
### 哪些组织可能需要用到这个评测集 ###
FinLongEval 评测集对于以下三类群体或组织有一定帮助：
- **大模型研发厂商**：帮助大模型厂商更准确理解金融场景下真实业务需求，帮助了解所研发的大模型在金融长文档场景下的能力范围及优化方向；
- **学术组织**：帮助学术机构更准确了解大模型在金融场景落地上的关键需求和主要挑战，以加快技术研究和创新；
- **金融机构**：百模大战之下，作为最终用户的金融机构，在选择大模型产品时已然 “乱花渐欲迷人眼”，本评测集可以帮助金融用户更科学、准确地筛选出符合真实场景需求的金融大模型和产品；
### 主流长文档工具的评测 ###
在 FinLongEval 评测集的基础上，本次我们也挑选了市面上几款具有代表性的用于长文档辅助阅读的产品，进行详细评估和分析。

不同于其他评测报告中直接以大模型作为评测对象，本次我们将长文档阅读和推理的产品作为评估对象，因此整个评估结果既包含了大模型本身的长文档推理和理解能力，也同时包含了处理链上的其他环节的性能，如检索准确度、文档解析和分割效果等（若产品采用 RAG 的路线）。

采用这一方案的原因在于，我们希望站在金融从业者（最终用户）的角度，全面评估当前大模型商业产品对于金融长文档处理能力的边界和不足，以及距离业务成熟可用的距离。
### 工作计划 ###
FinLongEval 评测集的整体工作计划如下：
- [x] **2023-12**：发布 FinLongEval 1.0 版，包含中文场景下的金融长文档评测集；
- [ ] **2024-02**：发布 FinLongEval 1.1 版，增加英文场景下的金融长文档评测集；
- [ ] **2024-04**：根据社区反馈，在评测集规模、问题类型覆盖度、问题难度、文件类型覆盖上进行一次较大升级 ；
## 评测集详情介绍 ##
### 构建原则 ###
在 FinLongEval 构建过程中，我们希望评测集能够从一线金融业务场景来，再服务到各个业务场景中去，能够真正代表金融场景下的各类典型问题和典型需求。为此，我们和多家一线证券公司的业务部门和IT部门进行深入沟通，最终整理和搜集了最具代表性的 **8 大类金融长文档**和 **12 大类问题**，共计 **43 篇金融长文档**和 **347 道问题**（FinLongEval 1.0版）。 
### 文档类型 ###
如上所述，在金融长文档类型上，我们总共搜集和整理了 8类一级分类文档，18类二级分类文档。各类文档的基本情况如下所述：
- **券商研究报告**：涵盖个股研报、行业研报、宏观研报、金工研报这四类常见券商研报，文本长度在1万字至3万字之间；
- **上市公司公告/募集书**：涵盖拟上市公司招股书、债券募集书、基金募集说明书、上市公司年报、业绩预告&快报、股权激励公告等，文本长度大部分在10万字至30万字之间；
- **财经资讯**：涵盖财经评论、主流财经媒体的财经早报等，文本长度在3千字至1万字之间；
- **会议路演**：涵盖业绩交流会、策略会等会议文字，文本长度在1万字至5万字之间；
- **政策文件**：涵盖国务院政策文件、政府工作报告、人民银行的货币政策报告等文件，文本长度在1万字至5万字之间；
- **学术论文**：涵盖货币政策、外汇储备、疫情研究等金融学术类文章，文本长度在1万字至3万字之间；

下图所示为本评测集的文件类型分布比例图，券商研究报告、上市公司公告/募集书（定期报告、公司发行、公司重大事项）、财经资讯、会议路演文件，占比分别为 25.4%、19.3%、17.9%、15.6%。在文件类型覆盖度和覆盖比例上面我们尽量做到与实际业务场景的需要处理文件类型分布比例保持一致。
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E6%96%87%E4%BB%B6%E7%B1%BB%E5%9E%8B%E5%88%86%E5%B8%83%E5%9B%BE%E9%A5%BC%E5%9B%BE.png" width="750px" height="500px">
</div>

### 问题类型 ###
为了充分考查大模型在金融长文档上面的能力表现，同时充分考虑在实际业务的各类场景，如投研分析、文档合规审查、投教服务等场景，我们设计了12类不同类型的问题，以期望从不同维度、不同场景下对于大模型进行充分的评估和测试。具体的问题类型、相应的考查目标和业务场景如下表所示：

| 问题类型 | 任务描述 | 金融场景任务描述 |
| ----- | ----- | ----- |
| 信息提取 | 从文本中获取指定类别信息，重点考查系统的检索能力以及大模型的信息提取能力。 | 金融机构需要从文档中提取出某种特定的信息，如识别公司实体、事件查询等。如快速获取招股书中的发行人基本信息。 |
| 表格提取 | 从文档中识别和提取表格，重点考查系统解析PDF表格能力，以及大模型对于二维表格数据的理解能力。 | 某些精细的投研数据只存在于表格中，需要精准识别。如定期报告的财务摘要数据一般存在于表格中，包括研报中的盈利预测数据等等。 |
| 关键数据提取 | 精确识别统计数值，重点考查系统精确检索能力，以及大模型的实体提取能力。 | 抽取金融文档中的特定数值信息，如从公司业绩会的纪要中抽取营收、毛利等指标数据，从公司报告中抽取产销量等经营指标。 |
| 阅读理解 | 深入分析和理解文本意义，重点考查大模型的长文本理解的综合能力。 | 常见场景如帮助分析师快速生成某个问题的相关数据、分析逻辑、结论。例如，公司的毛利率变化分析，需要大模型不仅找到相关数据，还要理解毛利率的概念，影响因素等，综合分析后给出结论。 |
| 事件分析 | 分析文本中的事件，大模型通过适当的逻辑推理得到正确答案，重点考查大模型的金融概念理解、金融事理的逻辑推理能力。 | 对于资讯中的事件，分析师可以让大模型进一步思考，获取更多推理后的信息。常见场景包括，量化投资、政策分析、ESG因子挖掘等等。 |
| 逻辑推理 | 分析文本中的论证和逻辑关系,并通过多步推理得出新的结论。重点考查大模型的逻辑推理能力，尤其在金融问题下的推理能力。 | 常见场景包括在投资研究场景中，分析师需要让大模型基于公司基本面情况辅助进行未来业绩分析，或者基于行业基本面情况，辅助进行行业走势分析。 |
| 关键词 | 摘录文本的主题词，重点考查大模型的文本提炼能力。 | 快速总结金融文档中的主旨的关键词。比如会议路演的关键词。 |
| 文本摘要 | 生成对文本主要内容的精简汇总，重点考查大模型的文本提炼能力。 | 快速金融投研文档中的摘要，如会议路演的文档可快速生成摘要，典型场景包括如政策分析、机构问答分析、文本因子挖掘等。|
| 生成提纲 | 产出文本内容的框架和要点，重点考查大模型的文本提炼能力。 | 服务于写作场景，如政府报告可生成简要提纲后，写点评。 |
| 对话人分辨 | 辨认出对话中不同的发言人，重要考查大模型的多人对话的理解能力。 | 会议路演通常是多人参与，准确识别多人角色才能准确总结每个角色的内容。 |
| 陷阱问题 | 重点考查大模型的在幻觉方面的严重程度。在我们的场景下，幻觉是指大模型在回答的答案中生成了金融文档并不包含的事实信息。 | 对于金融行业来说，精准的信息至关重要。大模型的幻觉程度，直接影响了基于大模型的系统在金融场景下的可落地程度。 |
| 计算问题 | 重点考查大模型的数学计算能力。 | 基于文档中的已知数据，分析师希望进一步做一些数据计算工作，如计算衍生指标。 |

下图所示为本评测集的问题类型分布图。其中，阅读理解、信息提取、逻辑推理的数量最多，占比分别是 26%、25%、13%，表格提取、事件分析、文本摘要、陷阱问题等的比例相当，均在 7% 左右。这一分布比例也较为符合我们在前期做机构调研时的抽样结果。

<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E9%97%AE%E9%A2%98%E7%B1%BB%E5%9E%8B%E5%88%86%E5%B8%83%E5%9B%BE.png" width="450px" height="350px">
</div>

### 文件的长度分布 ###
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E6%96%87%E6%A1%A3%E9%95%BF%E5%BA%A6%E5%88%86%E5%B8%83%E5%9B%BE.png" width="500px" height="280px">
</div>

上图所示为本次评测集中各个文件字数分布比例，可以看出，**超过80%以上的文件字数超过了1万字**，这一长度远远大于现有金融评测集的平均文本长度。超过 40% 以上的文件字数超过了2.5万字，这一长度超过了当下典型商用大模型的上下文窗口长度。此外，本评测集还包含了最长字数超过 **50万字**（约500页）的超长金融文档。

由此也可以看出，在实际各类金融业务场景中，典型的金融文件都在数万字，某些场景下几十万字也是常态，因此长文档处理能力是大模型在金融场景落地的必备基础能力。
### 参考答案的编写 ###
在编写本次评测集的参考答案过程中，我们采用了 “2+1+1” 的工作流程。首先，我们采用了2个当下最先进的大模型 GPT4 和 Claude2 根据问题和金融文档的原始内容，分别编写两个答案。接下来，会有一名人类专家根据原始文档对于两个答案进行逐一检查确认，并融合成一个完整、连贯的答案。最终，另有一名人类专家根据金融文档的原始内容对于这一答案进行复核和优化，并以此作为最终的参考答案。

采用这一流程的原因在于，本次评测集的问题 80% 为主观类问题且文本长度在几万字量级，如果直接由人工编写非常耗费时间，同时我们也发现当下最先进的AI系统通过适当人力协助，已经能够编写接近人类水平的答案，因此我们最终决定采用这种人机结合的方式。
### 样例数据 ###
如下图所示，本评测集的构成有**一级文件类型**、**二级文件类型**、**文件名**、**问题类型**、**问题**、**参考答案**等。
这里给出了三个例子，有研报的公司财务数据提取、招股书的发行人毛利率情况分析，还给了一个陷阱问题的示例。更多样例数据请参考[样例文件夹](https://github.com/valuesimplex/FinLongEval/blob/main/data/sample_data.jsonl)。
<details>
  <summary>点击查看表格</summary>

  | 一级类型 | 二级文件类型   | 文件名                                       | 问题类型 | 问题                                                         | 参考答案                                                     |
| -------- | -------------- | -------------------------------------------- | -------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 研报     | 个股研报       | 同花顺(300033)乘AI东风，金融信息服务扬帆起航 | 表格提取 | 提取同花顺2021-2025年的财务摘要。指标为营业收入、归属母公司净利润、每股收益、市盈率。要求：以表格形式输出。单位把百万元转换为亿元。 | “同花顺2021-2025年的财务摘要,具体如下: 财务摘要(亿元) 指标  2021A  2022A  2023E  2024E  2025E   营业收入  35.10  35.59  40.68  45.97  51.32  归属母公司净利润  19.11  16.91  20.51  22.29  24.49  每股收益(元)  3.56  3.15  3.82  4.15  4.55   市盈率  40.61  31.30  59.48  54.74  49.83  主要内容包括: 1. 2021-2022年的财务数据为公司报告的数据。 2. 2023-2025年的数据为预测值。 3. 单位全部转换为亿元。 4. 指标包括营业收入、归属母公司净利润、每股收益和市盈率。” |
| 公告     | 拟上市公司招股 | 中电港招股说明书                             | 阅读理解 | 请告诉我，发行人近三年的主营业务的毛利率情况，分析毛利率变化的原因。然后，比较一下发行人与可比公司的毛利率情况。 | “中电港近三年的主营业务毛利率情况如下：- 2019年度：3.72%- 2020年度：3.87%- 2021年度：3.53%，报 告期内公司主营业务综合毛利率较为稳定。 毛利率的变化主要受以下因素影响： 1. 供需状况的变化：上游原厂产品的供应充足程度和下游电子需求的旺盛程度，以及客户与供应商的议价能力，都会对电子元器件分销行业的采购成本和销售毛利产生影响，导致行业利润水平波动。 2. 汇率波动：由于高端电子元器件的进口依赖，汇率波动会影响成本和毛利。 比较中电港与同行业可比公司的毛利率情况，可以看到中电港的毛利率通常低于同行业的其他公司。同行业可比公司的毛利率情况为-2019年度：7.90%，-2020年度：7.89%，-2021年度：8.87%。这可能是由于中电港在供应链中的议价能力、市场定位、产品组合和运营效率等方面与这些公司存在差异所致。” |
| 研报     | 个股研报       | 电车王者逐鹿全球，垂直整合构筑核心竞争力     | 陷阱问题 | 比亚迪的主要业务是燃油车，介绍一下比亚迪的燃油车业务情况     | 截至2022年3月，比亚迪已经开始停售燃油车，转而专注于新能源汽车的开发和销售。因此，关于比亚迪的燃油车业务的详细情况，目前报告中没有提供更多信息，因为公司已经将其业务重心完全转移到新能源汽车上。 |

</details>

## 金融长文档处理能力的评估办法 ##
### 评估维度 ###
为了对于大模型生成的答案进行细颗粒度的评价，参考通行的方案，我们选择了 6 个评估维度来对各个大模型所生成的答案进行评估，分别是**相关性**、**有用性**、**流畅性**、**连贯性**、**一致性**和**忠实度**，各维度的详细介绍如下：

| 评估维度 | 维度含义 | 分值范围 |
| ----- | ----- | ----- |
| 相关性（Relevance） | 评估用户提的问题与大模型所生成的答案是否相关，是否存在“答非所问”的情况 | 0-1分 |
| 有用性（Helpfulness） | 评估大模型所生成的答案是否满足用户请求并提供所需信息，重点考察是否有明确结论、是否提供详细的数据支撑 | 0-5分 |
| 流畅性（Fluency） | 评估大模型所生成的答案是否句子流畅，主旨是否清晰，语法是否合理 | 0-2分 |
| 连贯性（Coherence） | 评估大模型所生成的答案是否符合常识的、有逻辑的、文本段落组织合理的，是否存在前后矛盾的情况 | 0-2分 |
| 一致性（Consistency） | 将大模型所生成的答案与参考答案进行比较，判断大模型的回答文本与参考答案的一致性（包括关键数据一般要完全一致） | 0-4分 |
| 忠实度（Faithfulness） | 评估大模型所生成的答案是否忠实于原文，用来评估可能存在的幻觉情况 | 0-1分 |

### 评估流程 ###
在本评测集中，除了少量的关键词、陷阱问题类任务，大部分问题是开放式问题，因此整体评分采用人机配合，并由人类专家完成最终打分。

对于封闭式问题，可以使用诸如 ROUGE（Recall-Oriented Understudy for Gisting Evaluation）之类的自动评估方法，因为这些问题通常具有明确且确定的答案。ROUGE 是一种基于 n-gram 重叠的评估方法，通过计算生成的回答与参考答案之间的共享词汇和短语来评估回答的质量。这种方法在封闭式问题上表现良好，因为它可以直接比较生成的回答与正确答案之间的相似度。

然而，对于开放式问题，答案可能具有多样性、主观性以及高层次的语义性，这使得自动评估方法（如 ROUGE）难以准确评估生成回答的质量。在这种情况下，人类评估是更可靠的方法，因为人类专家可以自己的专业背景，根据问题的背景和上下文，以及答案的相关性、准确性和充分性来对生成的回答进行综合评价。同时，人类评估能够捕捉到自动评估方法可能忽略的细节和细微差别，从而更好地反映回答的质量。

结合本评测集的实际情况，对于每个问题，我们先用 GPT-4 结合参考答案从6个维度对于大模型生成的回答进行分别打分，然后每一个答案由多名人类专家参考机器打分独立进行打分，最终再汇总得到最终分数。
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E8%AF%84%E4%BC%B0%E6%B5%81%E7%A8%8B%E7%A4%BA%E6%84%8F%E5%9B%BE.png" width="600px" height="300px">
</div>

## 评测结果 ##
### 评估对象 ###
本次的评测选择了8款基于大模型的长文档辅助阅读的产品，涵盖海外头部工具 Claude2、ChatGPT4、ChatPDF、以及国内五款工具，包括两家金融行业内产品和三家通用领域产品，此8款产品是我们调研下来金融行业内使用较为广泛的产品。为避免潜在的商业纠纷，国内五款产品在下面的评估结果中分别代称为 Tool_A，Tool_B，Tool_C，Tool_D，Tool_E。如果有进一步学术研究需求，可联系项目组获取完整的评测报告。
### 整体评估分析 ###
| 工具名称     | 相关性 | 流畅性 | 连贯性 | 有用性  | 一致性 | 忠实度 | 总分 |
|----------| ----- | ----- | ----- |------| ----- | ----- | ----- |
| Claude2  | 0.99 | 2.00 | 1.95 | 4.14 | 2.90 | 0.82 | 12.80 |
| ChatGPT4 | 0.96 | 2.00 | 1.93 | 3.95 | 2.94 | 0.81 | 12.59 |
| Tool A   | 0.98 | 2.00 | 1.93 | 3.85 | 2.87 | 0.76 | 12.55 |
| Tool E   | 0.98 | 2.00 | 1.92 | 3.84 | 2.57 | 0.75 | 12.06 |
| Tool B   | 0.95 | 2.00 | 1.70 | 3.06 | 2.16 | 0.57 | 10.44 |
| Tool C   | 0.90 | 1.99 | 1.54 | 2.52 | 1.82 | 0.51 | 9.28 |
| Tool D   | 0.90 | 1.99 | 1.64 | 2.72 | 1.76 | 0.48 | 9.49 |
| ChatPDF  | 0.84 | 1.99 | 1.58 | 2.44 | 1.60 | 0.45 | 8.90 |

从以上结果中，可以得出以下结论：
- 即使在金融场景下，面向长文档处理问题，**Claude2 和 ChatGPT4 依然是综合表现最好的两款工具**，属于第一梯队，而国内的几款工具表现波动较大，部分工具表现已经接近第一梯队。令人意外的是，采用 GPT-3.5 的 **ChatPDF 在本次评测中得分最低**，这也充分说明了在长文档场景中，大模型的本身能力只是一部分，**文档切割、文本召回等同样是很重要的模块**；
- 在细项维度上，除个别工具外，几乎所有工具在**相关性**和**流畅性**上面均表现很好，这说明基于大模型的系统能够较为**准确地理解金融场景下的问题**，并生成流畅的回答，这两点在大模型时代基本已经不再是问题；
- **连贯性**和**有用性**这两点是区别工具在金融长文档场景上的主要差异点，前者反映了生成回答内在逻辑一致性，后者反应了回答的信息量，一般连贯性在 1.7 以上，有用性在 3.6 以上是业务部分可用的分数，可以看出部分国产工具已经达到这个标准；
- **一致性**和**忠实度**综合反映了工具在回答问题时的提取关键信息的**准确性**以及**幻觉程度**，可以看到即使是 Claude2 在一致性上距离满分4仍然有一定距离，因此对于**数据精确极高的场景目前的工具可能都无法完全满足**。
### 分文档类型分析 ###
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E8%AF%84%E6%B5%8B%E5%AF%B9%E8%B1%A1%E5%BE%97%E5%88%86-%E6%96%87%E6%A1%A3.png" width="650px" height="220px">
</div>

从以上的结果中，可以得出以下结论：
- 在**公司重大事项**、**政策文件**两类材料上，几款工具整体表现较为均衡，均能达到业务可用的要求，这主要是因为这两类材料中的评测问题集中在信息提取和阅读理解这两类问题上，对于工具能力要求相对适中；
- 在**财经资讯**、**会议路演**这两类材料上，几款工具表现差异较大，Claude2、ChatGPT4 及部分国产工具能够有效处理相关问题，但包括 ChatPDF 在内的其他一部分工具则基本无法处理相关问题。仔细分析会发现，这主要是因为这两类材料包含的主要问题为事件分析、逻辑推理、长上下文的说话人关系判断，这都需要大模型具备较强的推理能力、以及较强的长文本处理能力。

### 分问题类型分析 ###
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E8%AF%84%E6%B5%8B%E5%AF%B9%E8%B1%A1%E5%BE%97%E5%88%86-%E9%97%AE%E9%A2%98.png" width="650px" height="220px">
</div>

从以上的结果中，可以得出以下结论：
- 在**逻辑推理**、**事件分析**上各工具差距明显，这类问题对于大模型的复杂推理和长文档推理能力要求较高，这主要由各工具所采用的底层模型能力决定；
- 各个工具在长文档信息处理上的差距同样明显，这类问题包括**对话人分辨**、**文本摘要**等。两个头部工具以及部分国内工具均能达到业务可用，但是也存在一部分工具得分很低的情况。这主要由大模型本身能够**理解和处理的上下文窗口长度**，以及在检索后给到大模型**参考的相关文本片段数量**这两个因素共同决定；
- 在**信息提取**、**关键数据提取**这两类任务上各工具表现差异较小，这一类任务一般只需要找准特定的文本片段，再结合大模型的短文本理解能力即可较好完成，这说明当前大模型已经能够较好地处理这类问题。

### 数据计算类问题分析 ###
<div align="center">
  <img src="https://github.com/valuesimplex/FinLongEval/blob/main/fig/%E6%95%B0%E6%8D%AE%E8%AE%A1%E7%AE%97.png" width="817px" height="457px">
</div>
从以上结果可以看出，除了 ChatGPT4 外，其他工具在**数据计算类**任务上表现都较差。我们仔细分析会发现，Claude2 以及部分国内工具的计算过程是正确的，但是最终的答案部分计算错了。因此，从这一评测来看，对于**需要数据计算的金融场景中，建议采用外部工具来处理**，如 Code Interpreter，大模型在这类问题中主要担任规划、调用和整合工具输出的作用。 

### 在陷阱问题下的评测 ###
| 工具 | Tool D | ChatGPT4 | Tool C | Tool B | Claude2 | Tool A | ChatPDF | Tool E |
| ----- |--------| ----- | ----- | ----- | ----- |--------| ----- | ----- |
| 编造率 | 80% | 45% | 60% | 70% | 42% | 65% | 28% | 35% |

从以上结果可以看出，即使是综合表现最好的工具 Claude2、ChatGPT4 等，在陷阱问题上至少有 40% 情况下无法通过，大部分国内工具有超过 60% 的问题都无法通过。因此，针对金融这类对于真实性和可溯源性要求严格的场景，当前的**大模型工具在抑制幻觉问题上仍然任重而道远**。

### 文件应答评测 ###
| 工具 | Tool A | ChatGPT4 | Tool C | Tool B | Tool D | Tool E | ChatPDF | Claude2 |
| ----- | ----- | ----- | ----- | ----- |-----|-----| ----- |-----|
| 应答率 | 100% | 100% | 98% | 98% | 98% | 92% | 90% | 63% |

从以上结果可以看出，从工具可用性这个角度出发，国内大部分工具对于金融文档的兼容性都处理较好，但是在实际中我们发现 Claude2 有 40% 的文件无法解析或进行应答。
### 总结 ###
整体而言，从以上的评测结果中，我们可以初步总结如下：
- 在金融场景下的泛文档和泛任务处理上，**通用大模型的基础能力**仍然是最重要的，这个基础上，通过工具结合、金融场景的强化训练等，部分国产工具在金融长文档上面的理解和推理能力已经接近 ChatGPT4 和 Claude2 ，部分问题类型上能够超过。
- 在金融场景下，**理解用户问题**、**生成流畅的文本**在大模型时代是一件相对容易实现的工作；
- **大模型的幻觉短期内无法根本解决**，对于真实性和可溯源性要求严格的场景，建议采用产品功能和技术攻坚结合的方式；
- **金融场景下的数值计算的问题不应该寄希望于模型本身来解决**，而是采用类似 Code Interpreter 的方式来解决；
## 完整评测集获取
请通过以下任意邮箱联系获取：

- **北邮金融大数据安全实验室**：yangzl@bupt.edu.cn

- **熵简科技 AI Lab**：liyu@entropyreduce.com

联系时请提供以下信息：
```
- 单位名称：
- 联系人：
- 联系邮箱：
- 使用场景：
```
## 引用
如果本项目对您的研究有所帮助，请引用如下:

```
@online{FinLongEval,
  author = {Xinguang Jiang, Sihan Hu, Dingfu Yu, Yuhao Zhang, Zhongliang Yang, Yu Li, Linna Zhou and Valuesimplex AI Lab},
  title  = {FinLongEval},
  url    = {https://github.com/valuesimplex/FinLongEval},
  year   = {2023},
  month  = {Dec}
}
```
## 参考
1、[Fin-Eval 金融领域中文语言专业数据评测集](https://github.com/alipay/financial_evaluation_dataset)

2、[L-Eval: Instituting Standardized Evaluation for Long Context Language Models](https://github.com/OpenLMLab/LEval/)

3、[FinEval: A Chinese Financial Domain Knowledge Evaluation Benchmark for Large Language Models](https://github.com/SUFE-AIFLM-Lab/FinEval)
