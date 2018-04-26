# React-Native

### 1. Abrir y configurar el IDE

Abrimos Snack, el IDE que vamos a utilizar: https://snack.expo.io/

Una vez dentro del snack borramos el contenido del archivo App.js

### 2. Iniciar un proyeto vacío

Vamos a importar los elementos que necesitamos desde React Native, así mismo vamos a crear una clase que, por el momento, permanecerá vacía.

Nuestro archivo App.js debería quedar así:

```javascript
import React, { Component } from 'react';
import { Text, View, ScrollView, StyleSheet, Button, Image, Modal } from 'react-native';

export default class App extends Component {
}
```

### 3. ¿De qué se trata nuestra aplicación?

Nuestra aplicación va a cambiar una imagen por medio de interacciones con botones y cambiará el título según una entrada de texto.

Para esto vamos a guardar los enlaces de las imágenes que vamos a utilizar en un arreglo, van a quedar justo debajo de los import.

Nuestro archivo App.js debería quedar así:

```javascript
import React, { Component } from 'react';
import { Text, View, ScrollView, StyleSheet, Button, Image, Modal } from 'react-native';

var images = [
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso1.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso2.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso3.jpg"
];

export default class App extends Component {
}
```


