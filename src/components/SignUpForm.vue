<template>
      <div class="flex min-h-full items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
    <div class="w-full max-w-md space-y-8">
      <div>
        <img class="mx-auto h-12 w-auto" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600" alt="Your Company" />
        <h2 class="mt-6 text-center text-3xl font-bold tracking-tight text-gray-900">Sign in to your account</h2>
        <p class="mt-2 text-center text-sm text-gray-600">
          Or
          <a href="#" class="font-medium text-indigo-600 hover:text-indigo-500">start your 14-day free trial</a>
        </p>
      </div>
      <form @submit.prevent="handleSubmit" class="mt-8 space-y-6">
        <input type="hidden" name="remember" value="true" />
        <div class="space-y-3 rounded-md shadow-sm">
          <div>
            <label class="sr-only">Email address</label>
            <input v-model="email" name="email" type="email" autocomplete="email" required="" class="relative block w-full appearance-none rounded-md rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm" placeholder="Email address" />
          </div>
          <div>
            <label  class="sr-only">Password</label>
            <input v-model="password" name="password" type="password" autocomplete="current-password" required="" class="relative block w-full appearance-none rounded-md     border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm" placeholder="Password" />
            <div v-if="passwordError" class="text-red-500 font-bold mt-2">
                {{passwordError}}
            </div>
          </div>
        </div>

        <div class="flex items-center justify-between">
          <div class="flex items-center">
            <input name="remember-me" type="checkbox" class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500" />
            <label class="ml-2 block text-sm text-gray-900">Remember me</label>
          </div>

          <div class="text-sm">
            <a href="#" class="font-medium text-indigo-600 hover:text-indigo-500">Forgot your password?</a>
          </div>
        </div>

        <div>
          <button type="submit" class="group relative flex w-full justify-center rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
            <span class="absolute inset-y-0 left-0 flex items-center pl-3">
            </span>
            Sign in
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            passwordError: '',
        }
    },
        methods: {
            handleSubmit() {
                this.passwordError = this.password.length > 5 ? '' : 'Password must be atleast 6 characters long'
                if (!this.passwordError) {
                    console.log('Email: ', this.email)
                    console.log('Password: ', this.password)
                }
            }
        },
    }
</script>