# Facade-ST0250-2018-2
Es un patrón de diseño que nos permite simplificar y unificar la interfaz de comunicación entre subsistemas. Nos sirve para:
- Minimizar la comunicación y las dependencias entre subsistemas.
- Proporcionar una interfaz sencilla para un subsistema complejo.
- Eliminar dependencias entre clientes y clases de implementación.
- Dividir conjuntos de subsistemas en capas.


# Integrantes
Juan Camilo Echeverri Salazar

Santiago Tello Ruiz


**Ejemplo en código**
>Nota: El siguiente código aún sigue en desarrollo, no se puede ejecutar en la versión actual.


 ```java
  public abstract class Ingeniero {
    public void despertar() {
        System.out.println(nombre() + " se despierta");
    }
    public void irAEstudiar() {
        System.out.println(nombre() + " va a la universidad");
    }
    public void irACasa() {
        System.out.println(nombre() + " va a su casa");
    }
    public void dormir() {
        System.out.println(nombre() + " va a dormir");
    }
    public class IngenieroDeSistemas extends Ingeniero{
        public String nombre(){
            return "Ingeniero de Sistemas";
        }
        public void miFuncion(){
            System.out.println(nombre() + " hace los trabajos 15 minutos antes de la entrega");
        }
    }
    public class IngenieroMatematico extends Ingeniero{
        public String nombre(){
            return "Ingeniero Matemático";
        }
        public void miFuncion(){
            System.out.println(nombre()+ " es muy buena persona");
        }
    }
}
 ```
Este código implementa la clase Ingeniero de la cual salen las clases hijas IngenieroMatematico e IngenieroDeSistemas, que heredan los metodos despertar(), irAEstudiar(), irACasa(), y dormir(). Además, cada una tiene un método llamado miFunción(), que indica que acción realizan.

```java
  public class facadeIngeniero{
    private final List<ingeniero> estudiantes;

    public facadeIngeniero(){
        estudiantes = new ArrayList<>();
        estudiantes.add(new IngenieroDeSistemas() );
        estudiantes.add(new IngenieroMatematico() );
    }

    public void inicio(){
        estudiantes.despertar();
        estudiantes.irAEstudiar();
    }

    public void nudo(){
        estudiantes.miFuncion();
    }
    
    public void desenlace(){
        estudiantes.irACasa();
        estudiantes.dormir();
    }

    public void existir(){
        inicio();
        nudo();
        desenlace();
    }
}

```
Esta ya es la implementación de una fachada, que es con la que el cliente interactúa. Esta fachada agrupa las funciones del otro componente 
