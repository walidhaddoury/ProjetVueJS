<template>
    <div class="style">
    <div class="article">
    <div class="Titre">
    <h1>{{articles.Titre}}</h1>
    <h3>{{articles.Auteur}} | {{articles.Date}}</h3>
    </div>

  
  <p>{{articles.Content}}</p>
  <img src="https://game-guide.fr/wp-content/uploads/2014/11/Overwatch_Poster_Final.jpg" alt="">
</div>
    </div>
</template>

<style>
.article{
  animation: article ease 5s;
  -webkit-animation: article ease 5s;
  -moz-animation: article ease 5s;
  -o-animation: article ease 5s;
  -ms-animation: article ease 5s;
}


@keyframes article{
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-moz-keyframes article {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-webkit-keyframes article {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-o-keyframes article {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-ms-keyframes article {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

/* The style below is just for the appearance of the example div */

.style {
  width:90vw; height:90vh;
  text-align:center;
  padding-top:calc(10vh - 50px);
  margin-left:5vw;
  opacity: 0,33;
}
.style p {
  color:black;
  font-size:30px;
}

.Titre{
    line-height:10px ;
}


</style>


<script>
export default{
    data(){
        return{
        articles: 
                {
                    Titre: "Overwatch est-il un bon jeu?",
                    Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                    Date: "13/07/2002",
                    Auteur: "Marcel Proust"
                
                }
                

                
        }
    }
}

</script>


