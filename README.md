# COMPX216-Midterm

**人工智能期中考试复习大纲**

**一、 人工智能导论 (Introduction to Artificial Intelligence)** (主要基于 `008_IntroductionToAI-1.pdf`)
    1.  **AI的定义与分类**:
        * 什么是人工智能？（思考、行动；像人、理性） (幻灯片 18-21)
        * 狭义AI (Narrow AI) vs. 通用AI (General AI) (幻灯片 3-4)
        * 理性智能体 (Rational Agents) 的概念：最大化期望效用 (幻灯片 22, 35)
    2.  **AI的影响与应用**:
        * AI在现实世界中的应用领域（如：文本助手、图像生成、科学、经济等） (幻灯片 5-15)
    3.  **AI简史**:
        * 关键的里程碑和发展阶段（早期、知识驱动、统计方法、深度学习等） (幻灯片 26-28)

**二、 问题解决型智能体 (Problem-Solving Agents)** (主要基于 `009_ProblemSolvingAgents-1.pdf`)
    1.  **智能体与环境**:
        * 智能体 (Agent) 的定义、传感器 (Sensors)、执行器 (Actuators) (幻灯片 3-6)
        * 感知 (Percepts)、感知序列 (Percept Sequence)、智能体函数 (Agent Function) (幻灯片 7-8)
        * 环境类型 (PEAS描述 - Performance, Environment, Actuators, Sensors - 虽未显式强调PEAS，但环境类型是重点):
            * 完全可观察 vs. 部分可观察 (Fully observable vs. partially observable) (幻灯片 12)
            * 单智能体 vs. 多智能体 (Single-agent vs. multi-agent) (幻灯片 13)
            * 确定性 vs. 非确定性 (Deterministic vs. non-deterministic / stochastic) (幻灯片 14)
            * 分散性/片段性 vs. 序列性 (Episodic vs. sequential) (幻灯片 15)
            * 静态 vs. 动态 (Static vs. dynamic) (幻灯片 16)
            * 离散 vs. 连续 (Discrete vs. continuous) (幻灯片 17)
    2.  **问题定义与形式化**:
        * 问题解决过程：目标制定、问题形式化、搜索、执行 (幻灯片 18, 20)
        * 搜索问题的组成部分 (幻灯片 21):
            * 状态空间 (States / State Space)
            * 初始状态 (Initial state)
            * 目标测试 (Goal states / Goal test)
            * 行动 (Actions)
            * 转移模型 (Transition model / Successor function / Result function) (幻灯片 9, 31)
            * 路径代价函数 (Action cost function / Path cost function)
    3.  **搜索树与数据结构**:
        * 状态空间图 vs. 搜索树 (幻灯片 28, `010_UninformedSearch.pdf` 幻灯片 4)
        * 节点 (Node) 的构成：状态、父节点、行动、路径代价、深度 (幻灯片 29)
        * 节点扩展 (Expanding nodes) (幻灯片 31)
        * 边界 (Frontier) 和已探索集合 (Explored set / Reached list) (幻灯片 29, `010_UninformedSearch.pdf` 幻灯片 39-43)
    4.  **搜索策略的评估标准** (幻灯片 33):
        * 完备性 (Completeness)
        * 最优性 (Optimality)
        * 时间复杂度 (Time complexity)
        * 空间复杂度 (Space complexity)

