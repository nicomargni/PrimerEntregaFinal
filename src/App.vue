<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>Inicia sesion</h1>
    <login-prueba />
    <button @click="registroValor()">Not a member? Register</button>
    <registro-prueba v-if="registro" />
    <h2 style="margin-top:45px">Carrito</h2>
    <prod-carrito class="carro"/>
    <h2>Lista de productos</h2>
    <div class="tarjeta">
      <prod-lista
        class="tarjetaHijo"
        v-for="(producto, index) of productos"
        :key="index"
        :titulo="producto.titulo"
        :imagen="producto.imagen"
        :costo="producto.costo"
        :stock="producto.stock"
      />
    </div>
    <button @click="mostrarInformacion()">
      Quieres ver mas informacion sobre estos videojuegos?
    </button>
    <div v-if="mostrarInfo">
      <info-prods
        v-for="(informacion, index) of info"
        :key="index"
        :titulo="informacion.titulo"
        :descripcion="informacion.descripcion"
      />
    </div>
  </div>
</template>

<script>
import LoginPrueba from "./components/LoginPrueba.vue";
import RegistroPrueba from "./components/RegistroPrueba.vue";
import ProdLista from "./components/ProdLista.vue";
import ProdCarrito from "./components/ProdCarrito.vue";
import InfoProds from "./components/InfoProds.vue";

export default {
  name: "App",
  components: {
    LoginPrueba,
    RegistroPrueba,
    ProdLista,
    ProdCarrito,
    InfoProds,
  },
  data() {
    return {
      registro: false,
      mostrarInfo: false,
      productos: [
        {
          id:1,
          titulo: "GTA V",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:2,
          titulo: "Batman arkham city",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:3,
          titulo: "Simpsons The Game",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:4,
          titulo: "GTA IV",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:5,
          titulo: "God of war 4",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: false,
        },
        {
          id:6,
          titulo: "Dying light 2",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:7,
          titulo: "Deus ex",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          id:8,
          titulo: "Fallout new vegas",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: false,
        },
      ],
      info: [
        {
          titulo: "GTA V",
          descripcion:
            "Se trata de una aventura de acci??n de mundo abierto con multitud de misiones en la que encarnamos a tres personajes distintos: Trevor, Michael y Franklin. Adem??s, cuenta con GTA Online, el modo multijugador en l??na de GTA 5.",
        },
        {
          titulo: "Batman Arkham City",
          descripcion:
            "Batman: Arkham City se construye en base a los intensos y atmosf??ricos pilares asentados en Batman: Arkham Asylum, y env??a a los jugadores a Arkham City, el nuevo 'hogar' de m??xima seguridad para todos los matones, g??ngsters y criminales dementes de Ciudad G??tica. Ubicado dentro de unas paredes fuertemente fortificadas de un distrito en expansi??n en el coraz??n de la ciudad, esta secuela tan esperada presenta una nueva historia que re??ne a un nuevo elenco estelar de personajes cl??sicos y villanos mortiferos del universo de Batman.",
        },
        {
          titulo: "Simpsons The Game",
          descripcion:
            "La familia Simpson se entera de que son parte de un videojuego y reciben superpoderes para salvar a sus predecesores de 8 bits. Segundo videojuego narrativo de alto presupuesto basado en la franquicia Los Simpson; como el anterior (Hit & Run) estuvo escrito y producido por el equipo habitual de la serie..",
        },
        {
          titulo: "GTA IV",
          descripcion:
            "La historia transcurre en una actualizaci??n de la antigua Liberty City, donde Niko Bellic, un ex-soldado de los Balcanes, llega a Am??rica en busca del sue??o americano, en parte atra??do por las mentiras de su primo Roman, pues le dijo que viv??a en una mansi??n con varios coches deportivos y muchas chicas hermosas.",
        },
        {
          titulo: "God of War 4",
          descripcion:
            "Kratos, que ha dejado atr??s el mundo de los dioses, deber?? adaptarse a tierras que no le son familiares, afrontar peligros inesperados y aprovechar una segunda oportunidad de ejercer como padre.",
        },
        {
          titulo: "Dying light 2",
          descripcion:
            "Dying Light 2, secuela del excelente t??tulo de mundo abierto, ofrece una visi??n postapocal??ptica y ??nica de la edad oscura moderna, una realidad despiadada y sombr??a en la que hombre e infectado representan la misma amenaza. Eres Aiden Caldwell, un sobreviviente infectado.",
        },
        {
          titulo: "Deus ex",
          descripcion:
            "Deus Ex es un videojuego para ordenador, de rol de acci??n desarrollado por Ion Storm y publicado por Eidos Interactive en el a??o 2000. La historia se desarrolla en un futuro dist??pico durante los a??os 2050, con elementos e historias de ciberpunk.",
        },
        {
          titulo: "Fallout New Vegas",
          descripcion:
            "En un comienzo se cre??a que Fallout: New Vegas ser??a una secuela o un complemento de su antecesor en la saga, Fallout 3. Se trata, no obstante, de un juego con una trama aislada de la historia de Fallout 3, aunque la misma est?? estrechamente relacionada con las tramas del Fallout original y Fallout 2, y posee algunos elementos en com??n con estos ??ltimos. Los sucesos del juego tienen lugar unos 120 a??os despu??s de los acontecimientos del Fallout original, 40 a??os despu??s de los de Fallout 2 y cuatro a??os despu??s de los de Fallout 3, y si bien Fallout: New Vegas ofrece una experiencia al jugador parecida con respecto a Fallout 3, ning??n personaje en com??n aparece entre el mismo y Fallout 3",
        },
      ],
    };
  },
  methods: {
    registroValor() {
      this.registro = true;
    },
    mostrarInformacion() {
      this.mostrarInfo = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: linear-gradient(to left, yellow, red);
}
.tarjeta {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding: 5px;
}
.tarjetaHijo {
  margin: 5px;
  margin-top: 40px;
}
.carro {
  border: solid 1px;
  display: flex;
  flex-direction: column;
  margin: 30px;
}
</style>
