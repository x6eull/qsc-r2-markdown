# 概述
部署url: [https://objflux.com/tool/of/markdown](https://objflux.com/tool/of/markdown)  
markdown的实现使用了我另一个项目的部分框架&工具链&组件&utils，此repo仅给出markdown作答的**核心代码**，它无法独立运行。  
尽管如此，核心代码也给出了较完整的实现逻辑，即使用正则、递归来氵

# 支持的语法
\# ~ \#\#\#\#\#\# h1~h6标题  
使用行尾2+空格或空行来换行  
\``行内代码块`\`  
*\*斜体\** **\*\*粗体\*\*** ***\*\*\*斜体粗体\*\*\****

\`\`\`
```
"围栏"代码块
```
\`\`\`

可在`# 标题`内嵌套斜体等（但由于h5元素有部分内建样式表覆盖，视觉效果不可预期）  
\[描述\]\(链接href\)  
\!\[alt描述\]\(图片src\)

# 开发故事
1. 感觉不如Vanilla
2. 写出了连续否定断言🤡`(?!>\\)\*(?!>\\)\*(?!>\\)\*`(后两个断言为noop)
3. &lt;a>的样式受大项目样式表影响，为恢复原生样式尝试🤡`all: unset`/`all: initial`
4. 想引库，但大项目不同意（等后续完善平台功能可能支持工具包管理甚至共享包）
5. `Each child in an array or iterator should have a unique "key" prop`设计初衷很好，但不支持object/symbol的key，纯纯摆设
6. h1~h6是用switch对应的，React狠狠输
