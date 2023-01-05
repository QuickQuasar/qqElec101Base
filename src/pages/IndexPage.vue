<template>
  <q-page class="row items-center justify-evenly">
    <div class="row col-12 q-pa-sm">
      <q-card class="col-3 q-pa-sm">
        <example-component
          title="Example component: ToDo's"
          active
          :todos="todos"
          :meta="meta"
        ></example-component>
      </q-card>
      <q-card class="col-9 q-pa-sm">
        <!-- this component is itself a q-card-section -->
        <QQcard-example></QQcard-example>
      </q-card>
    </div>
    <div class="row col-12 q-pa-sm">
      <q-card class="col-3 q-pa-md">
        <q-card-section class="q-pa-md justify-center">
          <img
            alt="DataSmith logo"
            src="~assets/DataSmith_logo222_20200205.jpg"
            style="width: 100%"
          />
        </q-card-section>
        <q-card-section class="q-pa-md justify-center">
          <img
            alt="Quasar"
            src="~assets/quasar-logo-vertical.svg"
            style="width: 80% align: center"
          />
        </q-card-section>
      </q-card>
      <q-card class="col-9 q-pa-md">
        <q-card-section class="q-pa-sm justify-center">
          <h6 class="q-pa-sm">
            App Id qqElec101Base: Base Electron app for further development
          </h6>
          <div class="q-pa-sm text-subtitle2 text-weight-bold">
            This is the base QQ Electron app with these features accentuated:<br />
            > TypeScript, with examples of Interface (Class) definitions for
            Todo, Item.<br />
            <br />
            > Pinia state management example-store.ts which retains Todo's
            (created during the yarn create quasar operation).<br />
            <br />
            > Eslint and TypeScript features provide a very robust bug-detection
            capability before executing the app.
          </div>
          <!-- Prob: cannot return: <div class="q-pa-sm text-subtitle2 text-weight-bold">
            This Quick Quasar starter app is available for your use at this<br />
            <a href="https://github.com/QuickQuasar/qqElec101Base">
              qqElec101Base QuickQuasar Repository</a
            > -->
          <div class="q-pa-sm text-subtitle2">
            This Quick Quasar starter app is available for your use at this
            URL:<br />
            <span>https://github.com/QuickQuasar/qqElec101Base</span>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/ExampleComponent.vue';
import QQcardExample from 'components/QQcardExample.vue';
import { ref } from 'vue';

const todos = ref<Todo[]>([
  {
    id: 1,
    content: 'Cut the Grass',
  },
  {
    id: 2,
    content: 'Wash dishes',
  },
  {
    id: 3,
    content: 'Wash car',
  },
  {
    id: 4,
    content: 'Will it never end?',
  },
  {
    id: 5,
    content: 'Have a cuppa Java',
  },
]);
const meta = ref<Meta>({
  totalCount: 1200,
});
</script>
