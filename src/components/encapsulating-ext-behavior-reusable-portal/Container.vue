<template>
  <div>
    <portal to="modals" v-if="showAnnouncement">
      <announcement-modal
        :show="showAnnouncement"
        @close="showAnnouncement = false"
      ></announcement-modal>
    </portal>

    <div class="min-h-screen bg-grey-darker p-8">
      <div class="max-w-sm mx-auto">
        <user-settings-form
          :account-id="accountId"
        ></user-settings-form>
      </div>
    </div>

    <portal-target name="modals"></portal-target>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator"
import UserSettingsForm from './UserSettingsForm.vue'
import AnnouncementModal from './AnnouncementModal.vue'

@Component({
  name: "Container",
  components: {
    UserSettingsForm,
    AnnouncementModal
  }
})
export default class extends Vue {
  accountId = 7
  showAnnouncement = true
}
</script>
