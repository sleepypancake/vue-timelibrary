<template lang="pug">
  .content-wrapper
    section
        .container
            h1.ui-title-1 Home
            input(
              type="text"
              placeholder="What we will watch?"
              v-model="taskTitle"
              @keyup.enter="newTask"
            )
            textarea(
              type="text"
              placeholder="Description"
              v-model="taskDescription"
              @keyup.enter="newTask"
            )
            .option-list
              input.what-watch--radio(
                type="radio"
                id="radioFilm"
                value="Film"
                v-model="whatWatch"
              )
              label(
                for="radioFilm"
              ) Film
              input.what-watch--radio(
                type="radio"
                id="radioSerial"
                value="Serial"
                v-model="whatWatch"
              )
              label(
                for="radioSerial"
              ) Serial

            // TOTAL TIME
            .total-time

              // Film Time
              .total-time__film(
                v-if="whatWatch === 'Film'"
              )
                span.time-title Hours
                input.time-input(
                  type="number"
                  v-model="filmHours"
                )
                span.time-title Minutes
                input.time-input(
                  type="numder"
                  v-model="filmMinutes"
                )

              // Serial Time
              .total-time__serial(
                v-if="whatWatch === 'Serial'"
              )
                span.time-title How many season?
                input.time-input(
                  type="number"
                  v-model="serialSeason"
                )
                span.time-title How many series?
                input.time-input(
                  type="number"
                  v-model="serialSeries"
                )

            .tag-list
              .ui-tag__wrapper
                .ui-tag
                  span.tag-title Dogs
                  span.button-close
</template>

<script>
export default {
  data () {
    return {
      taskTitle: '',
      taskDescription: '',
      whatWatch: 'Film',
      taskID: 3
    }
  },
  methods: {
    newTask () {
      if (this.taskTitle === '') {
        return
      }
      const task = {
        id: this.taskId,
        title: this.taskTitle,
        description: this.taskDescription,
        whatWatch: this.whatWatch,
        completed: false,
        editing: false
      }
      console.log(task)

      // Reset
      this.taskId += 1
      this.taskTitle = ''
      this.taskDescription = ''
    }
  }
}
</script>

<style lang="stylus" scoped >
  .option-list
    display flex
    .what-watch--radio
      margin-right 12px
    label
      margin-right 20px
      &:last-child
        margin-right 0

  .total-time
    margin-bottom 20px
</style>
