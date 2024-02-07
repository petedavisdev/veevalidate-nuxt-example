<script setup lang="ts">
import { useField, useForm } from 'vee-validate';
import { toTypedSchema } from '@vee-validate/zod';
import { z } from 'zod';

const rawValidationSchema = z.object({
	email: z.string().min(1).email(),
});

type FormSchema = z.input<typeof rawValidationSchema>;
const validationSchema = toTypedSchema(rawValidationSchema);

const { handleSubmit } = useForm({
	validationSchema,
});

const { value: email } = useField<FormSchema['email']>('email');
</script>

<template>
	<form @submit="handleSubmit">
		<AppField name="email">
			<AppInput name="email" />
		</AppField>
	</form>
</template>
