# 浅谈不确定性原理与傅里叶变换

晚上好！我是李宇轩，微电子学院大二本科生。首先非常感谢数学讲坛社团这边能给到我这样一次上台的机会，我也是之前无意中看到了数学讲坛的海报宣传，非常仰慕这样一种学术氛围。然后呢也很感谢各位同学能在周五晚上这个时间，愿意过来听我做这个分享。我之前问社团的负责人它们活动通常会有多少人，他们说，少则十人，多则几十人。那我想，我这要是能有五个人来听，算是很成功了。没想到会有这么多人，还是很开心的，很感谢大家的支持。

那我今天要讲的题目，浅谈傅里叶变换与不确定性原理。内容不会很深啊，因为是这样，我的专业呢，量子力学不算是一门核心的专业课，它是作为一个从普通物理到半导体物理间必要的过渡，就，必须要补充的物理知识。我们那门课是叫量子力学与固体物理基础，量子力学总共只上了三个半星期，折下来大概值2学分。所以呢，其实，我的量子力学功底是绝对没办法和物理系那些上了量子力学1,2总共12学分课程的同学比的。今天我来讲这个也是非常不自量力啊，“不要自学量子力学”。

之前我说可以保证让大一理工方向的同学都能听的懂，因为比这更难的东西我也确实不会了。那我想达成什么呢？我觉得呢，作为一个对量子力学浅尝辄止的学生，我和大部分普通人一样，在量子力学上都是外行。所以，我希望呢，以一个非物理专业学生的视角，告诉大家，如何凭借我们现有的数学物理基础，找到一条清晰的逻辑链，能让我们对量子力学的基本图景有一个大致的了解，能让我们觉得量子力学并不是一件非常神秘的事情，而是像经典力学一样的真实和自然。

除此之外，在这个探索的过程中，我会充分的联系和调动我们已有的课内知识，微积分，大学物理，让大家尽量不要有一种割裂感。同时，也让我们能对课内知识产生更深刻的理解，觉得，嗯，我们课内学的这些东西其实是很有意思很有价值的。

当然，受限于我的专业水平，我想今天分享中，难免还是会有许多认识不够准确不够深刻的地方，还请各位批评指正。

好吧，那我前面就说这些。今天这个题目我会先大致分为两部分，先讲物理部分，从大学物理3的德布罗意关系式出发，讨论波粒二象性的诠释，引出波函数的概念。再讲数学部分，从微积分3的傅里叶级数出发，引出傅里叶变换的概念。最后呢将这两者结合在一起，探讨如何用傅里叶变换认识不确定性原理，也就是我们说，量子力学里面为什么不能同时确定一个粒子的位置和动量。

## 物理准备

### 德布罗意关系式
我相信各位在大学物理3，嗯，我知道大一还没上过大学物理3，那高中物理，应该都学过德布罗意关系式。比较熟悉的形式是这样的，$E=h\nu$，$p=h/\lambda$。德布罗意关系告诉我们，任何一个具有能量$E$和动量$p$的粒子，都同时是一个频率为$\nu$波长为$\lambda$的波，反之亦然。换言之，将光的波粒二相性推广到了所有微观粒子。

但是呢，我不太喜欢这个形式，因为它并不对称，你看，这里是乘，这里是除，不美观。其实啊，这种不对称的根源在于普通物理范畴内，我们对波的描述，空间周期特性的波长，时间周期特性的频率，是不对称的。我们大学物理1中学过机械波，或许大家还记得，简谐平面机械波的波函数是这样，很明显，波长和频率是不对称的。啊，这里我说的波函数就是描述波的函数啊，机械波可以有波函数，电磁波可以有波函数，不是特指量子力学的那个波函数。

所以，这个到底是怎么一回事呢？让我们来回顾一下这些东西的定义。

所谓周期，描述的是波在时间上的“周期”，即同一个空间点上，相隔多长时间振动状态会重复一次。

所谓波长，描述的是波在空间上的“周期”，即同一个时间点上，相隔多少距离振动状态会重复一次。

频率是周期的倒数，表征单位时间内振动状态的重复次数，角频率定义为频率的$2\pi$倍，它是什么意义呢？我们知道，振动状态每重复一次，相位上就过了$2\pi$，这样呢，角频率的意义就是单位时间内的相位变化。

