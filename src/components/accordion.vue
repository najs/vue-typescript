<template>
	<div class="QnA">
		<ul>
			<li
					v-bind:key = "qna.key"
					v-for="qna in arrData"
			>
				<strong class="q-title" v-on:click="qna.state = !qna.state"> {{ qna.title }}</strong>
				<ul class="q-answer" v-if="qna.state">
					<li v-bind:key = "qna.key + '-' + index" v-for="(value, index) in qna.content">{{ value }}</li>
				</ul>
			</li>
		</ul>
	</div>
</template>

<script lang="ts">
    import {Component, Prop, Vue} from 'vue-property-decorator';



    @Component
    export default class Accordion extends Vue {
        name = 'accordion'
        @Prop() private arrData!: [];
        
       
    }
    
    /*@Component
    export default class HelloWorld extends Vue {
        @Prop() private msg!: string;
    }*/
</script>

<style scoped lang="scss">
	ul{list-style:none}
</style>