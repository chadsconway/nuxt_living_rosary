<template>
	<div>
		<v-tooltip top open-on-hover open-delay="300" color="red">
			<template v-slot:activator="{ on }">
				<v-btn
					v-bind:class="[bigfab ? 'fabisbig' : 'shrinkfab']"
					class="my-10 mx-5"
					v-on="on"
					fab
					color="#142745"
					link
					href="https://www.gofundme.com/f/this-living-rosary-apostolate?utm_source=customer&utm_medium=copy_link&utm_campaign=p_cf+share-flow-1"
					bottom
					right
					fixed
					ripple
					v-bind:x-large="bigfab"
					:elevation="20"
				>
					<svg viewBox="0 0 496 496" width="30" height="30" class="icon">
						<use xlink:href="#christian-1" />
					</svg>
				</v-btn>
			</template>
			<span>Donate Now!</span>
		</v-tooltip>
	</div>
</template>
<script>
	export default {
		data() {
			return {
				disabled: false,
				openDelay: '0',
				closeDelay: '0',
				value: false,
				bigfab: true
			};
		},
		mounted() {
			this.onResize();
			window.addEventListener('resize', this.onResize, { passive: true });
		},
		methods: {
			onResize() {
				if (window.innerWidth < 600) {
					this.bigfab = false;
				} else {
					this.bigfab = true;
				}
			}
		}
	};
</script>

<style scoped>
	v-btn {
		position: fixed;
		z-index: 100;
	}
</style>
