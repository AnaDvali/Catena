<template>
      <div>

     </div>
</template>

<script>
      export default {
            mounted() {
                  this.listen()
            },
            props: ['id'],
            methods: {
                  listen() {
                        Echo.private('App.User.' + this.id)
                            .notification( (notification) => {
                                  alert(notification.name);
                                 this.$store.commit('add_not', notification)
                            })
                  }
            }
      }
</script>