En Java, tanto las **librerías** (bibliotecas) como los **frameworks** son conjuntos de código reutilizable que facilitan el desarrollo, pero tienen diferencias clave en cuanto a **control** y **estructura**.

## 📚 Librería (Library)

Es un conjunto de clases, métodos y utilidades que puedes **llamar** cuando lo necesites. **Tú controlas el flujo** de tu aplicación y decides cuándo y cómo usar la librería.

- **Inversión de control**: No la hay. Tu código llama al código de la librería.
- **Ejemplos comunes**:
  - `java.util.*` (colecciones, fechas, escáner)
  - `Apache Commons` (utilidades de cadenas, IO)
  - `Google Gson` (convertir objetos Java a JSON)
- **Uso típico**:  
  ```java
  import org.apache.commons.lang3.StringUtils;
  
  public class MiApp {
      public static void main(String[] args) {
          String resultado = StringUtils.capitalize("hola"); // tú llamas a la librería
          System.out.println(resultado);
      }
  }
  ```

## 🏗️ Framework

Es una estructura de software que **define el esqueleto** de una aplicación. El framework **controla el flujo** y te llama a ti cuando necesita que ejecutes tu código (Inversión de Control).

- **Inversión de control**: Sí. El framework decide cuándo ejecutar tu código (por ejemplo, ante una petición HTTP, al iniciar la app, etc.).
- **Ejemplos comunes**:
  - **Spring Framework** (inyección de dependencias, MVC, seguridad)
  - **Hibernate** (mapeo objeto-relacional)
  - **JavaFX** (aplicaciones de escritorio con interfaz gráfica)
  - **Jakarta EE** (anteriormente Java EE, para aplicaciones empresariales)
- **Uso típico** (Spring Boot):
  ```java
  @RestController
  public class MiControlador {
      @GetMapping("/hola")
      public String saludar() {
          return "¡Hola! Esto lo llama el framework cuando llega una petición.";
      }
  }
  ```
  Aquí tú no llamas al framework; el framework te llama a ti.

## Comparativa rápida

| Característica       | Librería                          | Framework                          |
|----------------------|-----------------------------------|------------------------------------|
| **Control**          | Tu código controla el flujo       | El framework controla el flujo     |
| **Quién llama a quién** | Tu código llama a la librería   | El framework llama a tu código     |
| **Acoplamiento**     | Bajo (solo usas lo que necesitas) | Alto (debes seguir sus reglas)     |
| **Flexibilidad**     | Alta (puedes cambiarla fácilmente)| Baja (cambiar de framework es costoso) |
| **Ejemplo**          | Gson, Apache Commons, JUnit       | Spring, Hibernate, JavaFX          |

## ¿Cómo decidir cuál usar?

- Usa una **librería** cuando necesites una funcionalidad concreta (parsear JSON, manejar fechas, etc.) sin que el resto de tu aplicación se vea afectada.
- Usa un **framework** cuando quieras una arquitectura ya definida para un tipo de aplicación (web, persistencia, escritorio) y estés dispuesto a seguir sus convenciones.

> **Dato curioso**: Un framework suele incluir varias librerías internamente. Por ejemplo, Spring usa librerías como `spring-core`, `spring-beans`, etc.
