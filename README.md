#	dyeing
__Make text more accessible.__

This package helps you to color your text in a meaningful way. In other words, *dyeing* will generate colored text according to semantic names instead of color or style names.  
本模块采用基于语义的文本渲染方法。换句话说，*dyeing* 将依据语义名称来决定文本的色彩，而不是像 *colors* 或者 *chalk* 那样直接采用颜色或样式名称来命名其方法。

There are different color-themes available.  
提供多种颜色风格供选择。

##  Table of Contents

* [Get Started](#get-started)
* [Themes](#themes)
* [Semantic Names](#semantic-names)
* [API](#api)
* [Why *dyeing*](#why-dyeing)
* [References](#references)

##	Links

*	[CHANGE LOG](./CHANGELOG.md)
*	[Homepage](https://github.com/YounGoat/dyeing)

##	Get Started

```javascript
const dyeing = require('dyeing');

// Return colored string.
let tI = dyeing('INFO');
let tW = dyeing.warning('WARNING');
let tS = dyeing.success('SUCCESS');
let tD = dyeing.danger('DANDER');
console.log(tI, tW, tS, tD);

// Switch to theme "blue".
let blue = dyeing.theme('blue');
let bI = blue.info('INFO');
let bW = blue.warning('WARNING');
let bS = blue.success('SUCCESS');
let bD = blue.danger('DANDER');
console.log(bI, bW, bS, bD);

// Print colored text directly.
let printer = dyeing.printer(true /* without EOL */);
printer('INFO');
printer.warning('WARNING');
printer.success('SUCCESS');
printer.danger('DANDER');
```

##	Themes

*	(default)
*	dark
*	light
*	blue

##	Semantic Names

*	Bootstrap-Style Semantic Names  
	Bootstrap 风格的语义名称
	*	danger
	*	info
	*	primary
	*	secondary
	*	success
	*	warning

*	HTML-Style Semantic Names  
	HTML 风格的语义名称  
	*	cite
	*	code
	*	dd
	*	dt
	*	em
	*	kbd
	*	mark
	*	q
	*	quote = q
	*	strong

##	API

*	string __dyeing.[ *SemanticName* ]__( string *text* )  
	Generate colored text.

*	Dyeing __dyeing.theme__( string *themeName* )  
	Generate another *dyeing* with specified theme.

*	Dyeing __dyeing.printer__( boolean *noEOL* )  
	Generate anthoer *dyeing* whose member function will print colored text directly instead of returning it.

##  Why *dyeing*  

Most terminals are black-backgrounded. However, *terminal.app* in MacOS is white-backgrounded by default, while *PowerShell.exe* in Windows is blue-backgrounded by default. Text with fixed color may be friendly for one terminal, but unsightly in another one. Developers need some text render compatible with different terminals. That's why I wrote *dyeing*.

多数终端是黑色背景的。然而，MacOS 中 *terminal.app* 的默认背景是白色，而 Windows 中 *PowerShell.exe* 的默认背景是蓝色。特定颜色的文本在一种终端上具有较好的可读性，但在另一种终端上则未必。开发者需要一种能够兼容不同终端的文本渲染工具。这就是我开发 *dyeing* 的初衷。

##  References

*	Material Design: [The color system](https://material.io/design/color/the-color-system.htm)