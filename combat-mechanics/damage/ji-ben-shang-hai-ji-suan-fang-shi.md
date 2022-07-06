# 基本伤害计算方式

## 非反应伤害期望计算方式(大多数伤害）



$$
DamageExp = (BaseDamage \cdot SpecialTalentMult +OtherBaseDamage) \\ \cdot (1+CritRate \cdot CritDmg)\cdot (1+DamageBonus) \cdot  AmplifyReactionMult 
\\ \cdot EnemyDefMult \cdot EnemyResMult
$$

### ​基础伤害 BaseDamage

$$
BaseDamage = ATK \cdot TalentRate+HP \cdot TalentRate+Def\cdot TalentRate
$$

​默认情况下按照攻击力，部分按照最大生命值（夜兰），部分按照防御（阿贝多E）

少数角色天赋可以受到到多种方式加成，如钟离(同时收到攻击力和最大生命加成)

#### 特殊天赋加成 SpecialTalentMult

仅有少数角色具有该天赋，宵宫E、行秋4命等

#### 其他基础伤害 OtherBaseDamage

适用于申鹤、云堇以及将来的激化反应

### 暴击 Crit

### 增伤 DamageBonus

### 抗性减免系数 EnemyResMult

$$
EnemyResMult = \begin{aligned}
1-0.5\cdot R   && R<0 \\
1-R &&  0<=R<=0.75 \\ \frac{1}{4\cdot R+1} 
&& R>0.75 \end{aligned}
$$

R为抗性

### 增幅反应加成系数&#x20;

> 增幅反应（蒸发、融化）本身不造成伤害，而是后置元素伤害提高

$$
AmplifyReactionMult = BaseRate \cdot (1+\frac{2.78 \cdot EM}{1400+EM}+ReactionBonus)
$$

对于火打水、冰打火，BaseRate为1.5，火打冰、水打火，BaseRate为2,

ReactionBonus指魔女4的15%反应系数提高、莫娜命座的反应系数提高等

对于不触发增幅反应的伤害，该加成系数为1

## 反应伤害计算方式（剧变反应）

> 剧变反应(超导、超载、感电、碎冰、扩散)在伤害计算时，敌人防御不参与计算，同时也不受暴击爆伤、增伤等加成
>
> 其中超载虽然为火伤，但是不能进一步触发蒸发、融化等增幅反应

### 计算方式如下

$$
Damage = (BaseDamage +OtherBaseDamage) \\ \cdot  TransformativeReactionMult 
\cdot AmplifyReactionMult\cdot EnemyResMult
$$

剧变反应BaseDamage仅与造成反应的角色等级和具体反应类型有关

$$
BaseDamage = LevelMult \cdot ReactionBaseRate
$$

| 反应类型 | ReactionBaseRate | 是否可以进一步参与增幅反应 |
| ---- | ---------------- | ------------- |
| 超载   | 4                | False         |
| 碎冰   | 3                | False         |
| 感电   | 2.4              | False         |
| 扩散   | 1.2              | True          |
| 超导   | 1                | False         |

### OtherBaseDamage

TBD,主要为将来激化反应准备

## 特殊类型伤害计算方式（深渊buff）
