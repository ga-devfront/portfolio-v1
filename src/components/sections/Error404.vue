<template>
  <section>
      <h1 :data-text="$t('error404.title')" class="glitch">{{$t('error404.title')}}</h1>
      <p :data-text="$t('error404.details')" class="glitch">{{$t('error404.details')}}</p>
  </section>
</template>

<script>

export default {
  name: 'Error404',
  components: {
  },
  data() {
    return {
    };
  },
  computed: {
  },
  methods: {
  },
};
</script>

<style lang="scss" scoped>
section {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

p {
  text-align: center;
  margin: 0px;
  font-weight: bold;
}

h1 {
  text-align: center;
  margin: 10px;
  font-size: 4em;
}

@mixin glitchCopy {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.glitch {
font-family: 'Aquawax Pro DemiBold', Arial;
position: relative;
color: white;
letter-spacing: .5em;
animation: glitch-skew 1s infinite linear alternate-reverse;
  &:before{
    @include glitchCopy;
    left: 2px;
    text-shadow: -2px 0 #ff00c1;
    clip: rect(44px, 450px, 56px, 0);
    animation: glitch-anim 5s infinite linear alternate-reverse;
  }

  &:after {
    @include glitchCopy;
    left: -2px;
    text-shadow: -2px 0 #00fff9, 2px 2px #ff00c1;
    animation: glitch-anim2 1s infinite linear alternate-reverse;
  }
}

@keyframes glitch-anim {
  $steps: 20;
  @for $i from 0 through $steps {
    #{percentage($i*(calc(1 / $steps)))} {
      clip: rect(random(100)+px, 9999px, random(100)+px, 0);
      transform: skew(calc(random(100) / 100) + deg);
    }
  }
}

@keyframes glitch-anim2 {
  $steps: 20;
  @for $i from 0 through $steps {
    #{percentage($i*(calc(1 / $steps)))} {
      clip: rect(random(100)+px, 9999px, random(100)+px, 0);
      transform: skew(calc(random(100) / 100) + deg);
    }
  }
}

@keyframes glitch-skew {
  $steps: 10;
  @for $i from 0 through $steps {
    #{percentage($i*(calc(1 / $steps)))} {
      transform: skew((random(10) - 5) + deg);
    }
  }
}
</style>
