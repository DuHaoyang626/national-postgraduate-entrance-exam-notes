---
title: 02 - Mermaid 图表
date: 2026-08-03
tags:
  - obsidian
  - mermaid
  - 图表
aliases:
  - Mermaid
  - 流程图
---

# 📈 Mermaid 图表

> [!abstract] 说明
> Obsidian **原生支持** [Mermaid](https://mermaid.js.org) 图表：把代码放进以 `mermaid` 为语言标记的代码块即可在阅读视图渲染。本页演示全部常用图表类型，并展示如何把节点链接到笔记。

## 一、流程图 Flowchart（graph）

```mermaid
graph TD
    A[开始] --> B{判断条件}
    B -->|是| C[执行动作]
    B -->|否| D[结束]
```

指定方向：`graph LR`（左右）、`graph TD`（上下）、`graph RL`、`graph BT`。

带子图（subgraph）的流程图：

```mermaid
graph LR
    subgraph 前端
        A[组件] --> B[状态管理]
    end
    subgraph 后端
        C[接口] --> D[数据库]
    end
    A --> C
```

## 二、把节点链接到笔记（internal-link）

用 `class 节点 internal-link;` 让节点变成**内部链接**，点击即可跳转到对应笔记：

```mermaid
graph TD
    A[📘 阅读语法] --> B[04-链接与反链接]
    A --> C[07-属性与标签]
    A --> D[06-Callout提示框]
    class B internal-link;
    class C internal-link;
    class D internal-link;
```

## 三、时序图 Sequence Diagram

```mermaid
sequenceDiagram
    participant U as 用户
    participant S as 服务端
    U->>S: 发起请求
    S-->>U: 返回结果
    S->>S: 内部处理
    U-->>U: 收到通知
```

## 四、类图 Class Diagram

```mermaid
classDiagram
    class Animal {
        +String name
        +makeSound()
    }
    class Dog {
        +bark()
    }
    Dog --|> Animal
```

## 五、状态图 State Diagram

```mermaid
stateDiagram-v2
    [*] --> 待办
    待办 --> 进行中
    进行中 --> 已完成
    进行中 --> 已暂停
    已暂停 --> 进行中
    已完成 --> [*]
```

## 六、实体关系图 ER Diagram

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : "下单"
    ORDER ||--|{ LINE_ITEM : "包含"
    CUSTOMER {
        string name
        string email
    }
    ORDER {
        int number
        date created_at
    }
```

## 七、用户旅程图 User Journey

```mermaid
journey
    title 我的工作日
    section 早上
        起床: 5: 我
        吃早餐: 3: 我
    section 下午
        编码: 5: 我, 同事
        开会: 2: 我
```

## 八、甘特图 Gantt

```mermaid
gantt
    title 项目排期
    dateFormat YYYY-MM-DD
    section 设计
        需求分析 :a1, 2026-08-01, 7d
        原型设计 :a2, after a1, 5d
    section 开发
        前端开发 :2026-08-13, 14d
        后端开发 :2026-08-13, 14d
```

## 九、饼图 Pie

```mermaid
pie title 时间分配
    "工作" : 40
    "学习" : 30
    "休息" : 30
```

## 十、四象限图 Quadrant

```mermaid
quadrantChart
    title 重要紧急矩阵
    x-axis 紧急程度 --> 低紧急
    y-axis 重要程度 --> 低重要
    quadrant-1 重要且紧急
    quadrant-2 重要不紧急
    quadrant-3 不重要不紧急
    quadrant-4 紧急不重要
    "处理危机" : [0.9, 0.9]
    "制定计划" : [0.2, 0.8]
    "刷手机" : [0.2, 0.2]
    "回邮件" : [0.8, 0.3]
```

## 十一、时间线 Timeline

```mermaid
timeline
    title 里程碑
    2026-01 : 立项
    2026-03 : 原型评审
    2026-06 : 正式上线
```

## 十二、Git 图 Gitgraph

```mermaid
gitGraph
    commit
    branch feature
    checkout feature
    commit
    commit
    checkout main
    merge feature
```

## 十三、思维导图 Mindmap

```mermaid
mindmap
  root((Obsidian 语法))
    基础
      Markdown
      HTML
      Mermaid
    专属扩展
      链接
      嵌入
      Callout
    进阶
      Bases
      Canvas
```

## 十四、折线/柱状图 XYChart

```mermaid
xychart-beta
    title "月度销售额"
    x-axis [一月, 二月, 三月, 四月]
    y-axis "销售额(万)" 0 --> 60
    bar [10, 25, 40, 55]
    line [8, 20, 35, 50]
```

## 十五、桑基图 Sankey

```mermaid
sankey-beta
    Electricity [75] --> Home [65]
    Home [65] --> Heating [55]
    Home [10] --> Appliances [10]
```

## 十六、块图 Block Diagram

```mermaid
block-beta
    columns 3
    A["需求"] B["设计"] C["开发"]
    A --> B --> C
```

## 十七、C4 图（系统上下文）

```mermaid
C4Context
    title 系统上下文图
    Person(user, "用户", "使用系统")
    System(app, "应用系统", "处理业务")
    BiRel(user, app, "使用")
```

## 小结

- 所有图都以 `mermaid` 语言标记的围栏代码块包裹。
- 节点可通过 `class X internal-link;` 链接到笔记，与 [[04-链接与反链接]] 联动。
- 更多语法与进阶选项见 [Mermaid 官方语法参考](https://mermaid.js.org/intro/syntax-reference.html)。

---

*返回总览：[[Home]] · 上一篇：[[01-普通Markdown语法]] · 下一篇：[[03-HTML语法]]*
