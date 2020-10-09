<template>
  <div class="generator">
    <h3>{{ message }} {{ version }}</h3>
    <div class="container">
      <div class="form-group">
        <div class="col">
          <div class="">
            <input
              type="text"
              class=""
              v-on:click="select"
              v-model="newPassword"
              id="generatedPassword"
            />
            <a v-on:click="copy" href="#">Kopyala</a>
          </div>
          <span v-if="copied">Kopyalandı</span>
          <br />
        </div>
      </div>

      <br />

      <div class="form-group">
        <div class="col">
          <label for="formControlRange">Uzunluk: {{ length }}</label>
          <input
            type="range"
            class="form-control-range"
            id="formControlRange"
            min="4"
            max="16"
            v-model="length"
            v-on:change="getLen"
          />
        </div>
      </div>

      <div class="col">
        <label for="uppercase">Büyük Harf</label>
        <input
          type="checkbox"
          id="uppercase"
          v-bind:checked="uppercase"
          v-on:change="uppercase = !uppercase"
        />
      </div>
      <div class="col">
        <label for="lowercase">Küçük Harf</label>
        <input
          type="checkbox"
          id="lowercase"
          v-bind:checked="lowercase"
          v-on:change="lowercase = !lowercase"
        />
      </div>
      <div class="col">
        <label for="numbers">Rakam</label>
        <input
          type="checkbox"
          id="numbers"
          v-bind:checked="number"
          v-on:change="number = !number"
        />
      </div>

      <button v-on:click="generatePass" class="btn btn-success">Oluştur</button>
    </div>
  </div>
</template>
<style scoped>
</style>

<script>
export default {
  name: "PasswordGenerator",
  props: { message: String, version: String },
  data: () => {
    return {
      min: 4,
      max: 16,
      length: 8,
      lowercase: false,
      uppercase: false,
      number: true,
      copied: false,
      newPassword: "",
      lowers: "abcdefghijklmnopqrstuvwxyz",
      uppers: "abcdefghijklmnopqrstuvwxyz".toUpperCase(),
      numbers: "1234567890",
    };
  },
  methods: {
    getLen: function (value) {
      this.length = value.target.valueAsNumber;
    },
    select: function () {
      var copyText = document.getElementById("generatedPassword");
      copyText.select();
    },

    copy: function () {
      var copyText = document.getElementById("generatedPassword");
      copyText.select();
      copyText.setSelectionRange(0, 99999);
      document.execCommand("copy");
      this.copied = true;
    },

    generatePass: function () {
      this.copied = false;
      var password = "";
      var random;
      var cases = "";
      cases = this.lowercase ? this.lowers : "";
      cases += this.uppercase ? this.uppers : "";
      cases += this.number ? this.numbers : "";
      if (cases) {
        for (let index = 0; index < this.length; index++) {
          random = Math.floor(Math.random() * cases.length);
          password += cases[random];
        }
        this.newPassword = password;
      } else {
        this.newPassword = "En az bir kutucuğu işaretlemelisiniz.";
      }
    },
  },
};
</script>