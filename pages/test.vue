<template>
  <div>
    <h3>Hola mundo desde vue {{ number }}</h3>
    <table>
      <tr>
        <th>Name</th>
        <th>Id</th>
        <th>Value</th>
      </tr>

    </table>
    {{ devices }}
  </div>
</template>

<style>
table {
  border-collapse: collapse;
  margin: 40px;
}
th,
td {
  border: 1px solid black;
  padding: 5px;
}
</style>


<script>
export default {
  data() {
    return {
      devices: [],

      number: 0,
    };
  },
  created() {
    console.log("created");
  },
  mounted() {
    setTimeout(() => {
      this.getDevices();
    }, 3000);
  },
  updated() {
    this.loadNumberDevices();

  },
  unmounted() {},
  methods: {
    loadNumberDevices() {
      this.number=this.devices.length;
    },
    getDevices(){
      let response= [
        { name: "Home", id: 1, value: 0 },
        { name: "Office", id: 2, value: 0 },
        { name: "Kitchen", id: 3, value: 0 },
      ];
      this.devices= response;
    }
  },
};
</script>
