<template>
<div class="page">


      <div class="airlines">
         <input type="text" v-model="search">
              <h2>Авиакомпании</h2>
              <form>
                      <div style="display: flex">
                         <input 
                          v-model="all"
                          value=""
                         class="check"
                          type="checkbox" 
                          name="all"
                           id="all"
                           >
                        <label for="all" >Все</label>
                      </div>

                      <div>
                         <input type="checkbox" name="astana" id="astana"  v-model="astana"
                          value="">
                        <label for="astana">Air Astana</label>
                      </div>

                      <div>
                       
                        <input type="checkbox" name="bek" id="bek"  v-model="bek"
                          value="">
                         <label for="bek">Bek Air</label>
                      </div>

                      <div>
                              <input type="checkbox" name="fly" id="fly"  v-model="fly"
                          value="">
                        <label for="fly">Fly Arystan</label>
                  
                      </div>

                      <div>
                        <input type="checkbox" name="scat" id="scat"  v-model="scat"
                          value="">
                        <label for="scat">SCAT Airlines</label>
                        
                      </div>

                      <div>
                        <input type="checkbox" name="luft" id="luft"  v-model="luft"
                          value="">
                        <label for="luft">Lufthansa</label>
                        
                      </div>

                      <div>
                       
                        <input type="checkbox" name="turki" id="turki"  v-model="turki"
                          value="">
                         <label for="turki">Turkish Airlines</label>
                      </div>

                      <div>
                        <input type="checkbox" name="chin" id="chin"  v-model="chin"
                          value="">
                        <label for="chin">China Southern Air</label>
                        
                      </div>
              </form>
      </div>
<div class="cards">
      <div class="card" v-for="card, i in cards" :key="i">
        <div style="display: flex; justify-content: space-between; align-items: center">
            <img src="KC.png" alt=""><h2>{{card.company}}</h2>
           <p>Нет багажа</p>
        </div>
         
           <div class="datetime">
                    <div>
                      <h3>{{card.start}}</h3>
                      <h3>{{card.startTime}}</h3>
                    </div>
                    <div>
                      <h3>{{card.end}}</h3>
                      <h3>{{card.endTime}}</h3>
                    </div>
           </div>
             <h3 style="text-align: center">{{card.price}}</h3>
           <button class="btn">Выбрать</button>
            <p style="color: #707276; text-align: center">Цена за всех пассажиров</p>
      </div>
</div>      
</div>  
</template>

<script>
export default {
  name: 'HelloWorld',

  data() {
    return {
      search: '',
      all: false,
      astana: false,
      bek: false,
      fly: false,
      chin: false,
      turki: false,
      air: false,
      

      luft: false,
    
      scat: false,
      
      cards: [
        {
          company: 'Air Astana',
          price: '590 240',
          start: '25 ноя, вс',
          end: '26 ноя, сб',
          startTime: '23:25',
          endTime: '03:45',
          category: 'astana'
        },

        {
          company: 'Bek Air',
          price: '590 240',
          start: '25 ноя, вс',
          end: '26 ноя, сб',
          startTime: '23:25',
          endTime: '03:45',
           category: 'bek'
        },

        {
          company: 'Air Astana',
          price: '590 240',
          start: '25 ноя, вс',
          end: '26 ноя, сб',
          startTime: '23:25',
          endTime: '03:45',
           category: ['astana']
        }
      ]
    }
  },
   computed: {
   filteredCards: function () {
     return this.cards.filter( card => card.category.match(this.search))
   }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/* .cards {
  display: flex;
} */
.page {
  max-width: 1600px;
  margin: auto;
  padding: 10px;
}
.datetime {
  display: flex;
  justify-content: space-between;
}
.card {
  margin-top: 52px;
  height: 408px;
  width: 258px;
  background: #FFFFFF;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
}
.btn {
  margin-left: 25px;
  background: #55BB06;
  border-radius: 4px;
  padding: 7px 12px 8px 12px;
  width: 199px;
  color: white;
  font-weight: bold;
}

    .check {
      background: green !important;
      color: green !important;
      display: block;
    }

    @media(min-width: 300px) {
          
    }
</style>
