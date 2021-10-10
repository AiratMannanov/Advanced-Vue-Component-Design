<template>
  <input :value="value" ref="input" placeholder="YYYY-MM-DD">
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"
import Pikaday, { PikadayOptions } from "pikaday"
import "pikaday/css/pikaday.css"

@Component({
  name: "DatePickerInput"
})
export default class extends Vue {
  $refs!: {
    input: HTMLInputElement
  }

  @Prop({ required: true }) value: string
  @Prop({ default: "YYYY-MM-DD" }) format: string
  @Prop({ default: {} }) options: PikadayOptions

  mounted() {
    const picker = new Pikaday({
      field: this.$refs.input,
      format: this.format,
      onSelect: () => {
        this.$emit("input", picker.toString())
      },
      ...this.options
    })
  }
}
</script>