好了，让我们从时间部分回到空间部分，大家发现问题了吗？我东西呢，波长的倒数是啥，去哪里了？我们好像从来没定义过是吧，没有关系啊，现在我们来定义。有没有同学愿意来做这个定义，知道的不要说啊（互动）。好吧，那我来说吧，周期的倒数是单位时间振动状态的重复次数，波长的倒数就自然是单位空间振动状态的重复次数，或者形象的说，就是这1米的距离上，数数，有几个波形，有一个算一个，有半个算半个，因此，波长的倒数，我们形象的称为，波数，即单位距离上的波形的数目。波数这个量呢我参阅了不同的书，似乎没有一个特别统一的记号，因为其实更常用的是角量，无妨，姑且我们就记它为$\kappa$，好吧。然后呢，类似的，波数的$2\pi$倍就是角波数，它代表单位空间内的相位变化，记为$k$。

这之后，我们总是会用角频率和角波数来分别描述波的时间特性和空间特性，这样一来，大家来看原来那个平面简谐波的函数，是不是就特别清晰了，这一项是时间上的相位，这一项代表空间上的相位，两者符号相反，代表，随时间推移相位在增加，随空间推移相位在减少，当然反过来也可以。很简洁吧！所以其实到后面，大家都是用角频率和角波数，其实很少会去搞频率和波数，所以为了说话方便，角频率和角波数也就简单的称为频率和波数了。

这个波函数是一维的，那如果是三维情形呢，平面波，波阵面是一个平面，这个平面肯定向某一个方向传播对吧，那么是只有在这个传播方向上，单位距离的相位变化才是$k$，其他方向的距离要投影到这个方向上来看。所以呢，我们将角波数加上波的传播方向，构成一个矢量，称为角波矢，然后把这里改成矢量点乘，这样就把平面简谐机械波的波函数从推广到三维了。

现在让我们回到德布罗意关系式，改用角波矢和角频率，可以改写为这样的形式，这里角波矢是矢量也很合理啊，动量本身也是一个矢量嘛。哇，简洁很多了，不是吗？不过呢，这个$h/2\pi$还是稍显臃肿。数学和物理学的永恒主题就是，当你的式子变得复杂的时候，我们就引入一个新的符号，把它代换掉。这里$h$是普朗克常量，但是如果大家去看一些量子力学的东西，其实更多出现的都是这个很漂亮的h，其实就是h上面加一横，读作hbar，称为约化普朗克常量，它就定义为普朗克常数除以$2\pi$，用约化普朗克常量，我们就得到了德布罗意关系式的终极形态：

- 能量正比于频率
- 动量正比于波矢
- 比例系数是约化普朗克常数

### 波粒二象性
德布罗意关系式建立了波和粒子的关系，而且通过我们前面的努力，我们让这种关系显得尤为简洁。但问题是。我们到底应该怎么去理解波粒二象性，大家凭借朴素的物理观念告诉我们，波和粒子能存在于同一个客体上吗？

那肯定是不能啊！你说一个小球，和一个弦线上传播的波，你指着它说，瞧，这是同一个事物的两个方面，我第一个不信。所以，问题的关键在于，怎么认识波粒二象性？关于这个问题，其实在量子力学的初期，很多物理学家也都走过弯路，主要呢，有这样两种看法。

第一种是片面夸大波动性，而忽略粒子性的观点。我们以电子为例呢，这种观点认为，电子是一种物质波包。这个话讲的很抽象啊，我说的形象一点，它的意思就是，电子传统上可以认为是一个小球，现在呢，我拿个榔头，啪，把这个小球砸成一堆碎片，然后呢，它说，这个碎片，有些地方稀疏一些，有些地方密集一些，这个就是电子的波动性，但是呢整体上，它在某一个区域特别集中，像是一个鼓包一样，这个就是电子的那个粒子。当然，你们会说，这都不是一个周期函数，你怎么能说它是波呢，没有关系啊，我们后面会看到，其实通过不同频率的周期性的简谐波的叠加，我们可以得到几乎任何非周期函数，只要它是空间上的一种分布，都可以说它是一个波，像这种叠加后集中在一个区域的，我们称为波包。这里，我们的波包，是由电子的碎片构成的，所以我们前面说，电子是物质波包。

