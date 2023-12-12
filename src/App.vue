<script setup>
import { ref } from 'vue'

let person1 = ref(true)
let person2 = ref(false)
let person3 = ref(false)


function show (index){

if(index===1){
 this.person1 = false;
 this.person2 = true;
 this.person3 = false 
} else if(index ===2){
  this.person1 = false;
  this.person2 = false;
  this.person3 = true
}else{
  this.person1 = true;
 this.person2 = false;
 this.person3 = false 
}

}

const tendent = ref('Tendencias')
const msg = ref('mensajes directos')

let tendencias = ref([
  { tendent: '#titanic', done: 1 },
  { tendent: '#milonarios', done: 1 },
  { tendent: '#FinalSemestre', done: 1 },
  { tendent: '#UFC', done: 1 },
  { tendent: '#colombiaMarcha', done: 1 },
  { tendent: '#UFPSO', done: 1 }
])

let people = ([
  {people: 'Marcos Pérez', time: 'Hace 10 minutos'},
  {people: 'Juana Contreras', time: 'Hace 10 minutos' },
  {people:  'Anonymus',   time:'Hace una hora'},
])


// let mensajes = ref([
//   {people: 'coco77', texto: [{
//     msj: 'Hola, espero estés muy bien...'
//   }]},
// ])


// let mensajes = [{

//   people: {
//     name: 'Marcos Pérez', t: [{
//       m1: 'Hola, espero estés muy bien...'
//     },{
//       m2: 'Necesito un favor tuyo: D'
//     },{
//       m3: 'Cuando te conectes por favor me contestas y te cuento lo que necesito. Gracias.'
//     }
      
     
//     ]
//   }

// },{
//   people: {
//     name: 'Juana contreras', t: [{
//       m1: 'Hola, espero estés muy bien...',
//       m2: 'Necesito un favor tuyo: D',
//       m3: 'Cuando te conectes por favor me contestas y te cuento lo que necesito. Gracias.'
//     }]
// }
// },
// {
//   people: {
//     name: 'Anonymus', t: [{
//       m1: 'Hola, espero estés muy bien...',
//       m2: 'Necesito un favor tuyo: D',
//       m3: 'Cuando te conectes por favor me contestas y te cuento lo que necesito. Gracias.'
//     }]
// }
// }
  
// ]


// let day = ref(new Date().getDate());
// let month = ref(new Date().getMonth()+1);
// let anio = ref( new Date().getFullYear());

// let date = ref(( day.value + "/" + month.value + "/" + anio.value ));


// let clock = new Date() 
// let hour =   clock.getHours() 
// let minutes = clock.getMinutes() 
 

//  let print_clock = ref(hour + ":" + minutes);

let date = new Date();
let fechaAndHora = ref(date.toLocaleString());


let mensajes = [
  {
    mensajePerOne: 'hola, espero que estes muy bien y que pasaras un lindo día ',
    mensajePerTwo: 'Bonjour, jespère que vous allez bien et que vous passez une bonne journée.',
    mensajePerthree: 'Hello, I hope you are well and have a nice day.'
  },
  {
    mensajePerOne: 'hola, buenas tardes. Apenas puedas llamame',
    mensajePerTwo: 'Bonjour bon après-midi. Tu peux à peine mappeler',
    mensajePerthree: 'hello, good afternoon. You can barely call me'
  },
  {
    mensajePerOne: 'Mañana va a ser un buen dia',
    mensajePerTwo: 'Demain sera une bonne journée',
    mensajePerthree: 'Tomorrow is going to be a good day'
  }
]




</script>

<template>
  <div
    class="mx-auto container bg-slate-500 text-white h-16 flex items-center justify-center text-3xl font-semibold"
  >
    <h1 class="font-">Coco77</h1>
  </div>

  <div class="text-white bg-slate-600 flex container mx-auto h-screen">
    <div class="w-[10%] bg-black flex flex-col items-center">
      <div
        class="h-16 bg-white w-16 rounded-md mt-8 mb-2 bg-[url(https://media.licdn.com/dms/image/D4E03AQE72ePewxr9Rg/profile-displayphoto-shrink_800_800/0/1682260229955?e=2147483647&v=beta&t=qBLrapCI0mu6K0n3uKUPPhQoUZFFHwnJnAp4gloPjNE)] bg-center bg-[length:120%_120%]"
      ></div>
      <p class="text-2xl font-mono text-gray-400">Perfil</p>
    </div>

    <div class="w-[30%] bg-slate-800 px-8 ">

      <h1 class="text-3xl mt-10 uppercase ">{{ tendent }}</h1>

      <div class="mt-8 text-2xl  " v-for="(tendt, index) in tendencias" :key="index">
        {{ tendt.tendent }}
      </div>

      <div class="mt-20">
        <h2 class="uppercase text-3xl ml-3">{{ msg }}</h2>

        <div @click="show(index)" v-for="(p,index) in people" :key="index" class="hover:cursor-pointer mt-4 bg-gray-400 rounded p-3 flex ">
         
          <div class=" h-16 w-16 rounded-full bg-[url(https://media.licdn.com/dms/image/D4E03AQE72ePewxr9Rg/profile-displayphoto-shrink_800_800/0/1682260229955?e=2147483647&v=beta&t=qBLrapCI0mu6K0n3uKUPPhQoUZFFHwnJnAp4gloPjNE)] bg-center bg-[length:100%_100%]">
          </div>

          <div class="ml-3 my-auto">
            <h3>{{ p.people }}</h3>
            <h4>{{ p.time }}</h4>
            
          </div>
        </div>

      </div>
    </div>

    <div class="w-[40%] bg-slate-700">
      <h1 class="text-3xl ml-8 mt-8 mr-4">Name</h1>

      <div v-show="person1" v-for="(m,index) in mensajes" :key="index" class=" bg-slate-800 text-gray-400 mx-auto w-[90%] h-24 rounded border-2 text-white font-semibold mt-4 " >
        <div class="p-2">{{ m.mensajePerOne }}</div>
        <div class="bg-red-400 flex justify-end">  <h1>{{fechaAndHora}}</h1>
        </div>
      </div>

      <div v-show="person2" v-for="(m,index) in mensajes" :key="index" class=" bg-slate-800 text-gray-400 mx-auto w-[90%] h-24 rounded border-2 text-white font-semibold mt-4 " >
        <div class="p-2">{{ m.mensajePerTwo }}</div>
        <div class="bg-red-400 flex  justify-end">

          <h1 >{{fechaAndHora}}</h1>
        </div>
      </div>

      <div v-show="person3" v-for="(m,index) in mensajes" :key="index" class=" bg-slate-800 text-gray-400 mx-auto w-[90%] h-24 rounded border-2 text-white font-semibold mt-4 p-2 my-2 " >
        <div class="p-2">{{ m.mensajePerthree }}</div>
        <div class="bg-red-400 flex  justify-end">
          <h1 >{{fechaAndHora}}</h1>
        </div>
      </div>
    
    </div>
    <div class="w-[20%] bg-slate-800">Publicidad</div>
  </div>
</template>

<style scoped></style>
