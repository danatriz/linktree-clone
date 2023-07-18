<template>
    <AuthLayout>
        <div class="mt-10">
            <h1 class="lg:text-5xl text-3xl text-center font-extrabold">
                Create your account?
            </h1>

            <form 
                class="mt-12"
                @submit.prevent="$event =>register()"
            >

            <div>
                <TextInput 
                    placeholder="username"
                    v-model:input="name"
                    inputType="text"
                    :error="error && error.name ? error.name[0]:''"
                />
            </div>

            <div class="mt-4">
                <TextInput 
                    placeholder="Email: your@email.com"
                    v-model:input="email"
                    inputType="email"
                    :error="error && error.email ? error.email[0]:''"
                />
            </div>

            <div class="mt-4">
                <TextInput 
                    placeholder="Password"
                    v-model:input="password"
                    inputType="password"
                    :error="error && error.password ? error.password[0]:''"
                />
            </div>

            
            <div class="mt-4">
                <TextInput 
                    placeholder="Confirm Password"
                    v-model:input="confirmpassword"
                    inputType="password"
                    
                />
            </div>

            <div class="mt-10">
                <button
                type='submit'
                class="rounded-full w-full p-3 font-bold"
                :disabled="(!name || !email || !password || !confirmpassword)"
                :class="
                    (name && email && password && confirmpassword)
                    ? 'bg-[#b228D9] hover-bg-[#5c21b3] text-white'
                    : 'bg-[#EFF0eB] text-[#A7AAA2]'
                "
                >
                    Create account?
                </button>
            </div>

            </form>

            <div class="text-[14px] text-center pt-12">
                Already have an account?
                <NuxtLink
                    to="/"
                    class="text-[#8228D9] underline"
                >
                    Log in
                </NuxtLink>
            </div>
        </div>
    </AuthLayout>
</template>

<script setup>
import AuthLayout from '../layouts/AuthLayout.vue';

let name = ref(null)
let email = ref(null)
let password = ref(null)
let confirmpassword = ref(null)
let error = ref(null)


</script>



