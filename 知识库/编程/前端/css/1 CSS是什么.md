# CSS

**CSS** （Cascading Style Sheets，层叠样式表）是用来控制网页在[浏览器](https://developer.mozilla.org/zh-CN/docs/Glossary/Browser)中的显示外观的声明式语言。

浏览器会根据 CSS 的样式定义将其选定的元素显示为恰当的形式。CSS 的样式定义包括属性和属性值，它们共同决定网页的外观。

CSS 与 [HTML](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML) 和 [JavaScript](https://developer.mozilla.org/zh-CN/docs/Glossary/JavaScript) 并称 Web 三大核心技术。一般用它来定义 [HTML 元素](https://developer.mozilla.org/zh-CN/docs/Glossary/Element)的样式，但它也能用于其他标记语言，如 [SVG](https://developer.mozilla.org/zh-CN/docs/Glossary/SVG) 和 [XML](https://developer.mozilla.org/zh-CN/docs/Glossary/XML)。

CSS 规则由包含一组与[选择器](https://developer.mozilla.org/zh-CN/docs/Glossary/CSS_Selector)关联的[属性](https://developer.mozilla.org/en-US/docs/Glossary/Property/CSS "此页面目前仅提供英文版本")定义。以下示例将页面中的所有 HTML 段落显示为黑色背景和黄色文本：

CSSCopy to Clipboard

```
/* p 选择器表示页面中的所有段落都会被该规则所影响 */
p {
  /* color 属性用来定义文本颜色，这里为黄色 */
  color: yellow;

  /* background-color 属性用来定义元素的背景色，这里为黑色 */
  background-color: black;
}
```

CSS 中的第一个“C”（Cascading）表示“层叠”，意为多个选择器之间具有特定的优先级。这一点非常重要，因为复杂网站可能会有非常多的 CSS 规则，因此必须规定好这些规则的优先级，以免乱套。
