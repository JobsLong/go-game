# 使用 Vue 制作的 Go Game

![Screenshot](http://7xih70.com1.z0.glb.clouddn.com/15-12-17/92281101.jpg)

### 主要代码

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
