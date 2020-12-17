

![](https://picreso.oss-cn-beijing.aliyuncs.com/blockchain.png)

<div align = "center">

# Baby-BlockChain👶

From baby to learn and build a Blockchain in Java🌈

</div>

## 大纲

+ 理论部分

	1. 快速理解
	2. 深入技术

> 快速学习区块链，理解和掌握区块链相关知识。

+ 实践部分
  1. 基础区块链
  2. 扩展区块链

> 简单用Java实现一个区块链。

## 理论部分

### 定义

区块链本质上是一个**去中心化**的**分布式账本数据库**。

其本身是一串使用密码学相关联所产生的数据块，每一个数据块中包含了多次比特币网络交易有效确认的信息。 

这是区块链的定义，因此要逐步了解区块链，我们需要一步步了解如下东西。

### 快速理解

#### **去中心化**

先来考虑一个中心化集中式处理的过程。

你要在淘宝上买一部手机，交易流程是：

你将钱打给支付宝－支付宝收款后通知卖家发货－卖家发货－你确认收货－支付宝把钱打给卖家。

![](https://picreso.oss-cn-beijing.aliyuncs.com/mayun.png)

在这个过程中，虽然你是在和卖家交易，但是这笔交易还牵扯到了除了你和卖家的第三方，即支付宝，你和卖家的交易都是围绕支付宝展开。

因此，如果支付宝系统出了问题便会造成这笔交易的失败，并且虽然你只是简单的买了一个手机，但是你和卖家都要向第三方提供多余的信息。

因此考虑极端情况，如果支付宝跑路了或者是拿了钱不却不承认你的交易或者是支付宝所在的城市因为开G20把所有人都赶走了，那么你就悲剧了。

而去中心化的处理方式就要显得简单很多，你只需要和卖家交换钱和手机，然后双方都声称完成了这笔交易，就OK了。

可以看出在某些特定情况下，去中心化的处理方式会更便捷，同时也无须担心自己的与交易无关的信息泄漏。

其实如果只考虑两个人的交易并不能把去中心化的好处完全展示出来，设想如果有成千上万笔交易在进行，去中心化的处理方式会节约很多资源，使得整个交易自主化、简单化，并且排除了被中心化代理控制的风险。

去中心化是区块链技术的颠覆性特点，它无需中心化代理，实现了一种点对点的直接交互，使得高效率、大规模、无中心化代理的信息交互方式成为了现实。

当然，上述的例子有一个很大的潜在问题：没有了权威的中心化代理，怎样保证每笔交易的准确性和有效性呢？比如：如果没有了权威的中心化代理，张三某一天借了我100块钱，但是不还钱还不承认怎么办？这里就引出了区块链的其它特性。

#### **两个基础难题**

在去中心化以后，整个系统中没有了权威的中心化代理，信息的可信度和准确性便会面临问题。

#### 问题1：类两军问题

![](https://picreso.oss-cn-beijing.aliyuncs.com/tcp.png)

第一次听说这个问题居然是在TCP的课上，大致说的是有两个相距很远的军队要传递信息，红军派遣一个信使去跟蓝军说：“你他娘的把意大利炮拿出来！”。蓝军收到信息后又派了一个信使去红军说：“收到指令！”。然后红军又派一个信使去蓝军说：“知道你收到指令了！”。然后蓝军又派一个信使去红军说：“知道你知道我收到指令了！”。然后红军又派一个信使去蓝军说：“知道你知道我知道你收到指令了！”……然后就没完没了了。

在分布式计算中在异步系统和不可靠的通道上达到一致性是不可能的在这种情况下，因为是点对点的通信，双方不可能在这种情况下达到信息的一致性。严谨一点，就是“在分布式计算上，试图在异步系统和不可靠的通道上达到一致性是不可能的”。



#### 问题2：拜占庭将军问题

拜占庭罗马帝国在军事行动中，采取将军投票的策略来决定是进攻还是撤退，也就是说如果多数人决定进攻，就上去干。但是军队中如果有奸细（比如将军已经反水故意乱投票，或者传令官叛变擅自修改军令），那怎么保证最后投票的结果真正反映了忠诚的将军的意愿呢？



拜占庭将军问题反映到信息交换领域中来，可以理解为在一个去中心的系统中，有一些节点是坏掉的，它们可能向外界广播错误的信息或者不广播信息，在这种情况下如何验证数据传输的准确性。



#### **区块链技术的诞生**

现在让我们来一步一步在去中心化的系统中解决这些问题，见证区块链技术雏形的诞生。

我们先来建立一个去中心化的系统，为了方便理解，我们来看一个简单的去中心化借贷模型：

如果A借了B 100块钱，这个时候，A在人群中大喊“我是A，我借给了B 100块钱！”，B也在人群中大喊“我是B，A借给了我100块钱！”，此时路人甲乙丙丁都听到了这些消息，因此所有人都在心中默默记下了“A借给了B100块钱”。

你看，这个时候一个去中心化的系统就建立起来了，这个系统中不需要银行，也不需要借贷协议和收据，严格来说，甚至不需要人与人长久的信任关系（比如B突然又改口说“我不欠A钱！”，这个时候人民群众就会站出来说“不对，我的小本本上记录了你某天借了A100块钱！”）。

![](https://picreso.oss-cn-beijing.aliyuncs.com/money.png)



可能你已经发现了，在上述的模型中，所谓的“100块钱”已经不重要了。换句话说，任何东西都可以在这个模型中交换，甚至你可以凭空杜撰一个东西，只要大家承认，你就可以让你杜撰的东西流通。比如：我在人群中高喊一声“我创造了10个查克拉！”，我甚至不需要知道查克拉是什么，也不需要关心世界上是不是真的有查克拉，只要大家都听到，然后在自己的小本本上记下“LXZ有10个查克拉”，于是我就真的有100个查克拉了。从此以后，我便可以声称我给了某人1个查克拉，只要路人甲乙丙丁都收到并且承认了这一信息，那我就算完成了这次交易，哪怕世界上没有查克拉。



你现在脑海中是不是浮现出了三个字——“比特币”？由于真正的区块链和比特币比我上述的模型复杂太多，细节也丰富太多，因此以下还是以查克拉举例



假设过了很长一段时间，我凭空创造的查克拉已经在这个系统中流通了起来，大家都开始认可了查克拉。但是这个系统中一共就只有10个查克拉，于是有人动了坏心思，他在人群中高呼“我有10个查克拉！”怎么办？大家是直接在本本上记下他有10个查克拉么，这样不是人人都可以伪造查克拉了么？



为了防止这种现象发生，我决定在我创造查克拉的时候给我的查克拉打上标记（更准确地说，我是给我喊的那句“我创造了10个查克拉”打上标记，比如标记为001），这样以后在每一笔交易的时候，我在高喊“我给了某某1个查克拉！”的时候，会附加上额外的一句话：“这1个查克拉的来源是记为001的那条记录，我的这句话标记为002！”。我们再抽象一点，某人喊话的内容的格式就变成了：“这句话编号xxx，上一句话的编号是yyy，我给了某某1个查克拉！”，这样就解决了伪造的问题。其实上述模型就变成一个简化的中本聪第一版比特币区块链协议：

![](https://picreso.oss-cn-beijing.aliyuncs.com/model.png)

好了，看到这里你基本已经能够生动形象又不涉及任何细节地向你的弱智室友解释区块链了



#### “凭啥？”

你室友可能会问：“凭啥你喊一句话我就帮你记？我的小本本不要钱么？”。为了激励大家帮我传话和记账，我决定给第一个听到我喊话并且记录在小本本上的人一些奖励：第一个听到我喊话并记录下来的人，你就凭空得到了1个查克拉，这个查克拉是整个系统对你幸苦记账的报酬，而你记录了这句话之后，要马上告诉其它人你已经记录好了，让别人放弃继续记录这句话，并给你自己的记录编号让别人有据可查，然后你再把我的话加上你的记录编号一起喊出来，供下一个人记账。

当这个规则定下以后，这个系统中一定会出现一批人，他们开始竖着耳朵监听周围发出的声音，以抢占第一个记账的权利。对的，你脑海中是不是又浮现出了“比特币挖矿”的字眼？

值得一提的是，关于比特币挖矿

单身汪们要找女票，国民岳母说我有好多女儿，这样吧我给你们出点题目，解出一个就给其中一个姑娘的微信号。

单身汪们疯狂竞争，想破脑袋去解题。只要其中一只汪解出一道题，就立马得意洋洋地昭告天下，示威全部单身汪，这个姑娘是我的啦，你们放弃吧。其他单身汪们即使不服也没有办法，惆怅懊恼也不是个事儿啊，还是麻溜地立马去解下一道题目吧。这只喜赢姑娘的幸运小汪被岳母认可后还能得到25个货币单位的彩礼，简直人生赢家。

#### “听谁的？”

在这个系统中，如果我和另一个人C几乎同时地喊出一句：“为了艾泽拉斯！”。由于听众所处的位置不同，一定会有人先听到我说的那句话，而另外一些人则先听到C的那句话，如果我们规定只能有一个人说出这句话，那到底这句话是谁说的？

如果不加任何条件，那么上述的情况一定会这样发展：一部分人认为这句话是我说的，在听到这句话之后开始记账，之后他们所做的所有事情都是基于这个事实，并且随着这个信息一次次的传下去，这条信息链会越来越深；而另外一群认为是C先说这句话的人，也会按照这样的趋势发展。这样，原本是一条唯一的信息链，在我们喊出“为了艾泽拉斯”这句话之后，分叉了！？

![](https://picreso.oss-cn-beijing.aliyuncs.com/2way.png)

这会导致怎样的情况呢？按照我们的设想，应该每个人的小本本上记录的东西都是一样的，都是一条可以把所有信息串联起来的链条。但是在这一刻，他们小本本上记录的东西不一样了！这还玩毛啊？以后还怎么确定交易和信息的真实性！？

为了解决这个问题，我又追加了新的规则：每个人在记录小本本的时候，需要脱鞋然后用脚拿笔，在小本本上用正楷体书写！有了这个规定，由于用脚写字难度很大，每个人至少需要10分钟才能写完，而且由于每个人用脚写字的熟练度不通，写完这句话所用的时间也不同，因此一定会有人先写完然后高呼“我写完了！那句话是XXX喊的！”，这样其它正在写这句话的人便会停笔，然后在小本本上重新开始写“那句话是来文写的，上一句的编号是xxx”。

如果你对上述我的解决方法感兴趣，你可以对照我上面的比喻去了解以下知识：

“听谁的”——中本聪破解“拜占庭将军问题”的算法

“在小本本上记录”——比特币挖矿

“脱鞋用脚写字”——比特币挖矿难度

“脱鞋写字速度”——算力

“新的规则”——工作量证明链



## 实践部分



## TODO:

- [ ] 理论部分:
  - [x] 基础
  - [ ] 深入
- [ ] 实践部分

## Reference

1. 知乎：[汪乐-LaiW3n](https://www.zhihu.com/question/37290469/answer/107612456)
