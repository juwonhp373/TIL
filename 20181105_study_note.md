```html
html
	head
		link(rel="stylesheet" href="/stylesheets/20181105/just.css")
		link(rel="stylesheet" href="https://use.fontawesome.com/releases/v5.5.0/css/all.css"
		integrity="sha384-B4dIYHKNBt8Bc12p+WXckhzcICo0wtJAoU8YZTY5qE0Id1GSseTk6S+L3BlXeVIU" crossorigin="anonymous")
	body
		.particle-zone
			.particle-back
			.particle-back
			.particle-back
			.particle-back
			.particle-back
			.particle-back
			.particle-back
			.particle-back
			.particle-back
```

```sass
*
  box-sizing: border-box
  background: rgba(255, 255, 255, 0.2)

body
  margin: 0
  padding: 0

.particle-zone
  width: 100%
  height: 100%
  display: inline-block
  padding: 50px 50px 0
  background: #00acc1
  .particle-back
    display: block
    width: 200px
    height: 200px
    margin: 0 20px 20px 0
    background: white
```