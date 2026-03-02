# 🧠 LeetCode 刷题指南

<div align="center">

![LeetCode](https://img.shields.io/badge/LeetCode-算法刷题-FFA116?style=for-the-badge&logo=leetcode&logoColor=white)
![Progress](https://img.shields.io/badge/状态-持续更新-4CAF50?style=for-the-badge)
![Language](https://img.shields.io/badge/语言-中文-red?style=for-the-badge)

**系统化刷题，从零到 Offer**

[Hot 100](#-hot-100) • [刷题顺序](#-刷题顺序) • [专题分类](#-专题分类) • [易错点](#️-易错点总结)

</div>

---

## 📌 项目简介

本仓库收录了 LeetCode 高频考题的解题思路、代码模板与易错点总结，按专题分类整理，帮助你系统化地备战算法面试。

---

## 🔥 Hot 100

LeetCode 官方精选的 100 道高频面试题，覆盖各类核心数据结构与算法。

> 建议在掌握各专题基础后，以此作为综合训练与查漏补缺的题单。

📄 [查看 Hot 100 题单 →](./hot100.md)

---

## 📋 刷题顺序

推荐按照以下顺序学习，循序渐进，避免盲目刷题：

```
链表 → 哈希表 → 双指针 → 栈与队列 → 滑动窗口
  → 二分查找 → 动态规划 → 二叉树 → 回溯 → 图论
```

---

## 📚 专题分类

| 专题 | 难度 | 核心思想 | 题目数 |
|------|------|----------|--------|
| [🔗 链表](./链表.md) | ⭐⭐ | 指针操作、哨兵节点 | 20+ |
| [#️⃣ 哈希表](./哈希表.md) | ⭐⭐ | 空间换时间 | 15+ |
| [👆 双指针](./双指针.md) | ⭐⭐ | 快慢指针、左右指针 | 20+ |
| [📦 栈与队列](./栈与队列.md) | ⭐⭐ | LIFO / FIFO | 15+ |
| [🪟 滑动窗口](./滑动窗口.md) | ⭐⭐⭐ | 维护窗口状态 | 15+ |
| [🔍 二分查找](./二分查找.md) | ⭐⭐⭐ | 左右边界收缩 | 20+ |
| [💡 动态规划](./动态规划.md) | ⭐⭐⭐⭐ | 状态转移方程 | 30+ |
| [🌲 二叉树](./二叉树.md) | ⭐⭐⭐ | 递归、BFS、DFS | 25+ |
| [↩️ 回溯](./回溯.md) | ⭐⭐⭐ | 枚举 + 剪枝 | 20+ |
| [🗺️ 图论](./图论.md) | ⭐⭐⭐⭐ | BFS、DFS、并查集 | 20+ |

---

## ⚙️ 刷题流程

## ⚙️ 刷题流程

**① 选择专题** → **② 学习核心模板** → **③ 刷例题理解思路** → **④ 独立完成练习题**

如果尚未掌握，回到 ② 重新巩固模板；掌握后继续 → **⑤ 总结易错点** → **⑥ 进入下一个专题**

**建议节奏：**
- 每个专题 3～5 天
- 先看思路，再写代码，最后对比最优解
- 做完一遍后，定期回顾

---

## ⚠️ 易错点总结

<details>
<summary><b>🔗 链表</b></summary>

- 忘记处理头节点为空的边界情况
- 反转链表时丢失 `next` 指针
- 快慢指针奇偶长度处理不一致

</details>

<details>
<summary><b>🌲 二叉树</b></summary>

- 递归时未正确传递返回值
- 层序遍历忘记记录每层节点数
- 前中后序遍历的迭代写法容易混淆

</details>

<details>
<summary><b>💡 动态规划</b></summary>

- dp 数组初始化错误
- 状态转移方向（正向/逆向）搞反
- 未考虑边界条件（i=0 或 j=0）

</details>

<details>
<summary><b>↩️ 回溯</b></summary>

- 忘记回溯（撤销选择）
- 剪枝条件写错导致漏解或超时
- 结果收集时机（叶子 vs 中间节点）

</details>

---

## 🛠️ 代码模板

### 二分查找
```python
def binary_search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = left + (right - left) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

### 回溯框架
```python
def backtrack(path, choices):
    if 满足结束条件:
        result.append(path[:])
        return
    for choice in choices:
        做选择
        backtrack(path, choices)
        撤销选择
```

### BFS 模板
```python
from collections import deque

def bfs(graph, start):
    queue = deque([start])
    visited = {start}
    while queue:
        node = queue.popleft()
        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

---


---

## 🤝 贡献

欢迎提交 PR 补充题解或纠正错误！

1. Fork 本仓库
2. 新建分支 `git checkout -b feat/your-topic`
3. 提交更改 `git commit -m 'add: 新增XX题解'`
4. 推送分支并发起 Pull Request

---

<div align="center">

⭐ 如果这个项目对你有帮助，请给个 Star！

**持续更新中 · 欢迎 Star & Fork**

</div>
