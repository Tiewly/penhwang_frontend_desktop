<template>
  <section>
    <b-tabs v-model="activeTab">
      <b-tab-item label="เวลา">
        <!-- <card title="Notifications" sub-title="Custom Vue notifications plugin"> -->
        <card :title="'วันที่ ' + now">
          <div>
            <br />
            <div class="row">
              <div class="col-md-6">
                <h6>จำนวนปัจจุบัน</h6>
                <div class="alert alert-success alert-with-icon">
                  <span class="title">
                    <p>
                      <span data-notify="icon" class="ti-face-smile"></span
                      >เข้างาน
                    </p>
                    <p style="font-size: 20px">13</p>
                  </span>
                </div>
                <div class="alert alert-warning alert-with-icon">
                  <span class="title">
                    <p>
                      <span data-notify="icon" class="ti-face-smile"></span>สาย
                    </p>
                    <p style="font-size: 20px">3</p>
                  </span>
                </div>
                <div class="alert alert-danger alert-with-icon">
                  <span class="title">
                    <p>
                      <span data-notify="icon" class="ti-face-smile"></span
                      >ยังไม่เข้า
                    </p>
                    <p style="font-size: 20px">10</p>
                  </span>
                </div>
                <div class="alert alert-info alert-with-icon">
                  <span class="title">
                    <p>
                      <span data-notify="icon" class="ti-face-smile"></span
                      >ออกงาน
                    </p>
                    <p style="font-size: 20px">0</p>
                  </span>
                </div>
              </div>
              <div class="col-md-6">
                <h5>ประวัติการเข้า-ออกงาน</h5>
                <div class="my-table">
                  <div class="alert alert-warning">
                    <a>สาย</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                  <div class="alert alert-success">
                    <a>เข้างาน</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                  <div class="alert alert-success">
                    <a>เข้างาน</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                  <div class="alert alert-success">
                    <a>เข้างาน</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                  <div class="alert alert-success">
                    <a>เข้างาน</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                  <div class="alert alert-info">
                    <a>ออกงาน</a>
                    <span class="titleCard">
                      <h6>สมศรี ใจรักเธอ</h6>
                      <h6>8:50</h6>
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </card>
      </b-tab-item>

      <b-tab-item label="แจ้งเตือน">
        <card>
          <div>
            <div class="row">
              <div class="col-md-6">
                <h5>ประวัติการเข้า-ออกงาน</h5>

                <div class="alert alert-warning">
                  <a>สาย</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
                <div class="alert alert-success">
                  <a>เข้างาน</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
                <div class="alert alert-success">
                  <a>เข้างาน</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
                <div class="alert alert-success">
                  <a>เข้างาน</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
                <div class="alert alert-success">
                  <a>เข้างาน</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
                <div class="alert alert-info">
                  <a>ออกงาน</a>
                  <span class="titleCard">
                    <h6>สมศรี ใจรักเธอ</h6>
                    <h6>8:50</h6>
                  </span>
                </div>
              </div>
            </div>
          </div>
        </card>
      </b-tab-item>
    </b-tabs>
  </section>
</template>

<script>
import Card from "../../components/Cards/Card.vue";
export default {
  components: { Card },
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
}
.titleCard {
  display: flex;
  justify-content: space-between;
  font-size: 20px;
}
.my-table {
  max-height: 385px;
  overflow-y: auto;
}
</style>