但这个其实不正确啊，为什么呢？首先，我们见到的电子始终是一个一个的，对吧，密利根油滴实验测定元电荷。我们从来没有见过说，一些电子的碎片是吧。所以说这种物质波包的观点其实忽略了粒子性，这与科学事实是不相符的。而且如果仔细计算一下会发现，如果电子是物质波包，可以证明，这种波包会随时间迅速扩散到整个空间中，但是我们熟知的电子不是这么运作的，它总是定域在一个很小的空间内，比如，至少，一个原子的范围内吧。所以物质波包的观点是不正确的。

第二种是片面夸大粒子性，而忽略波动性的观点。这种观点认为，电子波是由大量电子的疏密构成的，什么意思呢？就好比说空气中，如果有声波在传播时，有些地方的空气分子会比较稀疏，有些地方的空气分子会比较密集，这种观点就是讲，电子波的波动性是由电子之间的疏密体现的。那这种观点有什么问题呢？我们知道，电子的波动性是可以由实验验证的，利用的就是双缝干涉实验，电子通过双缝后会呈现出和光类似的干涉条纹。我们做两个实验，第一次让电子大量通过双缝，光屏上出现干涉条纹，没有问题。第二次让电子一个一个通过双缝，这是可以做到的，我们只要让电子一个一个被打出就可以了，光屏上最开始呈现出随机的点，而经过一段时间后，光屏幕上也会出现干涉条纹。书上由此得出的结论是，少量电子体现粒子性，大量电子体现波动性，这分别依据的是第二个实验前后的两个结果，这个话讲的很讨巧，它没错，但是很容易被误读，误读为，少量电子具有粒子性，大量电子具有波动性，这分别依据的是第一个实验和第二个实验前面的结果，这就是完全错误的！因为单电子干涉实验恰恰告诉我们，哪怕是单个电子，也具有波动性！关键在于第二个实验后面的结果，虽然说最终仍然是大量电子通过后形成了干涉图样，但不要忘记，第二个实验中，这大量的电子，是一个一个通过双缝的，它们之间有没有联系，而最终能呈现出干涉图样，就必然说明，电子的波动性并不需要依赖大量电子的存在。所以这种观点中认为，电子的波动性是由大量电子的疏密分布体现的，这就站不住脚了，单电子通过的过程中，你根本没有机会形成什么电子的疏密波，对吧。

好啦，完蛋，那怎么办呢？两种理论都不对。没关系啊，让我们来回顾一下粒子性和波动性是什么。

经典上看，粒子具有原子性，是不可分割的，同时，粒子具有确定的轨道，这个轨道不光说是一个位置怎么随时间变化，而是也包含速度信息，换言之，我需要知道这个粒子的位置和速度随时间的函数。

经典上看，波代表了某种实在的物理量在空间上的分布，比如说，机械波是位移随空间的分布，电磁波是电磁矢量在空间的分布，等等。同时我们还知道，波具有衍射和干涉现象。

但是，让我们仔细想一下，量子力学中的波粒二象性，真的完全包含了上面讨论的特征吗？就粒子性而言，电子确实具有原子性，我们从未看到过半个电子或三分之一个电子。但是，电子具有确定的轨道吗，我们或许会这么想象，电子是一个在空间中运动的小球诸如之类的，但没有任何物理事实可以佐证这种说法。就波动性而言，电子波确实可以发生干涉和衍射现象，但是，电子波代表了什么物理量的波动吗？没有。

所以，量子力学中的波粒二象性，只包含了部分的波动性和部分的粒子性，波动性只继承了干涉和衍射特性，粒子性只继承了原子性。所以说，在量子力学中的波粒二象性是不矛盾的，因为，它并不是说微观客体要同时是波和粒子，它是说微观客体同时具有波和粒子的部分特性，部分特性，这样就不矛盾了。

### 波函数

那现在的问题是剩下的两条怎么办，你可以不承认，粒子可以不具有确定的轨道，波也可以不代表某种物理量的分布，但如果这样，你仍然需要另找解释，不能回避问题。破局的关键在于，概率。

