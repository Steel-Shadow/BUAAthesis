# 2024 计算机科学方法论

使用 `latexmk -xelatex` 或 `xelatex + bibtex` 编译。

```shell
latexmk -xelatex -outdir=latexOut -interaction=nonstopmodef main.tex
```

[xelatex 和 xelatexmk 的区别](https://tex.stackexchange.com/questions/108688/xelatex-vs-xelatexmk-compilation-what-s-the-difference)

## 修改参考文献格式

为了偷懒，我直接修改了 `gbt7714-numerical.bst` ，删除了字样 `S.l. s.n.`。

正确的处理方法：

根据 `GB/T 7714-2005` 中 `8.4 节 出版项` 中相关规定：

+ 无出版地的中文文献著录 “出版地不详”，外文文献著录 “S.l.”
+ 无出版者的中文文献著录 “出版者不详”，外文文献著录 “s.n.”

相应的解决方法为

+ 若编译的参考文献条目中出现 “出版地不详” 或 “S.l.”，请在相应的 bib 条目中添加 address 相关信息
+ 若编译的参考文献条目中出现 “出版者不详” 或 “s.n.”，请在相应的 bib 条目中添加 publisher 相关信息

实际使用中应避免出现 `［S.l.］:［s.n.］` 这样的著录形式。
