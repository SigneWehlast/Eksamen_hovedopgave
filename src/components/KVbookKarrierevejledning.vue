<script>
import { ref } from "vue";

export default {
  data() {
    return {
      currentDate: "",
      days: [],
      currYear: 0,
      currMonth: 0,
      months: [
        "Januar",
        "Februar",
        "Marts",
        "April",
        "Maj",
        "Juni",
        "Juli",
        "August",
        "September",
        "Oktober",
        "November",
        "December",
      ],
      showInput: false,
      nameValue: "",
      UCLMailValue: "",
      messageValue: "",
      selectedTime: "",
      selectedDate: {
        year: null,
        month: null,
        day: null,
      },
      dayClicked: "",
      tider: [
        "10:00 - 10:30",
        "10:45 - 11:15",
        "11:30 - 12:00",
        "12:15 - 12:45",
      ],
    };
  },
  mounted() {
    let currentDate = new Date();
    this.currYear = currentDate.getFullYear();
    this.currMonth = currentDate.getMonth();
    this.renderCalendar();
  },
  methods: {
    renderCalendar() {
      let currentDate = new Date();
      let date = new Date(this.currYear, this.currMonth, 1);
      let firstDayOfMonth = date.getDay();
      let lastDateOfMonth = new Date(
        this.currYear,
        this.currMonth + 1,
        0
      ).getDate();
      let lastDayOfMonth = new Date(
        this.currYear,
        this.currMonth,
        lastDateOfMonth
      ).getDay();
      let lastDateOfLastMonth = new Date(
        this.currYear,
        this.currMonth,
        0
      ).getDate();
      let daysArray = [];
      for (let i = firstDayOfMonth; i > 0; i--) {
        daysArray.push({ date: lastDateOfLastMonth - i + 1, active: false });
      }

      for (let i = 1; i <= lastDateOfMonth; i++) {
        let isActive =
          i === currentDate.getDate() &&
          this.currMonth === currentDate.getMonth() &&
          this.currYear === currentDate.getFullYear();
        daysArray.push({ date: i, active: isActive });
      }

      for (let i = lastDayOfMonth; i < 6; i++) {
        daysArray.push({ date: i - lastDayOfMonth + 1, active: false });
      }

      this.days = daysArray;
      this.currentDate = `${this.months[this.currMonth]} ${this.currYear}`;
    },
    changeMonth(direction) {
      this.currMonth += direction;
      if (this.currMonth < 0) {
        this.currMonth = 11;
        this.currYear--;
      } else if (this.currMonth > 11) {
        this.currMonth = 0;
        this.currYear++;
      }
      this.renderCalendar();
    },
    showInputBox(day) {
      this.showInput = true;
      this.dayClicked = day;
      this.selectedDate.day = day;
      this.selectedDate.month = this.currMonth + 1;
      this.selectedDate.year = this.currYear;
    },
    hideInputBox() {
      this.showInput = false;
    },
    sendData() {
      const dataToSend = {
        name: this.nameValue,
        uclMail: this.UCLMailValue,
        message: this.messageValue,
        selectedTime: this.selectedTime,
        selectedDate: {
          year: this.currYear,
          month: this.currMonth + 1,
          day: this.dayClicked,
        },
      };
      console.log("Data til afsendelse:", dataToSend);

      fetch(
        "https://hovedopgave-f875e-default-rtdb.firebaseio.com/booking.json",
        {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(dataToSend),
        }
      )
        .then((response) => {
          console.log("Data er sendt server:", response);
          this.nameValue = "";
          this.UCLMailValue = "";
          this.messageValue = "";
          this.selectedTime = "";
          this.popupMessage = "✔ Tak for din bestilling af tid til vejledning";
          setTimeout(() => {
            console.log("Fjerner popup-melding");
            this.$nextTick(() => {
              this.popupMessage = "";
              this.$forceUpdate();
            });
          }, 3000);
        })
        .catch((error) => {
          console.error("Fejl ved afsendelse af data:", error);
        });
    },
    selectTime(tid) {
      this.selectedTime = tid;
      console.log("Du har valgt tid: " + tid);
    },
  },
};
</script>
<template>
  <section id="bdk">
    <h2>Book en vejledning</h2>
    <div class="calendar">
      <div>
        <div class="current-date">
          {{ currentDate }}
          <div class="btn-wrap">
            <button class="carousel-btn" @click="changeMonth(-1)">
              <div class="btn-div-kalender">❮</div>
            </button>
            <button class="carousel-btn" @click="changeMonth(1)">
              <div class="btn-div-kalender">❯</div>
            </button>
          </div>
        </div>
        <div class="uge-dage">
          <div>
            <p id="uge-dage-tekst">Mandag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Tirsdag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Onsdag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Torsdag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Fredag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Lørdag</p>
          </div>
          <div>
            <p id="uge-dage-tekst">Søndag</p>
          </div>
        </div>
      </div>
      <div v-if="showInput" class="input-container">
        <div class="input-box">
          <div class="input-hide-box-1">
            <div class="input-hide-box-1-tekst">
              <h3>Book en tid til Karrierevejledning</h3>
            </div>
            <button @click="hideInputBox" class="btn-div-hide-box-x">X</button>
          </div>
          <div class="input-hide-box-2">
            <input
              type="text"
              v-model="nameValue"
              placeholder="Navn"
              class="input-felter-box"
            />
            <input
              type="text"
              v-model="UCLMailValue"
              placeholder="UCL mail"
              class="input-felter-box"
            />
            <div>
              <div>
                <p>
                  Hvornår ønsker du at bestille din tid hos karrierevejledning
                  d.
                </p>
              </div>
              <div class="selected-date">
                <p>
                  {{ selectedDate.day }}/{{ selectedDate.month }}/{{
                    selectedDate.year
                  }}
                </p>
              </div>
              <div class="bestil-tid-boks">
                <div
                  :class="{ 'selected-time': selectedTime === tid }"
                  v-for="(tid, index) in tider"
                  :key="index"
                  @click="selectTime(tid)"
                  class="bestil-tid"
                >
                  {{ tid }}
                </div>
              </div>
            </div>
            <p>
              Skriv gerne hvad du har brug for vejledning inden for. På den måde
              sikre vi at du for mest ud af din vejledning
            </p>
            <input
              type="text"
              v-model="messageValue"
              placeholder="Besked"
              class="input-felter-box"
              id="input-input-felter-box-besked"
            />
          </div>
          <div class="input-hide-box-3">
            <button @click="sendData" class="btn-div-hide-box-send">
              Send
            </button>
          </div>
          <div>
            <div class="popup-sendt">{{ popupMessage }}</div>
          </div>
        </div>
      </div>

      <ul class="days">
        <li
          v-for="day in days"
          :class="{ active: day.active, inactive: !day.active }"
          @click="showInputBox(day.date)"
        >
          {{ day.date }}
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
.current-date {
  font-size: 1.45rem;
  font-weight: 500;
  color: #e2f1ee;
  font-style: italic;
  display: flex;
  justify-content: space-between;
  align-items: end;
}

