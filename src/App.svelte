<script>
	/* By Connor Rothschild https://twitter.com/CL_Rothschild
	Scrollytelling component from Russell Goldenberg https://twitter.com/codenberg/status/1432774653139984387 */
	
  import Scrolly from "./Scrolly.svelte";
  import Scatterplot from "./components/Scatterplot.svelte";
	
  let value;
  const steps = [
		 "<p>Les statistiques le prouvent, entre les années 90 et 2000, le nombre d’adolescents fumeurs a doublé. En allumant leur première clope, ces jeunes allument par la même occasion la mèche d’une bombe à retardement.</p>",
    "<p>Leur jeune âge les rend plus vulnérables et augmente, drastiquement, le risque de dépendance sur le long terme. Une grande partie des fumeurs adultes se sont retrouvés enchaînés à la cigarette avant même leur majorité.</p>",
    "<p>Pour enrayer ce phénomène, l’Etat décide d’interdire aux moins de 16 ans, l’achat de produits contenant du tabac.</p>",
  ];

  const steps2 = [
		 "<p>Le nombre de fumeurs quotidiens ( une quinzaine de cigarettes par jour) ne fait que diminuer entre 1997 et 2018. Cependant, la proportion de fumeurs quotidiens reste dans les 60%.</p>",
    "<p>En revanche, le nombre de gros fumeurs ( plus de 20 cigarettes par jour) a drastiquement baissé. Il est non seulement moins élevé dans la population, mais il est aussi moins fréquent parmi les fumeurs.</p>",
    "<p>La légère augmentation du pourcentage de fumeurs occasionnels n’est pas forcément mauvais signe. Au contraire, ce graphique montre qu’en plus de la diminution du nombre de fumeurs, il y a davantage de fumeurs qui se contentent d’une cigarette de temps en temps.</p>",
  ];
</script>

<main>
  <section class="hero-section">
    <video autoplay loop muted plays-inline class="background-clip">
     <!-- <source src="https://media.publit.io/file/Projets/scrollytelling/les-belges-et-le-tabac.mp4" type="video/mp4"> -->
     <source src="./les belges et le tabac.mp4" type="video/mp4">
    </video>
    <div class="container content-width">
      <h1>La cigarette fait-elle toujours un tabac chez les Belges?</h1>
      <p>Historique de 20 ans de combat</p>
      <p>En 1997, 30% de la population de plus de 15 ans fume. Au cours du temps, les différents gouvernements ont tenté de faire diminuer ce taux. C’est dans les années 2000 que les autorités ont pris conscience que le tabac était un vrai problème de santé publique. Conséquences : interdictions sur les libertés des fumeurs, sensibilisation auprès des potentiels débutants ainsi qu’aux fumeurs confirmés et augmentation du prix des cigarettes. Comment ces différentes mesures ont impactés le taux de fumeurs dans notre pays ? Scrolle pour le découvrir</p>
    </div>
    <div class="arrow">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </section>

  <!-- Section Data -->
  <section>
    <div class="container data-container">
      <div class="year-header">
        <div class="year-number">
          2004
        </div>
        <h2>Fini d'envoyer le gamin chercher
          ses clopes</h2>
      </div>
        <p>14 ans, c’était l’âge parfait pour entamer une longue relation avec la cigarette.</p>
    </div>
  </section>

  <section>
