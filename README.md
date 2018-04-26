# React-Native

### 1. Abrir y configurar el IDE

Abrimos Snack, el IDE que vamos a utilizar: https://snack.expo.io/

Una vez dentro del snack borramos el contenido del archivo App.js

### 2. Iniciar un proyeto vacío

Vamos a importar los elementos que necesitamos desde React Native y de Expo, así mismo vamos a crear una clase que, por el momento, permanecerá vacía y una hoja de estilos al final del archivo.

Nuestro archivo App.js debería quedar así:

```javascript
import React, { Component } from 'react';
import { Text, View, ScrollView, StyleSheet, Button, Image, TextInput } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
}

const styles = StyleSheet.create({
});
```

### 3. ¿De qué se trata nuestra aplicación?

Nuestra aplicación va a cambiar una imagen por medio de interacciones con botones y cambiará el título según una entrada de texto.

Para esto vamos a guardar los enlaces de las imágenes que vamos a utilizar en un arreglo, van a quedar justo debajo de los import.

Nuestro archivo App.js debería quedar así:

```javascript
import React, { Component } from 'react';
import { Text, View, ScrollView, StyleSheet, Button, Image, Modal } from 'react-native';
import { Constants } from 'expo';

var images = [
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso1.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso2.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso3.jpg"
];

export default class App extends Component {
}

const styles = StyleSheet.create({
});
```

### 4. Estado de la aplicación

La funcionalidad de la aplicación se hará a través del estado de la misma (status funciona exactamente igual que en ReactJS).
Tendremos dos propiedades en el estado de la aplicación: 

1. Imagen: (0, 1, 2). Es un entero entre 0 y 2 que se utilizará para saber cual de las imágenes de nuestro arreglo de imágenes es la que se debe mostrar.

2. Título: (string). Es la cadena de texto que se mostrará en la cabecera de la aplicación.
  
```javascript
...
export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      image: 0,
      title: "Tiburoso: 100% real, 1000% letal"
    };
  }
}
...
```
  
```javascript
import React, { Component } from 'react';
import { Text, View, ScrollView, StyleSheet, Button, Image, Modal } from 'react-native';
import { Constants } from 'expo';

var images = [
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso1.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso2.jpg",
  "https://raw.githubusercontent.com/Agora-SE2/React-Native/master/images/tiburoso3.jpg"
];

export default class App extends Component {
}

const styles = StyleSheet.create({
});
```


