<template>
  <div class="generator">
    <h3>{{ message }} {{ version }}</h3>

    <div class="form-group">
      <div class="row justify-content-sm-center">
        <input
          type="text"
          class="form-control col-md-5"
          v-on:click="select"
          v-model="newPassword"
          id="generatedPassword"
          readonly
        />
        <a
          v-on:click="copy"
          href="#"
          v-text="copied ? 'Kopyalandı' : 'Kopyala'"
          class="btn btn-primary"
          >Kopyala
        </a>
      </div>
    </div>

    <div class="form-group">
      <div class="col">
        <label for="formControlRange">Uzunluk: {{ length }}</label>
        <input
          type="range"
          class="form-control-range"
          id="formControlRange"
          :min="min"
          :max="max"
          v-model="length"
          v-on:change="getLen"
        />
      </div>
    </div>

    <div class="form-group">
      <div class="col">
        <div class="row justify-content-center">
          <label for="uppercase" class="mr-5">Büyük Harf</label>
          <input
            type="checkbox"
            id="uppercase"
            v-bind:checked="uppercase"
            v-on:change="uppercase = !uppercase"
          />
        </div>
        <div class="row justify-content-center">
          <label for="lowercase" class="mr-5">Küçük Harf</label>
          <input
            type="checkbox"
            id="lowercase"
            v-bind:checked="lowercase"
            v-on:change="lowercase = !lowercase"
          />
        </div>
        <div class="row justify-content-center">
          <label for="numbers" class="mr-5">Rakam</label>
          <input
            type="checkbox"
            id="numbers"
            v-bind:checked="number"
            v-on:change="number = !number"
          />
        </div>
      </div>
    </div>

    <div class="form-group">
      <button v-on:click="generatePass" class="btn btn-success">Oluştur</button>
    </div>
  </div>
</template>
<style scoped>
.btn-success,
.btn-primary {
  background: #3a6e6b;
  border-color: #3a6e6b;
}
.btn-success:hover,
.btn-success:active,
.btn-primary:hover,
.btn-primary:active,
.btn-success.focus,
.btn-success:focus,
.btn-primary.focus,
.btn-primary:focus {
  background: #364d60;
  border-color: #364d60;
}

.btn-success:not(:disabled):not(.disabled).active,
.btn-success:not(:disabled):not(.disabled):active,
.show > .btn-success.dropdown-toggle {
  background: #364d60;
  border-color: #364d60;
}
.btn-primary:not(:disabled):not(.disabled).active,
.btn-primary:not(:disabled):not(.disabled):active,
.show > .btn-primary.dropdown-toggle {
  background: #364d60;
  border-color: #364d60;
}
</style>

<script>
export default {
  name: "PasswordGenerator",
  props: { message: String, version: String },
  data: () => {
    return {
      min: 6,
      max: 16,
      length: 8,
      lowercase: false,
      uppercase: false,
      number: true,
      copied: false,
      newPassword: "Tıkla ve Şifre Oluştur",
      lowerLetters: "abcdefghijklmnopqrstuvwxyz",
      upperLetters: "abcdefghijklmnopqrstuvwxyz".toUpperCase(),
      digits: "1234567890",
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
      cases = this.lowercase ? this.lowerLetters : "";
      cases += this.uppercase ? this.upperLetters : "";
      cases += this.number ? this.digits : "";
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