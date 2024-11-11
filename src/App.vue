<template>
  <div id="app">
    <!-- Barra de navegación con enlaces a diferentes rutas -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container">
        <router-link class="navbar-brand" to="/">Gestor de Tareas</router-link>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <router-link class="nav-link" to="/add-task">Agregar Tarea</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/fetch-tasks">Extraer Tareas</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/combined-view">Vista Combinada</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Mensaje de bienvenida -->
    <header class="welcome-header">
      <h1>Bienvenido al Gestor de Tareas</h1>
      <p>Organiza, gestiona y visualiza todas tus tareas en un solo lugar.</p>
      <button @click="fetchTasksFromAPI" class="primary-button">Cargar Tareas</button>
    </header>

    <!-- Componente dinámico de cada vista -->
    <router-view 
      :tasks="tasks"
      @add-task="addTask"
      @fetch-tasks="fetchTasksFromAPI"
    />

    <!-- Pie de página -->

  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      // Lista de tareas compartida
      tasks: [],
    };
  },
  methods: {
    // Método para agregar una tarea
    addTask(newTask) {
      this.tasks.push(newTask);
    },

    // Método para extraer tareas desde la API de DummyJSON
    async fetchTasksFromAPI() {
      try {
        const response = await axios.get("https://dummyjson.com/todos");
        // Asignar las tareas obtenidas a la lista de tareas global, manteniendo el formato
        this.tasks = response.data.todos.map((todo) => ({
          id: todo.id,
          todo: todo.todo,
        }));
      } catch (error) {
        console.error("Error al obtener tareas de la API:", error);
      }
    },
  },
  // Cargar tareas de la API al montar el componente
  mounted() {
    this.fetchTasksFromAPI();
  },
};
</script>

<style>
@import 'bootstrap/dist/css/bootstrap.min.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* Estilo de la barra de navegación */
.navbar-nav .nav-link {
  font-weight: bold;
  color: #ffffff;
}

.navbar-nav .nav-link.router-link-exact-active {
  color: #42b983;
}

/* Encabezado de bienvenida */
.welcome-header {
  background-color: #42b983;
  color: white;
  padding: 2rem;
  border-radius: 8px;
  margin: 20px auto;
  max-width: 800px;
}

.welcome-header h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.welcome-header p {
  font-size: 1.2rem;
  margin-bottom: 1.5rem;
}

/* Botón de bienvenida */
.primary-button {
  font-size: 1rem;
  color: #ffffff;
  background-color: #333;
  padding: 0.7rem 1.5rem;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.primary-button:hover {
  background-color: #555;
}


</style>
