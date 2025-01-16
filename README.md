# Modèles multi modaux et systèmes multi agents avec langgraph

## Modèle de vision

Les modèles de vision par ordinateur ont aujourd'hui des performances remarquables grâce au modèle _transformers_. Les modèles de vision prennent une image en entrée et fournissent en sortie une réponse à une question sur cette image. Capable de raisonner, ils peuvent par exemple décrire une image, compter des éléments ou repérer des éléments anormaux.

Il existent de nombreux modèles de vision, en voici quelques uns : 
- MiniCPM 2.6 https://huggingface.co/openbmb/MiniCPM-V-2_6
- Idefics https://huggingface.co/HuggingFaceM4/Idefics3-8B-Llama3
- Phi-3 vision https://huggingface.co/microsoft/Phi-3-vision-128k-instruct

Dans ce TP, vous allez mettre en place le modèle multi-modal **MiniCPM-o-2.6**.

Pour que le modèle de 8 milliards de paramètres fonctionne sous google colab, vous devrez le quantiser en utilisant les bibliothèques **bitsandbytes** et **accelerate**.

**Exercice** : mettre en place le modèle de vision **MiniCPM-o-2.6** et tester quelques prompts sur des images de votre choix.


## Multi agents avec langgraph

Dans ce TP, vous allez mettre en oeuvre un système multi agents pour construire un article structuré sur un thème que l'utilisateur donnera en entrée. Pour mettre en oeuvre les agents, vous utiliserez **langgraph**

### Agents

* Plannifieur : agent définissant le plan de l'article
* Recherche sur internet : agent effectuant des recherche sur internet. Utilisez [Tavily](https://docs.tavily.com/docs/python-sdk/tavily-search/getting-started)
* Générateur de contenus : génère des contenu à partir des résultats de recherche sur internet
* Proposition de recommandations sur les contenus générés : critique le contenu généré et fait des recommandations d'amélioration
* Critique des recherche : propose des informations pour adresser les recommandations en générant une liste de recherches à lancer sur Internet.

Vos agents s'organiseront comme suit :

![agents](./flow.png)

### LLM

Vous utiliserez **Ollama** comme serveur d'inférence avec le LLM de votre choix. **Qwen2.5:14b** est un exemple de LLM donnant des résultats satisfaisants.

**Exercice** : mettre en place les agents ci-dessous avec langgraph et tester sur la tâche de votre choix.

### Exemples de génération

Tâche : Actualité récente de l'Université de Toulon et de ses filières en informatique en particulier

Résultats 

### L’actualité récente de l’Université de Toulon et ses filières d’informatique

#### Introduction
L'Université de Toulon est un établissement d'enseignement supérieur reconnu en France, offrant une large gamme de formations dans divers domaines. À la rentrée 2024, l'université a accueilli entre 10 500 et 11 000 étudiants, témoignant d'une stabilité démographique depuis plusieurs années. Dans le contexte actuel où les compétences en informatique sont de plus en plus recherchées à l'échelle nationale et internationale, cette université a mis en place des initiatives innovantes pour renforcer ses filières d'informatique. Cet article présente les dernières actualités concernant l’Université de Toulon, avec un focus particulier sur ses filières d’informatique.

#### I. L'Université de Toulon : Présentation et Évolution
L'Université de Toulon a une longue histoire qui remonte à la création des premiers instituts universitaires dans le sud de la France au 19e siècle. Aujourd'hui, l'université est structurée en plusieurs facultés et départements, dont la Faculté des Sciences et Techniques (FST) abrite les filières d'informatique. À la rentrée 2024, l'Université de Toulon a annoncé une évolution institutionnelle importante avec l'introduction de nouvelles filières et la modification de certains programmes existants pour répondre aux besoins du marché du travail.

#### II. Les Filières en Informatique à l’Université de Toulon
L'Université de Toulon propose divers diplômes dans le domaine de l'informatique, allant des licences professionnelles aux masters spécialisés. Parmi les filières récemment mises en place figurent la licence professionnelle en développement web et mobile, ainsi que le master spécialisé en intelligence artificielle et systèmes d'information. Ces nouvelles formations visent à former des experts capables de répondre aux défis technologiques actuels.

L'université collabore également avec plusieurs entreprises locales et internationales pour offrir des stages pratiques et des projets de recherche conjoints. Par exemple, le département d'informatique a noué un partenariat avec la société IBM pour développer des solutions innovantes en intelligence artificielle.

#### III. Projets et Initiatives Récents
L'Université de Toulon mène plusieurs projets innovants dans le domaine de l'informatique, notamment en matière d’enseignement, de recherche et de développement technologique. Parmi les initiatives notables figurent des ateliers pratiques pour les étudiants débutants en programmation, ainsi que des séminaires réguliers sur les dernières avancées dans le domaine de l'informatique.

Un projet spécifique qui mérite d'être mentionné est la création d'un incubateur technologique dédié aux startups liées à l'intelligence artificielle. Ce projet vise à favoriser l'innovation et la croissance économique en soutenant les jeunes entreprises dans le développement de nouvelles technologies.

#### IV. Défis et Opportunités
Bien que l’Université de Toulon ait fait des progrès significatifs dans le domaine de l'informatique, elle rencontre encore certains défis. L'un d'eux est la nécessité de maintenir un équilibre entre les besoins du marché et les compétences acquises par les étudiants. De plus, il est crucial pour l’université de continuer à attirer des talents et à développer des partenariats avec le secteur privé.

Cependant, ces défis sont également des opportunités pour renforcer la position de l’Université de Toulon sur le marché de l'éducation en informatique. En investissant dans les technologies émergentes et en formant des experts capables d'innover, l'université peut continuer à se distinguer comme un leader dans ce domaine.

#### Conclusion
En résumé, l’Université de Toulon a fait preuve d'une dynamique remarquable pour renforcer ses filières d'informatique. Avec la mise en place de nouvelles formations et le développement de partenariats stratégiques, l'université est bien positionnée pour répondre aux besoins du marché du travail et former des experts capables d'innover dans ce domaine en constante évolution. Les perspectives d’avenir sont prometteuses, avec la possibilité de continuer à se développer et à s'imposer comme un acteur majeur dans l'éducation en informatique.






