<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { useForm } from "@inertiajs/vue3";
import TextInput from "@/Components/TextInput.vue";
import InputError from "@/Components/InputError.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import InputLabel from "@/Components/InputLabel.vue";
import FileInput from "@/Components/FileInput.vue";

defineOptions({
    layout: AdminLayout,
});

const props = defineProps({
    magazine: {
        type: Object,
        required: true,
    },
});

const magazineForm = useForm({
    id: props.magazine.id,
    name: props.magazine.name,
    publicated_at: props.magazine.publicated_at,
});

const handleUpdateMagazine = () => {
    magazineForm.patch(route("admin.magazines.update"));
};
</script>
<template>
    <Head title="Revista" />
    <h1 class="pl-8 text-3xl font-bold">Editar revista</h1>
    <div class="w-full p-8">
        <section class="flex w-full justify-between rounded bg-white p-8">
            <form @submit.prevent="handleUpdateMagazine" class="w-3/4">
                <div>
                    <InputLabel for="name" value="Nombre de la revista" />
                    <TextInput
                        id="name"
                        type="text"
                        class="mt-1 block w-full"
                        v-model="magazineForm.name"
                        required
                        autofocus
                        autocomplete="magazine_name"
                    />
                    <InputError
                        class="mt-2"
                        :message="magazineForm.errors.name"
                    />
                </div>
                <div class="mt-4">
                    <InputLabel
                        for="publicated_at"
                        value="Fecha de publicación"
                    />
                    <TextInput
                        id="magazine_publicated_at"
                        type="date"
                        class="mt-1 block w-full"
                        v-model="magazineForm.publicated_at"
                        required
                    />
                    <InputError
                        class="mt-2"
                        :message="magazineForm.errors.publicated_at"
                    />
                </div>
                <div class="mt-4 flex items-center gap-4">
                    <PrimaryButton :disabled="magazineForm.processing"
                        >Guardar</PrimaryButton
                    >
                    <Transition
                        enter-from-class="opacity-0"
                        leave-to-class="opacity-0"
                        class="transition ease-in-out"
                    >
                        <p
                            v-if="magazineForm.recentlySuccessful"
                            class="text-sm text-gray-600"
                        >
                            Guardado.
                        </p>
                    </Transition>
                </div>
            </form>
            <FileInput
                :file="magazine.file"
                :resource-id="magazine.id"
                :upload-file-route="route('admin.magazines.upload-file')"
                :delete-file-route="route('admin.magazines.delete-file')"
                class="w-1/4"
            />
        </section>
    </div>
</template>
