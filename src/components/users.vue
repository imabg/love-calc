<template>
  <div class="container">
    <label class="usr"> User: 1 <input type="text" v-model="user1" /> </label>
    <br />
    <label class="usr"> User 2: <input type="text" v-model="user2" /> </label>
    <br />
    <button
      class="btn"
      @click="calculateLove"
      style="margin-top: 10px; background-color:#2C3E50; color: #fff;"
    >
      <span>Calculate</span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user1: "",
      user2: ""
    };
  },
  methods: {
    calculateLove() {
      if (this.user1 === "" && this.user2 === "") {
        alert("Enter Name first!");
      } else {
        this.$emit("name", this.user1, this.user2);
        this.user1 = "";
        this.user2 = "";
      }
    }
  }
};
</script>

<style scoped>
button:hover span {
  display: none;
}
button:hover:before {
  content: "Love";
}

button {
  font-size: 20px;
}
.usr {
  font-family: "Pacifico", cursive;
  font-size: 18px;
}

input {
  text-align: center;
}
</style>
