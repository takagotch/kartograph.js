### kartograph.js
---
https://github.com/kartograph/kartograph.js

```js
map = $K.map('#map', 600, 400);
map.loadMap('world.svg', function(){
  map.addLayer('countries', {
    styles: {
      fill: '#ee9900'
    },
    title: function(d){
      return d.countryName;
    }
  });
});

pop_density = { 'USA': 123455, 'CAN': 232323, ... };
colorscale = new chroma.ColorScale({
  colors: chroma.brewer.Y1OrRd,
  limits: chroma.limits(chroma.analyze(pop_density), 'k-means', 9)
});
map.getLayer('countries').style({
  return colorscale.get(pop_density[data.iso]);
});

cities = [{ lat: 43, lon: -75, label: 'New York', population: 19465197 }];
map.addSymbols({
  data: cities,
  location: function(d){
    return [d.lon, d.lat];
  },
  type: Kartograph.Bubble,
  radius: function(d){
    return Math.sqrt(d.population) * 0.001;
  }
})
```

```
```

```
```

