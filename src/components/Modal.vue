<template>
  <div>
    <div
      class="modal fade bd-example-modal-lg"
      tabindex="-1"
      role="dialog"
      aria-labelledby="myLargeModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-lg">
        <div class="modal-content">
          <div class="quiz-window-header">
            <div class="quiz-window-title"></div>
            <button
              class="quiz-window-close"
              data-dismiss="modal"
              aria-label="Close"
            >
              &times;
            </button>
          </div>
          <div class="quiz-window-body">
            <div class="gui-window-awards">
              <p class="guiz-awards-row guiz-awards-header">
                <span class="guiz-awards-header-title"
                  >Bu 6 basit adımla daha güçlü ve bulunması zor şifreler
                  oluşturabilirsiniz.</span
                >
              </p>
              <ul class="guiz-awards-row guiz-awards-row-even">
                <li class="guiz-awards-star">
                  <span class="star goldstar">⭐</span>
                </li>
                <li class="guiz-awards-title">
                  Şifrenizi kolayca bulunabilecek bir yerde saklamayın.
                </li>
              </ul>
              <ul class="guiz-awards-row">
                <li class="guiz-awards-star">
                  <span class="star silverstar">⭐</span>
                </li>
                <li class="guiz-awards-title">
                  Şifrenizi belirli aralıklarla değiştirin.
                </li>
              </ul>
              <ul class="guiz-awards-row guiz-awards-row-even">
                <li class="guiz-awards-star">
                  <span class="star bronzestar">⭐</span>
                </li>
                <li class="guiz-awards-title">
                  Şifrenizde isminizi, soyisminizi, evcil hayvanınızın ismini
                  veya değer verdiğiniz birinin ismini kullanmayın.
                </li>
              </ul>
              <ul class="guiz-awards-row">
                <li class="guiz-awards-star">
                  <span class="star rhodiumstar">⭐</span>
                </li>
                <li class="guiz-awards-title">
                  Şifrenizde ardışık sayılar veya harfler kullanmayın. (1234,
                  abc vb.)
                </li>
              </ul>
              <ul class="guiz-awards-row guiz-awards-row-even">
                <li class="guiz-awards-star">
                  <span class="star platinumstar">⭐</span>
                </li>

                <li class="guiz-awards-title">
                  Şifrenizde şehir plakası, doğum tarihi, yaş, evlilik yıl
                  dönümü gibi tarihlere veya sayılara yer vermeyin.
                </li>
              </ul>
              <ul class="guiz-awards-row">
                <li class="guiz-awards-star"><span class="star">⭐</span></li>
                <li class="guiz-awards-title">
                  Şifrenizi 10 karakterden uzun tutun.
                </li>
              </ul>
            </div>
            <div class="guiz-awards-buttons">
              <button
                class="guiz-awards-but-back"
                data-dismiss="modal"
                aria-label="Close"
              >
                <i></i> 👍
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <a href="#" data-toggle="modal" data-target=".bd-example-modal-lg">
      6 adımda güçlü şifre nasıl oluşturulur?
    </a>
  </div>
</template>

<style scoped>
a:hover {
  text-decoration: none;
  color: #373a40;
}
a {
  color: #686d76;
}
* {
  box-sizing: border-box;
}

button,
select,
input {
  font-family: "Roboto", sans-serif;
  font-size: 17px;
}
.quiz-window {
  position: absolute;
  left: 0;
  right: 0;
  top: 50px;
  margin: auto;
  width: 600px;
  border-radius: 4px;
  background: #fff;
  overflow: hidden;
}
.quiz-window-header {
  padding: 30px 15px;
  text-align: center;
  position: relative;
}
.quiz-window-title {
  font-size: 26px;
}
.quiz-window-close {
  position: absolute;
  top: 15px;
  right: 20px;
  padding: 0;
  background: none;
  border: 0;
  width: 30px;
  height: 30px;
  font-size: 60px;
  font-weight: 100;
  line-height: 24px;
  color: #777;
  cursor: pointer;
}
.quiz-window-body {
  background-color: #f9f9f9;
}
.guiz-awards-row {
  margin: 0;
  padding: 10px 40px;
  list-style: none;
}
.guiz-awards-row:after {
  content: "";
  display: table;
  clear: both;
}
.guiz-awards-row-even {
  background-color: #fff;
}
.guiz-awards-row li {
  display: inline-block;
  vertical-align: top;
}
.guiz-awards-header {
  text-align: center;
  padding: 20px 40px;
}
.guiz-awards-star,
.guiz-awards-track,
.guiz-awards-time,
.guiz-awards-header-star,
.guiz-awards-header-track,
.guiz-awards-header-time {
  min-width: 54px;
  text-align: center;
  width: 16%;
}
.guiz-awards-title {
  width: 70%;
  min-width: 160px;
  font-size: 18px;
  font-weight: normal;
  padding-top: 3px;
  text-align: left;
}
.guiz-awards-header-title {
  width: 40%;
  min-width: 160px;
  font-weight: 600;
}
.guiz-awards-subtitle {
  color: #858585;
  font-size: 14px;
  font-weight: 300;
}
.guiz-awards-track,
.guiz-awards-time {
  width: 22%;
  min-width: 80px;
  font-size: 18px;
  line-height: 45px;
}
.guiz-awards-header-track,
.guiz-awards-header-time {
  width: 22%;
  min-width: 80px;
}
.guiz-awards-track .null,
.guiz-awards-time .null {
  color: #bababa;
}
.star {
  display: block;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 2px solid #bdc2c1;
}
.goldstar {
  border-color: #4c8193;
  background: #14b0bf;
}
.silverstar {
  border-color: #557e3a;
  background: #66931f;
}
.bronzestar {
  border-color: #998247;
  background: #aa984b;
}
.rhodiumstar {
  border-color: #743a7f;
  background: #a0409d;
}
.platinumstar {
  border-color: #10393b;
  background: #2b5770;
}

.guiz-awards-buttons {
  background: #fff;
  text-align: center;
  padding: 20px 0;
}
.guiz-awards-but-back {
  display: inline-block;
  background: none;
  border: 1px solid #61a3e5;
  border-radius: 21px;
  padding: 7px 40px 7px 20px;
  color: #61a3e5;
  font-size: 17px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.guiz-awards-but-back:hover {
  background: #61a3e5;
  color: #fff;
}

.guiz-awards-but-back i {
  font-size: 26px;
  line-height: 17px;
  margin-right: 20px;
  position: relative;
  top: 2px;
}
</style>