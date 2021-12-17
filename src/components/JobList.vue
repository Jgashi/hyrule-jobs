<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
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
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from '@/types/Job123';

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    }
  }
});
</script>

<style scoped></style>
