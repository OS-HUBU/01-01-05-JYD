##### Github 开发者敬业度评估指标

##### 一、问题

 开发者的敬业程度怎么衡量？

##### 二、描述

​		在软件开发领域，开发者的敬业度是一个非常重要的工作表现指标，它不仅反映了开发者对项目的投入程度和对工作的热情，还体现了开发者的职业品质。敬业度高的开发者通常具备积极的态度和高度的责任心，能够积极参与项目讨论、提出建设性意见、及时解决问题和回应反馈等。这些表现体现了他们对技术的热爱、对团队合作的积极参与和对项目的投入程度等优点，使得他们更容易与团队融合并创造出良好的合作效果，从而推动项目的进展并成功完成。

​		在企业招聘优秀的软件开发人才时，开发者的敬业度是非常重要的参考指标。敬业度高的开发者表现出更高的工作热情和责任心，能够推动项目的进展和成功完成，从而提高企业的竞争力。此外，敬业度高的开发者通常具备较强的自我驱动力和学习能力，能够持续学习和适应新的技术和工作方式，有助于他们在工作中不断提高并促进企业的长期发展。因此，考虑开发者的敬业度对企业招聘优秀的软件开发人才和企业的长期发展具有重要的意义。

##### 三、目标

​		当软件开发者的敬业度越高时，也就是说他们在工作中表现得越积极、认真，对工作的投入程度越高，其活跃频率和工作贡献度都会相应地提高。这意味着开发者会更加专注于工作，愿意花费更多的时间和精力来解决问题和创造价值，从而带来更多的成果。

​		同时，高敬业度的开发者通常也表现出更高的自我驱动力和责任心，他们对自己的工作质量有更高的要求，并且愿意主动承担更多的责任和挑战。这种积极的态度和工作风格往往也会对团队的氛围和效率产生积极的影响，带动团队成员共同进步和提高。

​		因此，一个敬业度高的软件开发者通常会表现出更好的工作表现、更高的职业发展潜力和更高的工作满意度，而这些因素也将有助于增强开发者的竞争力和吸引力。

​		通过对开发者敬业度的评估可以帮助招聘者找到更优质、更有潜力的开发者，提高团队的质量和效率。

##### 四、设计思路

​		在软件开发领域中，开发者的敬业度通常与其职业精神和工作态度有关，表现为其对项目的投入程度和对工作的热情。GitHub 作为开发者交流和贡献代码的重要平台，为评估开发者的敬业度提供了一个有力的工具。开发者在 GitHub 上的活跃频率和对项目的贡献量可以很好地反映出他们的工作表现和职业态度。因此我们可以从活跃频率和工作贡献度两个方面来衡量开发者的敬业度。

​		活跃频率是指开发者在一年中活跃的天数占全年天数的比例，其中活跃指任何与项目有关的交互行为，例如提交代码、发起讨论、回复问题等。活跃频率越高，说明开发者在 GitHub 上的活动越频繁，对项目的贡献也越大。

​		工作贡献度是指开发者在 GitHub 上一年的工作贡献量占同行的平均工作贡献量的比例，其中工作贡献量包括发表 issue 的数量、对 issue 进行评论的数量、发起 Pull Request (pr) 的数量、对 pr 进行评论的数量以及提交的 pr 被合并的数量。开发者在这些方面表现出的投入和贡献程度，可以反映出其敬业度的高低。

​		通过综合考虑开发者在活跃频率和工作贡献度方面的表现，将开发者的活跃频率和工作贡献度两个指标相乘得到一个综合的开发者敬业度指标，该指标可以为企业招聘优秀人才提供参考依据，帮助企业识别优秀的开发者。

##### 五、实现

###### 1. 开发者敬业度评估指标模型

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%875.png)

其中，LY 表示开发者的敬业度，WA 表示软件开发者一年中活跃天数占全年天数的比例（每日活跃频率），WC 表示软件开发者在一年中的工作贡献量占其同行的平均贡献量的比例（工作贡献度），AD 表示软件开发者在一年内活跃的天数，WL 表示软件开发者在 GitHub 上一年的工作贡献量，包括 issue_comment、open_issue、open_pr、review_comment和pr_merged 的数量。AVG (WL) 表示同行的平均工作贡献量，即所有软件开发者在 GitHub 上的工作贡献量的平均值。

###### 2. 评估函数的计算方式与合理性分

