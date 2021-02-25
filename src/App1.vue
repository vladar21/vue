<template>
  <div>
  {{great}} {{name}}
  </div>



<!-- <div v-html="channel"></div>
<h2 :id="headingId">Heading</h2>
<button :disabled="isDisable">Bind</button>
<h2 class="underline">Underlined text</h2>
<h2 class="underline" :class="status">Status</h2>
<h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
<h2 :class="isSoldout ? 'sold-out' : 'new'">Soldout? movie</h2>
<h2 :class="['new', 'promoted']">Newly promoted movie</h2>
<h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array conditional movie</h2>
<h2 :class="{
  promoted: isPromoted,
  new: !isSoldout,
  'sold-out': isSoldout
}">Object conditional movie</h2>
<h2 :style="{
  color: highlightColor,
  fontSize: headerSize + 'px',
  padding: '20px'
}">Inline Style</h2>

<h2 :style="headerStyleObject">Style Object</h2>

<div :style="[baseStyleObject, successStyleObject]">Success Style</div>
<div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div> -->

<!-- <h2 v-if="num === 0">
  The number is zero
  </h2>
<h2 v-else-if="num < 0">
  The number is negative
  </h2>
<h2 v-else-if="num > 0">
  The number is positive
  </h2>
<h2 v-else>
  Not a number
  </h2>

  <template v-if="displey">
    <h2>Vishwas</h2>
    <h2>Codevolution</h2>
    <h2>Vue</h2>
    <h2 v-show="showElement">Using v-show</h2>
    <h2 v-if="showElement">Using v-if</h2>
  </template> -->


  <!-- <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>

  <h2 v-for="(name, index) in fullNames" :key="name.last">{{ index }}{{name.first}} {{name.last}}</h2>

  <div v-for="actor in actors" :key="actor.name">
    <h2>{{actor.name}}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>

  </div>
  <h2 v-for="(value, key, index) in myInfo" :key="value"> {{ index }} {{ key }} {{ value }}</h2>

  <template v-for="name in names" :key="name">
    <h2>{{ name }}</h2>
     <hr />
  </template> -->

  <!-- <template v-for="name in names" :key="name">
    <h2 v-if="name === 'Bruce'">{{ name }}</h2>
  </template> -->


  <!-- <h2>{{ 2 + 3 + 5 }}</h2>
  <h2>{{ 5 + 10 + 15 }}</h2>
  <h2> Add method - {{ add(2,3,5) }}</h2>
  <h2> Add method - {{ add(10,15,20) }}</h2>
  <h2> Multipli method - {{ multiply(10) }}</h2> -->

  <!-- <h2>{{ name }}</h2>

  <div>
    <button v-on:mouseover="changeName($event), increment(1, $event)">Change name</button>
  </div>

  <h2>{{ count }}</h2>
  <div>
    <button @click="increment(1, $event)">Increment</button>
    <button @click="increment(5)">Increment 5</button>
    <button @click="decrement(1)">Decrement</button>
    <button @click="decrement(5)">Decrement 5</button>
    </div> -->

  <div>
    <pre>
      {{  JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit.prevent = "submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name">
    </div>
    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary"></textarea>
    </div>
    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>
    <div>
      <label for="job-location">Job Location</label>
      <select id="job-location" multiple v-model="formValues.jobLocation">
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value = "no" />
      <label for="remoteWork">Open to remote work?</label>
    </div>

    <div>
      <label>Years of Experience</label>
      <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience" />
      <label for="0-2">0-2</label>
      <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience" />
      <label for="3-5">3-5</label>
      <input type="radio" id="6-10" value="6-10" v-model="formValues.yearsOfExperience" />
      <label for="6-10">6-10</label>
    </div>

     <div>
      <label for="age">Open to remote work?</label>
      <input @keyup.enter = "submitForm" type="number" id="age" v-model.number="formValues.age" />      
    </div>

    <!-- <div>
      <button>Submit</button>
    </div> -->

  </form>
</template>

<script>

export default {
  name: "App",
  data(){
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: '',
        age: null,
      }


      // great: "Hello",
      // name: "Batman",
      // num: 'c',
      // displey: true,
      // showElement: true,
      // names: ['Bruce', 'Clark', 'Diana'],
      // fullNames: [
      //   { first: 'Bruce', last: 'Wayne' },
      //   { first: 'Clark', last: 'Kent' },
      //   { first: 'Princess', last: 'Diana' },
      // ],
      // actors: [
      //   {
      //     name: "Christian Bale",
      //     movies: ['Batman', 'The Prestige'],
      //   },
      //   {
      //     name: "Di Caprio",
      //     movies: ['Titanic', 'Inception'],
      //   },
      // ],
      // myInfo: {
      //   name: 'Vishwas',
      //   channel: 'Codevolution',
      //   course: 'Vue 3',
      // }
      // channel: "<b>Codevolution</b>",
      // headingId: "heading",
      // isDisable: false,
      // status: 'danger',
      // isPromoted: true,
      // isSoldout: true,
      // highlightColor: 'orange',
      // headerSize: 50,
      // headerStyleObject: {
      //   color: 'orange',
      //   fontSize: '50px',
      //   padding: '20px',
      // },
      // baseStyleObject: {
      //   fontSize: '50px',
      //   padding: '10px',
      // },
      // successStyleObject: {
      //   color: 'green',
      //   backgroundColor: 'lightgreen',
      //   border: '1px solid green',
      //   padding: '50px'
      // },
      // dangerStyleObject: {
      //   color: 'darkred',
      //   backgroundColor: 'red',
      //   border: '1px solid darkred',
      // }

      // baseMultiplier: 5,

      // name: "Vishwas",
      // count: 0

    };
  },
  methods: {
    // add(a, b, c) {
    //   return a + b + c
    // },
    // multiply(num){
    //   return num * this.baseMultiplier
    // }
    // increment(num, event){
    //   this.count += num
    //   console.log("Event", event)
    // },
    // decrement(num){
    //   this.count -= num
    // },
    // changeName(event){
    //   this.name = 'Batman'
    //   console.log('Event', event)
    // },
    submitForm(){
      console.log('Form values', this.formValues)
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-felx;

}

/* .underline {
  text-decoration: underline;
}

.promoted {
  font-style:italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
} */

</style>
