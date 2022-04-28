<template>
  <p>Edit the event here</p>
</template>

<script>
export default {
  props: ['event'],
  data: function() {
    return {
      unsavedChanges: true
    }
  },
  beforeRouteLeave() {
    if (this.unsavedChanges) {
      const answer = window.confirm(
        'Do you really want to leave? You have unsaved changes to do'
      )
      if (!answer) {
        return false
      }
    }
  }
}
</script>
