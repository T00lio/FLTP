# FLTP


In this repository I will be posting concepts and ideas reinforce by Brian Montero's tutoring. It provides some insight into some the techniques used in the development and review of portfolio full stak project



    Colocation en React

La "colocación" (colocation) en proyectos de React JS se refiere a la práctica de organizar y agrupar archivos relacionados con componentes específicos de manera conjunta en la misma ubicación o carpeta. Esta técnica promueve una estructura de proyecto más modular y mantenible, ya que agrupa todos los recursos y archivos relevantes para un componente particular (como archivos de estilo, tests y lógica) en un solo lugar.

### Ventajas de la Colocación

1. **Mantenibilidad**: Facilita el mantenimiento del código porque toda la lógica relacionada con un componente se encuentra en un único lugar.
2. **Escalabilidad**: Ayuda a escalar proyectos grandes al mantener el código organizado y modular.
3. **Encapsulamiento**: Promueve el encapsulamiento y la reutilización de componentes, haciendo que sea más fácil entender y trabajar con componentes individuales.
4. **Mejor colaboración**: Facilita la colaboración en equipos, ya que los desarrolladores pueden trabajar en componentes específicos sin interferir con otras partes del proyecto.

### Ejemplo de Estructura de Colocación

Considera un proyecto donde tienes un componente `UserProfile`. Con colocation, podrías estructurar tu proyecto de la siguiente manera:

```
src/
│
└── components/
    ├── UserProfile/
    │   ├── UserProfile.js
    │   ├── UserProfile.css
    │   ├── UserProfile.test.js
    │   └── UserProfileHelpers.js
    ├── Header/
    │   ├── Header.js
    │   ├── Header.css
    │   └── Header.test.js
    └── Footer/
        ├── Footer.js
        ├── Footer.css
        └── Footer.test.js
```

En este ejemplo:
- `UserProfile.js` contiene la lógica del componente `UserProfile`.
- `UserProfile.css` contiene los estilos específicos para el componente `UserProfile`.
- `UserProfile.test.js` contiene las pruebas unitarias para el componente `UserProfile`.
- `UserProfileHelpers.js` contiene funciones auxiliares relacionadas con el componente `UserProfile`.

### Implementación en React

Supongamos que tenemos el componente `UserProfile`. Así es como podrías organizarlo utilizando la técnica de colocación:

**UserProfile.js:**
```javascript
import React from 'react';
import './UserProfile.css';
import { getUserInfo } from './UserProfileHelpers';

const UserProfile = () => {
  const userInfo = getUserInfo();

  return (
    <div className="user-profile">
      <h1>{userInfo.name}</h1>
      <p>{userInfo.bio}</p>
    </div>
  );
};

export default UserProfile;
```

**UserProfile.css:**
```css
.user-profile {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
}

.user-profile h1 {
  font-size: 24px;
  margin-bottom: 10px;
}
```

**UserProfileHelpers.js:**
```javascript
export const getUserInfo = () => {
  return {
    name: "Tulio Salvatierra",
    bio: "Desarrollador web y músico aficionado."
  };
};
```

**UserProfile.test.js:**
```javascript
import React from 'react';
import { render } from '@testing-library/react';
import UserProfile from './UserProfile';

test('renders user profile', () => {
  const { getByText } = render(<UserProfile />);
  expect(getByText('Tulio Salvatierra')).toBeInTheDocument();
  expect(getByText('Desarrollador web y músico aficionado.')).toBeInTheDocument();
});
```

### Conclusión

La colocation es una práctica recomendada en el desarrollo de aplicaciones React para mantener el código organizado, modular y fácil de mantener. Al agrupar archivos relacionados en un mismo lugar, se mejora la legibilidad y mantenibilidad del proyecto, lo que resulta especialmente útil en aplicaciones de gran escala.

Los objetos de mapeo en JavaScript son estructuras de datos que permiten asociar claves (keys) con valores (values). Los dos tipos principales de objetos de mapeo en JavaScript son los objetos (`Object`) y los mapas (`Map`). A continuación, te explico ambos conceptos:

### Objetos (`Object`)

Un objeto en JavaScript es una colección de propiedades, y una propiedad es una asociación entre un nombre (o clave) y un valor. Los objetos se utilizan comúnmente para almacenar colecciones de datos relacionados y entidades más complejas.

