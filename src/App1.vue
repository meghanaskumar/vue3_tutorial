<template>
  <div>Heloooo {{ name }}</div>
  <div>
    <button v-on:click="changeName">Chnage name</button>
    <button v-on:mouseover="name = 'shinojjjjjj'">Chnage on mouse over</button>
  {{ count }}
  <button v-on:click="count += 1">+++</button>
  <button v-on:click="count -= 1">---</button>
  </div>
  <div v-text="channel"></div>
  <div v-html="channel"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Button</button>
  <h2 class="underline">Underline</h2>
  <h2 class="underline" v-bind:class="status">status</h2>
  <div v-bind:class="isPromoted && 'promoted'">Promoted movied</div>
  <div v-bind:class="isSoldOut ? 'sold-out' : 'new'">Solddddddd</div>
  <div v-bind:class="['success', 'promoted']">Array class</div>
  <div v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array class</div>
  <div v-bind:style="{
    color: orange,
    'font-size': headersize + 'px'
  }">Object binding style</div>
   <div v-bind:style="headerStyleObj">Object binding style in data</div>
   <div v-if="num === 0">Number is Zero</div>
   <div v-else-if="num < 0">Number is -ve</div>
   <div v-else-if="num > 0">Number is +ve</div>
   <div v-else>Not Number</div>
   <div v-show="isShow">V show directive</div>
   <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
   <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>
   <div v-for="actor in actors" :key="actor.name">
   <h2> {{ actor.name }}</h2>
   <h3 v-for="movie in actor.movies" :key="movie"> {{ movie }}</h3>
   </div>
   <h2 v-for="(value,key, index) in myInfo" :key="value">{{ value  }} {{ key }} {{ index }}</h2>
   <template v-for="name in names" :key="name">
  <h2 v-if="name === 'Anand'"> {{ name }}</h2>
</template>
{{ add(1,2,baseValue)}}
{{ multiply(baseValue) }}
<form>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" v-model="formValues.name">
  </div>
</form>
</template>


<script>
export default{
  name: "App",
  data() {
    return {
      formValues: {
        name: '',
      },
      count:0,
      basemul: 5,
      baseValue:2,
      names: ['Anand', 'B', 'C'],
      fullNames: [
        { first: 'A', last: 'Anand'},
        { first: 'B', last: 'Bincy'},
        { first: 'C', last: 'Carol'},
      ],
      actors:[
        {
          name:'ABC',
          movies: ['A', 'Bc']
        },
        {
          name:'DEF',
          movies: ['D', 'EF']
        },
        {
          name:'GHI',
          movies: ['G', 'HI']
        },
      ],
      myInfo:{
        name: 'Megha',
        age: 27,
        sex: 'Female',
      },
      num:5,
      isShow:true,
      name: "Meghanaeeeeeeee",
      channel: "<b>somee<b>",
      headingId: 'heading',
      isDisabled:true,
      isPromoted:false,
      isSoldOut:true,
      status:"success",
      headersize:40,
      orange:"orange",
      headerStyleObj: {
        color: "blue",
        'font-size':"14px",
        padding:"10px",


      },
    }
  },
  methods:{
    add(a,b,c){
      return a+b+c;
    },
    changeName(event){
this.name = 'Sundarii';
console.log('event', event)
    },
    multiply(num){
      return this.basemul * num;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  font-style: italic;
  text-decoration: underline;
}
.danger{
  color: red;
}
.headersize{
  font-size: 40;
}
.orange{
  color: orange;
}
.success{
  color: green;
}
.promoted{
  font-style: italic;
}
.new{
  color: green;
}
.sold-out{
  color: brown;
}
</style>
