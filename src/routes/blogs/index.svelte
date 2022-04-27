<script>
    import Card from '$lib/components/card.svelte';
</script>

<h2 class="text-center mt-14 mx-6 py-6 bg-neutral-700 rounded-lg text-4xl font-bold">
	Blogs
</h2>

<section id="blog-page" class="lg:grid grid-cols-3 2xl:grid-cols-4">
    <Card let:date><p class="" slot="info">Date: {date}</p></Card>
</section>