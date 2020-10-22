<template>
  <div>
    <button @click="randomStart()" class="startButton" type="button">Start</button>
    <div class="row">
      <div class="col">
        <button @click="randomDamage(50,70)" class="attackButton" type="button" >Attack</button>
        <button @click="randomDamageSP(100,150)" class="specialAttackButton" type="button">SP Attack</button>
      </div>
    </div>
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <div class="alert alert-primary" role="alert">Hero : {{randomPlayer}} HP : {{hp1}} </div>
          <img :src="image1" class="img-fluid" />
        </div>
        <div class="col">
          <div class="alert alert-primary" role="alert">Enemy : {{randomMonster}} HP : {{hp2}} </div>
          <img :src="image2" class="img-fluid" />
        </div>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  
  data: function () {
    return {
      randomAttack: "",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: "",
      hp2: "",
      win: "https://www.nicepng.com/png/full/235-2359549_street-fighter-ko-png-ko-street-fighter-png.png",
      lose: "http://pngimg.com/uploads/game_over/game_over_PNG45.png",
      player: [
        {
          name: "Lufy",
          hp: 800,
          image: "https://icon-icons.com/icons2/1048/PNG/256/Lufy_icon-icons.com_76554.png",
        },
        {
          name: "Nico",
          hp: 400,
          image: "https://cdn.icon-icons.com/icons2/1048/PNG/256/Nico_soffa_icon-icons.com_76558.png",
        },
        {
          name: "zoro",
          hp: 600,
          image: "https://cdn.icon-icons.com/icons2/1048/PNG/256/Roronoa_Zoro_icon-icons.com_76560.png",
        },
      ],
      randomPlayer: "",
      monster: [
        {
          name: "Shank",
          hp: 800,
          image: "https://cdn.icon-icons.com/icons2/1048/PNG/256/Shanks_le_roux_icon-icons.com_76562.png",
        },
        {
          name: "Crocodile",
          hp: 500,
          image: "https://cdn.icon-icons.com/icons2/1048/PNG/256/Crocodile_icon-icons.com_76550.png",
        },
        {
          name: "Ener",
          hp: 500,
          image: "https://cdn.icon-icons.com/icons2/1048/PNG/256/Ener_icon-icons.com_76551.png",
        },
      ],
      randomMonster: "",
    }
  },

  props: {
    Label: String,
  },

  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;

      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },

    randomDamage: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp1 -= this.randomAttack;
      }
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0 ) {
        this.hp1 = 0;
        this.image1 = this.lose;
      }
      if (this.hp2 <= 0 && this.hp1 != 0) {
        this.hp2 = 0;
        this.image2 = this.win;
      }
    },

    randomDamageSP: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp1 -= this.randomAttack;
      }
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image1 = this.lose;
      }
      if (this.hp2 <= 0 && this.hp1 != 0) {
        this.hp2 = 0;
        this.image2 = this.win;
      }
    },
  },
};

</script>

<style scoped>
  .attackButton {
    background-color: red;
    border: 1px solid red;
    color: white;
  }
  .specialAttackButton {
    background-color: #5bc0de;
    border: 1px solid #5bc0de;
    color: white;
  }
  .startButton {
    background-color: green;
    border: 1px solid green;
    color: white;
  }
</style>