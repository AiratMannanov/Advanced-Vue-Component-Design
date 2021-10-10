<template>
  <span class="toggle" role="checkbox" tabindex="0"
    @click="toggle"
    @keydown.space.prevent="toggle"
    :aria-checked="toggled.toString()"
  ></span>
</template>

<script lang="ts">
import { Vue, Component, Prop, Model } from "vue-property-decorator"

@Component({})
export default class extends Vue {
	@Model("toggle") readonly toggled: boolean
  
	toggle() {
		this.$emit("toggle", !this.toggled)
	}
}
</script>