**三、 无信息搜索策略 (Uninformed Search Strategies)** (主要基于 `010_UninformedSearch.pdf`)
    1.  **通用最佳优先搜索 (Generic Best-First Search)** (幻灯片 6-8, 11, 41-43)
        * 理解其框架以及如何通过不同的队列/策略实例化不同算法。
    2.  **广度优先搜索 (Breadth-First Search, BFS)**:
        * 策略：扩展最浅的节点 (幻灯片 12-13, `009_ProblemSolvingAgents-1.pdf` 幻灯片 2)
        * 数据结构：FIFO 队列 (幻灯片 12, 15, 37)
        * 特性：完备性、最优性（当路径代价一致时）、时间与空间复杂度 (幻灯片 13)
        * Java实现逻辑（练习题中可能会涉及代码理解）
    3.  **一致代价搜索 (Uniform-Cost Search, UCS)**:
        * 策略：扩展路径代价 $g(n)$ 最低的节点 (幻灯片 30-32, 38, 45)
        * 数据结构：优先队列 (幻灯片 32, 38)
        * 特性：完备性、最优性（代价非负时）、时间与空间复杂度 (幻灯片 31)
    4.  **深度优先搜索 (Depth-First Search, DFS)**:
        * 策略：扩展最深的节点 (幻灯片 25-26)
        * 数据结构：LIFO 队列 (栈) (幻灯片 26, 29, 37)
        * 特性：完备性（有限无环图或记录已访问节点时）、非最优性、时间与空间复杂度 (幻灯片 26, 44)
    5.  **避免重复状态**：使用已达到列表 (reached list) / 已探索集合 (幻灯片 39-43)

**四、 有信息（启发式）搜索策略 (Informed (Heuristic) Search Strategies)** (主要基于 `011_InformedSearch-1.pdf`)
    1.  **启发式函数 (Heuristic Function, $h(n)$)**:
        * 定义：估计从当前状态到目标的代价 (幻灯片 2, `010_UninformedSearch.pdf` 幻灯片 5)
        * 作用：指导搜索向更有希望的方向进行 (幻灯片 87-94)
    2.  **贪婪最佳优先搜索 (Greedy Best-First Search)**:
        * 策略：扩展启发式函数值 $h(n)$ 最低的节点 (幻灯片 96-97)
        * 特性：不完备（可能陷入循环）、非最优 (幻灯片 130)
    3.  **A\* 搜索 ($A^{*}$ Search)**:
        * 策略：扩展评估函数 $f(n) = g(n) + h(n)$ 值最低的节点 (幻灯片 132, 134)
        * $g(n)$: 从起点到节点n的实际代价
        * $h(n)$: 从节点n到目标的估计代价
        * **可接受的启发式 (Admissible Heuristics)**：$h(n) \le h^*(n)$ (不 overestimate 真实代价) (幻灯片 171)
        * **一致的启发式 (Consistent Heuristics / Monotonicity)**：$h(n) \le c(n,a,n') + h(n')$ (幻灯片 172)
        * 特性：完备性；最优性（当h(n)可接受且一致时）(幻灯片 171-173)
        * 搜索等高线 (Search Contours) (幻灯片 174)
    4.  **启发式的创建**:
        * 松弛问题 (Relaxed problems) (幻灯片 176)
        * 8-puzzle问题的启发式例子：错位棋子数量、曼哈顿距离 (幻灯片 177)
    5.  **内存有界搜索**:
        * **集束搜索 (Beam Search)**：限制边界 (frontier) 大小为 k (幻灯片 175)

**五、 局部搜索和优化 (Local Search and Optimisation)** (主要基于 `012_LocalSearchAndOptimisation.pdf`)
    1.  **优化问题 (Optimisation Problems)** vs. 路径搜索 (幻灯片 3-6)
        * 目标函数 (Objective function) / 代价函数 (Cost function) (幻灯片 3, 11-12)
    2.  **局部搜索算法**:
        * 特点：只保留当前状态（或少量状态），不记录路径，内存消耗小 (幻灯片 6)
        * 状态空间地貌 (State-space landscape) (幻灯片 10)
    3.  **爬山算法 (Hill-Climbing Search)**:
        * 基本思想：持续向值更高的邻居移动 (幻灯片 15-27)
        * **最陡峭上升爬山法 (Steepest-Ascent Hill Climbing)** (幻灯片 27)
        * 问题：
            * 局部最大值/最小值 (Local maxima/minima) (幻灯片 37-40, 练习题 Sec B, Q3a)
            * 山脊 (Ridges)
            * 平顶/高原 (Plateaus / "flat" local maximum) (幻灯片 46, 47)
        * N-皇后问题作为例子 (幻灯片 28)
    4.  **爬山算法的变体** (幻灯片 49):
        * **随机重启爬山法 (Random-Restart Hill-Climbing)** (练习题 Sec A, Q5)
        * 随机爬山法 (Stochastic Hill-Climbing)
        * 首选爬山法 (First-Choice Hill-Climbing) (练习题 Sec B, Q3b)
    5.  **模拟退火 (Simulated Annealing)**:
        * 思想：允许以一定概率接受更差的移动以跳出局部最优 (幻灯片 50-60)
        * 温度参数 (Temperature variable T) 的作用：初期高温允许更多探索，后期低温趋向利用 (幻灯片 60, 练习题 Sec B, Q3c)
    6.  **局部集束搜索 (Local Beam Search)** (幻灯片 63)
        * 与随机重启爬山的不同之处。

