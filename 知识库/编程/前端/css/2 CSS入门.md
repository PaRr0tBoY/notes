Selector {
	property:value;
	...
	property:value;
}

- 所有声明语句都要以分号结尾，最后一条声明语句后面的分号是可以省略的，不过更容易出错；
- 为html元素添加类名，<li class="类名">，然后就可以在css文件中通过 .类名 来为此特定类的html元素添加层叠样式

根据位置确定样式{
	包含选择符 space {
	例如li em，会选择li标签中的em；
	嵌套包含，article p span就是article中的p中的span元素；
	}
	相邻选择符 + {
	例如h1+p可以给h1邻近的p标签元素添加相同层级的段落样式；
	当第二个元素_紧跟在_第一个元素之后，并且两个元素都是属于同一个父元素的子元素，则第二个元素将被选中；
	嵌套选择，h1+ul+p就是h1之后的ul之后的p；
	}
}

根据状态确定样式{
	a:link
	a:hover
	a:visited
	...
}

层叠：后面的样式会替换样式表中较早出现的冲突样式。这就是**层叠**规则。

优先级：一个类被认为是更具体的，因此它比元素选择器**优先级**更高，所以它取消了其他冲突的样式声明。

- 如果属性未知或某个值对给定属性无效，则声明被视为_无效_，并被浏览器的 CSS 引擎完全忽略。
- 在 CSS（和其他 web 标准）中，当语言表达存在不确定性时，美式拼写被视作公认的标准。例如，“颜色”应该始终拼写为 `color`，`colour` 是不起作用的。