<!--     <div class='hero'>
    </div> -->
    <div class="section-container">
      <div class="steps-container">
        <Scrolly bind:value>
          {#each steps as text, i}
            <div class="step" class:active={value === i}>
              <div class="step-content">{@html text}</div>
            </div>
          {/each}
          <div class="spacer" />
        </Scrolly>
      </div>
      <div class="sticky sticky-center">
        <img src="./Enfants-qui-fument.gif" alt="enfant qui fume">
        <p class="sticky-text">En 2018, l'âge moyen lors de la toute première cigarette est remonté à 16,6 ans et le début du tabagisme, à 18,3 ans.</p>
        <!-- <Scatterplot step={value} /> -->
      </div>
    </div>
</section>

    <!-- Datail Section -->
 <section class="detail-section">
  <div class="container-medium detail-wrapper">
    <div class="year-header">
      <div class="year-number">
        2015
      </div>
      <h2 class="heading-year">Manger et fumer en même temps : c’est terminé</h2>
    </div>
    <div class="detail-content">
      <img width="450px" src="./Chandler smokes at work  Best scenes while hiding.gif" alt="Chandler smokes at work  Best scenes while hiding">
      <div class="detail-text">
        <p>Fumer à sa table au restaurant ou au café, s’allumer une cigarette dans le train, c’était possible jusqu’en 2005.</p>
        <p>1er janvier 2006 : les fumeurs devront aller à l'extérieur pour honorer leur moment de plaisir. Depuis cette date, il sera interdit de fumer dans les lieux fermés accessibles au public. 
        </p>
      </div>
    </div>
    <p class="txt-center">le but est d’éviter aux non-fumeurs, une consommation passive. Autre argument : limiter la liberté des fumeurs et les pousser à arrêter appuie la mesure. C’est à ce moment que la cigarette passe d’une pratique anodine à un danger public. </p>
  </div>
</section>

    <!-- Lapub Section -->
 <section class="detail-section">
  <div class="container-medium">
  <div class="detail-wrapper">
    <div class="year-header">
      <div class="year-number">
        2005
      </div>
      <h2 class="heading-year">La pub… Beurk!</h2>
    </div>
  </div>
  <p class="txt-center">Pas facile de se remémorer cette époque où la cigarette rendait plus fort, plus virile, voire même en meilleure santé.</p>
  <div>
    <div class="detail-content">
      <div class="detail-text">
        <p>Et pourtant, avant 2005, l’industrie du tabac diffusait encore des campagnes mettant en lumière ce merveilleux partenaire de vie, qui aidait, même, à mieux dormir. 
        </p>
      </div>
      <div>
        <video autoplay loop muted>
          <source src="./ancienne pub cigarette JOB.mp4" type="video/mp4">
         </video>
      </div>
    </div>
  </div>
</section>

<!-- Smoke Section -->
<section class="detail-section">
  <div class="container-medium detail-wrapper">
    <div class="year-header">
      <div class="year-number">
        2007
      </div>
      <h2 class="heading-year">Du sang et des poumons en cover</h2>
    </div>
    <div class="detail-content">
      <img width="450px" src="./Images choc.jpeg" alt="images choc de la cigarette">
      <div class="detail-text">
        <p>Certains en font la collection, les photos choquantes placées en avant et en arrière des paquets de cigarettes ou de tabac. C’est en 2007 qu’elles deviennent obligatoires.</p> 
        <p>Des photos couleurs saisissantes de poumons sanguinolents ou de cœurs ouverts. Elles couvrent 65% du paquet.</p>
        <p>Les photos sont destinées tant à dissuader de commencer à fumer qu'à inciter à abandonner cette très mauvaise habitude. Ces photos sont accompagnées de l’avertissement “fumer tue” et du numéro du TabacStop.
        </p>
      </div>
    </div>
    <p class="txt-center">le but est d’éviter aux non-fumeurs, une consommation passive. Autre argument : limiter la liberté des fumeurs et les pousser à arrêter appuie la mesure. C’est à ce moment que la cigarette passe d’une pratique anodine à un danger public. </p>
  </div>
</section>

  <!-- Fumeur Section -->
  <section class="detail-section">
    <div class="container-medium">
    <div class="detail-wrapper">
      <div class="year-header">
        <div class="year-number">
          2018
        </div>
        <h2 class="heading-year">La majorité des fumeurs sont comme Nicolas</h2>
      </div>
    </div>
    <div>
      <div class="detail-content">
        <div class="detail-text">
          <img class="bulle" src="./Bulle nicolas.png" alt="bulle du fumeur Nicolas">
        <img  width="550px" src="./Nicolas fumeur type.png" alt="Nicolas le fumeur type qui fume">
      </div>
    </div>
  </section>

  <!-- Paquets Section -->
<section>
  <div class="container-medium detail-wrapper">
    <div class="year-header">
      <div class="year-number">
        2020
      </div>
      <h2 class="heading-year">Les paquets deviennent neutres</h2>
    </div>
    <p class="txt-center">Encore plus loin que l’obligation d’apposer une image dissuasive choquante, l’idée d’identité de marque est abolie pour les entreprises de tabac.</p>
    <div class="detail-content">
      <img width="450px" src="./paquet-neutre.jpg" alt="carton d'un paquet neutre">
      <div class="detail-text">
        <p>Tous les paquets devront se ressembler : finis les logos, couleurs et polices bien identifiables. Ce sera dorénavant un texte écrit en petit sur un fond brun uni.</p> 
        <p>Pour les autorités, le but est clair : retirer tout signe identifiable qui rendrait le paquet attirant. 
        </p>
      </div>
    </div>
  </div>
</section>


<!-- Scroll Section -->
<section>
  <div class="container-medium margin-top">
    <h2 class="heading-year txt-center">Fumer oui, tous les jours peut-être pas</h2>
  </div>
  <div>
    <div class="section-container">
      <div class="steps-container">
        <Scrolly bind:value>
          {#each steps2 as text, i}
            <div class="step" class:active={value === i}>
              <div class="step-content">{@html text}</div>
            </div>
          {/each}
          <div class="spacer" />
        </Scrolly>
      </div>
      <div class="sticky sticky-center">
        <img width="750px" src="./types-de-fumeurs-dans-la-population-belge.png" alt="graphique de types de fumeurs belges">
        <!-- <Scatterplot step={value} /> -->
      </div>
    </div>
  </div>
</section>

<!-- Prix Section -->
<section class="detail-section">
  <div class="container-medium detail-wrapper">
      <h2 class="heading-year txt-center">En 20 ans, le paquet coûte deux fois plus cher.</h2>
    <div class="detail-content">
      <img width="450px" src="./tarif-du-paquet-de-20-cigarettes.png" alt="tarif du paquet">
      <div class="detail-text">
        <p>C’est probablement le moyen de pression le plus utilisé par les autorités pour tenter de réduire la consommation de cigarettes : jouer sur le prix du paquet.</p> 
        <p>Si en 2002, un paquet de taille classique (20 cigarettes) tournait autour des 3,20€, 20 ans plus tard, il coûte deux fois plus cher. Si l’inflation explique en toute petite partie cette augmentation, c’est principalement aux taxes qui évoluent progressivement chaque année.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- Section conclusion -->
<section>
  <div class="container narrow-content">
    <h2>En 2022, 1 personne sur 4 fume</h2>
    <div>
      <p>Après tous ces efforts de la part des autorités pour faire diminuer le taux de fumeurs, ils sont encore un quart de la population à fumer. C’est 5% de diminution par rapport à il y 24 ans. Si le taux était passé en dessous des 20% en 2018, il est fortement remonté. Cela est due à deux raisons principales : </p>
        <p>
          La période covid a poussé les gens en confinement, isolés chez eux, à retenter la cigarette.
        </p>
        <p>
          L’arrivée de la cigarette électronique a fortement modifié le marché. Des fumeurs de tabac sont passés à la e-cigarette, quand de nouveaux consommateurs, qui ne fumaient pas avant sont arrivés.
        </p>
    </div>
    <div class="lung-image-wrapper">
      <img width="250px" height="250px" src="./Poumon sain.png" alt="poumons d'une personne saine">
      <img width="250px" height="250px" src="./Poumon fumeur.png" alt="poumons d'une personne malade">
    </div>
  </div>
</section>

<!-- Section Fin -->
<section>
  <div class="container narrow-content">
    <h2>“Fumer Tue”</h2>
    <div>
      <p>On ne le dira jamais assez. Le tabagisme est la cause de 90% des cancers du poumons et d’un cancer sur 3 peu importe son type. Encore aujourd’hui 20 000 Belges meurent tous les ans de cette addiction.  </p>
    </div>
  </div>
</section>
</main>

<style>
  .container {
    width: 1280px;
  }

  .data-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    max-width: 60ch;
    margin: auto;
    min-height: 90vh
  }

  /* Typography */
  h1 {
    font-size: 2.5rem;
  }

  h2 {
    font-size: 2rem;
  }


  .hero-section {
    background-color: rgba(0, 0, 0, 0.5);
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  }

  .hero-section > div {
    text-align: center;
  }

  .content-width {
    max-width: 70ch;
  }

  .background-clip {
    position: absolute;
    right: 0;
    bottom: 0;
    z-index: -1;
  }

  /* Scrolling Arrow */

  .arrow {
            position: absolute;
            top: 85%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .arrow span {
            display: block;
            width: 20px;
            height: 20px;
            border-bottom: 3px solid rgb(250, 238, 224, 0.6);
            border-right: 3px solid rgb(250, 238, 224, 0.6);
            transform: rotate(45deg);
            margin: -10px;
            animation: scroll1 3s infinite;
        }
        
        .arrow span:nth-child(2) {
            animation-delay: .2s;
        }
        
        .arrow span:nth-child(3) {
            animation-delay: .4s;
        }
        
        @keyframes scroll1 {
            0% {
                opacity: 1;
                transform: rotate(45deg) translate(20px, -20px);
                border-bottom: 3px solid #c26b31;
                border-right: 3px solid #cb9c56;
            }
            50% {
                opacity: 0;
                transform: rotate(45deg) translate(20px, -20px);
            }
            100% {
                opacity: 1;
                transform: rotate(45deg) translate(20px, -20px);
            }
        }

/* Scatterplot */

	:global(body) {
		overflow-x: hidden;
	}
	
/* 	.hero {
		height: 60vh;
		display: flex;
		place-items: center;
		flex-direction: column;
		justify-content: center;
		text-align: center;
	} */
	
	/* .hero h2 {
		margin-top: 0;
		font-weight: 200;
	} */
	
  .spacer {
    height: 40vh;
  }

  .sticky {
    position: sticky;
    top: 25%;
		flex: 1 1 60%;
    width: 60%;
    align-items: center;
  }

  .sticky-text {
    max-width: 45ch;
    text-align: center;
  }

  .sticky-center {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .section-container {
    margin-top: 1em;
    text-align: center;
    transition: background 100ms;
    display: flex;
  }

  .step {
    height: 80vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content {
    font-size: 1rem;
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: .5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
    text-align: left;
		width: 75%;
		margin: auto;
		max-width: 500px;
  }

	.step.active .step-content {
		background: white;
		color: black;
	}
	
  .steps-container,
  .sticky {
    height: 100%;
  }

  .steps-container {
    flex: 1 1 40%;
    z-index: 10;
  }
	
/* Comment out the following line to always make it 'text-on-top' */
  @media screen and (max-width: 768px) {
    .section-container {
      flex-direction: column-reverse;
    }
/*     .sticky {
      width: 95%;
			margin: auto;
    } */
  }

  .txt-center {
    text-align: center;
    max-width: 70ch;
  }

  /* Section header - Year */

  .year-header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;

  }

  .year-number {
   font-size: 5.5rem;
   font-weight: 700;
   color: #aeabab;
  }

  .heading-year {
    max-width: 45ch;
  }

  .detail-content {
    display: flex;
    gap: 2rem;
    align-items: center;
    justify-content: flex-end;
    margin-top: 4rem;
  }

  .detail-section {
    padding: 100px 0; 
    position: relative;
  }

  .detail-wrapper {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    align-items: center;
    justify-content: center;
  }

  .container-medium {
    max-width: 1180px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: auto;
  }

  .narrow-content {
    max-width: 40rem;
    align-content: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: auto;
  }

  .lung-image-wrapper {
    display: flex;
    flex-direction: row;

  }

  .margin-top {
    margin-top: 100px;
    margin-bottom: 50px;
  }

  .bulle {
    position: absolute;
    top: 50%;
    left: 20%;
    width: 550px;
  }
</style>