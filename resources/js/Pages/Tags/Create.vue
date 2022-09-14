<script setup>
import AdminLayout from '@/Layouts/AdminLayout.vue';
import { Link, useForm } from '@inertiajs/inertia-vue3';

const createTagForm = useForm({
    tag_name: '',
});

const createTag =()=>{
    createTagForm.post(route('admin.tags'))
}
</script>
        
<template>
    <AdminLayout title="tags">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                tags
            </h2>
        </template>

        <div class="py-12">
            <div class=" mx-auto sm:px-6 lg:px-8" style="width: 60%;">
                <form action="" class="p-8 mt-6 mb-0 rounded-lg shadow-2xl space-y-4">

                    <div>
                        <label for="tag_name" class="text-sm font-medium">tag name</label>

                            <input type="text" id="tag_name" v-model="tag_name"
                                class="w-full p-4 pr-12 text-sm border-gray-200 rounded-lg shadow-sm"
                              />

                    </div>



                    <button type="submit"
                        class="block w-48 mt-2 px-5 py-3 text-sm font-medium text-white bg-gray-600 rounded-lg">
                        Sign in
                    </button>


                </form>
            </div>
        </div>
    </AdminLayout>
</template>
        