# 硬核

----

#### 18-600（15-513） Foundations of Computer Systems


- Intro:

 	> 这门课就是CMU传说中的神课之一（15-513）的ECE版本，使用那本经典的CSAPP作为教材，涵盖了计算机大部分的基础知识，为以后的进阶学习打下基础。关于这个课还有经典的8个lab的描述已经很多，我就不再废话了。 详情可见[小土刀](https://wdxtub.com/2016/04/16/thin-csapp-0/)。
	> 在我们这届，ECE和CS的课程还是有些许不同的，因为我们的老师是[John Shen](https://sv.cmu.edu/directory/faculty-and-researchers-directory/faculty-and-researchers/shen.html)，他是做architecture出身，所以ECE版多了八节关于super scalar，多路并发架构的课程，architecture lab作业的编排也做了相应的改变，所以还是有些难度的。

- Content:
	> 这是我入学的第一门课，也是我觉得非常非常受用的一门课。课程从`0101`的bit manipulate讲起，依次讲了汇编，寄存器，cpu，底层堆栈，寻址取址，link和编译，计算机架构与super scalar，内存系统和虚拟内存，malloc，线程与多路并发，网络编程等等。让我恶补了所有在冬青阿姨和刘依阿姨课上睡过去的知识，并且第一次对计算机是如何工作的有了相当清晰的了解。同时，大量的实操经验（尤其是shell lab和malloc lab） 也让我对 c 语言有了二次学习的机会，指针的运算简直是人生中的噩梦。

- Workload:
	> 每周大概需要20+小时，特定的lab（malloc）时期可能需要超过30+。对于基础好或者之前有过经验的同学可能会相应的少一些。

- Grade:
	> 老师给分非常大方，尽管因为考试完全没有按照SCS的套路来，考得非常得发散以至于两次考试的median都在60分左右，老师和TA们最后也会疯狂地curve成绩，给出不错的分数。
- Personal thought:
	> 因为之前基础不好的缘故，这门课对我来说还是非常吃力的，有些其他学校的同学（PKU,SJTU,FDU,NJU）在本科就已经上过这门课了，所以可能会感觉比较简单一些。这也反映了我济在教学方面是真的垃圾，万年不变的教材和老掉牙的知识真的是缺乏竞争力。如果有可能，真的希望能在本科阶段引进这门课，让大家至少在面试的时候能够回答的出类似“线程与进程有什么不同”这类的ABC问题。


----


#### 15-619 Cloud Computing :


- Intro:

 	> 这门课是CMU传说中workload最大的课程之一（和15-410 Operating System Design and Implementation有的一比）。每周花费在这门课上的工作时长达30+个小时。因为这也是硅谷校区能选的为数不多的“神课”，基本上大家都会选择挑战这门课程。这门课每周有1个project和quiz，中间再辅以使用aws cloud9来练习协同编程以及code review，所以几乎每周都可以过的很“充实”。

- Content:
	> 课程内容丰富到可以分为三个部分，一部分是每周一次的Quiz，还有一部分是每周一次的project，最后是一个team project。
	
	> Quiz的形式有点像阅读理解，会给你非常多的阅读材料，每周要读完规定的部分，quiz就会考这里面的内容。全部的阅读材料加起来基本上就是讲述了如何构建一个cloud。从最底层的数据中心开始讲起，到虚拟化，云上存储结构和分布式编程以及一些经典的分布式系统的结构（多线程，cassandra，hadoop，spark，Kafka，samza）。让我比较意外得是每部分内容的详尽程度真得是令人发指。例如，在数据中心的讲解过程中，不仅仅讲了如何设计数据中心的网络拓扑和服务器机柜的部署，甚至讲到了如何尽可能得保障数据中心的供电以及降低数据中心的功耗。那些一本正经介绍的电路图和变电设置真得让我直接懵逼。
	
	> 每周的project，简单来说就是会利用aws，gcp和azure三个主流的云服务提供商各种各样的云服务来完成特定的任务。本课从如何使用基本的vm instance开始，到yarn cluster，autoscaling，loader balancer，docker & k8s， function as service，database on the lcoud， spark，machine learning on the cloud以及最后的stream processing使用的Kafka和samza，几乎是包罗万象，有容乃大。每一次的project都会让你探索一个全新的领域，然后再完成规定的任务，一个学期上下来的11个project基本会让你走马观花地了解几乎所有aws主流的服务并且亲自上手使用这些服务来完成一些特定的task。

	> 最后也是最精彩的，便是team project了。team project分为三个phase，基本上是要让你设计和实现一个高吞吐量，高可靠性的后端service。 这个project比较妙的地方在于一下几个点：1. 预算是有限制的，不可以通过暴力地疯狂scale out到很多台机器达到要求的target rps。而且预算有两种限制，一种是在做整个project的时候总体花费不能超过某个特定值（每周的project也都有这个限制），第二种限制就是，当你所有的机器在进行live test的时候，它们的总价值不能超过某个特定值。在这两个的限制下，如何提高单台的rps，如何选择多台机器的协作方式便有了大学问（大坑）。2.成绩完全由live test的表现来决定。 所谓的live test，就是会规定一个时间，你提前部署好机器，提交一个dns的地址，助教会在接下来的6个小时内向你提交的dns地址发起丧心病狂的请求。3.数据库的设计和调优是关键。因为要求完成的query是非常特定的query（只有读操作），这个时候就要针对这种情况将数据库高度特异化，只针对这一种情况疯狂优化。

- Workload:
	> 平均下来每周大概需要30+小时，最后的team project简直是彻夜不眠，几乎每周都需要熬夜两到三次。

- Grade:
	> 老师给分非常大方，认认真真完成每周的quiz，project以及最后的team project的话基本都是A。
	
- Personal thought:
	> 俗话说的好，在CMU没上过CC是不完整的。本学期在确定了工作以后，我也大胆地选择了这门据说能看到凌晨4点硅谷的课。每周的quiz让我对cloud computing这个概念有相当透彻的了解。project则是能够大大提升使用aws，gcp以及azure的能力。难怪大家都说cc写在简历上会很好看，cc课上做的project感觉就能填充满整页的简历。最后的team project虽然踩了n多的坑，也经历了各种的绝望时刻，但是最后还是靠着队友的carry存活了下来，也对数据库和架构的设计调优之类的又了更深刻的了解。
	
	> 总体来说这是一门值得上的课，尤其是对以后工作中可能需要接触云计算的人来说，这门课应该能让你轻松地在同事中脱颖而出。
	

----

#### 11-785 Introduction to Deep Learning


- Intro:

 	> 通过这门课的名字就可以得知该课的火热程度，在AI火热的今天，deep learning当仁不让成为了相当热门的课程。这门课的老师Bhiksha在第一节课就放大招劝退，“this course is not for chicken”，并且声称如果能够拿到B以上就可以在工业界胜任DL的工作（然而感觉master连找都不可能找到DL的工作）。

- Content:
	> 课程安排和上面的cloud computing有些类似，每周一次的quiz，然后四个individual project以及最后的final project。本课选用或者说是推荐的深度学习框架是pytorch。感觉随着pytorch在学界近乎垄断的地位，以后工业界也可能要不断地向其倾斜，有可能威胁到tf在工业界的地位。
	
	> 每周的quiz考的应该是本周讲课的内容，然而因为每周的内容容量真的是巨大，所以会有很多slides上的内容并不能在课上cover，只好在做quiz之前把slides仔仔细细看完。本课会从简单多层的神经网络讲起，然后到梯度下降和反向传播，optimizer，BN和learning rate，CNN，RNN，LSTM，CTC，Attention，Boltzmann机，强化学习，迁移学习以及Q learning等等比较前沿的概念。由于这个学期的后半段我忙于找工作，所以其实理论知识没有学的太好，从Attention之后的内容基本上是没有听，有些可惜。
	
	> 该课所有的project都是分成两部分，一部分在auto lab上进行，另一部分则在kaggle上的举行。这样导致的结果就是peer pressure空前的巨大，每次都会变成leader board上前面几名的神仙打架。而且本来说好的baseline也会根据大家的表现动态地改变，所以不到最后一刻，你永远不知道你到底能得到多少分。还有就是总共只提供150刀的aws coupon（折算成p2.xlarge的话大概就167个小时），根本不够用。到了最后只能变成氪金游戏，自掏腰包“炼丹”。
	
	> 最后是team project，随意选择做有意思的深度学习项目或者参加复现当年最新的ICLR paper的挑战。


- Workload:
	> 这个课的workload也是鬼畜级别的高，我个人每周要花超过30+小时，如果算上整晚整晚训练的时间的话会更长。

- Grade:
	> 这课虽然我拿到了A，但是必须老实说一句是多亏了team project得到了Carlee小姐姐的关照，要不然以我们复现的水平，在team project上拿到高分基本上是不可能的。
	
	
- Personal thought:
	> 本课虽然写着intro to DL，但是没有一定基础的话感觉上这门课程会非常的吃力，因为总有一些大佬还要选这种intro课程来鱼塘炸鱼，而该课的成绩又有点取决于自己同学的成绩。最后我觉得还是尽量自备GPU来上这门课好了，这样你至少不用每天在那里斤斤计较自己的余额到底还够不够用。
	
	> 总之这门课对于非常想了解DL这目前最炙手可热的领域的人来讲上一下还是挺有意思的，虽然我上下来的感觉就是真真正正的**“炼丹”**。真的是一切都是玄学一切都是黑盒。因为课程还处于初期阶段，难免有些地方会有些不合理之处。比如我觉得就应该规定训练的budget上限，并且大家都要使用统一的平台，例如aws来进行训练。防止有些人在那氪金training而有些人却只能开一台小水管的现象发生。



----

#### 18-661（10-661） Introduction to Machine Learning

- Intro:

 	> 这是ECE第一次开设这门课程，由SV和Pitts两个老师来教，基本上是10-661的翻版，但反而难度更高。可能因为是第一次开课的缘故，[Carlee](https://sv.cmu.edu/directory/faculty-and-researchers-directory/faculty-and-researchers/joe-wong.html)老师明显高估了我们的水平，尤其是数学水平。当然也有可能因为在普林斯顿应用数学专业直博的Carlee老师眼里，这些可能就是1+1的问题吧😂。导致一开始看到遍布slides的数学公式，真的是一个头两个大，明显跟不上老师的节奏。后来老师调整了难度之后虽然稍微好了一些，但是感觉Pitts那边的老师讲课实在是不太上心，加上自己那段时间找工作找的慌慌张张的，最后学的确实不太好。

- Content:
	> 课程从MLE，MAP讲起，然后就是各种回归，贝叶斯，SVM，k近邻，decision tree，boosting，聚类，EM，NN，PCA以及最后的强化学习。可以说基本覆盖了所有常见的内容。
	
	> 有6次assignment和两次考试，assignment既有考数学推导的部分也有实际的编程实操，所以其实花费的时间还是不少的。

- Workload:
	> 本身的workload可能不算特别大，但是因为我的数学基础真的只能算是一般般，所以每次的assignment做起来真的很费力，要和同学请教好久才能写完。每周花的时间也超过了20小时。

- Grade:
	> 虽然老师还是很大方的给了个B，但是考了62的我比median分数都差了不少。
	
- Personal thought:
	> 本课应该创下了我学生生涯考试的最低分数吧，真的是我最受打击的一门课程，不仅仅考试考的低，而且发现自己是确确实实学不会。直到最后复习的时候，我才慢慢地有些感悟到，这些机器学习方法都是通过定义和假设得出一个目标函数，然后通过各种变形和方法（简单的变换求导，拉格朗日对偶之类），最后变成可以使用MLE或者MAP求得最优解的过程。也就是有点所谓的求解“凸优化”过程吧。这门课也打消了我最后一点点想做科研的想法，我觉得如果没有过硬的数学功底就投入到轰轰烈烈的AI大潮中去，最终也只能沦为调参工程师而已。

----