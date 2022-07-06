# 基本伤害计算方式

## 非反应伤害计算方式(大多数伤害）



$$
DamageExp = (BaseDamage \cdot SpecialTalentAmplify+ OtherBaseDamage) \\ \cdot (1+CritRate \cdot CritDmg)\cdot (1+DamageBonus) \cdot  AmplifyReactionMult 
\\ \cdot EnemyDefMult \cdot EnemyResMult
$$

### ​基础伤害 BaseDamage

$$
BaseDamage = ATK \cdot TalentRate+HP \cdot TalentRate+Def\cdot TalentRate
$$

​默认情况下按照按照攻击力，部分按照最大生命值（夜兰），部分按照防御（阿贝多E）

少数角色天赋可以受到到多种方式加成，如钟离(同时收到攻击力和最大生命加成)

### 特殊天赋增幅 SpecialTalentMult

仅有少数角色具有该天赋，宵宫E、行秋4命等

### 其他基础伤害 OtherBaseDamage

适用于申鹤、云堇以及将来的激化反应

## 反应伤害计算方式（剧变反应）

> 剧变反应在伤害计算时，敌人防御不参与计算

## 特殊类型伤害计算方式（深渊buff等）
