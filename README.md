# CMU-Courses-Cool-Down
My learning experience in CMU.

--

### Hardcore:

#### 18-600（15-513） Foundations of Computer Systems：

 -  这门课就是CMU传说中的神课之一（15-513）的ECE版本，使用那本经典的CSAPP作为教材，涵盖了计算机大部分的基础知识，为以后的进阶学习打下基础。关于这个课还有经典的8个lab的描述已经很多，我就不再废话了。 详情可见[小土刀]([https://wdxtub.com/2016/04/16/thin-csapp-0/](https://wdxtub.com/2016/04/16/thin-csapp-0/)
)。

- 在我们这届，ECE和CS的课程还是有些许不同的，因为我们的老师是[John Shen](https://sv.cmu.edu/directory/faculty-and-researchers-directory/faculty-and-researchers/shen.html)，他是做architecture出身，所以ECE版多了八节关于super scalar，多路并发架构的课程，architecture lab作业的编排也做了相应的改变，所以还是有些难度的。

- 这门课的考试也完全没有按照SCS的套路来，感觉考得非常得……发散，会覆盖所有讲到过的知识，所以大家的总体成绩都偏低，两次考试的median都在60分左右，老师和TA们最后只得疯狂地curve成绩。

- 这是我入学的第一门课，也是我觉得非常非常受用的一门课。课程从bit manipulate讲起，依次讲了汇编，寄存器，cpu，底层堆栈，寻址取址，link和编译，内存系统和虚拟内存，malloc，线程与多路并发，网络编程等等，让我恶补了所有在冬青阿姨和刘依阿姨课上睡过去的知识，并且第一次对计算机是如何工作的有了相当清晰的了解。同时，大量的实操经验（尤其是shell lab和malloc lab） 也让我对 c语言有了二次学习的机会，指针的运算简直是人生中的噩梦。
 
- 因为之前基础不好的缘故，这门课对我来说还是非常吃力的，有些其他学校的同学（PKU,SJTU,FDU,NJU）在本科就已经上过这门课了，所以可能会感觉比较简单一些，这也反映了我济在教学方面是真的垃圾，万年不变的教材和老掉牙的知识真的是缺乏竞争力。（如果有可能，真的希望能在本科阶段引进这门课）


--


#### 15-619 Cloud Computing:

- 这门课是CMU传说中workload最大的课程之一（和15-410 Operating System Design and Implementation有的一比）。每周花费在这门课上的工作时长达30+个小时。因为这也是硅谷校区能选的为数不多的“神课”，基本上大家都会选择挑战这门课程。

- 云计算这门课每周有1个project和1个quiz，中间再辅以使用aws cloud9来练习协同编程以及code review，几乎每周都可以过的很“充实”。

- 对于每周的project，简单来说就是会利用aws，gcp和azure三个主流的云服务提供商各种各样的云服务来完成特定的任务。本课从如何使用基本的vm instance开始，到使用yarn cluster，autoscaling，loader balancer，docker & k8s， function as service，database on the lcoud， spark，machine learning on the cloud以及最后的stream processing使用的Kafka和samza，几乎是包罗万象，有容乃大。每一次的project都会让你探索一个全新的领域，然后再完成规定的任务，一个学期上下来的11个project基本会让你走马观花地了解几乎所有aws能够提供的服务并且亲自上手使用这些服务来完成一些特定的task。

- quiz是每周一次，形式有点像阅读理解，会给你很多的阅读材料（非常多），然后每周要读完规定的部分，然后这周的quiz就会考这周阅读材料里面的内容。全部的阅读材料加起来基本上就是讲述了如何构建一个cloud。从最底层的数据中心开始讲起，到虚拟化，云上存储结构和分布式编程以及一些经典的分布式系统的结构（多线程，cassandra，hadoop，spark，Kafka，samza）。让我比较意外得是每部分内容的详尽程度真得是令人发指。例如，在数据中心的讲解过程中，不仅仅讲了如何设计数据中心的网络拓扑和服务器机柜的部署，甚至讲到了如何尽可能得保障数据中心的供电以及降低数据中心的功耗😂。那些一本正经介绍的电路图和变电设置真得让我直接懵逼。
  - 最后也是最精彩的，便是team project了。team project分为三个phase，基本上是要让你设计和实现一个高吞吐量，高可靠性的后端service。 这个project比较妙的地方在于一下几个点：
    - 预算是有限制的，不可以通过暴力地疯狂scale out到很多台机器达到要求的target rps。而且预算有两种限制，一种是在做整个project的时候总体花费不能超过某个特定值（每周的project也都有这个限制），第二种限制就是，当你所有的机器在进行live test的时候，它们的总价值不能超过某个特定值。在这两个的限制下，如何提高单台的rps，如何选择多台机器的协作方式便有了大学问（大坑）。
    - 成绩完全由live test的表现来决定。 所谓的live test，就是会规定一个时间，你提前部署好机器，提交一个dns的地址，助教会在接下来的6个小时内向你提交的dns地址发起丧心病狂的请求。
    - 数据库的设计和调优是关键。因为要求完成的query是非常特定的query（只有读操作），这个时候就要针对这种情况将数据库高度特异化，只针对这一种情况疯狂优化。


- 俗话说的好，在CMU没上过CC是不完整的。本学期在确定了工作以后，我也大胆地选择了这门据说能看到凌晨4点硅谷的课，于是我就差点把自己交代在cc上了😂。我只能说选了CC之后，每周都过的十分充实，尤其是最后三周的team project，我简直是每周必要熬夜两天半，得益于队友的疯狂carry，我们最后取得了不错的成绩。除非对数据库调优或者aws有着丰富的经验，否则建议team project一定要和靠谱的队友组队，不要幻想你能carry，因为一个人真得顶不住。

--

####11-785 Introduction to Deep Learning

TODO

--

#### 18-661（10-661） Introduction to Machine Learning

TODO

--


###Hard:

#### 18-652 Foundations of Software Engineering

TODO

--



#### 14-736 （简单版15-640）Distributed Systems

TODO

--


### Medium:

#### 18-656 Data Intensive Workflow

TODO

--

#### 18-843 Mobile Pervasive Computing

TODO

--

### Easy:

#### 49-801 Enterprise Innovation
TODO

--

#### 49-807 Exponent Innovation

TODO

--


