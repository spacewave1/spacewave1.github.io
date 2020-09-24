<template>
	<div class="line" :style="{width: `${length}px`,right:`${x1}px`,top:`${y1}px`, transform: `rotate(${angle}rad) translateY(${deltaY}px)`}">
		<hr :style="{color: `${color}`}">
	</div>
</template>

<script>
export default {
	name: 'Link',
	props: {
		x1:Number,
		y1:Number,
		x2:Number,
		y2:Number,
		color:String,
		id:String
	},
	computed: {
		length() {
			let deltaX = this.x2-this.x1
			let deltaY = this.y2-this.y1
			return Math.sqrt(deltaX*deltaX + deltaY*deltaY)
		},
		angle() {
			let deltaX = this.x2-this.x1
			let deltaY = this.y2-this.y1
			
			return -Math.atan(deltaY/deltaX)
		},
		deltaY() {
			return (this.y2-this.y1)/2;
		},
		deltaX() {
			return -(this.x2-this.x1)/2;
		},
	},
}
</script>

<style>
div.line {
	position: absolute;
}
hr {
	height: 10px;
}
</style>