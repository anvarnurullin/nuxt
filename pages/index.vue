<template>
  <div class="container">
    <div>
      <h1>Nuxt.js</h1>
      <div class="cards">
        <widget-card
          v-for="widget in widgets"
          :key="widget.id"
          :title="widget.title"
          :description="widget.description"
        ></widget-card>
      </div>
    </div>
  </div>
</template>

<script>
import WidgetCard from "~/components/WidgetCard.vue";

export default {
  components: { WidgetCard },
  data: () => ({
    widgets: new Array(100).fill(1).map((value, index) => {
      return {
        id: index,
        title: `Widget ${index}`,
        description: `Some text that describes widget ${index}`,
      };
    }),
  }),
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  max-width: 900px;
  margin: 0 auto;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
