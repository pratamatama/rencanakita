<script setup lang="ts">
import { Form } from 'vee-validate'
import { object, string } from 'yup'

const client = useSupabaseAuthClient()
const router = useRouter()

const loginWithGoogle = async () => {
  const { error, data } = await client.auth.signInWithOAuth({
    provider: 'google',
  })

  if (error) {
    return alert('Something went wrong!')
  }

  console.log(data)
  // router.push({ name: 'dashboard' })
}

const loginWithEmail = (data: any) => {
  console.log(data)
}

const invalidLoginWithEmail = (err: any) => {
  console.log('VALIDATION ERRORS:', err)
}

const schema = object().shape({
  email: string().email().required().label('Alamat Email'),
  password: string().required().label('Password'),
})
</script>

<template>
  <div class="h-screen">
    <div class="md:grid md:grid-cols-12 h-full">
      <div class="h-full md:col-span-8 lg:col-span-6 xl:col-span-4">
        <div class="h-full bg-white dark:bg-gray-800 px-8 md:px-16 2xl:px-20">
          <div class="h-full flex flex-col justify-center">
            <div>
              <h1 class="text-2xl font-medium">RencanaKita</h1>
              <p class="mt-1">Satu aplikasi, untuk segala rencana kita.</p>
            </div>

            <BaseButton
              @click="loginWithGoogle"
              type="button"
              class="block w-full !bg-gray-200 dark:!bg-gray-700 hover:!bg-gray-300 dark:hover:!bg-gray-600 mt-8"
            >
              <span class="flex justify-center items-center">
                <IconsGoogle class="w-5 h-5" />
                <span class="mx-2">Masuk dengan Google</span>
              </span>
            </BaseButton>

            <BaseDivider class="mt-8" text="Atau" />

            <div class="mt-8">
              <Form
                :validation-schema="schema"
                @submit="loginWithEmail"
                @invalid-submit="invalidLoginWithEmail"
              >
                <FormInput
                  name="email"
                  label="Alamat Email"
                  placeholder="someone@example.com"
                />
                <FormInput
                  class="mt-4"
                  name="password"
                  label="Password"
                  type="password"
                />

                <div class="mt-4 flex justify-end">
                  <a href="#" class="text-blue-600 hover:text-blue-800 text-sm"
                    >Lupa password</a
                  >
                </div>

                <BaseButton class="block w-full mt-4"
                  >Masuk dengan Email</BaseButton
                >
              </Form>
            </div>

            <div class="mt-8 flex flex-col justify-center items-center">
              <p class="text-sm">Belum punya akun?</p>
              <a href="#" class="block mt-2 text-blue-600 hover:text-blue-700"
                >Buat akun</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
