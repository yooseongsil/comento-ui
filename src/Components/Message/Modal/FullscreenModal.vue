<template>
	<Modal :show="show" :show-close-button="showCloseButton" @close="close">
		<slot />
	</Modal>
</template>

<script>
import Modal from '@/src/Components/Message/Modal/Modal';

export default {
	name: 'FullscreenModal',
	props: {
		show: {
			type: Boolean,
			default: false,
		},
		showCloseButton: {
			type: Boolean,
			default: true,
		},
	},
	methods: {
		close() {
			this.$emit('update:show', false);
		},
	},
	components: { Modal },
};
</script>

<style lang="scss" scoped>
.c-modal {
	&--mask::v-deep {
		.c-modal--container {
			max-width: 100%;
			width: 100%;
			height: 100%;
			border-radius: 0;
		}
	}
}
</style>
