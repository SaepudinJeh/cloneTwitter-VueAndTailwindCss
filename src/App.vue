<template>
  <section class="flex container h-screen w-full">
  	<!-- Side bar -->
  	<Sidebar />

  	<!-- Tweet -->
  	<Tweet />

  	<!-- Trending -->
  	<Trending />
  	
  </section>
</template>

<script>
	import Sidebar from './components/Sidebar.vue'
	import Tweet from './components/Tweet.vue'
	import Trending from './components/Trending.vue'
	export default {
		name: 'App',
		components: {
			Sidebar,
			Tweet,
			Trending
		}
	}
</script>