为了更好地评估和比较不同开发者之间的敬业度表现，我们可以通过分析317348个开发者的敬业度指标值的分布情况，设计分段函数以打分的形式评估每个开发者的敬业度。通过这样的分段函数设计，可以将每个开发者的敬业度指标值映射到相应的分段，并为每个开发者赋予相应的得分，从而更直观地反映开发者的敬业度表现。这种评估方式综合考虑了敬业度指标值的分布情况，并根据不同分段赋予不同得分，以便更全面、客观地评估每个开发者的敬业度水平。

根据对 317348 个开发者的敬业度数据进行分析，我们获得了下表所示的统计数据。根据这些数据，我们可以设计一个分段函数来评估每个开发者的敬业度水平。

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%876.png)

上表中的第一列是开发者敬业度指标值，第二列是敬业度指标值为相应数值的开发者总人数，第三列是敬业度指标值为相应数值的开发者人数占总开发者人数的百分比，第五列是开发者敬业度指标值小于等于第一列对应指标值的开发者人数占总开发者人数的百分比。

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%877.png)

上图反映了开发者敬业度的分布情况。敬业度为 0 的开发者人数最多，达到 204016 人，占所有开发者数量的 64.3%。这说明敬业度为 0 的情况是普遍存在的，需要引起关注，给予 0 分。敬业度在 0-0.02 之间的开发者数量较少，占比 17.8%，这部分开发者相对较优秀，但仍有提升空间，给予 20 分。敬业度在 0.02-0.15 之间的开发者有 25552 人，占比 8%，这部分开发者已经很优秀了，给予 50 分。敬业度在 0.15-0.5 之间的开发者有 9632 人，占比 3.1%，给予 60 分。敬业度在 0.5-1.5 之间的开发者有 8921人，占比 2.8%，这些开发者的敬业度值较高，人数相对较少，给予 70 分。敬业度大于 1.5 的开发者不足 3%，占比非常小，说明这部分开发者的敬业度相对极其高了，所以区间定为 1.5-4、4-8.7、8.7-16.8、16.8-29.2，相应的分数为 80 分、85 分、90 分、95 分。随着敬业度值的增加，相应的开发者人数逐渐减少。在敬业度为 29.2 时，开发者敬业度已经达到峰值了，敬业度大于等于 29.2 的开发者人数只有 158 人，因此可以给予满分 100 分的评价。

具体分段函数的表达式如下图所示：

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%878.png)

###### 3. 举例说明

假设一个软件开发者在过去一年中，共参与了 200 天的开发工作，GitHub 上的工作总量（包括issue_comment、open_issue、open_pr、review_comment 和 pr_merged 的数量）为 1000。同行平均工作量为 500。

则该开发者的活跃频率WA可以通过以下公式计算：
$$
WA=\frac{AD}{365}=\frac{200}{365}=0.548
$$
该开发者的工作贡献度WC可以通过以下公式计算：
$$
WC=\frac{WL}{AVG(WL)}=\frac{1000}{500}=2
$$

最终，该开发者的敬业度LY可以通过以下公式计算：
$$
LY=WA\times WC=0.548\times2=1.096
$$
因此，该开发者的敬业度为 1.096，对应的分值为 70 分，表示其表现出了比较高的活跃频率和工作贡献度，对工作表现非常认真和积极。

##### 六、数据来源及处理

以 2020 年一年的 Github 全域日志数据为例，数据库中开发者总共产生了 109 G 的数据，其中有仓库的开发者人数共有 30 多万个。在实验中我们总共利用了这 30 多万开发者产生的日志数据，其中我们获取到了这 30 多万开发者的六类指标数据分别为：

-   获取每个开发者活跃天数 AD (GitHub)

    > **具体操作：**根据给定的数据日志表(events表)中的 create_at 字段，提取其中的年月日信息，并以开发者姓名和时间字段为条件对表中数据进行去重，去重后每个开发者在某一天只会保留一条数据，表示这个开发者在这天活跃了。为了进一步统计开发者的活跃天数，将表中数据以时间字段的单个月为条件，接着以开发者名分组，统计每组数据的条数，得出每个月开发者的活跃天数。最后将每个月的活跃天数相加，得出整年的活跃天数。

-   获取每个开发者发表 issue 的数量 (open_issue)

    > **具体操作**：根据给定的数据日志表(events表)中的 type 字段，筛选出所有类型为 "Issueevent" 的事件，接着按照开发者分组统计每个开发者发表的 issue 事件的数量。最终得到的结果即为每个开发者发表的 issue 事件的数量。

-   获取每个开发者针对 issue 评论的数量 (issue_comment)

    > **具体操作**：根据给定的数据日志表(events表)中的 type 字段，筛选出所有类型为 "IssueCommentEvent" 的事件，接着按照开发者分组统计每个开发者 issue 评论事件的数量。最终得到的结果即为每个开发者针对issue 评论事件的数量。

