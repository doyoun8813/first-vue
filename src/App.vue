<template>
  <h1 v-show="isShow">Hello vue</h1>
  <a :href="naverUrl">go naver</a>
  <img v-bind:src="imgSrc" />
  <img :src="imgSrc" /><br/>
  <input type="text" name="" id="" :placeholder="textHint" v-model="textData"/>
  <p>{{textData}}</p>

  <h3>상품목록</h3>
  <ul>
    <li v-for="product in products" :key="product">{{ product }}</li>
    <li v-for="(product, n) in products" :key="n">{{n}}. {{ product }}</li>
  </ul>
  <p v-if="true">v-if test</p>
  <p v-else>v-else test</p>
  <button @click="buttonClicked()">click</button>
  <p>{{ now() }}</p>
  <p>{{ textComputed }}</p>
  <p v-text="textValue"></p>

</template>

<script>

export default {
  name: 'App',
  created(){
    console.log("created");
  },
  mounted(){
    console.log("mounted");
  },
  updated(){
    console.log("updated");
  },
  computed:{
    textComputed(){
      return this.textData.toUpperCase().substring(0,3);
    }
  },
  methods:{
    buttonClicked(){
      console.log("hi");
    },
    now(){
      console.log('methods');
      return new Date();
    }
  },
  data(){
    return {
      naverUrl: 'http://www.naver.com',
      imgSrc: "./../src/assets/logo.png",
      isShow: true,
      textHint: '글자 입력',
      textData: 'ganada',
      textValue: "가나다라",
      products: ['iPhone13','Galaxi','Monitor']
    }
  },
  components: {
  }
}
</script>

<style>
</style>
