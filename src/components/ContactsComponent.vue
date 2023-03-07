<template>
  <div>
    <div class="flex items-center">
      <img style="height: 10vh" :src="iconTelegram" alt="">
      <span>
        @codereduser
      </span>
    </div>
    <div class="flex items-center">
      <img style="height: 10vh" :src="iconDiscord" alt="">
      <span>
        gachimane#1278
      </span>
    </div>
  </div>
</template>

<script>
import iconTelegram from 'assets/icons/icon-telegram.svg'
import iconDiscord from 'assets/icons/icon-discord.svg'
export default {
  name: "ContactsComponent",
  data () {
    return {
      iconTelegram,
      iconDiscord,
    }
  }

}
</script>

<style scoped>

</style>
