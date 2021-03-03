<template>
  <div>
    <button @click="modalAtivo = !modalAtivo">Cadastre-se</button>
    <transition name="modal" :duration="1000">
      <div class="modal-wrapper" v-show="modalAtivo" @click="cliqueFora">
        <div class="modal">
          <h1>Cadastre-se</h1>
          <form>
            <label for="email">E-mail:</label>
            &nbsp;<input type="email" name="email" id="email" /> <br />
            <label for="password">Senha:</label>
            &nbsp;<input type="password" name="password" id="password" /> <br />
            <br />
            <br />
            <input type="submit" value="Logar" />
          </form>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      modalAtivo: false,
    };
  },
  methods: {
    cliqueFora({ currentTarget, target }) {
      if (currentTarget === target) this.modalAtivo = false;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  box-shadow: black;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  margin: 0 px 0px 20px 0px;
}

.modal-wrapper {
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0px;
  left: 0px;
  background: rgba(0, 0, 0, 0.4);
  overflow-y: scroll;
}

.modal {
  background: #e5e5e5;
  padding: 20px;
  border-radius: 4px;
  max-width: 400px;
  margin: 120px auto 0 auto;
  z-index: 10;
}

label {
  display: block;
  margin-bottom: 5px;
}

input,
button {
  width: 100%;
  border: 2px solid rgba(0, 0, 0, 0.2);
  border-radius: 2px;
  padding: 15px 10px;
  font-size: 1rem;
  margin-bottom: 20px;
}

input[type="submit"],
button {
  width: 200px;
  background: #84e;
  color: white;
  text-transform: uppercase;
  font-size: 1rem;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

input[type="submit"]:active,
button:active {
  background: #94e;
}

button {
  margin: 20px auto;
  display: block;
  cursor: pointer;
}

.modal-enter {
  opacity: 0;
}

.modal-enter-active,
.modal-leave-to {
  transition: opacity 0.7s;
}

.modal-enter-to .modal {
  animation: slide 1s;
}

.modal-leave-to .modal {
  animation: slide 1s reverse;
}

@keyframes slide {
  from {
    transform: translate3d(0, -40px, 0);
  }
  to {
    transform: translate3d(0, 0px, 0);
  }
}
</style>
