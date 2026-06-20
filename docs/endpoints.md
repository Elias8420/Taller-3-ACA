# Catálogo de Servicios Web: Módulo de Aulas

El módulo de gestión de aulas (`classrooms`) centraliza el inventario físico del campus. Debido al alto volumen de registros, este recurso implementa un esquema de ordenamiento y paginación a nivel de base de datos para mitigar la sobrecarga de red.

## 1. Obtener Listado General de Aulas

* **URL Base:** `/api/v1/classrooms`
* **Método de Red:** `GET`
* **Nivel de Seguridad:** Requiere token de portador (`Bearer JWT`) válido en las cabeceras.

### Parámetros de la Solicitud

| Parámetro | Tipo de Dato | Ubicación | Descripción | Requerido |
| :--- | :--- | :--- | :--- | :--- |
| `page` | `Integer` | Query string | Índice cero del bloque de registros solicitado. | No (Por defecto: 0) |
| `size` | `Integer` | Query string | Dimensionamiento máximo de elementos por página. | No (Por defecto: 10) |

---

## 2. Ejemplos Prácticos de Consumo

Utiliza los selectores interactivos a continuación para alternar entre el comando de ejecución en consola y la estructura de transferencia del cuerpo de respuesta devuelto por el servidor de Spring Boot.

### Ejemplos de Consumo

A continuación, se muestra cómo realizar la petición utilizando la terminal y cuál es la estructura exacta de la respuesta JSON estandarizada.

=== "Petición con cURL"

    ```bash
    curl -X GET "https://api.buhoseats.lat/api/v1/classrooms?page=0&size=2" \
         -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..." \
         -H "Accept: application/json"
    ```

=== "Respuesta HTTP 200 OK"

    ```json
    {
      "content": [
        {
          "id": 1,
          "code": "LAB-B2",
          "capacity": 35,
          "building": "Edificio B"
        },
        {
          "id": 2,
          "code": "AUD-01",
          "capacity": 120,
          "building": "Planta Baja"
        }
      ],
      "pageable": {
        "pageNumber": 0,
        "pageSize": 2
      },
      "totalPages": 5,
      "totalElements": 10
    }
    ```