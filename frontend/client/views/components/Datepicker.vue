<template>
  <div>
    <div class="tile is-ancestor">
      <div class="tile is-parent">
        <article class="tile is-child box">
          <h1 class="title">Basics</h1>
          <p class="control">
            <datepicker :inputClass="{ test: true }" v-model="value"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="European Format ('d-m-Y')" :config="{ dateFormat: 'd-m-Y', static: true }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="American Format ('m/d/Y')" :config="{ dateFormat: 'm/d/Y' }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="Fancy Textual Format ('l, F j, Y')" :config="{ dateFormat: 'l, F j, Y' }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="minDate: today" :config="{ minDate: today, defaultDate: today }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="minDate: '2016-09-20'" :config="{ minDate: '2016-09-20' }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="minDate: new Date('September 2, 2015')" :config="{ minDate: new Date('September 2, 2015') }"></datepicker>
          </p>
          <p class="control">
            <datepicker :placeholder="placeholder" :config="{ minDate: 'today', maxDate: maxDate }"></datepicker>
          </p>
        </article>
      </div>
      <div class="tile is-parent is-vertical">
        <article class="tile is-child box">
          <h1 class="title">Form addons</h1>
          <datepicker :inputClass="{ test: true }" :config="{ wrap: true }" readonly>
            <a class="button" data-toggle><i class="fa fa-calendar"></i></a>
            <a class="button" data-clear><i class="fa fa-close"></i></a>
          </datepicker>
        </article>
        <article class="tile is-child box">
          <h1 class="title">Display week numbers</h1>
          <p class="control">
            <datepicker placeholder="Enabled week numbers" :config="{ weekNumbers: true }"></datepicker>
          </p>
        </article>
        <article class="tile is-child box">
          <h1 class="title">Date Range</h1>
          <p class="control">
            <datepicker placeholder="Select a range" :config="{ mode: 'range' }"></datepicker>
          </p>
        </article>
      </div>
    </div>

    <div class="tile is-ancestor">
      <div class="tile is-parent is-vertical">
        <article class="tile is-child box">
          <h1 class="title">Preload date and time</h1>
          <p class="control">
            <!-- TODO: click out side cannot handle hidden input yet. Will fix this later. -->
            <datepicker placeholder="The real input is hidden :^)" :config="{ altInput: false, altFormat: 'F j, Y' }"></datepicker>
            <!-- <datepicker placeholder="The real input is hidden :^)" :config="{ altInput: true, altFormat: 'F j, Y' }"></datepicker> -->
          </p>
          <p class="control">
            <datepicker :config="{ defaultDate: '2016-03-01 03:30:00 -0300', enableTime: true }"></datepicker>
          </p>
          <p class="control">
            <datepicker :config="{ defaultDate: '2016-12-27T16:16:22.585Z', enableTime: true }"></datepicker>
          </p>
        </article>
        <article class="tile is-child box">
          <h1 class="title">UTC mode</h1>
          <p class="control">
            <datepicker :config="{ utc: true, defaultDate: '2016-03-01 03:30:00 -0300', enableTime: true }"></datepicker>
          </p>
          <p class="control">
            <datepicker :config="{ utc: true, defaultDate: '2016-12-27T16:16:22.585Z', enableTime: true }"></datepicker>
          </p>
        </article>
      </div>
      <div class="tile is-parent">
        <article class="tile is-child box">
          <h1 class="title">Inline or embedded calendar</h1>
          <p class="control">
            <datepicker placeholder="Pick date and time" :config="{ inline: true }"></datepicker>
          </p>
        </article>
      </div>
    </div>

    <div class="tile is-ancestor">
      <div class="tile is-parent is-vertical">
        <article class="tile is-child box">
          <h1 class="title">DateTime Picker</h1>
          <p class="control">
            <datepicker placeholder="Pick date and time" :config="{ enableTime: true }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="24 hour time" :config="{ enableTime: true, time_24hr: true, dateFormat: 'Y-m-d H:i' }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="Pick date and time" :config="{ enableTime: true, enableSeconds: true, dateFormat: 'Y-m-d h:i:S K' }"></datepicker>
          </p>
        </article>
        <article class="tile is-child box">
          <h1 class="title">Time Picker</h1>
          <p class="control">
            <datepicker placeholder="Pick time" :config="{ enableTime: true, enableSeconds: true, noCalendar: true }" value="09:00:00"></datepicker>
          </p>
        </article>
      </div>
      <div class="tile is-parent is-vertical">
        <article class="tile is-child box">
          <h1 class="title">Disable specific dates or date intervals</h1>
          <p class="control">
            <datepicker placeholder="disabled from July 6-9" :config="{ disable: [ { from: '2016-07-06', to: '2016-07-09' }, '2016-07-24' ], minDate: 'today' }"></datepicker>
          </p>
          <p class="control">
            <datepicker placeholder="disabled September 6-9 & August 25-31 2016" :config="{ disable: [ { from : '2016-09-06', to : '2016-09-09' }, { from : '2016-08-25', to : '2016-08-31' } ], minDate: 'today', dateFormat: 'Y-m-d' }"></datepicker>
          </p>
        </article>
        <article class="tile is-child box">
          <h1 class="title">Setting options dynamically</h1>
          <p class="control">
            <datepicker ref="checkIn" placeholder="Check-In Date" :config="{ minDate: new Date() }"></datepicker>
          </p>
          <p class="control">
            <datepicker ref="checkOut" placeholder="Check Out Date" :config="{ minDate: new Date() }"></datepicker>
          </p>
        </article>
      </div>
    </div>

    <div class="tile is-ancestor">
      <div class="tile is-parent">
        <article class="tile is-child box">
          <h1 class="title">Setting custom defaults</h1>
          <p class="control">
            <datepicker :config="{ prevArrow: '<i class=\'fa fa-angle-left\'></i>', nextArrow: '<i class=\'fa fa-angle-right\'></i>' }"></datepicker>
          </p>
        </article>
      </div>
      <div class="tile is-parent">
        <article class="tile is-child box">
          <h1 class="title">Localization</h1>
          <p class="control">
            <datepicker :config="{ locale: l10n }"></datepicker>
          </p>
        </article>
      </div>
    </div>
  </div>
