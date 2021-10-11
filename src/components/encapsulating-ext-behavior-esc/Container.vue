<template>
  <div>
    <div class="min-h-screen bg-grey-darker p-8">
      <div class="max-w-sm mx-auto">
        <user-settings-form :account-id="accountId"></user-settings-form>
      </div>
    </div>

    <portal-target name="modals"></portal-target>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"
import UserSettingsForm from './UserSettingsForm.vue'

@Component({
  components: {
    UserSettingsForm,
  }
})
export default class extends Vue {
  accountId = 7
}
</script>
