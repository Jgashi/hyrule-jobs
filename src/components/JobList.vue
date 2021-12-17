<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <transition-group name="list" tag="ul">
      <li v-for="job in orderedJobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <img src="../assets/rupee.svg" alt="rupee icon" />
          <p>{{ job.salary }} repees</p>
        </div>
        <div class="describtion">
          <p>
            Lorem, infopqhfiqm wqmdpqwmfdmf fmdf21opfmpovc md1pdo 1m2ep1pd
            1dmdpoue;lm mndpq mdd qweopm wqeom m[pwdmq[wdhdjcm dq mpo eq dqwopf
            djpowqd dqpodj
          </p>
        </div>
      </li>
    </transition-group>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType, toRef } from 'vue';
import Job from '@/types/Job123';
import OrederTerm from '@/types/OrderTerm';

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    },
    order: {
      required: true,
      type: String as PropType<OrederTerm>
    }
  },
  setup(props) {
    const orderedJobs = computed(() => {
      //另一種寫法
      // const jobs = toRef(props, 'jobs');
      // const order = toRef(props, 'order');
      // return jobs.value.sort((a: Job, b: Job) => {
      //   return a[order.value] > b[order.value] ? 1 : -1;
      // });
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });

    return { orderedJobs };
  }
});
</script>

<style scoped>
.job-list {
  max-width: 960;
  margin: 40px auto;
}
.job-list ul {
  padding: 0;
}
.job-list li {
  list-style-type: none;
  background: white;
  padding: 16px;
  margin: 16px 0;
  border-radius: 4px;
}
.job-list h2 {
  margin: 0 0 10px;
  text-transform: capitalize;
}
.salary {
  display: flex;
}
.salary img {
  width: 30px;
}
.salary p {
  color: #12bf66;
  font-weight: bold;
  margin: 10px 4px;
}
.list-move {
  transition: all 1s;
}
</style>