</template>

<script>
import Datepicker from 'vue-bulma-datepicker'

export default {
  components: {
    Datepicker
  },

  data () {
    return {
      value: '2016-12-12'
    }
  },

  mounted () {
    const { checkIn, checkOut } = this.$refs
    checkIn.datepicker.set('onChange', (selectedDates, dateStr, instance) => {
      checkOut.datepicker.set('minDate', selectedDates[0].fp_incr(1))
    })

    checkOut.datepicker.set('onChange', (selectedDates, dateStr, instance) => {
      checkIn.datepicker.set('maxDate', dateStr)
    })
  },

  computed: {
    today () {
      return new Date()
    },
    maxDate () {
      let d = new Date()
      d.setDate(32)
      return d
    },
    placeholder () {
      return `minDate: today, maxDate: ${this.maxDate.getFullYear()}-${this.maxDate.getMonth() + 1}-${this.maxDate.getDate()}`
    },
    // https://github.com/chmln/flatpickr/blob/gh-pages/src/flatpickr.l10n.zh.js
    l10n () {
      return {
        firstDayOfWeek: 1,
        weekdays: {
          shorthand: ['??????', '??????', '??????', '??????', '??????', '??????', '??????'],
          longhand: ['?????????', '?????????', '?????????', '?????????', '?????????', '?????????', '?????????']
        },
        months: {
          shorthand: ['??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '?????????', '?????????'],
          longhand: ['??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '??????', '?????????', '?????????']
        }
      }
    }
  },

  watch: {
    value (newVal, oldVal) {
      console.log(newVal, oldVal)
    }
  }
}
</script>

<style lang="scss" scoped>
.tile.is-parent {
  min-width: 50%;
}
</style>
