<script setup>
import { useForm } from 'vee-validate';
import { toTypedSchema } from '@vee-validate/zod';
import { z } from 'zod';

const { errors, defineField } = useForm({
	validationSchema: toTypedSchema(
		z.object({
			email: z.string().min(1).email(),
		})
	),
});

const [email, emailAttrs] = defineField('email');
</script>

<template>
	<AppField name="email" label="Email">
		<input v-model="email" v-bind="emailAttrs" />
	</AppField>
</template>
