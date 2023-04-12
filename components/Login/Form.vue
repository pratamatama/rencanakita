<script setup lang="ts">
import { Form } from 'vee-validate'
import { object, string } from 'yup'

const schema = object().shape({
  email: string().email().required().label('Alamat Email'),
  password: string().required().label('Password'),
})

const onSubmit = (data: any) => {
  console.log(data)
}

const onInvalidSubmit = (err: any) => {
  console.log('VALIDATION ERRORS:', err)
}
</script>

<template>
  <Form
    :validation-schema="schema"
    @submit="onSubmit"
    @invalid-submit="onInvalidSubmit"
  >
    <FormInput
      name="email"
      label="Alamat Email"
      placeholder="someone@example.com"
    />
    <FormInput class="mt-4" name="password" label="Password" type="password" />

    <div class="mt-4 flex justify-end">
      <a href="#" class="text-blue-600 hover:text-blue-800 text-sm"
        >Lupa password</a
      >
    </div>

    <BaseButton class="block w-full mt-4">Masuk dengan Email</BaseButton>
  </Form>
</template>
