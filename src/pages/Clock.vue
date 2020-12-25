<template>
  <div>
    <p>hello user "{{ userId }}" this is clock page</p>
    <p>your reply token is {{ replyToken }}</p>
    <b-button @click="getLocation" type="is-primary" class="my-btn">get location สวัสดี</b-button>
    <div id="location">
      <p>latitude: {{ userCurrentPosition.latitude}}</p>
      <p>longitude: {{ userCurrentPosition.longitude }}</p>
    </div>
    <section>
      <p>{{ datetime }}</p>
      <b-field label="Select datetime">
        <b-datetimepicker
          rounded
          placeholder="Click to select..."
          icon="calendar-today"
          :locale="locale"
          :datepicker="{ showWeekNumber }"
          :timepicker="{ enableSeconds, hourFormat }"
          horizontal-time-picker
          v-model="datetime">
        </b-datetimepicker>
      </b-field>
    </section>
  </div>
</template>
<script>
  export default {
    name: 'Clock',
    data() {
      return {
        userId: this.$route.params.userId,
        replyToken: this.$route.params.replyToken,
        userCurrentPosition: {
          latitude: 0,
          longitude: 0
        },
        datetime: new Date(),
        showWeekNumber: false,
        enableSeconds: false,
        hourFormat: undefined, // Browser locale
        locale: undefined // Browser locale
      }
    },
    methods:{
      getLocation() {
        if (navigator.geolocation) {
          navigator.geolocation.getCurrentPosition((position) => {
            this.$data.userCurrentPosition.latitude = position.coords.latitude
            this.$data.userCurrentPosition.longitude = position.coords.longitude;
          });
        } else {
          document.getElementById("location").innerHTML = "Geolocation is not supported by this browser.";
        }
      }
    },
    created() {
      console.log(this.$route.params);
    },
  }
</script>

