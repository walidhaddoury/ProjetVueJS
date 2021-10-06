<template>
<div>
    <div class="title">
        <h1>Nos Articles du moment</h1>
    </div>
    
    
        
        <div class="tableau" v-for = "(item, index) in articlesCut" :key="index">
          <h1> {{item.Titre}} </h1>
          <p>{{troncText(item.Content)}}</p>
          <div class="info">
            <p class="date">{{item.Date}}</p>
          <p class="auteur">{{item.Auteur}}</p>
          <p class="btn"><button>Lire</button> </p>
          </div>
          
        </div>

  
</div>
  
</template>

<script>
export default {
    props:{
    },
    data(){
        return{
            articles: [
            {
                Titre: "Overwatchs est-il un bon jeux?",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "Paladins est meilleurs que Overwatch !",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "1",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "2",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "3",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "4",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "5",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "6",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "7",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "8",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },{
                Titre: "9",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "10",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "11",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "12",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "13",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            },
            {
                Titre: "14",
                Content: "Paladins : Champions du Royaume (Paladins: Champions of the Realm) est un jeu vidéo de tir à la première personne en équipe développé par Hi-Rez Studios. Le jeu est officiellement entré en bêta ouverte le 16 septembre 2016. Lors de sa sortie en bêta ouverte sur Steam, le jeu a attiré 800 000 téléchargements en une semaine et a été l'un des top 10 des jeux les plus populaires par utilisateurs simultanés sur Steam. La version bêta fermée a commencé le 17 novembre 2015. Le jeu continue à créer de nouveaux personnages",
                Date: "13/07/2003",
                Auteur: "Marcel Prout"
            
            },
            {
                Titre: "15",
                Content: "Overwatch est un jeu vidéo de tir (FPS) en ligne et en équipe de 6, développé et publié par Blizzard Entertainment. Le jeu est annoncé le 7 novembre 2014 à la BlizzCon, et est commercialisé le 24 mai 2016 sur Windows, PlayStation 4 et Xbox One et le 15 octobre 2019 sur Nintendo Switch. Le jeu met l'accent sur la coopération entre différentes classes représentées par différents personnages ayant chacun leurs capacités et particularités. Le jeu s'inspire notamment des jeux de tir en vue subjective en équipe de la décennie précédente mettant eux aussi l'accent sur la coopération entre plusieurs classes de personnage, notamment Team Fortress 2. Le 1er novembre 2019, Blizzard annonce la production de Overwatch 21, lors de cette BlizzCon. Le développement de ce second opus reste à suivre.",
                Date: "13/07/2002",
                Auteur: "Marcel Proust"
            
            }
            
            

            ],
            page: 10
        }
    },
    methods:
    {
        troncText(text){
         text = text.substring(0,100);
         text = text+"...";
         return text;
        },
        CutArticles(index){
            let article = []
            let taille = 10;
            
            if(this.articles.length < index+10){
                taille = index+10 - this.articles.length;
                taille = 10- taille;
                
                taille = taille+index-1;
            }else{
                taille = index+10
            }
            
            for(let i = index; i<= taille; i++){
                
                article.push(this.articles[i]);
            }

            return article;
        }
    },
    computed:
    {
        articlesCut(){
            return this.CutArticles(this.page);
        } 
    }


}
</script>

<style>
img
{
    width: 100%;
    height: 300px;
}
body
{
    background-color:#DCDCDC ;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

}

.tableau
{
    background-color:white;
    width: 99%;
    display: flex;
    flex-direction: column;
     border: solid 1px;
     margin-top: 10px ;
    height: auto;
    
    box-shadow: 0px 10px 13px -7px #000000, 5px 5px 22px 6px rgba(0,0,0,0);
}
table
{
    width: 100%;
}


.first th
{
    border: solid 1px;
    width: 100%;

}

.title
{
    display: flex;
    width: 100%;
    justify-content: center;
}

.info
{
    display: flex;
    flex-direction: row;
    width: 100%;
    justify-content: space-around;
}

div.tableau:hover
{
    background-color: #D3D3D3 ;
    text-decoration: underline;
}

</style>