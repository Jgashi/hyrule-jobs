<template>
  <div class="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import JobList from './components/JobList.vue';
import Job from './types/Job123';

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup() {
    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as string | number
    // });
    // state.name = 999 //connot change type
    // state.age = '26'
    // return { ...toRefs(state) };
    // const name = ref('link');
    // const age = ref<number | string>(25);
    // return { name, age };
    const jobs = ref<Job[]>([
      {
        title: 'farm worker',
        location: 'lon lon ranch',
        salary: 30000,
        id: '1'
      },
      { title: 'quarryman', location: 'death moutain', salary: 40000, id: '2' },
      {
        title: 'flute player',
        location: 'the lost woods',
        salary: 35000,
        id: '3'
      },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      {
        title: 'prison guard',
        location: 'gerudi vally',
        salary: 32000,
        id: '5'
      }
    ]);

    return { jobs };
  }
});
</script>

<style></style>
