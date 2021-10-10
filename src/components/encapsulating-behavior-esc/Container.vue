<template>
  <div>
    <div class="min-h-screen flex items-center justify-center">
      <button @click="modalOpen = true" type="button" class="btn btn-blue">Open Modal</button>
    </div>

    <announcement-modal
      :show="modalOpen"
      @close="modalOpen = false"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator"
import AnnouncementModal from './AnnouncementModal.vue'

@Component({
  components: {
    AnnouncementModal,
  },
	name: "ModalContainer"
})
export default class extends Vue {
	modalOpen = false
}
</script>
