<template lang="">
    <Head title="Create New Posts" />
    <AppLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Create New Posts
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <a
                            :href="route('posts.index')"
                            class="w-4 bg-sky-500 p-2 text-white rounded-md"
                            >Post Lists</a
                        >
                        <div class="mt-4">
                            <form @submit.prevent="form.post(route('posts.store'))">
                                <label class="block">
                                    <span
                                        class="block text-sm font-medium text-slate-700"
                                        >Title</span
                                    >
                                    <input
                                        type="text" v-model="form.title"
                                        class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md text-sm shadow-sm placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:bg-slate-50 disabled:text-slate-500 disabled:border-slate-200 disabled:shadow-none invalid:border-pink-500 invalid:text-pink-600 focus:invalid:border-pink-500 focus:invalid:ring-pink-500"
                                    />
                                    <span v-if="errors.title" class="text-red-600">{{ errors.title }}</span>
                                </label>
                                <label class="block">
                                    <span
                                        class="block text-sm font-medium text-slate-700"
                                        >Content</span
                                    >
                                    <textarea
                                        type="text"
                                        rows="5"
                                        v-model="form.content"
                                        class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md text-sm shadow-sm placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:bg-slate-50 disabled:text-slate-500 disabled:border-slate-200 disabled:shadow-none invalid:border-pink-500 invalid:text-pink-600 focus:invalid:border-pink-500 focus:invalid:ring-pink-500"
                                    />
                                     <span v-if="errors.content" class="text-red-600">{{ errors.content }}</span>
                                </label>
                                <div class="flex my-4">
                                    <button type="reset"
                                    class="px-4 py-1 mx-2 text-sm bg-amber-500 text-white font-semibold rounded-full border border-purple-200 hover:text-white hover:bg-yellow-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-amber-500 focus:ring-offset-2"
                                >
                                    Reset
                                </button>
                                <button type="submit"
                                :disabled="form.processing"
                                    class="px-4 py-1 text-sm bg-sky-600 text-white font-semibold rounded-full border border-purple-200 hover:text-white hover:bg-lime-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-lime-600 focus:ring-offset-2"
                                >
                                    Submit
                                </button>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
<script>
import AppLayout from "../../Layouts/Authenticated.vue";
import { Head, Link, useForm } from "@inertiajs/inertia-vue3";
export default {
    components: {
        AppLayout,
        Head,
        Link,
    },

    props:{
            errors:Object
    },

    setup(){
         const form = useForm({
              title: '',
              content: ''
         })
         return {form}
    }
};
</script>
