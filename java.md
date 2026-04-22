Sí, Java tiene estructuras de datos tipo **diccionario** (también llamados mapas o tablas hash). La interfaz principal es `Map<K, V>`, donde `K` es el tipo de la clave y `V` el tipo del valor.

## Implementaciones más comunes de `Map`

| Clase | Descripción | ¿Hilos segura? | Permite `null` (clave/valor) |
|-------|-------------|----------------|------------------------------|
| `HashMap<K,V>` | Tabla hash estándar, sin orden predecible. | No | Sí / Sí |
| `LinkedHashMap<K,V>` | Similar a `HashMap`, pero mantiene orden de inserción o acceso. | No | Sí / Sí |
| `TreeMap<K,V>` | Implementado con árbol rojo-negro; ordena por claves (natural o `Comparator`). | No | No (claves) / Sí |
| `Hashtable<K,V>` | Versión antigua y sincronizada (poco recomendada hoy). | Sí (sincronizada) | No / No |
| `ConcurrentHashMap<K,V>` | Optimizada para concurrencia (mejor que `Hashtable`). | Sí | No / No |

## Ejemplo básico con `HashMap`

```java
import java.util.HashMap;
import java.util.Map;

public class EjemploDiccionario {
    public static void main(String[] args) {
        // Crear un diccionario (mapa) que asocia String -> Integer
        Map<String, Integer> edades = new HashMap<>();

        // Agregar pares clave-valor
        edades.put("Ana", 25);
        edades.put("Luis", 30);
        edades.put("Carlos", 28);

        // Obtener un valor por su clave
        System.out.println("Edad de Ana: " + edades.get("Ana")); // 25

        // Verificar si existe una clave
        if (edades.containsKey("Luis")) {
            System.out.println("Luis está en el diccionario");
        }

        // Recorrer todas las entradas
        for (Map.Entry<String, Integer> entrada : edades.entrySet()) {
            System.out.println(entrada.getKey() + " -> " + entrada.getValue());
        }

        // Eliminar una entrada
        edades.remove("Carlos");
    }
}
```

## ¿Qué significa "lista hash"?

Probablemente te refieres a una **tabla hash** (hash table). En Java, `HashMap` es la implementación por excelencia. También existe `HashSet` para conjuntos (solo claves, sin valores), pero eso no es un diccionario.

## Diferencias con otros lenguajes

- En **Python**, el diccionario es `dict` → en Java es `HashMap`.
- En **JavaScript**, el objeto `{}` o `Map` → en Java es `HashMap` o `LinkedHashMap`.
- En **C#**, `Dictionary<TKey, TValue>` → en Java `HashMap<K,V>`.

## ¿Cuándo usar cada uno?

- **`HashMap`** → caso general, sin necesidad de orden ni concurrencia.
- **`LinkedHashMap`** → cuando necesitas mantener el orden de inserción o acceso.
- **`TreeMap`** → cuando las claves deben estar ordenadas (alfabéticamente, numéricamente, etc.).
- **`ConcurrentHashMap`** → si múltiples hilos acceden y modifican el mapa simultáneamente.

> **Nota**: A partir de Java 8, `HashMap` mejora con árboles internos para colisiones, pero sigue siendo una tabla hash en esencia.

Si buscas una estructura **exactamente** como un diccionario (con clave-valor), `Map` es la respuesta. No hay una clase llamada `Dictionary` excepto una clase abstracta obsoleta (`java.util.Dictionary`) que fue reemplazada por `Map` desde Java 1.2.
