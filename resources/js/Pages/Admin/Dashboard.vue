<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import CountCard from "@/Components/CountCard.vue";

defineOptions({
    layout: AdminLayout,
});


</script>
<template>
    <Head title="Dashboard" />
    <h1 class="pl-8 text-3xl font-bold">Dashboard</h1>
    <!-- <section class="w-full p-8 grid grid-cols-1 md:grid-cols-4 gap-4">
		<CountCard :route=" route( 'admin.books.index' ) " :count=" books " :text=" 'Libros' " :icon=" 'book' " />
		<CountCard :route=" route( 'admin.magazines.index' ) " :count=" magazines " :text=" 'Revistas' "
			:icon=" 'book-open' " />
		<CountCard :route=" route( 'admin.historical-publications.index' ) " :count=" publications "
			:text=" 'Publicaciones históricas' " :icon=" 'file' " />
		<CountCard :route=" route( 'admin.investigations.index' ) " :count=" investigations " :text=" 'Investigaciones' "
			:icon=" 'magnifying-glass' " />
	</section>
	<CountCard :route=" route( 'admin.convocations.index' ) " :count=" convocations " :text=" 'Convocatorias' "
		:icon=" 'calendar' " />
	<CountCard :route=" route( 'admin.gallery.index' ) " :count=" gallery " :text=" 'Galería eventos' " :icon=" 'images' " />
	<section class="w-full p-8 grid grid-cols-1 md:grid-cols-4 gap-4">
		<CountCard :route=" route( 'admin.users.index' ) " :count=" admin_users " :text=" 'Administradores' "
			:icon=" 'user-lock' " />
		<CountCard :route=" route( 'admin.users.index' ) " :count=" users " :text=" 'Usuarios' " :icon=" 'users' " />
	</section> -->
</template>