其实我们仔细来回顾一下，单电子干涉实验的结果和我们抛硬币很像，如果我们只抛几次，结果是随机的，肯定不会说刚好是一半正面一半反面，而如果抛的次数很多，则正面和反面的频率就会趋于一半和一半的规律结果，单电子干涉实验，最初光屏上的点是随机的，而一段之后会趋于规律的干涉图案。所以说，单电子衍射实验表现的是电子的统计行为。确切的说，电子不具有确定的轨道，电子的运动是概率的，电子波不代表某种物理量的分布，而是代表电子出现在各个地方的概率，换言之，波动着的，是概率。

当然，如果我们说，量子力学中的波函数就代表概率，那还不太确切。

首先，我们不能讲电子出现在空间某个确切点的概率有多少，你说电子出现在$x=2$，它还可以在$x=2.1,2.01,2.001$，它还可以在$x=\pi$，对吧，空间中的位置是连续分布的，出现在任何一个特定位置的概率都是零，我们只能说粒子出现在某一区域内的概率是多少。这就好比什么，质量，这有一个苹果，我们可以说，苹果这切下一块的质量是多少多少，但是，我们不能说，苹果哪个点上的质量，这一个点上有什么质量呢？但你可以讲什么，我可以说，这个点上苹果的密度是多少，那一般来说苹果的密度是不均匀的，那我要考察一个点的密度，就取这个点附近的一小块区域，这块区域的质量比上体积，在区域那一点时的极限，就可以定义为该点的密度。而类似的，概率的密度，就称为概率密度。所以，我真正能讨论的是什么，电子在空间各点的概率密度，这个如果有了，你如果关心电子出现在某个区域内的概率，那我们只要将概率密度在这个区域内积分就可以了。

概率密度的想法其实是非常重要的，质量和密度这个道理其实很明白，但换成概率，很多人就搞不明白，我们大学物理3里面讲麦克斯韦-波尔兹曼分布律和波函数，其实都有遇到概率密度的概念，但我觉得当时，其实这个点都没能揭示出来。

其次，电子的统计分布符合干涉图案，这是指与光强分布是一致的，而我们知道，波的强度是波幅模的平方。如果用$\psi$描述表示电子的波函数，那么遵从概率密度分布的其实是波函数模的平方，换言之，波函数模的平方才代表概率密度，波函数没有明确的物理意义，通常称为概率幅。

以上，就是量子力学中，波函数的统计诠释。至此，物理部分，准备完成。

## 数学准备

### 傅里叶级数
数学部分呢，我们从傅里叶级数讲起，我这个分享时间选的特别不错，刚好赶上各位大一同学微积分3学完级数，开微分方程这个时间点上，那我相信大家对傅里叶级数应该非常熟悉啊。傅里叶级数就是说，任何一个周期函数，它都可以分解为由正弦和余弦函数构成的三角级数，它们这些正弦和余弦前的叠加系数，则由原来这个周期函数的积分确定。没关系啊，这个积分看的挺吓人的，但又没让大家积是不是。

我们从一个引例出发，大家知道，方波，这么个函数，它可以表达为这样一个正弦级数。

这个数学式或许有点抽象是吧，那我们来看图，我们看到，如果我们取级数中的前$N$项进行绘制，随着$N$的增大，这个叠加结果会越来越接近方波，这个很直观吧，现在，应该我们可以认同这个式子了。

那我现在想说的是，关于这个方波信号，一方面我们可以从时间上看，它可以记为$f(t)=...$，一方面我们也可以从频率上看，或者说，就是参与方波叠加的这些不同频率的正弦波中，每个频率的叠加系数是多少，即$F(\omega)=...$，其实说白了就是傅里叶级数中的系数$b_n$，换个写法。如果大家还不理解，请看这张动图。当时我一个朋友我这个地方反复讲了三遍它也没明白，但是看了这张图就瞬间懂了。

所以就是说，一个随时间变化的信号，我们可以从时域上考察，我们也可以从频域上考察。傅里叶变换研究的，就是时域函数和频域函数之间如何相互转化，但是呢，从傅里叶级数到傅里叶变换，我们还有两步要走，或者说，要克服两个困难

