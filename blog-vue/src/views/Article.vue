<template>
  <div class="p-20 article w-full h-5/6">
    <div class="text-center mb-20">
      <h1 class="text-5xl">{{ articles.Titre }}</h1>
      <h3 class="text-xl">{{ articles.Auteur }} | {{ articles.Date }}</h3>
    </div>
    <p class="text-lg mb-20 text-left">{{ articles.Content }}</p>
    <img
      src="https://game-guide.fr/wp-content/uploads/2014/11/Overwatch_Poster_Final.jpg"
      alt=""
    />
  </div>
</template>

<style>
.article {
  animation: article ease 5s;
  -webkit-animation: article ease 5s;
  -moz-animation: article ease 5s;
  -o-animation: article ease 5s;
  -ms-animation: article ease 5s;
}

@keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-moz-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-webkit-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-o-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-ms-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>

<script>
export default {
  data() {
    return {
      articles: {
        Titre: "Overwatch est-il un bon jeu ?",
        Content:
          "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
        Date: "13/07/2002",
        Auteur: "Marcel Proust",
      },
    };
  },
};
</script>
