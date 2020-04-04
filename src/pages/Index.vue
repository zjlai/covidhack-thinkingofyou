<template>
  <q-page class="fit">
    <background />
    <q-fab icon="person" color="red" class="float-right" size="lg" flat />
    <div class="row fit fixed-center">
      <div class="col-6 q-pl-lg">
        <h1 class="text-white text-weight-bolder text-uppercase">Hello Mary!</h1>
        <h3 class="text-white text-weight-light">Join us today to bring blessings to your friends and loved ones today. There is no better time than now. <span style="background:rgba(44,13,214,0.8)" class="q-px-md">#thinkingofyou</span></h3>
        <q-separator color="transparent" style="margin-bottom:450px" />
        <div style="background:rgba(0,0,0,0.1)">
          <h4 class="text-white text-weight-thin q-mb-none">People who have joined this movement: 847</h4>
          <h4 class="text-white text-weight-thin q-mt-none">Blessings sent: 2304</h4>
        </div>
      </div>
      <div class="col-6 q-pa-lg row justify-center items-center">
        <q-card dark bordered class="blessings">
          <q-card-section>
            <p class="text-overline">MY BLESSINGS</p>
          </q-card-section>
          <q-card-section>
            <!--<q-chat-message
              label="Saturday, 4th April"
            />-->
            <q-chat-message
              v-for="(blessing,idx) in blessings"
              :key="idx"
              :text="blessing.text"
              :name="blessing.name"
              :stamp="blessing.stamp"
              :avatar="blessing.avatar"
            />
          </q-card-section>
          <q-space />
          <q-card-section class="bg-white absolute-bottom">
            <q-input type="textarea" autogrow square  dense placeholder="send a blessing!">
              <template v-slot:append>
                <q-icon color="primary" name="send" />
              </template>
            </q-input>
          </q-card-section>
        </q-card>
      </div>
    </div>
    <div class="footer fixed-bottom shade">
      <div class="row">
        <div class="col-auto">
        </div>
        <div class="col-grow">
          <verse class="text-center" />
        </div>
        <div class="col-auto">
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import Background from '../components/background'
import Verse from '../components/quotations'

export default {
  name: 'MainPage',
  components: {
    Background,
    Verse
  },
  data () {
    return {
      blessings: [
        { avatar: 'https://cdn.quasar.dev/img/avatar2.jpg', text: ['Hey there! just thought of you and wanted to let you know that I am thinking and praying for you! Stay safe!'], stamp: '~a blessing for you', name: 'Jane' },
        { avatar: 'https://cdn.quasar.dev/img/avatar3.jpg', text: ['hwaiting 💪🏻'], stamp: '~a blessing for you', name: 'Hyojin' },
        { avatar: 'https://cdn.quasar.dev/img/avatar1.jpg', text: ['Sis, Let\'s grab a beer when this is over. In the meantime stay tough.'], stamp: '~a blessing for you', name: 'Barry' },
        { avatar: 'https://cdn.quasar.dev/img/avatar1.jpg', text: ['send help am chionging an assignment now XD'], stamp: '~a blessing for you', name: 'Barry' }
      ]
    }
  }
}
</script>
<style>
.textarea {
  font-size: 24px;
  line-height: 1.5em !important;
  font-weight: 300;
  padding-bottom: 20px;
}
.blessings {
  background: rgba(0,0,0,0.4);
  width: 80%;
  height: 90%;
  max-height:90%;
}
.shade {
  background: rgb(0,0,0);
  background: linear-gradient(0deg, rgba(0,0,0,0.4248074229691877) 0%, rgba(0,0,0,0.14469537815126055) 67%, rgba(0,0,0,0) 100%);
}
</style>
