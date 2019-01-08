# Vuetify
## Theme
### Customizify has a standard theme applied for all components.
> primary, secondary, accent, error, info, success, warning

If need change, pass a *theme* property to the `Vue.use` function. You can choose to modify all or only some of the theme properties, with the remaining inheriting from the default.

```ts
import colors from 'vuetify/es5/util/colors' // you can also use the pre-defined material colors.

Vue.use(vuetify, {
	theme: {
		primary: '#3f51b5',
		secondary: '#b0bec5',
		accent: colors.shades.black
	}
})
```

```ts
this.$vuetify.theme.primary = '#4caf50'
```

## Grid

## Breakpoints
5 types of media breakpoints
Material Design Viewport Breakpoints

* Extra small:  `xs`
-> small to large handset ( <600px )
* Small:  `sm`
-> small to medium tablet ( 600px > < 960px )
* Medium:  `md`
-> large tablet to laptop ( 960px > < 1264* ) 
* Large: `lg`
-> desktop ( 1264 > < 1904px* )
* Extra large: `xl`
-> 4k and ultra-wides ( > 1904px* )

> * -16px on Desktop


## `$vuetify.breakpoint`
```ts
export default {
	mounted () {
		console.log(this.$vuetify.breakpoint)
	},

	computed: {
		imageHeight () {
			switch (this.$vuetify.breakpoint.name) {
				case 'xs': return '220px'
				case 'sm': return '400px'
				case 'md': return '500px'
				case 'lg': return '600px'
				case 'xl': return '800px'
			}
		}
	}	
}
```

## Display
### Display
Specify the elements 	`display` property. -> `d-{display}`.
	* `d-inline-flex` : sets the element display property to `inline-flex`
	* `d-flex`
	* `d-inline-block`
	* `d-block`
	* `d-inline`
	* `d-none`


### Visibility
Display an element based upon the current *viewport*
These classes can be applied using the format of -> `hidden-{breakpoint}-{condition}`

*condition* applies the class base on:
	* `only` : hide the element only on `xs` through `xl` breakpoints.
	* `and-down` : hide the element on the specified breakpoint and down `sm` through `lg` breakpoints
	* `and-up` : hide the element on the specified breakpoint and up `sm` through `lg` breakpoints
	* Additionally, /media types/ can be targeted using the `only` condition. Both `hidden-screen-only` and `hidden-print-only` are supported.

### Overflow
`overflow-{axis}-hidden` or simply `overflow-hidden`.
	* `overflow-hidden` : hide overflow on both the x and y axis.
	* `overflow-y-hidden` : hide overflow on the y axis.
	* `overflow-x-hidden` : hide overflow on the x axis.
## Text alignment
Alignment classes helps position text based on viewport size.

```ts
<template>
	<v-card>
		<v-card-text>
			<p class="text-lg-right">Right align on large viewport sizes</p>
			<p class="text-md-center">Center align on medium viewport sizes</p>
			<p class="text-sm-left">Left align on small viewport sizes</p>
			<p class="text-xs-center">Center align on all viewport sizes</p>
			<p class="text-xs-right">Right align on all viewport sizes</p>
		</v-card-text>
	</v-card>
</template>
```

## Spacing
Update layout without creating new classes.

## 개발 용어
* boilerplate 보일러 플레이트
> 변경없이 계속하여 재사용할 수 있는 저작품을 말한다.
> 철강제조 부문에서 증기 보일러 내에 사용되는 커다란 압연 강판 에서 유래되었다. 
> 오랜기간동안 시험되었으며, 강철처럼 튼튼하다, 또는 반복적으로 재사용하기에 충분할 정도로 강력한 어떤 물건으로 만들어졌다.

* opt to
> ~ 을 선택하다.

* breakpoint 브레이크 포인트
> 중단점, 중지점 은 소프트웨어 개발에서 프로그램을 의도적으로 잠시 또는 아예 멈추게 하는 장소를 가리키며 디버깅 목적으로 넣는 것이다.

* under the hood
> 자동차 보닛 안에를 본다.
> 겉으로 드러난것이 아닌 구현을 어떻게 했는지 본다.

## References
> [Vuetify_Theme](https://vuetifyjs.com/en/framework/theme)
> [Vuetify_Breakpoints](https://vuetifyjs.com/ko/framework/breakpoints)
> [Vuetify_Text Alignment](https://vuetifyjs.com/en/framework/alignment)
> [Vuetify_Display](https://vuetifyjs.com/en/framework/display)