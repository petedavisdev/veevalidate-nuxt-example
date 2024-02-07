<template>
	<div>
		<label>
			{{ props.label }}
		</label>

		<slot />

		<p>
			{{ errorMessage }}
		</p>
	</div>
</template>

<script setup lang="ts">
import { useField } from 'vee-validate';

const props = defineProps<{
	name: string;
	label: string;
}>();

const { errorMessage } = useField(() => props.name);
</script>
