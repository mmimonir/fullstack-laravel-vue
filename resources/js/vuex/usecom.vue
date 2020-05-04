<template>
  <div>
    <div class="content">
      <div class="container-fluid">
        <h1>I will show how all other components react to changes</h1>
        <p>Current state of counter is : {{ counter }}</p>
        <div>
          <coma />
        </div>
        <div>
          <comb />
        </div>
        <div>
          <comc />
        </div>
        <Button type="info" @click="changeCounter">Change the state of the counter</Button>
      </div>
    </div>
  </div>
</template>

<script>
import coma from "./comA";
import comb from "./comB";
import comc from "./comC";
import { mapGetters, mapActions } from "vuex";

export default {
  data() {
    return {};
  },
  computed: {
    ...mapGetters({
      counter: "getCounter"
    })
  },

  methods: {
    changeCounter() {
      this.$store.dispatch("changeCounterAction", 1);
      //this.$store.commit("changeTheCounter", 1);
    }
  },

  created() {
    console.log(this.$store.state.counter);
  },

  components: {
    coma,
    comb,
    comc
  },
  watch: {}
};
</script>
