<template>
  <div class="min-h-screen bg-grey-darker p-8">
    <div class="max-w-sm mx-auto">
      <div class="card">
        <label class="block">
          <span class="form-label mb-2">Select a date</span>
          <date-picker class="form-input" v-model="date" format="D MMM YYYY" :options="{ firstDay: 1 }" />
        </label>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator"
import DatePicker from "./DatePicker.vue"

@Component({
  components: {
    DatePicker
  },
  name: "DatePickerForm"
})
export default class extends Vue{
	date = "2018-04-12"
}
</script>
