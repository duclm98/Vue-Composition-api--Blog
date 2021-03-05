<template>
  <div class="home">
    <p>Home</p>

    <!-- <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
    <input type="text" v-model="name">
    <button @click="age++">Add 1 to age</button> -->
    
    <!-- <p>Refs</p>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <p>Reactive</p>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button> -->

    <!-- <p>{{ name }}</p> -->
    <!-- <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      <p>{{ name }}</p>
    </div>
    <button @click="handelClick">Stop watching</button> -->

    <posts-list :v-if="showPosts" :posts="posts"></posts-list>
    <button @click="showPosts = !showPosts">Toggle posts</button>
  </div>
</template>

<script>
import { ref, reactive, computed, watch, watchEffect } from 'vue';
import PostsList from '../components/PostsList';
export default {
  name: 'Home',
  components: {
    PostsList,
  },
  setup() {
    // Basic
    // const p = ref(null);
    // const handleClick = () => {
    //   console.log('You clicked me!');
    //   console.log(p, p.value);
    //   p.value.classList.add('test');
    //   p.value.textContent = 'Hello, Duc';
    // }


    // Template Refs
    // const name = ref('Duc');
    // const age = ref(23);

    // const handleClick = () => {
    //   name.value = 'Chi';
    //   age.value = 20;
    // }

    // return {
    //   // p,
    //   name,
    //   age,
    //   handleClick,
    // }


    // Refs vs Reactive
    // const ninjaOne = ref({
    //   name: 'Duc',
    //   age: 23
    // });
    // const ninjaTwo = reactive({
    //   name: 'Chi',
    //   age: 20
    // })

    // const updateNinjaOne = () => {
    //   ninjaOne.value.age = 25;
    // }
    // const updateNinjaTwo = () => {
    //   ninjaTwo.age = 22;
    // }

    // return {
    //   ninjaOne,
    //   updateNinjaOne,
    //   ninjaTwo,
    //   updateNinjaTwo
    // }


    // Computed values, watch and watch effect
    // const name = computed(() => {
    //   return {
    //     name: 'Duc',
    //   }
    // })
    // return {
    //   name
    // }
    
    // const search = ref('');
    // const names = ref(['Duc', 'Chi', 'Hung', 'Hoang', 'Linh']);

    // const stopWatch = watch(search, () => {
    //   console.log('Watch function ran!');
    // })

    // const stopEffect = watchEffect(() => {
    //   console.log('WatchEffect function ran!', search.value);
    // })

    // const matchingNames = computed(() => {
    //   return names.value.filter(name => name.includes(search.value));
    // })

    // const handelClick = () => {
    //   stopWatch();
    //   stopEffect();
    // }

    // return {
    //   names,
    //   search,
    //   matchingNames,
    //   handelClick
    // }


    // Props, lifecycle hook
    const posts = ref([{
      title: 'Welcome to the blog',
      body: 'Lorem ipsum',
      id: 1
    }, {
      title: 'Top 5 CSS tips',
      body: 'Lorem ipsum',
      id: 2
    }]);
    const showPosts = ref(true);

    return {
      posts,
      showPosts,
    }
  }
}
</script>
