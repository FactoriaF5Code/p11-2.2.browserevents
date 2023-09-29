# Inspeccionando eventos del DOM

Esta página utiliza la solución de [https://paul.kinlan.me](https://paul.kinlan.me/monitoring-all-events-on-an-element/) para mostrar los eventos que se producen en ella.

Abre esta página y la consola para ver los logs con información de los eventos que ocurren. 

- Cuántos eventos diferentes eres capaz de ver?
- Cuál es el nombre de cada evento?
- Qué es la información que se muestra en la consola?


También puedes visualizarlo en otra página, abriendo la consola y copiando el código siguiente: 

```
function monitorEvents(element) {
  var log = function(e) { console.log(e);};
  var events = [];

  for(var i in element) {
    if(i.startsWith("on")) events.push(i.substr(2));
  }
  events.forEach(function(eventName) {
    element.addEventListener(eventName, log);
  });
}
```
