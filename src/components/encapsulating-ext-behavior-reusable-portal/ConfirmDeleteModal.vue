<template>
  <div class="modal-backdrop" v-show="show">
    <div class="modal">
      <h1 class="text-center text-2xl font-bold mb-4">
        Are you sure?
      </h1>
      <p class="text-center text-grey-darker mb-6">
        Deleting your account cannot be undone.
      </p>
      <div class="text-center">
        <button @click="cancel" type="button" class="btn btn-grey mr-4">
          Cancel
        </button>
        <button @click="confirmDelete" type="button" class="btn btn-red">
          Delete it
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop, Watch } from "vue-property-decorator"

@Component({
  name: "ConfirmDeleteModal"
})
export default class extends Vue {
  @Prop() readonly show: boolean 
	@Prop() readonly accountId: number

	cancel() {
		this.$emit("close")
	}
	confirmDelete() {
		console.log(`Deleting account ${this.accountId}...`)
		this.$emit("close")
	}

	@Watch("show", { immediate: true })
	reactShow(show: boolean) {
		if (show) {
			document.body.style.setProperty("overflow", "hidden")
		} else {
			document.body.style.removeProperty("overflow")
		}
	}

  created() {
    const escapeHandler = (e: KeyboardEvent) => {
      if (e.key === "Escape" && this.show) {
        this.cancel()
      }
    }
    document.addEventListener("keydown", escapeHandler)
		
    this.$once("hook:destroyed", () => {
      document.removeEventListener("keydown", escapeHandler)
    })
  }
}
</script>
