<template>
  <div>
    <v-app>
      <div class="answer">
        <div class="wrapper__content">
          <div class="question">
            {{ itemList.text }}
          </div>

          <div class="answer__wrapper" v-if="itemList.type === 'worker'">
            <div class="answer__block">
              <div class="answer__head d-flex">
                <div class="answer__user d-flex">
                  <i class="icon smile mr-2"></i>
                  <span>Ассистент IS</span>
                </div>
                <div class="d-flex">
                  <i class="icon dislike mr-5"></i>
                  <i class="icon share"></i>
                </div>
              </div>
              <div class="answer__worker answer__text">
                <p v-for="(text, index) in itemList.sections" :key="index">
                  {{ text }}
                </p>
                <div class="answer__worker-info d-flex">
                  <img src="../../assets/kadr.png" alt="">
                  <div class="answer__worker-text ml-5">
                    <div>{{ itemList.user[0].fio }}</div>
                    <div class="grey-text">{{ itemList.user[0].position }}</div>
                    <div class="mt-2">Тел: {{ itemList.user[0].phone }}</div>
                    <div class="mt-2">Эл.почта: {{ itemList.user[0].email }}</div>
                    <div class="mt-2">График работы: {{ itemList.user[0].work_schedule }}</div>
                    <div class="mt-2">Кабинет: {{ itemList.user[0].office }}</div>
                  </div>
                </div>
              </div>
              <div class="answer__footer web-only">
                <div class="answer__footer-content d-flex">
                  <div class="answer__footer-input">
                    <v-text-field placeholder="спросить"
                                  prepend-inner-icon="mdi-magnify"
                                  variant="outlined"></v-text-field>
                  </div>
                  <div class="answer__footer-questions d-flex">
                    <div  v-for="(question, index) in itemList.questions" :key="index"
                        class="answer__footer-question d-flex ml-5">
                      <i class="icon search-small mr-2"></i>
                      <span>{{ question }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="answer__footer mobile-only">
              <div class="answer__footer-content d-flex">
                <div class="answer__footer-input">
                  <v-text-field placeholder="спросить"
                                prepend-inner-icon="mdi-magnify"
                                variant="outlined"></v-text-field>
                </div>
                <div class="answer__footer-questions d-flex">
                  <div  v-for="(question, index) in itemList.questions" :key="index"
                        class="answer__footer-question d-flex ml-5">
                    <i class="icon search-small mr-2"></i>
                    <span>{{ question }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="answer__wrapper" v-if="itemList.type === 'text'">
            <div class="answer__block">
              <div class="answer__head d-flex">
                <div class="answer__user d-flex">
                  <i class="icon smile mr-2"></i>
                  <span>Ассистент IS</span>
                </div>
                <div class="d-flex">
                  <i class="icon dislike mr-5"></i>
                  <i class="icon share"></i>
                </div>
              </div>
              <div>
                <div class="answer__text">
                  <p v-for="(text, index) in itemList.sections" :key="index">
                    {{ text }}
                  </p>
                </div>
                <div class="answer__docs d-flex">
                  <div v-if="itemList.documents[0].statement"
                      class="answer__doc answer__docs-statement mr-5 d-flex">
                    <i class="icon statement mr-2"></i>
                    <div class="answer__docs-text">
                      Заявление на отпуск
                      <span class="grey-text">Скачать</span>
                    </div>
                  </div>

                  <div v-if="itemList.documents[0].manual"
                      class="answer__doc answer__docs-manual mr-5 d-flex">
                    <i class="icon manual mr-2"></i>
                    <div class="answer__docs-text">
                      Инструкция
                      по заполнению заявления
                      <span class="grey-text">Открыть</span>
                    </div>
                  </div>

                  <div v-if="itemList.documents[0].order"
                      class="answer__doc answer__docs-order mr-5 d-flex">
                    <i class="icon order mr-2"></i>
                    <div class="answer__docs-text">
                      Внутреннее рапоряжение
                      <span class="grey-text">Скачать</span>
                    </div>
                  </div>

                  <div v-if="itemList.documents[0].labor_code"
                      class="answer__doc answer__docs-order mr-5 d-flex">
                    <i class="icon order mr-2"></i>
                    <div class="answer__docs-text">
                      Трудовой кодекс РФ
                      <span class="grey-text">Скачать</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="answer__footer web-only">
                <div class="answer__footer-content d-flex">
                  <div class="answer__footer-input">
                    <v-text-field placeholder="спросить"
                                  prepend-inner-icon="mdi-magnify"
                                  variant="outlined"></v-text-field>
                  </div>
                  <div class="answer__footer-questions d-flex">
                    <div  v-for="(question, index) in itemList.questions" :key="index"
                          class="answer__footer-question d-flex ml-5">
                      <i class="icon search-small mr-2"></i>
                      <span>{{ question }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="answer__footer mobile-only">
              <div class="answer__footer-content d-flex">
                <div class="answer__footer-input">
                  <v-text-field placeholder="спросить"
                                prepend-inner-icon="mdi-magnify"
                                variant="outlined"></v-text-field>
                </div>
                <div class="answer__footer-questions d-flex">
                  <div  v-for="(question, index) in itemList.questions" :key="index"
                        class="answer__footer-question d-flex ml-5">
                    <i class="icon search-small mr-2"></i>
                    <span>{{ question }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </v-app>
  </div>
</template>

<script>

export default {
  name: 'Answer',

  components: {

  },

  props: {
    item: Object,
  },
  data() {
    return {
      itemList: {},
      itemNumb: '',
    }
  },

  watch: {
    item: {
      deep: true,
      handler(newVal) {
        if (newVal === null) {
          this.itemList = {};
          this.itemNumb = '';
        } else {
          this.itemList = { ...newVal};
          this.itemNumb = newVal.numb;
        }
      },
    },
  },

  mounted() {
    if (this.item !== null) {
      const {
        numb,
      } = this.itemList;
      this.itemList = this.item;
      this.itemNumb = numb;
    }
  },

  computed: {
  },
  methods: {
  },
}

</script>

<style lang="scss">
@import './Answer.scss';
</style>
