---
{"dg-publish":true,"permalink":"/01-projets/pod-semaine-de-valkann/articles/2024-semaine-15-garder-une-trace-des-choses/","title":"2024 - Semaine 15 - Garder Une Trace Des Choses","tags":["blog"]}
---


# 2024 - Semaine 15 - Garder Une Trace Des Choses

## Garder Une Trace Des Choses

Bienvenue je vais vous partager mes méthodes pour suivre et préserver mes sources d'inspiration au quotidien. Si vous êtes ici, c'est que vous cherchez peut-être à comprendre ma manière de garder une trace de mes découvertes et de ma consommation médiatique.

Au cœur de ma démarche de gestion de connaissances personnelles se trouve Obsidian,[^1] un compagnon fidèle que j'utilise pour créer, organiser et structurer mes idées, mes projets et mes apprentissages.

### Alimenter Sa Base De Connaissances

L'objectif principal est de nourrir ma base de connaissances avec les contenus que je découvre chaque jour. Pour cela, j'ai cherché une solution simple pour intégrer ces découvertes à mon système de gestion de connaissance ou PKM.[^2]

C'est là qu'intervient Raindrop, une application de gestion de signets en ligne qui me permet de sauvegarder, d'organiser et de partager mes trouvailles sur le web, avec une intégration fluide avec Obsidian.

### Capturer Les Ressoucres

Raindrop me permet de capturer facilement les médias que je rencontre au fil de ma navigation en ligne.

- Pour les podcasts, je partage simplement le lien vers Raindrop depuis mon application favorite.
- Pour les films, séries, articles ou pages web, je les sauvegarde avec l'extension de mon navigateur.

Raindrop offre également la possibilité de surligner les passages importants dans les textes, une fonctionnalité qui se retrouve ensuite dans mes notes Obsidian.

Pour les toot sur Mastodon, il y a moyen de faire un flux RSS des toot que je sauvegarde, à partir de là avec IFTTT j'ai pu faire un petit flux qui va prendre  les nouveaux items du flux RSS et les envoyés dans Raindrop

### Organiser Et Intégrer

À l'intérieur de Raindrop, je classe mes trouvailles dans différentes catégories. Certaines sont des réservoirs pour mes découvertes récentes, tandis que d'autres sont synchronisées avec Obsidian.

![RaindropMenu.png](/img/user/Extras/IMG/RaindropMenu.png)

Une fois assimilées, je déplace mes trouvailles vers leur catégorie respective, et le reste se déroule harmonieusement dans Obsidian.

**Synchroniser avec Obsidian**

Le plugin Raindrop Highlight assure la synchronisation des signets et des surlignages avec Obsidian. J'ai configuré mes catégories préférées pour une intégration ciblée.

![RaindropConfig2.png](/img/user/Extras/IMG/RaindropConfig2.png)

Les catégories se transforment en dossiers dans Obsidian, organisés dans une structure cohérente pour faciliter la navigation.

![RaindropConfig.png](/img/user/Extras/IMG/RaindropConfig.png)

![Menu.png](/img/user/Extras/IMG/Menu.png)

### Partage

Pour ceux qui souhaitent suivre mes pas dans cette quête de préservation et de gestion des connaissances, je partage volontiers mon template Obsidian, conçu pour accueillir élégamment les informations essentielles.

#### Content Template

```markdown
{% if is_new_article %}
# {{title | safe}}

![]({{cover}})

## Review

review::

## Informations

{{excerpt}}
***
{{note}}

## Highlights

{% endif -%}{% for highlight in highlights %}
{% if highlight.color == "red" -%}
    {%- set callout = "danger" -%}
{%- elif highlight.color == "blue" -%}
    {%- set callout = "info" -%}
{%- elif highlight.color == "green" -%}
    {%- set callout = "check" -%}
{%- else -%}
    {%- set callout = "quote" -%}
{%- endif -%}
> [!{{callout}}]+ Updated on {{highlight.lastUpdate}}
>
> {{highlight.text.split("\n") | join("\n>")}}
{% if highlight.note -%}> > {{highlight.note}}{%- endif %}

{%- endfor -%}


### Qu'est-ce ?

### Définition

### Pourquoi C'est Important ?

### 🧭 Boussole

#### 🔼 : Thème / Question

#### ⬅ : Similaire

#### ➡ : Opposé

#### 🔽 : À Quoi Cela Conduit-il ?

### Références

### Notes




## Qu'est-ce que j'ai ressenti ? 

## À quoi cela m'a-t-il fait penser ?

## Qu'est-ce que cela m'a fait / me donne envie de faire ?
```

#### Metadata Template

```markdown
date: '[[2024-04-08]]'
week: '[[2024-15]]'
author: 
type: #SN/{% if collection.title %}{{collection.title}}{% endif %}
statut: ✅
tags: 
 - new
{% if tags|length %}Tags: #{{ tags | join(", #") }}{% endif %}
rating:
{% if link %}source: {{link}}{% endif %}

```

#### Filename Template

```markdown
{{title}}
```

### Pour Finir

En conclusion, la pratique de garder une trace de nos inspirations et de notre consommation médiatique est bien plus qu'une simple habitude,en cultivant cette démarche, nous apprenons à valoriser chaque découverte, à les intégrer dans notre parcours personnel et professionnel. Que ce soit pour alimenter nos projets créatifs, enrichir nos connaissances ou simplement pour le plaisir de la découverte, garder une trace de nos inspirations nous permet de rester connectés à notre monde intérieur et extérieur et se diriger pourquoi pas vers la création de notre propre Foyer Numérique.

## Notes

---

[^1] : Obsdian est un logiciel de prise de note qui utilise le langage [[Markdown\|Markdown]]. Il permet de :
- Utiliser des tags
- Intégrer des méta donnée en YAML
- Utiliser le markdown pour la mise en page
- Faire des liens bidirectionnels entre les notes de manière simple.
- De représenter les liens sous forme de graphique
- D'inclure le contenu de n'importe quel autre fiche ou fichier
- De modifier le comportement grâce à des thèmes et des plugins.
[^2] : Personnal Kwowledege management ou La gestion des connaissances personnelles. C'est l'ensemble des procédés qu'un individu met en œuvre pour rassembler, rechercher, classifier et partager la connaissance au quotidien, ainsi que la manière dont ces processus aident son travail.