-   获取每个开发者为项目提交 pr 的数量 (open_pr)

    > **具体操作**：根据给定的数据日志表(events表)中的 type 字段，筛选出所有类型为 "PullRequestEvent" 的事件，接着按照开发者分组统计每个开发者为项目提交 pr 事件的数量。最终得到的结果即为每个开发者为项目提交 pr 事件的数量。

-   获取每个开发者对项目中的 pr 进行评论的数量 (review_comment)

    > **具体操作**：根据给定的数据日志表(events表)中的type字段，筛选出所有类型为 "PullRequestReviewCommentEvent" 的事件，接着按照开发者分组统计每个开发者对项目中的 pr 进行评论事件的数量。最终得到的结果即为每个开发者对项目中的 pr 进行评论事件的数量。

-   获取每个开发者代码合并的数量 (pr_merged)

    > **具体操作**：根据给定的数据日志表(events表)中的 type 字段，过滤出类型为 "PullRequestEvent" 的事件，并通过 "pull_merged = 1" 筛选出已合并的 PR ,接着按 actor_login 分组，使用聚合函数 COUNT (actor_login) 统计每个用户合并的 PR 数量。最终得到的结果即为每个开发者合并了多少个 Pull Request (PR) 的数量。

将这六类指标值以及对应的开发者合并进一张新的数据库表中，然后通过上述计算公式最终得出这 30 多万开发者各自的敬业度指标值。

**数据日志表(events表)：**

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%879.png)

##### 七、Github 开发者敬业度分析与可视化

###### 1. 开发者敬业度指标计算与评估分析

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%8710.png)

上图反映了开发者敬业度的分布情况。敬业度为 0 的开发者人数最多，达到 204016 人，占所有开发者数量的 64.3%。这说明敬业度为 0 的情况是普遍存在的，需要引起关注。敬业度在 0-0.02 之间的开发者数量较少，占比 17.8%，这部分开发者相对较优秀，但仍有提升空间。敬业度在 0.02-0.15 之间的开发者有 25552 人，占比 8%，这部分开发者已经很优秀了；敬业度在 0.15-0.5 之间的开发者有 9632 人，占比 3.1%；敬业度在 0.5-1.5 之间的开发者有 8921 人，占比 2.8%。这些开发者的敬业度值较高，人数相对较少。同时，敬业度小于等于4的开发者占据了总开发者人数的 98.7%，敬业度大于 4 的开发者不足 2%。因此，随着敬业度值的增加，相应的开发者人数逐渐减少。在敬业度为 29.2 时，开发者敬业度已经达到峰值了，人数只有 158人。

###### 2. 开发者敬业度可视化

- 敬业度排名表

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%871.png)

上表中的第一列是开发者敬业度排名，第二列是相对应的开发者姓名，第三列是敬业度指标值，此图总体反应出每个开发者敬业度排名以及它的敬业度是多少。并且此图数据是使用 GitHub 2020 年全年开发者产生的数据，通过指标模型计算得到的，具有一定的严谨性。

- 每段活跃天数及对应的开发者人数柱状图

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%872.png)

上图中横坐标表示的是分段后的活跃天数，分别为 0-30 天，30-60 天等等，纵坐标表示的是开发者人数。此图总体反应出每个活跃天数段及此段对应的开发者人数有多少。

- 开发者敬业程度饼状图

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%873.png)

上图中共有 3 个部分每个部分代表着一种开发者的敬业程度，这个敬业程度是跟具开发者的最终敬业度评分来划分的，0-50 分，50-80 分，80-100 分三个等级分别为低，中，高。因此该图代表的是每种敬业程度开发者人数占全体开发者人数的比例。

- 开发者活跃天数排名表

![](https://github.com/OS-HUBU/JYD/raw/main/images/%E5%9B%BE%E7%89%874.png)

上表中的第一列是开发者活跃天数排名，第二列是相对应的开发者姓名，第三列是活跃天数指标值，此图总体反应出每个开发者活跃天数排名以及它的活跃天数是多少。

##### 参考资料

1. 开源软件项目定性和定量分析指标——chaoss 指标解析

[https://chaoss.community/kb-metrics-and-metrics-models/](#_引用)

2. 在线一体化产品设计协作平台——墨刀

[https://modao.cc/app/design/pblfnou5vjc2jx96#builtin_chart_collapse](#_引用)

3. 文献引用：

基于混合神经网络的开源社区软件开发者人力资源价值预测_汤佳杰

##### 合作者

•张子璇

•李龙飞

 # JYD
敬业度文档
