<template>
  <div class="h-screen bg-white dark:bg-gray-800 px-8">
    <div class="h-full flex flex-col justify-center">
      <div>
        <h1 class="text-2xl font-medium">RencanaKita</h1>
        <p class="mt-1">Satu aplikasi, untuk segala rencana kita.</p>
      </div>

      <BaseButton
        type="button"
        class="block w-full border border-gray-200 dark:border-gray-700 !bg-transparent mt-8"
      >
        <span class="flex justify-center items-center">
          <IconsGoogle class="w-5 h-5" />
          <span class="mx-2">Masuk dengan Google</span>
        </span>
      </BaseButton>
      <BaseDivider class="mt-8" text="Atau" />
      <LoginForm class="mt-8" />

      <div class="mt-8 flex flex-col justify-center items-center">
        <p class="text-sm">Belum punya akun?</p>
        <a href="#" class="block mt-2 text-blue-600 hover:text-blue-700"
          >Buat akun</a
        >
      </div>
    </div>
  </div>
</template>