1. 第一个，刚刚方波比较特别，它只由正弦函数叠加而来，而一般的周期函数有正弦和余弦两个部分，那么，我们将哪个部分作为频域函数呢？
2. 第二个，傅里叶级数只能展开周期函数，那非周期函数怎么办呢。

这是我们要克服的两个困难，这一部分呢，数学公式会比较多，但是希望大家不要害怕啊，只是看起来比较唬人，我推导过程写的也很细。

第一个困难，正弦和余弦，我们选哪个作为频域函数呢？其实呢，我们都不选，我们怎么办。大家是不是都学过欧拉公式，欧拉公式呢不仅是可以将复指数表示为三角函数，它也可以反过来，将三角函数展开为复指数。证明也很容易啊，将$\theta$那里分别带入$\pm\theta$，然后解一下方程组就出来了。

我们现在要做的呢，就是将傅里叶级数中的正弦和余弦，还有常数项，统一的转化为复指数形式，这样的话，我们是不是就只有一个系数了？

这是刚刚的傅里叶级数的展开式，我们代入欧拉公式，就得到这个。

然后我们整理一下，$e^i$归在一起，$e^{-i}$归在一起。

我刚刚说了，我们最终希望将傅里叶级数转化为复指数形式，我们想要的就是这个，对吧，注意啊，下标改成$k$了，范围从负无穷到正无穷，负数就对应这里，正数对应这里，零呢就对应$a_0$常数项。而我们比较一下这两个式子，待定的$c_k$就分别应该等于这些。

而这些$a_n,b_n$，还有$a_0$，前面都有了，我们代进去整理一下就行了，对吧，这里你看又出现了欧拉公式的那个形式，那么再换成复指数。这样一来以后，大家看，我$c_k$其实可以统一的记为这样一个统一的形式。

到这里，我们就成功的将傅里叶级数转换为了复数形式，为什么啊，哎，展开式有了，展开式中的系数也有了，那就OK了。第一个问题到这里就解决了，现在我们的频域函数只有一个了，就是复指数前的这个系数$c_k$，没有什么正弦余弦了。

第二个困难，就是说，非周期函数怎么办，其实大家想一下，什么是非周期函数，非周期函数不就是一个周期$L$无穷大的函数吗，这会发生什么呢，大家看，我们的频谱，两个的频率间的间隔是和周期$L$有关，周期越长，频率间隔就越小，频谱就越密，如果周期$L$趋向无穷大，那会发生什么，频率就连续了，就是说，你那个频域函数$F(\omega)$是关于$\omega$的连续函数了，额，我意思是说，这个$\omega$定义域是一个连续的区间了，不像原来那样$\omega$只能取一些分立的值了。

这个想法有了，我们就可以明确什么是傅里叶变换，傅里叶变换的实质，就是傅里叶级数的复数形式，在周期$L\to\infty$的极限形态。当然咯，说着轻松，实际上，我们还是有几步要走的。

首先呢，我们先取个极限，为了计算这个极限，引入两个代换变量，$\omega$代表频率，$\Delta\omega$代表频率间隔。那运用这两个代换量，展开式可以改写为，这里就是乘了一个$\Delta\omega$除了一个$\Delta\omega$。然后大家看这个形式，这不就是，和式的极限嘛，这就是一个定积分，当然咯，广义积分，我们是负无穷积到正无穷。

现在的问题是$Lc_k$的极限怎么算，这个很容易啊，你把$c_k$代进去，哎，$L$被约没了，这就是个常数。

我们就把这个极限记作$F(\omega)$，当然咯，前面有些系数，这是为了最后结果配的好看的，这样$f(x)$就可以表示为这样。

好了，这，就是傅里叶变换，很简单吧。我们将由时域$f(x)$求频域$F(\omega)$的过程，称为傅里叶变换，相反的，由频域求时域的过程，称为傅里叶逆变换，然后我们有两个特别的记号，这个花里胡哨的$F$，没记错的话，$\LaTeX$里面是用mathcal的字体，来表示傅里叶变换和傅里叶逆变换。


