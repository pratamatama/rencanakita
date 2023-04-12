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
              type="button"
              class="block w-full !bg-gray-200 dark:!bg-gray-700 hover:!bg-gray-300 dark:hover:!bg-gray-600 mt-8"
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
      </div>
    </div>
  </div>
</template>
