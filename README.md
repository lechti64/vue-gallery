<p align="center">
<img src="https://cdn.rawgit.com/RobinCK/vue-gallery/a08dae25/doc/gallery.png">
</p>

<p align="center">
  <a href="https://travis-ci.org/RobinCK/vue-gallery"><img src="https://img.shields.io/travis/RobinCK/vue-gallery.svg?style=flat-square"></a>
  <a href="https://github.com/RobinCK/vue-gallery"><img src="https://img.shields.io/badge/vuejs-2.x-brightgreen.svg?style=flat-square"></a>
  <a href="https://www.npmjs.com/package/vue-gallery"><img src="https://img.shields.io/npm/dt/vue-gallery.svg?style=flat-square"></a>
</p>  
  
<p align="center">
  <a href="https://david-dm.org/RobinCK/vue-gallery"><img src="https://david-dm.org/RobinCK/vue-gallery.svg?style=flat-square"></a>
  <a href="https://david-dm.org/RobinCK/vue-gallery?type=dev"><img src="https://david-dm.org/RobinCK/vue-gallery/dev-status.svg?style=flat-square"></a>
  <a href="https://github.com/RobinCK/vue-gallery"><img src="https://img.shields.io/npm/v/vue-gallery.svg?style=flat-square"></a>
  <a href="https://github.com/RobinCK/vue-gallery/blob/master/LICENSE"><img src="https://img.shields.io/npm/l/vue-gallery.svg?style=flat-square"></a>

</p>

# Vue-Galerie
Projet français lechti64

Inspiré du projet original de RobinCK

# descriptif du script  Vue-Galerie

:camera: VueJS vous propose une galerie d'images et de vidéos réactives 100% personnalisables, carrousel et lightbox sont de la partie, optimisées pour les navigateurs Web mobiles (smartphones, tablettes) et de bureau (PC) afin de respecter les standards actuels pour tout ces types d'usage.

## Example  d'utilisation avec jsFiddle
[jsFiddle - image](https://jsfiddle.net/lechti64/7tgucb0r/embedded/result/dark/#Result)

[jsFiddle - video](https://jsfiddle.net/lechti64/u8bqt0m1/embedded/result/dark/#Result)

## Installation
#### CDN

Conseillé: https://unpkg.com/vue-gallery, qui reflètera la dernière version dès sa publication dans npm. Vous pouvez également parcourir la source du paquet npm à l’adresse suivante: https://unpkg.com/vue-gallery/

#### NPM

``` bash
npm install vue-gallery --save
```

#### Yarn

``` bash
yarn add vue-gallery
```
## Configuration du développement

``` bash
# install dependencies
npm install

# build dist files
npm run build
```

## Usage

### VueJS un seul fichier (ECMAScript 2015)
```html
<template>
  <div>
    <gallery :images="images" :index="index" @close="index = null"></gallery>
    <div
      class="image"
      v-for="(image, imageIndex) in images"
      :key="imageIndex"
      @click="index = imageIndex"
      :style="{ backgroundImage: 'url(' + image + ')', width: '300px', height: '200px' }"
    ></div>
  </div>
</template>

<script>
  import VueGallery from 'vue-gallery';
  
  export default {
    data: function () {
      return {
        images: [
          'https://dummyimage.com/800/ffffff/000000',
          'https://dummyimage.com/1600/ffffff/000000',
          'https://dummyimage.com/1280/000000/ffffff',
          'https://dummyimage.com/400/000000/ffffff',
        ],
        index: null
      };
    },

    components: {
      'gallery': VueGallery
    },
  }
</script> 

<style scoped>
  .image {
    float: left;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
    border: 1px solid #ebebeb;
    margin: 5px;
  }
</style>

```

### Navigateur web (ES5)
```html
  <script type="text/javascript" src="https://unpkg.com/vue@2.4.3/dist/vue.js"></script>
  <script type="text/javascript" src="https://unpkg.com/blueimp-gallery@2.27.0/js/blueimp-helper.js"></script>
  <script type="text/javascript" src="https://unpkg.com/blueimp-gallery@2.27.0/js/blueimp-gallery.js"></script>
  <script type="text/javascript" src="https://unpkg.com/blueimp-gallery@2.27.0/js/blueimp-gallery-fullscreen.js"></script>
  <script type="text/javascript" src="vue-gallery.js"></script>
  <link rel="stylesheet" type="text/css" href="https://unpkg.com/blueimp-gallery@2.27.0/css/blueimp-gallery.min.css">
  

<div id="app">
  <gallery :images="images" :index="index" @close="index = null"></gallery>
  <div
    class="image"
    v-for="image, imageIndex in images"
    @click="index = imageIndex"
    :style="{ backgroundImage: 'url(' + image + ')', width: '300px', height: '200px' }"
  ></div>
</div>

<script type="text/javascript">
  new Vue({
    el: '#app',
    data: function () {
      return {
        images: [
          'https://dummyimage.com/800/ffffff/000000',
          'https://dummyimage.com/1600/ffffff/000000',
          'https://dummyimage.com/1280/000000/ffffff',
          'https://dummyimage.com/400/000000/ffffff'
        ],
        index: null
      };
    },

    components: {
      'gallery': VueGallery
    }
  });
</script>
```

## Props

| Props               | Type      | Par défaut                                         | Description  |
| --------------------|:----------| ------------------------------------------------|--------------|
| images              | Array     | []                                              | Liste des URL  |
| index               | Number    | null                                            | Index d'image ouvert  |
| options             | Object    |                                                 | [blueimp-gallery](https://github.com/blueimp/Gallery) options |



## Événements
| Nom              | Paramètres              | Description  |
| -----------------|:------------------------|--------------|
| onopen           |                         |              |
| onopened         |                         |              |
| onslide          |                         |              |
| onslideend       |                         |              |
| onslidecomplete  |                         |              |
| onclose          |                         |              |
| onclosed         |                         |              |


## Autre plugins du concepteur de Vue JS

| Projet | Statut | Description |
|---------|--------|-------------|
| [vue-ls](https://github.com/RobinCK/vue-ls)    | ![npm](https://img.shields.io/npm/v/vue-ls.svg)  | Plugin pour travailler avec le stockage local, le stockage de session et le stockage de mémoire du contexte Vue |
| [vue-popper](https://github.com/RobinCK/vue-popper)      | ![npm](https://img.shields.io/npm/v/vue-popperjs.svg) | Composant popover basé sur <a href="https://popper.js.org/">popper.js</a> |178

## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2FRobinCK%2Fvue-gallery.svg?type=large)](https://app.fossa.io/projects/git%2Bhttps%3A%2F%2Fgithub.com%2FRobinCK%2Fvue-gallery?ref=badge_large)

MIT © [Igor Ognichenko](https://github.com/RobinCK)
