# Máquina de estados

---

Máquina de café desarrollada en Kotlin que permite seleccionar un tipo de café, insertar crédito y preparar y servir el café. Incluye una versión básica y una versión premium mediante herencia.

## Diagrama de estados

---

## Estados:

---

- **Apagada:** La máquina está apagada y no permite seleccionar productos ni insertar crédito.
- **SeleccionandoProducto:** La máquina está encendida y lista para que el usuario inserte crédito y seleccione un café.
- **PreparandoCafe:** La máquina está preparando el café seleccionado por el usuario.
- **Error:** Se ha producido un error durante el funcionamiento, como disponer de crédito insuficiente para comprar el café.
- **SirviendoCafe:** La máquina está sirviendo el café preparado e identifica la marca y el recipiente utilizado.

## Transacciones:

---

- **Encender máquina:** Transición de Apagada a SeleccionandoProducto.
- **Insertar crédito:** Permite añadir dinero mientras la máquina está en el estado SeleccionandoProducto.
- **Seleccionar tipo de café:** Transición de SeleccionandoProducto a PreparandoCafe, si hay crédito suficiente.
- **Crédito insuficiente:** Transición de SeleccionandoProducto a Error cuando el usuario no dispone de dinero suficiente.
- **Preparar café:** Transición de PreparandoCafe a SirviendoCafe cuando termina la preparación.
- **Servir café:** La máquina registra la marca del café y el tipo de recipiente utilizado.
- **Apagar máquina:** Transición al estado Apagada y reinicio del crédito disponible.
- **Reiniciar máquina:** Restablece el estado inicial Apagada y el crédito a cero.

## Herencia

---

La clase `MaquinaCafePremium` hereda de `MaquinaCafe` y sobrescribe el método `servirCafe()` para servir el café en una taza de cerámica premium.

## Pruebas

---

El programa principal (`main`) comprueba el funcionamiento básico de la máquina, la preparación de un café con crédito suficiente, el funcionamiento de la versión premium, el error por crédito insuficiente y el reinicio de la máquina.