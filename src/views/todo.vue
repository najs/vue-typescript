<template>
	<div class="home">
		<TodoList msg="!!TODO LIST 만들기!!"/>
	</div>
</template>

<script>
	// @ is an alias to /src
	import TodoList from '@/components/todolist.vue'

	export default {
		name: 'Home',
		components: {
			TodoList
		}
	}
</script>
