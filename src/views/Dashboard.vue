<template>
  <div>
    <Navbar />
    <div class="row">
      <div class="col-md-1"><Navbar2 /></div>
      <div class="col-md-10" style="margin-top: 30px">
        <div class="row">
          <div class="col-md-6">
            <p class="dashboard">Dashboard</p>
          </div>
          <div class="col-md-6">
            <date-range-picker v-model="date"></date-range-picker>
          </div>
        </div>
        <div class="row">
          <img
            style="width: 276px; height: 104px"
            src="../assets/img/group-645.svg"
          />
        </div>
        <div class="accordion" role="tablist">
          <b-card no-body class="mb-1">
            <b-card-header
              v-b-toggle.accordion-1
              header-tag="header"
              role="tab"
              style="background-color: #37b04c; height: 48px"
            >
              <b-row>
                <b-col sm="10"
                  ><p class="marketInsight">MARKET INSIGHT</p></b-col
                >
                <!-- <b-col sm>col-sm</b-col> -->
                <b-col sm="2" style="display: flex; height: fit-content">
                  <img src="../assets/img/help.png" alt="" />
                  <a href="#" class="help">Click Here for Help</a>
                  <b-icon
                    v-if="open"
                    class="chevronIcon"
                    icon="chevron-up"
                    @click="onClickClose"
                  ></b-icon>
                  <b-icon
                    v-else
                    class="chevronIcon"
                    icon="chevron-down"
                    @click="onClickOpen"
                  ></b-icon>
                </b-col>
              </b-row>
            </b-card-header>
            <b-collapse
              id="accordion-1"
              visible
              accordion="my-accordion"
              role="tabpanel"
              style="height: max-content"
            >
              <b-row class="text-center">
                <b-col cols="5">
                  <b-card-body>
                    <b-card class="mb-2">
                      <div class="row">
                        <div class="col">
                          <p class="cardText">
                            AVERAGE PURCHASE VALUE
                          </p>
                        </div>
                        <div class="col">
                          <b-dropdown
                            text="Select"
                            variant="outline-success"
                            class="m-2"
                          >
                            <b-dropdown-item href="#"
                              >Yesterday</b-dropdown-item
                            >
                            <b-dropdown-item href="#"
                              >Last 7 Days</b-dropdown-item
                            >
                            <b-dropdown-item href="#"
                              >Last 30 Days</b-dropdown-item
                            >
                            <b-dropdown-item href="#"
                              >This Month</b-dropdown-item
                            >
                          </b-dropdown>
                        </div>
                      </div>
                    </b-card>
                  </b-card-body>
                </b-col>
                <b-col>
                  <b-card-body>
                    <b-card class="mb-2">
                      <div class="row">
                        <div class="col" style="width: max-content">
                          <p class="cardText">BEST SELLING SKU</p>
                        </div>
                      </div>
                    </b-card>
                  </b-card-body>
                </b-col>
                <b-col>
                  <b-card-body>
                    <b-card class="mb-2">
                      <div class="row">
                        <div class="col" sm="3">
                          <p class="cardText">TOP COMPETITOR SKU</p>
                        </div>
                        <!-- <div class="col">
                            </div> -->
                      </div>
                    </b-card>
                  </b-card-body>
                </b-col>
              </b-row>
            </b-collapse>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Navbar2 from "@/components/Navbar2.vue";
import moment from "moment";
import "moment/min/locales";
import Chart from "chart.js";
import { DummyData } from "../assets/dummy-data.js";
import Product1 from "../assets/img/product1.png";
import Product2 from "../assets/img/product2.png";
import Competitor from '../assets/img/product-competitor.png'

import DateRangePicker from "vue2-daterange-picker";
import "vue2-daterange-picker/dist/vue2-daterange-picker.css";

const start = moment().subtract(7, "days");

export default {
  name: "Dashboard",
  components: {
    Navbar,
    Navbar2,
    DateRangePicker,
    Chart,
  },
  data() {
    return {
      date: "",
      open: true,
      // range: '',
      startDate: start,
      dataBestSellingSKU: [
        {
          name: "Product 1",
          img: Product1,
          price: "100000",
          sold: "1000",
        },
        {
          name: "Product 2",
          img: Product2,
          price: "15000",
          sold: "840",
        },
        {
          name: "Product 2",
          img: Product2,
          price: "15000",
          sold: "560",
        },
        {
          name: "Product 2",
          img: Product2,
          price: "16000",
          sold: "300",
        },
        {
          name: "Product 2",
          img: Product1,
          price: "10000",
          sold: "200",
        },
      ],
      dataTopCompetitor: [
        {
          name: "Product A",
          img: Competitor,
          price: "100000",
          sold: "100",
        },
        {
          name: "Product B",
          img: Competitor,
          price: "15000",
          sold: "200",
        },
        {
          name: "Product C",
          img: Competitor,
          price: "15000",
          sold: "200",
        },
        {
          name: "Product D",
          img: Competitor,
          price: "15000",
          sold: "200",
        },
        {
          name: "Product E",
          img: Competitor,
          price: "15000",
          sold: "200",
        },
      ],
    };
  },
  methods: {
    onClickClose() {
      this.open = false;
    },

    onClickOpen() {
      this.open = true;
    },
  },
};
</script>

<style>
.dashboard {
  width: 187px;
  height: 50px;
  opacity: 1;
  color: #707070c4;
  font-family: "Source Sans Pro", sans-serif;
  text-align: left;
  letter-spacing: 0px;
  font-style: normal;
  font-size: 40px;
  line-height: 28px;
}

.marketInsight {
  width: 158px;
  height: 25px;
  text-align: left;
  font-family: "Source Sans Pro", sans-serif;
  letter-spacing: 0px;
  color: #ffffff;
  opacity: 1;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 13px;
  margin-top: 5px;
}

.cardText {
  width: 230px;
  height: 25px;
  text-align: left;
  letter-spacing: 0px;
  color: #4d4f5c;
  opacity: 1;
  font-style: normal;
  font-size: 18px;
  line-height: 13px;
  font-family: "Source Sans Pro", sans-serif;
  margin-bottom: 0;
  margin-top: 20px;
}

.help {
  color: white;
  font-weight: 300;
  text-decoration: underline;
  margin-left: 10px;
}

.chevronIcon {
  color: white;
  margin-left: 5px;
  align-self: center;
}

.daterangepicker .ranges ul {
  font-weight: normal;
}

.daterangepicker .ranges li.active {
  background-color: #37b04c;
  font-weight: bold;
}

.daterangepicker .calendar-table table {
  font-weight: normal;
}

.daterangepicker td.start-date.end-date {
  background: rgba(55, 176, 76, 0.3);
  color: #37b04c;
  border-radius: 100%;
  font-weight: bold;
}

.daterangepicker td.in-range {
  border-radius: 100%;
  background: rgba(55, 176, 76, 0.3);
  border-color: transparent;
  color: #37b04c;
  border-radius: 100%;
}

.calendars[data-v-4391f606] {
  flex-wrap: unset;
}
</style>
