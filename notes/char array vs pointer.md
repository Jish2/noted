---
created: 2024-03-10T03:49
updated: 2025-09-30T17:02
---
#languages/cpp #languages/c 
`char[]` is a "constant pointer" where as `char *` can be moved

```c++
char[] str1 = "foo";

str1++; // invalid

char  *str2 = "foo";

str++ // valid
```

`char[]` : char array stored on stack
`char *` : pointer to string literal stored anywhere, cannot modify the string