// El principal objetivo de este desafío es fortalecer tus habilidades en lógica de programación. Aquí deberás desarrollar la lógica para resolver el problema.
let lista = [];
let listaAmigos = document.getElementById('listaAmigos');
let resultado = document.getElementById('resultado');

function agregarAmigo() {
    let nombre = document.getElementById('amigo').value;
    if (nombre === '') {
        alert('Ingrese un nombre por favor');
    } else {
        lista.push(nombre);
        document.getElementById('amigo').value = ''; // limpiar el campo
        mostrarAmigo();
    }
}

function mostrarAmigo() {
    listaAmigos.innerHTML = ''; // limpiar la lista antes de mostrar
    if (lista.length > 0) {
        // Mostrar la lista de amigos
        for (let nombre of lista) {
            let li = document.createElement('li'); // crear un nuevo elemento li
            li.textContent = nombre; // asignar el nombre al li
            listaAmigos.appendChild(li); // añadir el li al contenedor
        }
    } else {
        listaAmigos.innerHTML = 'No hay lista de amigos';
    }
}

function sortearAmigo() {
    if (lista.length > 0) {
        // Seleccionar un amigo aleatorio
        let sortearAmigo = lista[Math.floor(Math.random() * lista.length)];
        resultado.innerHTML += 'El amigo del sorteo es: ' + sortearAmigo + '<br>'; // Mostrar el nombre sorteado
        console.log(sortearAmigo);
    } else {
        resultado.innerHTML = 'No hay amigos para sortear';
    }
}