.calendar {
  padding: 20px;
  background: url("../assets/img/background.png") top center fixed;
  background-size: cover;
}

.calendar ul {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  text-align: center;
}

.calendar .days {
  margin-bottom: 20px;
}

.calendar li {
  color: #333;
  width: calc(100% / 7);
  font-size: 1.07rem;
}

.calendar .weeks li {
  font-weight: 500;
  cursor: default;
}

.calendar .days li {
  z-index: 1;
  cursor: pointer;
  position: relative;
  margin-top: 30px;
}

.days li.inactive {
  color: #ffffff;
}

.days li.active {
  color: #fff;
}

.days li::before {
  position: absolute;
  content: "";
  left: 50%;
  top: 50%;
  height: 40px;
  width: 40px;
  z-index: -1;
  border-radius: 50%;
  transform: translate(-50%, -50%);
}

.days li.active::before {
  background: #f8ccc4;
}

.days li:not(.active):hover::before {
  background: #f8ccc4;
}

.input-container {
  position: fixed;
  top: 20%;
  left: 59%;
  transform: translateX(-50%);
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
  height: 480px;
  width: 500px;
  z-index: 9999;
  display: flex;
}
.input-box {
  display: flex;
  flex-direction: row;
  align-items: center;
  flex-wrap: wrap;
  width: 20px;
}
.input-box input {
  flex: 1;
  margin-right: 10px;
}

.input-hide-box-1 {
  margin-left: 50px;
  display: flex;
}

.input-hide-box-2 {
  display: flex;
  flex-wrap: wrap;
  grid-row-gap: 30px;
  padding-left: 36px;
}

.input-felter-box {
  width: 420px;
  border: 1px solid #1a424b;
}

#input-input-felter-box-besked {
}

.input-hide-box-3 {
  margin-left: 170px;
}

.btn-div-hide-box-x {
  background-color: #cae4e3;
  width: 30px;
  height: 30px;
  color: #1a444d;
  align-content: center;
  font-size: 20px;
  border-radius: 15%;
}

.btn-div-hide-box-x:hover {
  background-color: #f8ccc4;
}

.btn-div-hide-box-send {
  background-color: #fce977;
  font-weight: bold;
  border: none;
  border-radius: 20px;
  width: 150px;
  height: 50px;
  color: #1a444d;
  align-content: center;
  font-size: 14px;
}

.btn-div-hide-box-send:hover {
  background-color: #f8ccc4;
}

.input-hide-box-1-tekst {
  width: 400px;
}

.popup-sendt {
  display: flex;
  width: 480px;
  justify-content: center;
  color: #1a424b;
}

.bestil-tid {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100px;
  background-color: #fce977;
  border: none;
  border-radius: 20px;
}

.bestil-tid:hover {
  background-color: #f8ccc4;
}
.btn-div-kalender {
  background-color: #fce977;
  width: 30px;
  height: 30px;
  color: #1a444d;
  align-content: center;
  font-size: 30x;
}

.btn-div-kalender:hover {
  background-color: #f7eca7;
}

.btn-div-kalender:focus {
  background-color: #fae13e;
}

.bestil-tid-boks {
  display: flex;
  width: 425px;
  justify-content: space-between;
}

.selected-time {
  background-color: #f8ccc4;
}

.uge-dage {
  display: flex;
  justify-content: space-evenly;
  gap: 5%;
}
#uge-dage-tekst {
  color: #cae4e3;
}

#input-input-felter-box-besked {
  display: flex;
  height: 100px;
}
</style>
