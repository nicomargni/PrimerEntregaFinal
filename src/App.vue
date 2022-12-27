<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>Inicia sesion</h1>
    <login-prueba />
    <button @click="registroValor()">Not a member? Register</button>
    <registro-prueba v-if="registro" />

    <div class="carro">
      <h2>Carrito</h2>
      <prod-carrito
        v-for="(elemento, index) of carrito"
        :key="index"
        :titulo="elemento.titulo"
        :precio="elemento.precio"
      />
      <h3>Total:$2400</h3>
    </div>

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
          titulo: "GTA V",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "Batman arkham city",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "Simpsons The Game",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "GTA IV",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "God of war 4",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: false,
        },
        {
          titulo: "Dying light 2",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "Deus ex",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: true,
        },
        {
          titulo: "Fallout new vegas",
          imagen:
            "https://sm.ign.com/ign_es/tag/v/videojuego/videojuegos_4ze8.jpg",
          costo: 1200,
          stock: false,
        },
      ],
      carrito: [
        {
          titulo: "Deus ex",
          precio: 1200,
        },
        {
          titulo: "Dying Light 2",
          precio: 1200,
        },
      ],
      info: [
        {
          titulo: "GTA V",
          descripcion:
            "Se trata de una aventura de acción de mundo abierto con multitud de misiones en la que encarnamos a tres personajes distintos: Trevor, Michael y Franklin. Además, cuenta con GTA Online, el modo multijugador en lína de GTA 5.",
        },
        {
          titulo: "Batman Arkham City",
          descripcion:
            "Batman: Arkham City se construye en base a los intensos y atmosféricos pilares asentados en Batman: Arkham Asylum, y envía a los jugadores a Arkham City, el nuevo 'hogar' de máxima seguridad para todos los matones, gángsters y criminales dementes de Ciudad Gótica. Ubicado dentro de unas paredes fuertemente fortificadas de un distrito en expansión en el corazón de la ciudad, esta secuela tan esperada presenta una nueva historia que reúne a un nuevo elenco estelar de personajes clásicos y villanos mortiferos del universo de Batman.",
        },
        {
          titulo: "Simpsons The Game",
          descripcion:
            "La familia Simpson se entera de que son parte de un videojuego y reciben superpoderes para salvar a sus predecesores de 8 bits. Segundo videojuego narrativo de alto presupuesto basado en la franquicia Los Simpson; como el anterior (Hit & Run) estuvo escrito y producido por el equipo habitual de la serie..",
        },
        {
          titulo: "GTA IV",
          descripcion:
            "La historia transcurre en una actualización de la antigua Liberty City, donde Niko Bellic, un ex-soldado de los Balcanes, llega a América en busca del sueño americano, en parte atraído por las mentiras de su primo Roman, pues le dijo que vivía en una mansión con varios coches deportivos y muchas chicas hermosas.",
        },
        {
          titulo: "God of War 4",
          descripcion:
            "Kratos, que ha dejado atrás el mundo de los dioses, deberá adaptarse a tierras que no le son familiares, afrontar peligros inesperados y aprovechar una segunda oportunidad de ejercer como padre.",
        },
        {
          titulo: "Dying light 2",
          descripcion:
            "Dying Light 2, secuela del excelente título de mundo abierto, ofrece una visión postapocalíptica y única de la edad oscura moderna, una realidad despiadada y sombría en la que hombre e infectado representan la misma amenaza. Eres Aiden Caldwell, un sobreviviente infectado.",
        },
        {
          titulo: "Deus ex",
          descripcion:
            "Deus Ex es un videojuego para ordenador, de rol de acción desarrollado por Ion Storm y publicado por Eidos Interactive en el año 2000. La historia se desarrolla en un futuro distópico durante los años 2050, con elementos e historias de ciberpunk.",
        },
        {
          titulo: "Fallout New Vegas",
          descripcion:
            "En un comienzo se creía que Fallout: New Vegas sería una secuela o un complemento de su antecesor en la saga, Fallout 3. Se trata, no obstante, de un juego con una trama aislada de la historia de Fallout 3, aunque la misma está estrechamente relacionada con las tramas del Fallout original y Fallout 2, y posee algunos elementos en común con estos últimos. Los sucesos del juego tienen lugar unos 120 años después de los acontecimientos del Fallout original, 40 años después de los de Fallout 2 y cuatro años después de los de Fallout 3, y si bien Fallout: New Vegas ofrece una experiencia al jugador parecida con respecto a Fallout 3, ningún personaje en común aparece entre el mismo y Fallout 3",
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
  margin-top: 50px;
  align-items: center;
}
</style>