这里我说几个点
1. 首先是前面这个$1/\sqrt{2\pi}$的系数，其实刚刚，我令$F(\omega)$的时候大家就注意到的，我就是在配这个系数。实际上呢，这地方无所谓，只要变换和逆变换前的系数乘起来是$1/2\pi$就可以，这个系数怎么分配也没有统一的，我这里是一人一半$1/\sqrt{2\pi}$，物理上这种常见一点，也有变换不放逆变换$1/2\pi$，我当时学数物方法这种见的多，也有变换放$1/2\pi$逆变换不放的，反正没有统一的。当时学到这里，我有个同学问我，说，我能不能变换放$1/2$，逆变换放$1/\pi$，我白了他一眼，其实都可以啊，看你实际需要。我记得当时数物张凌峰老师在这里强调过，就是说，如果你要傅里叶变换，你必须要同时写出变换和逆变换的公式，否则人家不知道你用的到底是哪套，哪个系数。反正今天我这里，我们用的就是这样的傅里叶变换，一边一半。
2. 然后这里，我说这是傅里叶变换的核，这是啥意思呢。我们说啊，傅里叶变换它是一种积分变换，除了傅里叶，还有拉普拉斯变换，那这些积分变换间是什么区别呢，就是说，这个核不同，不同的核就代表了不同的积分变换，傅里叶变换的核就是这个。
3. 还有就是，$f(x)$我们称为原函数，这个原函数和积分里面那个原函数没关系啊，$F(\omega)$称为像函数。这个是比较一般的称呼啊，因为你不一定是信号，讲时域频域有时候就太狭隘了。

傅里叶变换有很多性质啊，我们今天只讲一个，因为和今天的内容关系很密切。它是什么意思呢，就是说如果$f(x)$的傅里叶变换是$F(\omega)$，那么$f(\lambda x)$的傅里叶变换，就是这个。

证明很容易啊，走定义，然后我们代换一下变量，这里$\xi,\xi,\xi$统一了，那就又可以用傅里叶表示了，搞定。

这个性质告诉我们什么呢，时域上的压缩，你函数自变量乘以一个数$\lambda$，这个数$\lambda$假设它是大于$1$的，它就代表压缩这个函数图形，它在频域上，表现为等比例的横向拉伸，这里自变量除以$\lambda$，这函数图形不就拉伸了嘛，以及等比例的纵向压缩，这里函数值除了$\lambda$。

我们关注的主要是自变量横向的部分，那就是说，时域上压缩，频域上就会别拉伸，或者说，时域和频域无法同时被压缩，嗯，很奇妙吧，就是这样。

大家会不会觉得，时域和频域不能同时被压缩，嗯嗯，什么和什么不能被同时压缩，是不是和不确定性原理中，位置和动量不能被同时确定，有点像，嗯，像就对了啊，不确定性原理就是从这里出来的。这个我们放一下，等会儿在说。

至此，数学部分，准备完毕！

## 傅里叶变换与不确定性原理
好啦，现在，我们要开始正式的进入不确定性原理。我们都知道啊，不确定性原理讨论的其实说的就是，这一个微观粒子，位置和动量不能被同时确定，所以，我们先要弄清的是，到底什么是动量。前面物理部分讨论，我们已经知道，粒子的位置服从波函数给出的概率分布，它不是一个确定的值，其实啊，粒子的动量也是这样的概率分布。因为我们说，微观粒子没有确定的轨道，轨道包含位置和速度两个部分，动量就是速度乘以质量，一回事，所以说，微观粒子没有确定的位置和速度，两者都是概率的。

现在的问题就是说，位置的概率分布我知道的，就是波函数，动量呢？动量的概率分布是啥？

其实啊，我可以告诉大家，动量，就是位置的傅里叶变换，当然咯，这样说的意思是，位置满足的概率幅函数的傅里叶变换是动量满足的概率幅函数。但是，为什么呢？这动量和位置，这八竿子打不着，咋就，傅里叶变换了？乱搞嘛不是，我们来看为什么啊。

