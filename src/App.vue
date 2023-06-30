 <template>
  <div class="container">
    <Header title= "Task Tracker" />
    <Tasks @toggle-reminder="toggleReminder" @deleteTask='deleteTask' :tasks ="tasks"/>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'

const tasks = ref([]);
onMounted(() => {
  tasks.value = [
    {
      id: 1,
      text: "hello",
      day: "march 20",
      reminder: true
    },
    {
      id: 2,
      text: "hel",
      day: "march 20",
      reminder: true
    },
    {
      id: 3,
      text: "helo",
      day: "march 20",
      reminder: false
    }
  ];
});

const deleteTask = (id) => {
  if(confirm('Are you sure?!!'))
  {
  //tasks.value = tasks.value.filter((task) => task.id == id); //explanation in my book
  tasks.value = tasks.value.filter((task) => task.id !== id); //explanation in my book
  }

};
const toggleReminder = (id) => {
  /*
  tasks.value = tasks.value.map((task) => {
    return task.id === id ? { ...task, reminder: !task.reminder } : task;
  });
  */
 console.log(id)
}

</script>


<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Poppins", sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
