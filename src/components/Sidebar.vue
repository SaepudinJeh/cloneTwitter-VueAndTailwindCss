 <template>
	<section class="lg:w-1/5 border-r border-lightblue lpx-2 lg:px-6 py-2 flex flex-col justify-between">
		<div>
			<button class="h-12 w-12 hover:bg-lightblue text-3xl rounded-full text-blue">
				<i class="fab fa-twitter"></i>
			</button>
			<div>
				<button v-for="tab in tabs" @click="id = tab.id" :class="`focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full wr-auto mb-3 ${ id === tab.id ? 'text-blue' : '' }`">
					<i :class="`${tab.icon} text-2xl mr-4 text-left`"></i>
					<p class="hidden lg:block text-lg font-semibold text-left">{{ tab.title }}</p>
				</button>
			</div>
			<button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-12 h-12 lg:h-auto lg:w-full p-3 hover:bg-darkblue">
				<p class="hidden lg:block">Tweet</p>
				<i class="fa fa-plus lg:hidden"></i>
			</button>
		</div>
		<div class="lg:w-full relative">
			<button @click="dropdown = true" class="flex items-center w-full hover:bg-lightblue rounded-full p-2 focus:outline-none">
				<img src="/src/assets/img/Master.jpg" class="w-10 h-10 rounded-full border-lightblue">
				<div class="hidden lg:block ml-4">
					<p class="text-sm font-bold leading-tight"> Agung Saepudin </p>
					<p class="text-sm leading-tight"> @SaepudinJeh </p>
				</div>
				<i class="hidden lg:block fas fa-angle-down ml-auto text-lg"></i>
			</button>
			<div v-if="dropdown === true" class="absolute bottom-0 left-0 w-64 rounded-lg shadow-md border-lightest bg-white mb-16">
				<button @click="dropdown = false" class="p-3 flex items-center w-full hover:bg-lightest p-2 focus:outline-none">
					<img src="/src/assets/img/Master.jpg" class="w-10 h-10 rounded-full border-lightblue">
					<div class="ml-4">
						<p class="text-sm font-bold leading-tight"> Agung Saepudin </p>
						<p class="text-sm leading-tight"> @SaepudinJeh </p>
					</div>
					<i class="fas fa-check ml-auto text-blue"></i>
				</button>
				<button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm focus:outline-none">
					Add an existing account
				</button>
				<button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm focus:outline-none">
					Log out @SaepudinJeh
				</button>
			</div>
		</div>
	</section>
</template>

<script>
	export default {
		name: 'Sidebar',
		data() {
			return {
				tabs: [
					{icon: 'fas fa-home', title: 'Home', id:'home'},
			        {icon: 'fas fa-hashtag', title: 'Explore', id: 'explore'},
			        {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
			        {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
			        {icon: 'far fa-bookmark', title: 'Bookmarks', id: 'bookmarks'},
			        {icon: 'fas fa-clipboard-list', title: 'Lists', id: 'lists'},
			        {icon: 'far fa-user', title: 'Profile', id: 'profile'},
			        {icon: 'fas fa-ellipsis-h', title: 'More', id: 'more'}
				],
				id: 'home',
				dropdown: false,
			}
		}
	}
</script>