<template>
	<div class="select-country-wrap">
		<div class="">
			<strong><label for="select-country">나라 선택:</label></strong>
			<select name="country" id="select-country" v-model="countrySelected">
				<option value="">나라를 선택해 주세요.</option>
				<option
						:key = "index"
						v-for="(value,index) in countries"
						:value="value"
				>{{ value }}</option>
			</select>
			<p>{{ returnMessage }}</p>
		</div>
	</div>
</template>

<script lang="ts">
import { Component,Vue } from 'vue-property-decorator';

@Component
export default class ChoiceCountry extends Vue {
  countrySelected = ''
	countries = ['한국', '미국', '프랑스', '스위스', '독일', '중국', '일본']
  /*countries = [
      {englishName: 'kr', koreanName: '한국'},
      {englishName: 'en', koreanName: '미국'},
      {englishName: 'fr', koreanName: '프랑스'},
      {englishName: 'sw', koreanName: '스위스'},
      {englishName: 'de', koreanName: '독일'},
      {englishName: 'cn', koreanName: '중국'},
      {englishName: 'jp', koreanName: '일본'}
  ]*/
  get returnMessage() {
    if(this.countrySelected) {
      return this.countrySelected + '를(을) 선택하였습니다.';
    }else {
			// eslint-disable-next-line getter-return
      return;
    }
  }
}
</script>

<style scoped>

</style>