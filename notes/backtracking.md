---
created: 2024-03-26T20:44
updated: 2024-07-20T19:07
---
#patterns 
when you need to find a correct series of choices

> "pruning the recursion tree" - normal dfs will traverse every node, backtracking allows you to escape a path once invalidated

you will need to "backtrack" to the previous choice when landing on an incorrect choice

can be done recursively or non-recursively

- recursive is unintuitive as it is harder to see the backtracking done in code