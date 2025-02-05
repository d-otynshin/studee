<template>
  <main>
    <div class="max-w-4xl relative bg-white rounded-3xl shadow-md">
      <div class="flex m-12">
        <div>
          <form action="index.html" autocomplete="off" class="sign-in-form">
            <div class="flex items-center">
              <img class="w-10" src="/src/assets/images/studee-logo.png" alt="easyclass" />
              <h4 class="font-bold text-md uppercase">studee</h4>
            </div>

            <div class="heading mb-16">
              <h2>Добро Пожаловать</h2>

              <div class="flex gap-1">
                <h6>Нет аккаунта?</h6>
                <a href="#" class="toggle">Зарегистрироваться</a>
              </div>
            </div>

            <div class="actual-form">
              <div class="input-wrap">
                <input
                  placeholder="Логин"
                  type="text"
                  minlength="4"
                  class="input-field"
                  autocomplete="off"
                  required
                />
              </div>

              <div class="input-wrap">
                <input
                  placeholder="Пароль"
                  type="password"
                  minlength="4"
                  class="input-field"
                  autocomplete="off"
                  required
                />
              </div>

              <router-link to="/">
                <input type="submit" value="Войти" class="sign-btn" />
              </router-link>

              <p class="text">
                Забыли пароль? <a href="#">Помощь</a>
              </p>
            </div>
          </form>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
input {
  font-family: "Poppins", sans-serif;
}

main {
  width: 100%;
  min-height: 100vh;
  overflow: hidden;
  padding: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.heading h2 {
  font-size: 2.1rem;
  font-weight: 600;
  color: #151111;
}

.heading h6 {
  color: #bababa;
  font-weight: 400;
  font-size: 0.75rem;
  display: inline;
}

.toggle {
  color: #151111;
  text-decoration: none;
  font-size: 0.75rem;
  font-weight: 500;
  transition: 0.3s;
}

.toggle:hover {
  color: #8371fd;
}

.input-wrap {
  position: relative;
  height: 37px;
  margin-bottom: 2rem;
}

.input-field {
  position: absolute;
  width: 100%;
  height: 100%;
  background: none;
  border: none;
  outline: none;
  border-bottom: 1px solid #bbb;
  padding: 0;
  font-size: 0.95rem;
  color: #151111;
  transition: 0.4s;
}

label {
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  font-size: 0.95rem;
  color: #bbb;
  pointer-events: none;
  transition: 0.4s;
}

.input-field.active + label {
  font-size: 0.75rem;
  top: -2px;
}

.sign-btn {
  display: inline-block;
  width: 100%;
  height: 43px;
  background-color: #151111;
  color: #fff;
  border: none;
  cursor: pointer;
  border-radius: 0.8rem;
  font-size: 0.8rem;
  margin-bottom: 2rem;
  transition: 0.3s;
}

.sign-btn:hover {
  opacity: 0.9;
}

.text {
  color: #bbb;
  font-size: 0.7rem;
}

.text a {
  color: #bbb;
  transition: 0.3s;
}

.text a:hover {
  color: #8371fd;
}

.text-group h2 {
  line-height: 2.2rem;
  font-weight: 600;
  font-size: 1.6rem;
}

.bullets span {
  display: block;
  width: 0.5rem;
  height: 0.5rem;
  background-color: #aaa;
  margin: 0 0.25rem;
  border-radius: 50%;
  cursor: pointer;
  transition: 0.3s;
}

</style>

<script lang="ts" setup>
</script>