其实这个事很简单，我们先来看，波函数的傅里叶变换是啥，在这里，波函数就是我们的时域，但是呢，这个自变量，并不是时间，而是空间啊，波函数其实是坐标空间上的一个函数，波动是在空间上的。时域傅里叶变换后得到频域，时间对应频率$\omega$，空间对应波矢$k$。所以坐标空间上的波函数傅里叶变换后得到的就是波矢空间上的一个函数，时域-频域，坐标空间-波矢空间。

这里波矢空间的函数我们记为$\phi_0(k)$，它描述的就是波函数中波矢为$k$的简谐波的成分有多少啊，那么因为是在量子力学的意义下在探讨，$\phi_0(k)$其实应该解读为波矢为$k$的简谐波的出现概率啊。

然后还要解释一下，因为我们坐标空间是三维的，所以你这个傅里叶变换就也是三维的，首先看到，这个地方系数是$1/\sqrt{2\pi}$的三次方，这里原来是$\omega x$，现在改成点乘$k\cdot r$了，然后积分也变成三重的了，积三次嘛，这里要说一下，这个$d^3x$可能看的很迷惑，它不是说积三次$x$啊，它意思就是$dx,dy,dz$，是一种简写啊，下面$d^3k$也一样啊，就是$dk_x,dk_y,dk_z$。

好，现在我们已经知道，坐标空间上的波函数$\psi(r)$傅里叶变换后会得到一个波矢空间上的函数$\phi_0(k)$，那这和动量有什么关系啊？不要忘记，德布罗意关系式，$p=\hbar k$，动量是正比于波矢，所以说，傅里叶变换的这个像空间，我们既可以用波矢空间，也可以把它进一步转换为动量空间，有点感觉了吧，下面我们来看，怎么转化啊。

首先，就是说，动量是$p$的概率幅$\phi(p)$应该等于波矢为$p/\hbar$的概率幅，所以呢$\phi(p)$就等于$\phi_0(p/\hbar)$，这里呢，我们再将$k$换成$p/\hbar$，就可以了。

然后，下面这里要涉及到微分的转换，原来是$d^3k$，它相当于是$d^3p/\hbar^3$，因为你$p_x=\hbar k_x$，$p_y=\hbar k_y$，$p_z=\hbar k_z$，然后$1/\hbar^3$提出来，这里$k$一样换成$p$，就好了。

这里$1/\hbar^3$全部在逆变换上面，那我们也可以调整一下，把它改成一人一半，这样，我们就建立了位置和动量间的傅里叶变换关系。

这里，$|\psi(r)|^2$表示粒子的位矢为$r$的概率 密度，$|\phi(p)|^2$表示粒子的动量为$p$的概率密度。

其实我们回过来看，其实这种傅里叶变换的根本在于什么，还是德布罗意关系式$p=hk$，它联系了动量和波矢。

我当时学量子力学的时候，这么多的演绎中，让我觉得最为精彩的，就是之类，动量和位置间的傅里叶变换关系，非常美妙啊，嗯。

接下来，我们就是说，动量和位置间的傅里叶变换关系，和不确定性原理是什么关系。我们都知道，不确定性原理是将，量子力学中，我们无法同时确定一个粒子的动量和位置，嗯。其实，不确定性原理到底是想解决什么一个问题呢？就是我们都知道，量子力学中已经摒弃了经典中的轨道的概念，取而代之的是波函数，但是，总是波函数波函数的，太抽象了，我就是要把电子想象一个到处乱跑的小球，行不行呢？这个其实就是在问，经典粒子中轨道的想法对于微观粒子，究竟在多大程度上适用？对此，不确定性原理做了最为集中且最为形象的概况。

轨道，就是说，粒子每一时刻的动量和位置是可以确定的，量子力学中，这个都是概率，我们只能说，粒子的动量和位置有较大概率处于某一范围。

比如说，这是一个高斯分布啊，它经过傅里叶变换还是高斯分布，大家不用管什么是高斯分布啊，总之，就是说，我们$|\psi(x)|^2$，它傅里叶变换后的$|\phi(p)|^2$差不多还是这个形状，所以说，我们没办法准确的说，这个粒子的位置和动量是多少，但是我们可以划定一个范围，位置有很大的概率，比如说$68.3\%$，会落在这么个范围内，动量一样的，有$68.3\%$的概率，会落在这么个范围呢，这里下标都不用管它啊，看图就行。

