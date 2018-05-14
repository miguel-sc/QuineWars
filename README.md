# [QuineWars](https://quinewars.com)

An HTML file, that prints out its own source code in the style of the famous Star Wars opening crawl.
Check it out on [quinewars.com](https://quinewars.com).

## How it works

A [quine](https://en.wikipedia.org/wiki/Quine_%28computing%29) is a program that produces a copy of its own source code as its output.
An example for a basic [HTML+CSS quine](https://rosettacode.org/wiki/Quine#HTML_.2B_CSS):
```
<!DOCTYPE html>
<html>
<head>
	<title>HTML/CSS Quine</title>
	<style type="text/css">
	* { font: 10pt monospace; }

	head, style { display: block; }
	style { white-space: pre; }

	style:before {
		content:
			"\3C""!DOCTYPE html\3E"
			"\A\3Chtml\3E\A"
			"\3Chead\3E\A"
			"\9\3Ctitle\3E""HTML/CSS Quine""\3C/title\3E\A"
			"\9\3Cstyle type=\22text/css\22\3E";
	}
	style:after {
		content:
			"\3C/style\3E\A"
			"\3C/head\3E\A"
			"\3C""body\3E\3C/body\3E\A"
			"\3C/html\3E";
	}
	</style>
</head>
<body></body>
</html>
```
The style tag in HTML can be made visible by setting the display property to block.
To display the entire source code we need to additionally print out the rest of the html code that comes before and after the style tag. The command to display the rest of the code has to come from within the style tag, so that the command itself will be printed out as well. Not doing so, will lead to an infinite recursion problem.

## Writing a styled quine

In order to give our quine some science fiction styling, we start off by writing a website that prints out some placeholder text in the desired style. We can then remove the placeholder text and move our style element into that location. Finally, we set the style tag's visibility and add the rest of the HTML file to the content of the style tag.

---

QuineWars should render correctly on all major browsers, except for Internet Explorer. If someone finds a solution, a pull request is always greatly appreciated.

Show some :heart: by giving this repository a :star:
