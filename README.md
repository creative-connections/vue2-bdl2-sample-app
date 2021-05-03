# vue2-bdl2

Sample project using Bodylight.js-Components as web components in Vue.js 2 application.

Includes these changes in:
1) `index.html`
```html
...
    <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
  </head>
  <body aurelia-app="webcomponents">
...
```
2) `main.js`
```javascript
...
Vue.config.ignoredElements = ['bdl-fmi','bdl-chartjs-time','bdl-range']
...
```
3) `About.vue`
```html
<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div>
      <p>bodylight components:</p>
    Press buttons to start/stop/step/reset simulation:
    <bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370" valuelabels="aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

    Change the slider value. When released - it is sent to model and simulation is recalculated accordingly:
    <bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

    Show some variables in chart:
    <bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta" initialdata="" refindex="0" refvalues="1"></bdl-chartjs-time>
    </div>
  </div>
</template>

```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
