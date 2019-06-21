<template>
  <div id="app">
    <h2
      class="titulo"
    >Você foi escolhido para criar um sistema de votação para uma premiação musical.</h2>
    <h2 class="sub">Escolha seu artista favorito e vote.</h2>
    <div class="row">
      <div class="col">
        <p class="artista">Rita Lee</p>
        <p>
          <img class="foto" src="https://imagens.som13.com/2891218/rita-lee.jpg">
        </p>
        <p class="votos">votos {{ artista1 }} | {{ porcentagem1 }}%</p>
        <p class="nvotos">#100</p>
      </div>
      <div class="col">
        <p class="artista">Cartola</p>
        <p>
          <img
            class="foto"
            src="https://i.pinimg.com/originals/7d/86/aa/7d86aa1899a75641ecf1172573486199.jpg"
          >
        </p>
        <p class="votos">votos {{ artista2 }} | {{ porcentagem2 }}%</p>
        <p class="nvotos">#101</p>
      </div>
      <div class="col">
        <p class="artista">Ney Matogrosso</p>
        <p>
          <img
            class="foto"
            src="data:image/jpeg;base64,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"
          >
        </p>
        <p class="votos">votos {{ artista3 }} | {{ porcentagem3 }}%</p>
        <p class="nvotos">#102</p>
      </div>
      <div class="col">
        <p class="artista">Anitta</p>
        <p>
          <img
            class="foto"
            src="data:image/jpeg;base64,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"
          >
        </p>
        <p class="votos">votos {{ artista4 }} | {{ porcentagem4 }}%</p>
        <p class="nvotos">#103</p>
      </div>
      <div class="col">
        <p class="artista">Nulo</p>
        <p>
          <img
            class="foto"
            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAMFBMVEXMzMz////JycnNzc339/fy8vLn5+f8/Pzp6enU1NTs7Oz5+fnZ2dnQ0NDf39/V1dXlSjGaAAAFA0lEQVR4nO2cCZqrIBCEI4o7ev/bvjgTX8QlLnSHSqb+A+SjAr0KfbsRQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIWcc8ib0UcYxJ06rt8toO1HnXVmn6PTqNcV1pi8SnsGXnvkGkubV5k2zR5O3ts0WaKs825f2S5dUHa+zL7e2bbGRZxV7oNUxVzm1vi6L8wH00aX5U34/GPP00jd2R8+md1S72kk/h6pP6BmoXe9nHqfYc6DrZp3gc056xwClF+xnGmF/UN5DHXvwRygCBSVLGXv4uaZjAu8Q0toQdQgWi76IJscGRHNjdmE5AYJJ0uBJbEYFJ0sYWsoW7GgfnFKjZzZVUbZ06tpRVRLzMCKQpVmeriVc0iCmq3BkdsLHlLJHyoyNw/tRcK5i2ydAsUSbWTwGr+VPpLbxvIlYKLm2FA1iWaBUUQrnTSkFgkgDFRNF05glSGSXvZway2LKe9CoCgXyN0iFFOqYannQAxpumSgKTBCXoa4T7X1AMUT4nHQHJTY1sZTilBnE1Wo4Gx9XoxPsBlJgv1URcUsSW9kBNYJLElvaACqmQCuNDhVSIr/D7I77kRycflKzt6zPvP1A9aTWicC6BfX8XQy9cxBb2n6/vJv6BjrCWIcKYoVbMb2LLevIHvq7pfHzqY8ua8vVfuYUulvqA3W1TuG0SW9KMr78xJB8wgELFL+KWCGaFA7LuFMqRPugl2zUFVCwckUxsUEpfn1TunFqUKwozKrHXCEA32jyM2IsSPD/6QKjGQKopFkg0FjGfk4wIeBtULzMSLBFSoKmmqwo7qN4RRZlC0NfFdF1B72S9N7J9UyOkNu3PsfTcX3f5tbpXMbmh5rSR+22mH81uWgpcfZA/e47/+Gnbxzurppq4lel/bS75G+uZnXn+hI01+cQ3uMI/TsGTP7wfj/OEvZ21ZhrvjBl3zuGUzt+nWXaURTDHZYI2MyPTHj+qdp6JLv+eN9dTZn16yazzcFTjQt9qTM3eaY2bTZnFH13tTopaTokybuOPeWPrZruEqN18Fa4rm63gUTRlt3yYPjfwF3+gFq/ysmwlC3Ftbperzmzerr27f5UvvKfsMDvGtdbJNcb13V3m7+KLu7iuXx24txdJ7RsO6v5r0a0Abcz+aMjdhE//ZemWF5hS5NeW8cwBX/1/yhMlDqZjVwL0PUc4lM7qFpB7NjhZx8lukklfDJCc/bSiLZ6635V1x8daGndmQp/eXbCzrbQm74+INK5dTDd9jVYz7kI7tLBd9dJszD1Ylue/rio1VK8NLyk2AvtA2ndldqVa1hl9ctzLLBdk666vXPo/JN5SV7X/M4ALaHib4H72PZOpy/yHsrahn4wVTFFnqMB15M+p3lXna0h/JFa5MBOGcLUoNqhMDtmRZyZ8HKI8peQmin3dlUTyS7Hie4MQBPNTtEgxIraJoFsouIl6cy9CESqG1a7ihyOVu+lNFAhF6A6q3qOfcEQ+2MD6mQERX+P0HlCG00ikbsiHVOSYQh9SmWOKfEhFroNrzWKTIvjGDWDp6xNcCIOboYAhGmwzvBtiqELcrHskNPvGjoYDgRER3tEEuxrgymkksIKCd6XhzhSt1b0ktPmNHizC8zbERqlP6JSe2Os/ABVSIT5USIX4UCEV4kOFVIgPFVIhPlRIhfhQIRXiQ4VUiA8VUiE+VEiF+FAhFeJDhVSIDxVSIT5/XuE/dvVdXNF64l4AAAAASUVORK5CYII="
          >
        </p>
        <p class="votos">votos {{ artista5 }}</p>
      </div>
    </div>
    <div class="form">
      <input type="number" placeholder="NUMERO ESCOLHIDO" v-model="voto">
      <input type="number" placeholder="INSIRA SEU CPF" v-model="cpf">
      <button @click="Votar">Votar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  computed: {
    total() {
      return this.artista1 + this.artista2 + this.artista3 + this.artista4;
    },
    porcentagem1() {
      return parseInt((10000 * this.artista1) / this.total) / 100 || 0;
    },
    porcentagem2() {
      return parseInt((10000 * this.artista2) / this.total) / 100 || 0;
    },
    porcentagem3() {
      return parseInt((10000 * this.artista3) / this.total) / 100 || 0;
    },
    porcentagem4() {
      return parseInt((10000 * this.artista4) / this.total) / 100 || 0;
    },
    porcentagem5() {
      return parseInt((10000 * this.artista5) / this.total) / 100 || 0;
    }
  },
  data() {
    return {
      voto: "",
      cpf: "",
      artista1: 0,
      artista2: 0,
      artista3: 0,
      artista4: 0,
      artista5: 0
    };
  },
  methods: {
    Votar() {
      if (!this.cpf || !this.voto) {
        return alert("Digite seu voto e CPF");
      }
      if (this.voto == 100) {
        this.artista1 = this.artista1 + 1;
      } else if (this.voto == 101) {
        this.artista2 = this.artista2 + 1;
      } else if (this.voto == 102) {
        this.artista3 = this.artista3 + 1;
      } else if (this.voto == 103) {
        alert("Essa artista foi desclassificada, vote novamente!");
      } else {
        this.artista5 = this.artista5 + 1;
      }
    }
  }
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
}
.titulo {
  padding: 35px 0;
  background: #ff5c00;
  color: #fff;
  text-align: center;
  font-size: 14px;
}
.sub {
  text-align: center;
  font-size: 18px;
}
.row {
  display: flex;
  justify-content: center;
}
.col {
  width: 111px;
  padding: 10px;
}
p {
  padding: 0;
}
.artista {
  font-size: 12px;
  text-align: center;
}
.votos {
  font-size: 12px;
  text-align: center;
}
.nvotos {
  font-size: 12px;
  text-align: center;
}
.form {
  text-align: center;
}
.foto {
  width: 111px;
}
</style>
