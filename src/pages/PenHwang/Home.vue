<template>
  <section>
    <b-tabs v-model="activeTab">
      <b-tab-item label="เวลา">
        <!-- <card title="Notifications" sub-title="Custom Vue notifications plugin"> -->
        <card :title="'วันที่ ' + now">
          <div>
            <div class="row">
              <div class="col-md-6">
                <h6>จำนวนปัจจุบัน</h6>
                <div class="alert alert-success">
                  <span class="title">
                    <p><i class="ti-angle-down"></i>เข้างาน</p>
                    <p style="font-size: 20px">13</p>
                  </span>
                </div>
                <div class="alert alert-warning">
                  <span class="title">
                    <p><i class="ti-angle-down"></i>สาย</p>
                    <p style="font-size: 20px">3</p>
                  </span>
                </div>
                <div class="alert alert-danger">
                  <span class="title">
                    <p><i class="ti-angle-down"></i>ยังไม่เข้า</p>
                    <p style="font-size: 20px">10</p>
                  </span>
                </div>
                <div class="alert alert-info">
                  <span class="title">
                    <p><i class="ti-angle-down"></i>ออกงาน</p>
                    <p style="font-size: 20px">0</p>
                  </span>
                </div>
              </div>
              <div class="col-md-6">
                <h5>ประวัติการเข้า-ออกงาน</h5>
                <div class="alert alert-info">
                  <button type="button" aria-hidden="true" class="close">
                    ×
                  </button>
                  <span>
                    <b> Info - </b> This is a regular notification made with
                    ".alert-info"</span
                  >
                </div>
                <div class="alert alert-success">
                  <button type="button" aria-hidden="true" class="close">
                    ×
                  </button>
                  <span>
                    <b> Success - </b> This is a regular notification made with
                    ".alert-success"</span
                  >
                </div>
                <div class="alert alert-warning">
                  <button type="button" aria-hidden="true" class="close">
                    ×
                  </button>
                  <span>
                    <b> Warning - </b> This is a regular notification made with
                    ".alert-warning"</span
                  >
                </div>
                <div class="alert alert-danger">
                  <button type="button" aria-hidden="true" class="close">
                    ×
                  </button>
                  <span>
                    <b> Danger - </b> This is a regular notification made with
                    ".alert-danger"</span
                  >
                </div>
              </div>
            </div>
          </div>
        </card>
      </b-tab-item>

      <b-tab-item label="Music">
        Lorem <br />
        ipsum <br />
        dolor <br />
        sit <br />
        amet.
      </b-tab-item>

      <b-tab-item :visible="showBooks" label="Books">
        What light is light, if Silvia be not seen? <br />
        What joy is joy, if Silvia be not by— <br />
        Unless it be to think that she is by <br />
        And feed upon the shadow of perfection? <br />
        Except I be by Silvia in the night, <br />
        There is no music in the nightingale.
      </b-tab-item>

      <b-tab-item label="Videos" disabled>
        Nunc nec velit nec libero vestibulum eleifend. Curabitur pulvinar congue
        luctus. Nullam hendrerit iaculis augue vitae ornare. Maecenas vehicula
        pulvinar tellus, id sodales felis lobortis eget.
      </b-tab-item>
    </b-tabs>
  </section>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 0,
      showBooks: false,
      now: "",
    };
  },
  created() {
    setInterval(() => {
      const date = new Date();
      this.now =
        date.toLocaleString("th-TH", {
          year: "numeric",
          month: "long",
          day: "numeric",
        }) +
        " " +
        date.getHours() +
        ":" +
        date.getMinutes() +
        ":" +
        date.getSeconds() +
        " น.";
    }, 1000);
  },
};
</script>
<style scoped>
.title {
  display: flex;
  justify-content: space-between;
  /* font-size: 22px; */
  font-weight: 500;
}
</style>