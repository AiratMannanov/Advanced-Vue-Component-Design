<template>
  <button type="button" class="text-red-dark hover:underline"
    @click="modalOpen = true"
  >
    Delete Account
    <portal to="modals" v-if="modalOpen">
      <confirm-delete-modal
        :show="modalOpen"
        @close="modalOpen = false"
        :account-id="accountId"
      />
    </portal>
  </button>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"
import ConfirmDeleteModal from "./ConfirmDeleteModal.vue"

@Component({
  name: "DeleteAccountButton",
  components: {
    ConfirmDeleteModal
  }
})
export default class extends Vue {
	@Prop() readonly accountId: number
	modalOpen = false
}
</script>