所以说呢，其实量子力学中，我们不能准确的说，粒子的位置和动量是多少多少，但我们可以说，粒子的位置和动量大概在哪个范围内。这就有一个很朴素的想法，就是说，哪怕是在经典力学，大家做大物实验知道的呀，测量也都是有误差的呀，这个20分度50分度的游标卡尺不确定度多少多少，螺旋测微尺不确定度多少多少，等等。所以，反正测量有误差，那我们只要尽可能同时比较准确的测定位置和动量，是不是就和经典轨道一样了。虽然说，位置和动量在量子力学是个范围，但你测量本身也就是得到一个范围，是吧。

遗憾的是，这个是做不到的。为什么呢，不是说，你测量的设备做不到这个精度，而是说，如果你能将位置测的非常准确，动量不确定度一定是很大的，如果你能将动量测的非常准确，位置不确定度一定是很大的。这怎么回事，因为大家想一下，你如果位置测量很准确，不确定度很小，位置的这个概率幅函数的波包肯定是很窄的，我这里不想探讨，测量会影响微观粒子的波函数怎么样，我就是想说，如果你能测量的很精确，这个波包是不是一定的很窄，否则你精确个啥，是吧。

而我们前面说了，动量是位置的傅里叶变换，或者说$\phi(p)$是$\psi(r)$的傅里叶变换，而傅里叶变换有什么性质，相似性质，时域和频域不能同时被压缩，这里来讲，位置的概率幅$\psi(r)$的波包你压缩了$\lambda$倍，精确了，$\Delta x$减小了$\lambda$倍，动量的概率幅$\phi(p)$的波包就要拉伸$\lambda$倍，这就不精确了，$\Delta p$要增大$\lambda$倍，反之亦然。

所以说呢，位置和动量的不确定性是相互制约的，这两个乘起来是个定值，对吧，因为刚刚我们也看到，它增加几倍，它就要减小几倍。这，其实就是不确定性原理了，确定位置，动量不确定了。确定动量，位置不确定了。

当然咯，还有一个问题，这里定值是多少。嗯，这个我们可以通过一些办法估计一下，比如说，像刚刚这样，我们可以设$\psi(r),\phi(p)$都是高斯分布，然后去算，过程不难，但数学上比较繁琐，我这里就略掉了，结论告诉大家，算出来是$\hbar$，$\Delta x\Delta p=\hbar$，这也是为什么我们说，普朗克常量其实代表了一个尺度，只有说你的测量的不确定度能精确到普朗克常量的尺度，那才会产生这种制约效应。如果说你的测量都很不精确，$\Delta x$比普朗克常数大很多，那不确定度导致的$\Delta p$其实是很小的，你可能真正测动量的仪器的不确定度$\Delta p$都还要更大，所以说，量子力学的原理对于宏观其实没有太大的影响。

刚刚这个$\Delta x\Delta p=\hbar$其实只是一个估测，更准确的分析指出，这个值应该可以达到$\hbar/2$，而且因为测量误差的因素，这里还是大于等于$\hbar/2$的，这个就是不确定性原理的一个比较常见的数学表达。

最后我们来总结一下。

不确定性原理告诉我们，同时尽可能准确的测出微观粒子的位置和动量的努力存在一个不可逾越，无关测量本身，由量子力学基本原理所决定的物理极限。

不确定性原理的本质是什么，由于波粒二象性和德布罗意关系式，微观粒子的位置和动量间存在傅里叶变换关系，而傅里叶变换关系的相似性质表明，原函数和像函数不能同时被压缩，因此，位置和动量不能同时被测定准确，

简而言之，不确定性原理，是量子力学的物理图景下，由数学定理直接决定的一个必然结果。

我今天的分享就到这里，谢谢大家！

接下来，我们进入了互动的环节，大家有什么问题可以提出来，啊，然后今天演讲的这个beamer，大家可以通过这个链接下载，它的$\LaTeX$源代码在Github上也都是开放的。然后我今天演讲中的内容和里面的图片，其实主要都来自我各专业课的笔记，微积分，大学物理，数学物理方法，量子力学，这些笔记本身也是开放下载的，可以在我的Github主页上找到。