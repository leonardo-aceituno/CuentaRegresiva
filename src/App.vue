<template>
  <div class="container w-25 my-4 p-3 border rounded-3">
    <h3 class="text-center mb-3 ">Cuenta regresiva</h3>

    <div class="d-flex justify-content-evenly mb-3">
      <button
        v-for="(item, index) of botones"
        :key="index"
        @click="regresiva(item.numero)"
        class="btn btn-warning mb-3"
      >
        {{ item.nombre }}
      </button>
    </div>
    <div>
      <h3 class="text-center fs-1">{{ contador }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tarea: "",
      botones: [
        { nombre: " 3 segundos", numero: 3 },
        { nombre: " 5 segundos", numero: 5 },
        { nombre: "10 segundos", numero: 10 },
      ],
      contador: 0,
    };
  },
  methods: {
    regresiva(num) {
      this.contador = num;

      let id = setInterval(() => {
        if (this.contador === 0) {
          clearInterval(id);
        } else {
          this.contador = this.contador - 1;
        }
      }, 1000);
    },
  },
};
</script>


