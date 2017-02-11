## Sumar

### Review 1

Ce ai facut bine:
* ai pus imaginile
* ai facut navigare pe pagini noi la imagini
* ai facut o galerie

Ce nu ai facut bine, si pe viitor trebuie sa iei in considerare:
* ai facut commit in foderul parinte, am zis ca se face commit pentru fiecare tema in acelasi folder
* ai folosit pathuri absolute, in navigare se folsesc numai pathuri relative, eu de exemplu nu pot naviga pe path-urile de pe pc-ul tau, dar asta nu e asa de relevat pentru ca tu nu ai un server in spate la website, am pus doua linkuri in index.html sa vezi cum se face cu pathuri relative
* taguri neinchise, browserele moderne stiu sa corecteze aceste probleme, dar site-ul tau are de suferit la indexarea de catre roboti motoarelor de cautare, exemplu cu probleme:

```html
<a href="somwhere.html">
  <img src="whatever.jpg" alt="myalt">
</a>
<!-- img tag trebuie sa fie -->
<img src="whatever.jpg" alt="myalt" />
```

Acum sa vedem ce aveam eu de gand, si eventual sa corectezi, o sa folosesc engleza ca sa iti fie mai usor sa cauti.

* use only one page for gallery, all images should be loaded at page load or better with javascript
* use css to hide gallery inactive frames
* use javscript to show/hide gallery frames when gallery frames selectors are clicked

Example:

#### css:
```css
.hidden {
  display: none;
}

```
#### html:
```html
<div id="gallery">
  <div id="frame1">
     <img src="http://lorempixel.com/400/400/sports/1"/>
  </div>
  <div id="frame2" class="hidden">
      <img src="http://lorempixel.com/400/400/sports/2"/>
  </div>
</div>
<!-- use buttons if you don't like anchors -->
<div class="gallery-buttons">
 <a id="page1" href="#">1</a>
 <a id="page2" href="#">2</a>
<div>
```
#### js:
```javascript
document.getElementById("page1").onclick = function(){
   //hide all gallery frames
   document.getElementById("frame2").setAttribute("class", "hidden");
   //show freme specific to button clicked
   document.getElementById("frame1").setAttribute("class", "");
}

document.getElementById("page2").onclick = function(){
  //hide all gallery frames
   document.getElementById("frame1").setAttribute("class", "hidden");
  //show freme specific to button clicked
   document.getElementById("frame2").setAttribute("class", "");
}
```
