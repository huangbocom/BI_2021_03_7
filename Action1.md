###  Action（五子棋）： 棋盘大小 10 * 10 , 采用强化学习（策略价值网络），用AI训练五子棋AI , 请说明都有哪些模块，不同模块的原理
** 基于对Alphogo的理解, AI走五子棋也要有如下的问题：

1. 首先把要解决的问题转化成为一个环境（environment）
2. 状态空间（state space）：对于围棋来说，每一个棋盘布局（记为s）就是一个状态，所有可能的棋盘布局就是状态空间
3. 动作空间（action space）：对于围棋来说，所有可能落子的位置就是一个动作空间
4. 可行动作（available action）： 给定一个棋盘，哪里可以落子，哪里不可以
5. 状态转化：下棋之后，对手可能会下的棋。如果是两个五子棋AI，相互是对方环境的一个部分
6. 奖励函数：下棋之后得到的信号反馈。在围棋里面，就是胜率的一个正函数。胜率越大，奖励越大

对应的模块：
1、 定义状态空间和动作空间的模块。
2、实现五子棋策略网络的MCTS模块，MCTS的输出     是根据值函数V得到的一个更优策略，它将被用于通过self－play来生成数据供深度神经网络学习，能够通过self－play不断变强。

3、实现价值网络的MCTS模块， 让我们更准确地选择需扩展的节点，策略网络可以让我们对动作使用输出概率来表示，对于离散动作空间，使用softmax动作的出现概率；对于连续空间，使用高斯分布来获取动作的概率

4、实现随机走子的MCTS模块。可以快速的计算结果，加快落子的效率。用于前期。
5、实现人机对弈的模块


