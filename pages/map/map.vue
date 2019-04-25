<template>
	<view>
		<map class="map" id="map"
		 :longitude="longitude" :latitude="latitude" :controls="controls"
		 show-location
		 @controltap="controltap"
		 @tap="mapTap"></map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				longitude: '',
				latitude: '',
				scale: 16,
				controls: [{
					id: 1,
					position: {
						left: 300,
						top: 475,
						width: 50,
						height: 50
					},
					iconPath: require('static/images/map/position.png'),
					clickable: true
				}]
			};
		},
		onLoad () {
			this.mapCtx = uni.createMapContext('map',this)
		},
		onShow() {
			var _this = this;
			uni.getLocation({
				type: 'gcj02',
				success: function(res) {
					console.log(res)
					_this.longitude = res.longitude
					_this.latitude = res.latitude
				},
			})
		},
		methods:{
			controltap (ev) {
				if (ev.mp.controlId === 1) {
					this.mapCtx.moveToLocation({
						longitude: this.longitude,
						latitude: this.latitude
					})
				}
			},
			mapTap (ev) {
				console.log(ev)
			}
		}
	}
</script>

<style lang="scss">
	.map {
		width: 100vw;
		height: 100vh;
		position:relative;
	}
</style>
