<template>
  <v-app>
    <v-toolbar title="Todo App"></v-toolbar>

    <v-main>
      <v-container>
        <div class="d-flex align-center">
          <v-text-field
            clearable
            label="タスクを追加"
          ></v-text-field>

          <v-btn
            class="ml-4"
            color="primary"
          >
            追加
          </v-btn>
        </div>

        <v-list>
          <v-list-item
            v-for="task in tasks"
            :key="task.id"
          >
            <v-list-item-title>
              {{ task.name }}
            </v-list-item-title>

            <template v-slot:append>
              <v-btn
                class="mr-2"
                color="success"
              >
                編集
              </v-btn>

              <v-btn
                color="red"
              >
                削除
              </v-btn>
            </template>
          </v-list-item>
        </v-list>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
const { data: tasks, error } = await useFetch('http://localhost:8000/api/tasks')
</script>
