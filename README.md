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

Nuestro archivo _App.js_ debería quedar así:

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

2. Título: (_string_). Es la cadena de texto que se mostrará en la cabecera de la aplicación.
  
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

### 5. Funciones para actualizar la imagen

Vamos a crear las funciones que se llamarán desde los botones, ambas funciones serán muy sencillas y tendrán un if para evitar que se seleccione un índice que no existe.

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
  goBack() {
    if(this.state.image > 0){
      this.setState({image: this.state.image - 1});
    }
  }
  upgrade() {
    if(this.state.image < 2){
      this.setState({image: this.state.image + 1});
    }
  }
}
...
```

### 6. Containers y estilos

Al no ser HTML, la posibilidad de utilizar CSS deja de existir. 
Sin embargo, React Native tiene su propia StyleSheet y funciona muy parecido a como lo hace CSS.

Al final del _App.js_ vamos a definir un arreglo con colores y la hoja de estilos.
  
```javascript
...
var colors = [
  "darkorange",
  "deepskyblue",
];

const styles = StyleSheet.create({
});
```

________________________________________

Hasta este momento nuestro archivo _App.js_ debería verse así:

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
  constructor(props) {
    super(props);
    this.state = {
      image: 0,
      title: "Tiburoso: 100% real, 1000% letal"
    };
  }
  goBack() {
    if(this.state.image > 0){
      this.setState({image: this.state.image - 1});
    }
  }
  upgrade() {
    if(this.state.image < 2){
      this.setState({image: this.state.image + 1});
    }
  }
}

var colors = [
  "darkorange",
  "deepskyblue",
];

const styles = StyleSheet.create({
});
```
________________________________________

### 7. ¿Y el contenido?

Añadamos el _render()_ a nuestra clase para, por fin, poder ver algo en pantalla.

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
  
  goBack() {
    if(this.state.image > 0){
      this.setState({image: this.state.image - 1});
    }
  }
  
  upgrade() {
    if(this.state.image < 2){
      this.setState({image: this.state.image + 1});
    }
  }
  
  render() {
    return ();
  }
}
```

Aunque nos podemos ir olvidando de retornar un div, React Native utiliza un sistema de etiquetas muy parecido a HTML.
  
Por ejemplo, en vez de **div** tenemos **View**, en vez de **p** tenemos **Text** y así. Toda la información está disponible en la página oficial: https://facebook.github.io/react-native/docs/tutorial.html 

Para poder hacer scroll utilizaremos la etiqueta **ScrollView**, dentro de ella tendremos una etiqueta **View** a la que le añadiremos todo el contenido de la aplicación y la asociaremos con los estilos del container.

Así quedará nuestro render:

```javascript
...
render() {
    return (
      <ScrollView>
        <View style={styles.container}>
          <Image source={{uri: images[this.state.image]}}
            style={styles.image} 
          />
        </View>
      </ScrollView>
      
    );
  }
...
```

Y así quedará nuestra hoja de estilos:

```javascript
...
const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    paddingTop: Constants.statusBarHeight,
  }
});
...
```



