# 🔥Critical Render Path Optimization

<img src="./assets/images/render_path_opt.png" alt="Render Path Performance" width="700" height="400">

---

## ⚡Critical Render Path

> This is the typical path browser follows to render a webpage🎨

<img src="./assets/images/critical_render_path.png" alt="Render Path Performance" width="700" height="400">

### ⚙1st Step

- Load styles in the **\<head\>** of the HTML file.
- Load scripts right before **\</body\>**. Scripts usually take time to manipulate DOM. It is ideal to keep at end of the body.

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			h1 {
				color: green;
			}
			button {
				padding: 10px 10px;
				background: orangered;
			}
		</style>
	</head>
	<body>
		<h1>Hello World Website</h1>
		<button type="submit">Submit</button>

		<script>
			alert('Hello 😃😃');
		</script>
	</body>
</html>
```

### ⚙2nd Step

?> **DOM + CSSOM = Render Tree**

- Only load what ever is needed.
- Consider above the fold loading.
- Use **Media attributes**.
- less specificity

<details>
  <summary>Click to expand to view example!</summary>

```html
<!--
HTML
  #1 Load <style> in <head>
  #2 Load <script> right before /body
CSS
  #3 Load only what is needed
  #4 Above the fold loading
  #5 Media attributes
  #6 Less specificity
JS
  #7 Load scripts asynchronously
  #8 Defer loading of scripts
  #9 Minimize DOM manipulation
  #10 Avoid long running Javascript
-->

<!DOCTYPE html>
<html>
	<head>
		<title>Critical Render Path</title>

		<!-- External CSS-->
		<!--media="all" is the default value -->
		<link rel="stylesheet" href="./style.css" media="all" />
		<!-- #5 download in the background and not disrupt the page load if screen doesnt match -->
		<!-- <link rel="stylesheet" href="./style2.css" media="only screen and (min-width:501px)"> -->

		<!-- Internal CSS Pro: Allows us to not have to request CSS file -->
		<style>
			h1 {
				font-size: 30px;
			}
		</style>

		<!-- #2 Render blocking and Parser blocking JS -->
		<!-- <script>alert('check')</script> -->
	</head>
	<body>
		<!-- Inline CSS -->
		<h1 style="background-color: yellow">Hi</h1>
		<button>Click Me</button>

		<!-- #4 Above the fold loading -->
		<!--   <h2 class="important">
    Important above the fold view
  </h2>

  <h2 class="secondary">
    Below the fold content. You won't see until after page loads.
  </h2> -->

		<!-- #7/8 defer and async loading -->
		<!--   <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script type="text/javascript" src="./script.js"></script>
  <script type="text/javascript" src="./script2.js"></script>
  <script type="text/javascript" src="./script3.js"></script>
  <script>
    const button = document.querySelector("button");
    button.addEventListener("click", function () {
      alert("Stop Clicking Me!");
    });
  </script> -->

		<!-- #4 above the fold loading -->
		<!--   <script>
    const loadStyleSheet = (src) =>{
        if (document.createStyleSheet) {
          document.createStyleSheet(src);
        }
        else {
          const stylesheet = document.createElement('link');
          stylesheet.href = src;
          stylesheet.rel = 'stylesheet';
          stylesheet.type = 'text/css';
          document.getElementsByTagName('head')[0].appendChild(stylesheet);
        }
    }
      // All of the objects are in the DOM, and all the images, scripts, links have finished loading.
      window.onload = function () {
        console.log('window done!')
        loadStyleSheet('./style3.css');
      };
  </script> -->
	</body>
</html>
```

</details>

### ⚙3rd and 8th Steps

- Load scripys asynchronously
- Defer loading of scripts.
- Minimize DOM manipulation.
- Avoid long running Javascript.

<img src="./assets/images/async_js.png" alt="Async JS" width="700" height="400">

?> If core functionaility need Javascript then use **async**, if not use **defer**.

**Deferred execution \<script defer\>**

Simply put: delaying script execution until the HTML parser has finished. A positive effect of this attribute is that the DOM will be available for your script. However, since not every browser supports defer yet, don’t rely on it!

**Asynchronous execution \<script async\>**

Don’t care when the script will be available? Asynchronous is the best of both worlds: HTML parsing may continue and the script will be executed as soon as it’s ready. I’d recommend this for scripts such as Google Analytics.

<details>
  <summary>Click to expand to view example!</summary>

```html
<!--
HTML
  #1 Load <style> in <head>
  #2 Load <script> right before /body
CSS
  #3 Load only what is needed
  #4 Above the fold loading
  #5 Media attributes
  #6 Less specificity
JS
  #7 Load scripts asynchronously
  #8 Defer loading of scripts
  #9 Minimize DOM manipulation
  #10 Avoid long running Javascript
-->

<!DOCTYPE html>
<html>
	<head>
		<title>Critical Render Path</title>

		<!-- External CSS-->
		<link rel="stylesheet" href="./style.css" media="all" />
	</head>
	<body>
		<h1>How Fast?</h1>
		<button>Click Me</button>
		<img
			src="https://5.imimg.com/data5/GR/PD/MY-4659120/img-20161230-wa0170-500x500.jpg"
		/>

		<!-- Render blocking and Parser blocking JS -->
		<!--   <script>
    var button = document.querySelector("button");
    button.style.color = "red";
  </script> -->
		<script src="./script.js"></script>
		<script src="./script2.js" async></script>
		<script src="./script3.js"></script>
		<script>
			const button = document.querySelector('button');
			button.addEventListener('click', function () {
				alert('Stop Clicking Me!');
			});
		</script>
	</body>
</html>
```

</details>