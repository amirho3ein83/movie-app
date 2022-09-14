<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { Link, useForm } from "@inertiajs/inertia-vue3";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import InputError from "@/Components/InputError.vue";
import InputLabel from "@/Components/InputLabel.vue";
import TextInput from "@/Components/TextInput.vue";

const props = defineProps({
    tag: Object,
});

const editTagForm = useForm({
    tag_name: props.tag.tag_name
});

const editTag = () => {
    editTagForm.put(route('admin.tags.update',props.tag.id))
};
</script>

<template>
    <AdminLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                tags
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto sm:px-6 lg:px-8" style="width: 60%">
                <form @submit.prevent="editTag">
                    <div>
                        <InputLabel for="tag_name" value="tag name" />
                        <TextInput
                            id="tag_name"
                            v-model="editTagForm.tag_name"
                            type="text"
                            class="mt-1 block w-full"
                            required
                            autofocus
                        />
                        <!-- <InputError class="mt-2" :message="form.errors.email" /> -->
                    </div>

                    <button type="submit" class="inline-block px-5 py-1 text-lg mt-2 font-medium text-gray-600 border bg-yellow-200 rounded transition border-current hover:scale-105 hover:shadow-xl active:text-gray-500 focus:outline-none focus:ring"> Edit </button>
                </form>
            </div>
        </div>
    </AdminLayout>
</template>
