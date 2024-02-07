<template>
	<input v-model="value" />
	<h1>{{ errorMessage }}</h1>
</template>

<script setup>
import { useField } from 'vee-validate';

const props = defineProps({
	name: String,
});

const { value, errorMessage } = useField(() => props.name);
</script>
