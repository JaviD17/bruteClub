<script>
    import Card from '$lib/components/blogCard.svelte';
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">Blog</h2>
</section>


<section id="blog-page" class="lg:grid grid-cols-3 2xl:grid-cols-4">
    <Card let:date><p class="" slot="info">Date: {date}</p></Card>
</section>