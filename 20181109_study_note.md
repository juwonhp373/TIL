```pug
html
	head
		link(rel="stylesheet" href="/stylesheets/20181105/just.css")
		link(rel="stylesheet" href="https://use.fontawesome.com/releases/v5.5.0/css/all.css"
		integrity="sha384-B4dIYHKNBt8Bc12p+WXckhzcICo0wtJAoU8YZTY5qE0Id1GSseTk6S+L3BlXeVIU" crossorigin="anonymous")
	body
		.black-cover-zone.flex
			.arrow
				i.fas.fa-angle-left
			.image-field
			.arrow
				i.fas.fa-angle-right
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
  //background: rgba(255, 255, 255, 0.2)

body
  margin: 0
  padding: 0

.black-cover-zone
  position: fixed
  top: 0
  left: 0
  width: 100vw
  height: 100vh
  background: rgba(0, 0, 0, 0.7)
  align-items: center
  padding: 20px 20px
  .arrow
    font-size: 100px
    color: white
  .image-field
    height: 100%
    width: 600px
    margin: 0 auto
    background: rgba(255, 255, 255, 0.8)


.particle-zone
  width: 100%
  height: 100%
  //display: inline-block
  padding: 50px 50px 0
  background: #00acc1
  .particle-back
    display: inline-block
    width: 200px
    height: 200px
    margin: 0 20px 20px 0
    background: white


.flex
  display: flex
.flex--1
  flex: 1
.align-center
  align-items: center
  justify-content: center
```