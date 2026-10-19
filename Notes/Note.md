## Reinforcement_Learning

> 整理自《**Mathematical Foundations of  Reinforcement Learning**》 by Shiyu Zhao

***

### Outline

<img src="E:\Reinforcement_Learning\Notes\assets\image-20261019210145674.png" alt="image-20261019210145674" style="zoom:50%;" />

**PART_1** :  建立基础性认知，对一般性问题能抽象建模，对`RL`有直观认知

> 基础概念、模型框架MDP、数学工具`bellman equation`

**PART_2** : 掌握各种算法思想、数学基础、以及实现流程，理清原理依赖与直观感受的对应关系

> 值迭代/策略迭代/截断策略迭代、蒙特卡洛、时序差分、值函数、策略梯度、



***

### Ch 1  Basic Concepts

#### 1 基本术语

**state** ： 描述智能体在特定环境中某一时刻的状态，记为 $s_i$

**state space** : 在某一环境下智能体所有状态的集合，记为 $S$ = {$s_i$}

**action** : 智能体在某一状态下所能采取的某一行为，记为 $a_i$

**action space** : 智能体在某一状态下所能采取的行为集合，记为 $A(s_i)$ = {$a_i$}

**state transition** : 智能体在一个状态下采取某一行动而变化到另一状态的概率分布，一般表示为 $p(s_j|s_i,a)$

**policy** : 智能体在某一状态下采取某一行动的概率分布，一般表示为 $\pi(a|s)$

**reward** : 智能体在某一状态下采取某一行动而获得的汇报的概率分布，一般表示为 $p(r|s,a)$

> 1. reward的实际含义是相对的，从数学层面讲，reward越大表示越鼓励该行为。故一般设置reward为正数时表述奖励，为负数时表示惩罚，但是这个标准不是绝对的
>
> 2. 从直觉上来讲，获得的反馈应与结果相关，因此此处reward可以用全概率公式拆分为
>
>    ​                                 $p(r|s,a)$=$\sum_{s^{'}} p(s^{'}|s,a)p(r|s,a,s^{'})$

**trajectory** : 轨迹，即指agent在某个策略$\pi$指导下走出的一条具体路线

**episode** : 特殊的，当trajectory为有限长时，被称作episode，对应episodic task，反之对应continuing task

**return** : agent的某条轨迹的累计奖励和，常见为$G_t$=$R_t+\gamma R_{t+1}+\gamma^2R_{t+2}+...$



#### 2 Markov decision process

> 在MDP框架下给出问题建模框架

**MDP 构成**

1. Sets:

   * State space  $S$
   * Action space  $A(s)$
   * Reward set  $R(s,a)$

2. Model

   > 可以理解为环境

   * State transition probability  $p(s^{'}|s,a)$

   * Reward probability   $p(r|s,a)$

3. Policy  $\pi(a|s)$

**MDP性质**
$$
p(s_{t+1} \mid s_t, a_t, s_{t-1}, a_{t-1}, \ldots, s_0, a_0)
= p(s_{t+1} \mid s_t, a_t)
$$

$$
p(r_{t+1} \mid s_t, a_t, s_{t-1}, a_{t-1}, \ldots, s_0, a_0)
= p(r_{t+1} \mid s_t, a_t)
$$

即指：未来的情况（状态、奖励）仅与当下的状态与采取的行动有关，与过往历史无关







***

### CH 4  Bellman Equation









