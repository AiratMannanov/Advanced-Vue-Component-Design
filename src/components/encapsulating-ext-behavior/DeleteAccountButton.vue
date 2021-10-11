<template>
  <button type="button" class="text-red-dark hover:underline"
    @click="confirmDeleteModalOpen = true"
  >
    Delete Account
    <portal to="modals">
      <confirm-delete-modal
        :show="confirmDeleteModalOpen"
        @close="confirmDeleteModalOpen = false"
        :account-id="accountId"
      />
    </portal>
  </button>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"
import ConfirmDeleteModal from "./ConfirmDeleteModal.vue"

@Component({
  components: {
    ConfirmDeleteModal
  }
})
export default class extends Vue {
	@Prop() readonly accountId: number
	confirmDeleteModalOpen = false
}
</script>
