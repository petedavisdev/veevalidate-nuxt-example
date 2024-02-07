<template>
	<div>
		<label>
			{{ props.name }}
		</label>

		<slot />

		<p>
			{{ errorMessage }}
		</p>
	</div>
</template>

<script setup lang="ts">
import { useFieldError } from 'vee-validate';

const props = defineProps<{
	name: string;
}>();

const errorMessage = useFieldError(props.name);
</script>
