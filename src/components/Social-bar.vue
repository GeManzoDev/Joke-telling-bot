<template>
  <div>
    <ul>
      <li>
        <a target="_blank" href="https://www.instagram.com/helloworldge/"
          >Instagram</a
        >
      </li>

      <li>
        <a target="_blank" href="mailto:gennaromanzo1993@gmail.com">Email</a>
      </li>

      <li>
        <a target="_blank" href="https://github.com/GeManzoDev">Github</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Social-bar',
};
</script>

<style scoped>
ul {
  display: inline-grid;
  grid-auto-flow: row;
  grid-gap: 24px;
  justify-items: center;
  margin: auto;
  list-style-type: none;
}

@media (min-width: 500px) {
  ul {
    grid-auto-flow: column;
  }
}
@media screen and (max-width: 480px) {
  ul {
    display: flex;
  }
}

a {
  color: #b07e00;
  text-decoration: none;
  box-shadow: inset 0 -1px 0 hsla(0, 0%, 100%, 0.4);
}

a:hover {
  box-shadow: inset 0 -1.2em 0 hsla(0, 0%, 100%, 0.4);
}

li:last-child {
  grid-column: 1 / 2;
  grid-row: 1 / 2;
}

li:hover ~ li p {
  animation: wave-animation 0.3s infinite;
}

div {
  margin-top: 15rem;
  display: flex;
  line-height: 1.3;
}

@keyframes wave-animation {
  0%,
  100% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(20deg);
  }
  75% {
    transform: rotate(-15deg);
  }
}
</style>
