<template>
  <div id="app">
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Notes App",
      note: {
        title: "",
        descr: "",
      },
      notes: [
        {
          title: "First title note",
          descr: "First description note",
          date: new Date(Date.now()).toLocaleDateString(),
        },
        {
          title: "Second title note",
          descr: "Second description note",
          date: new Date(Date.now()).toLocaleDateString(),
        },
        {
          title: "Third title note",
          descr: "Third description note",
          date: new Date(Date.now()).toLocaleDateString(),
        },
      ],
    };
  },
};
</script>