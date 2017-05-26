<template lang="html">
  <div class="home">
    <div class="container">
      <div class="columns">
        <div class="column is-offset-2">
          <center><h2>KMUTNBT GRADE</h2><br></center>
        </div>
      </div>
      <div class="columns">
        <div class="column is-offset-2 is-3">
            <div class="field">
              <label class="label">เกรดเฉลี่ยสะสม</label>
              <p class="control">
                <input class="input" type="text" placeholder="Gpa">
              </p>
            </div>
        </div>
        <div class="column">
          <a   class="button is-info is-small" @click="createTb(subject)">ตกลง</a><br><br><br>
          <table v-if="showtb"  class="table is-striped is-narrow">
            <thead>
              <th>#</th><th>ชื่อวิชา</th><th>หน่วยกิต</th><th>เกรด</th>
            </thead>
            <tr>
              <td>1</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits1"></td>
              <td><input class="input" type="text"  v-model="grades1"></td>
            </tr>
            <tr>
              <td>2</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits2"></td>
              <td><input class="input" type="text"  v-model="grades2"></td>
            </tr>
            <tr>
              <td>3</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits3"></td>
              <td><input class="input" type="text"  v-model="grades3"></td>
            </tr>
            <tr>
              <td>4</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits4"></td>
              <td><input class="input" type="text"  v-model="grades4"></td>
            </tr>
            <tr>
              <td>5</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits5"></td>
              <td><input class="input" type="text"  v-model="grades5"></td>
            </tr>
            <tr>
              <td>6</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits6"></td>
              <td><input class="input" type="text"  v-model="grades6"></td>
            </tr>
            <tr>
              <td>7</td>
              <td><input class="input" type="text" ></td>
              <td><input class="input" type="text" v-model="credits7"></td>
              <td><input class="input" type="text"  v-model="grades7"></td>
            </tr>
            <tr>
              <td><a  class="button is-info is-small" @click="cal">คำนวณ</a></td>
            </tr>
          </table>
        </div>

      </div>
      <div class="columns">
        <div class="column is-offset-2">
            {{gpa}}
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data () {
    return {
      subject: '',
      showtb: false,
      credits1: '',
      credits2: '',
      credits3: '',
      credits4: '',
      credits5: '',
      credits6: '',
      credits7: '',
      grades1: '',
      grades2: '',
      grades3: '',
      grades4: '',
      grades5: '',
      grades6: '',
      grades7: '',
      gpa: ''
    }
  },
  methods: {
    createTb (sub) {
      this.showtb = true
    },
    cal (sub) {
      let vm = this
      let crt = (parseInt(vm.credits1) + parseInt(vm.credits2) + parseInt(vm.credits3) + parseInt(vm.credits4) + parseInt(vm.credits5) + parseInt(vm.credits6) + parseInt(vm.credits7))
      vm.gpa = ((vm.credits1 * vm.grades1) + (vm.credits2 * vm.grades2) + (vm.credits3 * vm.grades3) + (vm.credits4 * vm.grades4) + (vm.credits5 * vm.grades5) + (vm.credits6 * vm.grades6) + (vm.credits7 * vm.grades7))
      console.log(crt)
      vm.gpa = (vm.gpa / crt).toFixed(2)
      console.log(vm.gpa)
    }
  }
}
</script>

<style lang="css">
.home{
  margin-top: 40PX;
  font-family: RSU;
}
</style>
