<template lang="pug">
  .content-wrapper
    section
        .container
            h1.ui-title-1 Home
    section
      .container
        .task-list
          .task-item(

          )
</template>

<script>
export default {
  data () {
    return {
      tasks: [
        {
          'id': 1,
          'title': 'GrowthBusters: Hooked on Growth',
          'description': 'I directed this documentary challenging the myths linking growth with prosperity and fulfillment. It explores how our beliefs about economic and consumption',
          'whatWatch': 'Film',
          'completed': false,
          'editing': false
        },
        {
          'id': 2,
          'title': 'Game of thrones',
          'description': 'Best serials',
          'whatWatch': 'Serial',
          'completed': false,
          'editing': false
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped >

</style>
