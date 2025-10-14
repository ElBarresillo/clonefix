# Version 2

no hay mucho cambio o podria decir un cambio nulo
en el diseño de la pagina, unicamente en esta
version añadimos un poco de JavaScript y añadimos
la API de TVMaze de donde agarraremos todos los
shows para nuestra pagina CLON.

## 😶‍🌫️ Código

JavaScript

```JavaScript
// api a tvmaze
const API = "https://api.tvmaze.com"

//Elementos del DOM
const rowsContainer = document.getElementById('rowsContainer')
const hero = document.getElementById('hero')
const heroTitle = document.getElementById('heroTitle')
const heroDesc = document.getElementById('heroDesc')
const heroPlay = document.getElementById('heroPlay')

const init = async () => {
    const trending = await fetchJSON(`${API}/shows?page=1`)
    renderRow("Tendencias", trending.slice(0, 20))
    console.log('@@@ trending =>', trending)
}

const renderRow = (title, shows) => {
    const section = document.createElement('section')
    section.classList = 'mb-3'
    section.innerHTML = 
    `
        <h3 class="rowTitle">${title}</h3>
        <div class="rail" data-rail></div>
    `
    // funcion para crear el poster mini y pegarlos
    rowsContainer.appendChild(section)
}

const fetchJSON = async (url) => {
    const res = await fetch(url)
    if(!res.ok){
        throw new Error('Error al Cargar Datos', url);
    }
    return await res.json()
}

init()

```

---
Links de Navegación

-✔️ [README](README.md)
-✔️ [Version 1](version1.md)
-✔️ [Version 3](version3.md)