**六、 进化算法 (Evolutionary Algorithms)** (主要基于 `013_EvolutionaryAlgorithms.pdf`)
    1.  **基本思想**：模仿生物进化和自然选择 (幻灯片 3-4)
    2.  **核心组成**:
        * 种群 (Population) (幻灯片 6, 7)
        * 个体 (Individual) / 染色体 (Chromosome) / 基因 (Gene) (幻灯片 7)
        * **适应度函数 (Fitness Function)**：评估个体的优劣 (幻灯片 5, 10, 练习题 Sec A, Q6)
    3.  **主要操作**:
        * 选择 (Selection)：根据适应度选择父代 (如轮盘赌选择、锦标赛选择、精英保留等) (幻灯片 8, 12)
        * **交叉/重组 (Crossover / Recombination)**：组合父代基因产生后代 (幻灯片 9, 12, 13, 练习题 Sec B, Q1d)
        * **突变 (Mutation)**：对后代进行随机的小修改 (幻灯片 9, 12, 13)
    4.  **遗传算法 (Genetic Algorithm) 伪代码** (幻灯片 11-12)
    5.  **遗传算法与生物进化的区别** (幻灯片 15, 练习题 Sec B, Q1e)
    6.  应用实例：进化天线 (幻灯片 16)

**七、 连续空间中的局部搜索 (Local Search in Continuous Spaces)** (主要基于 `014_LocalSearchInContinuousSpaces.pdf`)
    1.  **连续状态空间**：用向量表示状态 (幻灯片 3, 5)
    2.  **梯度下降 (Gradient Descent)**:
        * 目标：找到函数的局部最小值 (幻灯片 2, 6, 10)
        * 梯度 ($\nabla f(x)$)：指向函数最陡峭上升方向的向量 (幻灯片 8-9, 21, 23)
        * 更新规则：$x \leftarrow x - \gamma \nabla f(x)$ (其中 $\gamma$ 是学习率/步长) (幻灯片 11, 13, 14, 20)
        * 多维梯度下降 (幻灯片 21)
        * 不保证找到全局最小值（可能陷入局部最小值） (幻灯片 24-25, 练习题 Sec B, Q3d)
    3.  **梯度上升 (Gradient Ascent)**:
        * 目标：找到函数的局部最大值。
        * 与梯度下降的关系：更新规则变为 $x \leftarrow x + \gamma \nabla f(x)$ (练习题 Sec B, Q3e)
    4.  **超越基本梯度下降**:
        * 步长/学习率的选择
        * 二阶方法（如牛顿法，使用Hessian矩阵） (幻灯片 26-27)

**复习建议**:
* **理解定义**：确保你理解每个术语的准确含义。
* **对比算法**：比较不同搜索算法的策略、优缺点、适用场景。
* **掌握特性**：记住关键算法的完备性、最优性、时间空间复杂度的大致情况。
* **代码理解**：练习题中可能会有伪代码或Java代码片段，要能理解其逻辑（尤其是各种搜索算法的队列/栈操作，节点扩展）。
* **应用场景**：思考不同算法适合解决什么类型的问题。

