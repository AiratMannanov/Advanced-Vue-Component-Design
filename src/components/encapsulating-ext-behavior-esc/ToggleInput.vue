<template>
  <span class="toggle" role="checkbox" tabindex="0"
    @click="toggle"
    @keydown.space.prevent="toggle"
    :aria-checked="value.toString()"
  ></span>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"

@Component({})
export default class extends Vue {
  @Prop() readonly value: boolean
	
	toggle() {
		this.$emit("input", !this.value)
	}
}
</script>
