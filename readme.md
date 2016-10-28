# 使用 Vue 制作的 Go Game

![Screenshot](/screenshot.jpg)

### 非黑即白

```javascript
new Vue({
  el: 'body',
  data: {
  	current: true, // black
  	white_count: 360,
  	black_count: 361
  },
  methods: {
  	do: function (event) {
  		if(event.target.className.match(new RegExp('(\\s|^)white|black(\\s|$)'))) {return}
  		var name = this.current ? 'black' : 'white'
		event.target.className += ' ' + name
		if (this.current) {this.black_count-=1} else {this.white_count-=1}
		this.current = !this.current
  	}
  }
})
```
