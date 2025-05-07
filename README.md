#Actividad Patrones
# 🪪 Generador de Credenciales de Evento

### Estudiante(s):  
- Bastian Umaña - Patrones de Diseño (Seccion 1)

---

## 🎯 Objetivo del Proyecto

Este sistema permite emitir credenciales personalizadas para un evento, a partir de una plantilla clonable. Se aplican los patrones de diseño **Prototype** (para clonar credenciales) y **Singleton** (para configuración global del evento). (redactar el suyo)

---

## 🧬 Patrón Prototype – Aplicación

- `CredencialBase` implementa `clonarC`.
- Clonar()

```java
public class CredencialBase implements clonarC {
    private String nombre;
    private String cargo;
    private String rut;

    public CredencialBase(String nombre, String cargo, String rut){
        this.nombre=nombre;
        this.cargo=cargo;
        this.rut=rut;
    }

    @Override
    public clonarC clonar(){
    return new CredencialBase(this.nombre, this.cargo, this.rut);
    }
```

---

## 🔒 Patrón Singleton – Aplicación

- `Aplicacion` contiene:
  - CredencialBase <List>String
- Se accede con `getInstancia()`:

```java
Singleton.getInstancia().atributo("atributo");

public class Aplicacion {

    private static Aplicacion instancia;
    private List<CredencialBase> credenciales;

    private Aplicacion() {
        credenciales = new ArrayList<>();
    }

    public static Aplicacion getInstancia() {
        if (instancia == null) {
            instancia = new Aplicacion();
        }
        return instancia;
    }

public class Main {
    public static void main(String[] args) {
        Aplicacion app = Aplicacion.getInstancia();
        app.iniciar();
    }
}


```

---

## 🖥️ Menú por consola

```
Credencial original:
=== Menú de Credenciales ===
1. Nombre: Bastian
2. Cargo: Ayudante
3. RUT: 21349720-0
============================
Credencial clonada:
=== Menú de Credenciales ===
1. Nombre: Bastian
2. Cargo: Ayudante
3. RUT: 21349720-0
============================
=== Editar Credenciales ===
Ingrese nuevo nombre (actual: Bastian):
```

---

## 📊 Diagrama de Clases (UML)

![imagen](https://github.com/user-attachments/assets/343ea256-7718-4d1d-adda-a50229f79649)




---

## 📸 Captura del sistema funcionando

>![imagen](https://github.com/user-attachments/assets/631ba9dc-da69-46d8-92b5-0865582c9f05)

>![imagen](https://github.com/user-attachments/assets/4c850d35-4e62-4b1a-8080-e46cb158749d)

>![imagen](https://github.com/user-attachments/assets/4a006f72-300b-4dc6-b583-3217498b71b9)

>![imagen](https://github.com/user-attachments/assets/00ff7105-fa62-4ad4-8b70-942a57482a43)

> ![imagen](https://github.com/user-attachments/assets/13dfe88f-8614-43e8-ae5f-dea1722a71aa)

