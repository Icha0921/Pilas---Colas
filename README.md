# Pilas---Colas
Operaciones en Listas, Pilas, Colas y Árboles en un Sistema de Gestión de Tareas
# 1. Lista: Tareas ordenadas por prioridad
tareas_lista = ["Revisar informe", "Enviar correo al cliente", "Preparar presentación"]
print("Lista de tareas (ordenadas por prioridad):", tareas_lista)

# Operaciones con listas
tareas_lista.append("Actualizar base de datos")  # Insertar al final
tareas_lista.pop(1)  # Eliminar la tarea en la posición 1
print("Lista actualizada:", tareas_lista)

# 2. Pila: Tareas urgentes (último en entrar, primero en salir - LIFO)
tareas_pila = []
tareas_pila.append("Corregir error crítico")  # Insertar (push)
tareas_pila.append("Revisar código de seguridad")
print("Pila de tareas urgentes:", tareas_pila)

tarea_completada = tareas_pila.pop()  # Eliminar (pop) la última tarea
print("Tarea completada (pila):", tarea_completada)
print("Pila actualizada:", tareas_pila)

# 3. Cola: Tareas en orden de llegada (primero en entrar, primero en salir - FIFO)
from collections import deque

tareas_cola = deque(["Atender solicitud 1", "Atender solicitud 2", "Atender solicitud 3"])
print("Cola de tareas (orden de llegada):", list(tareas_cola))

tareas_cola.append("Atender solicitud 4")  # Insertar (enqueue)
tarea_atendida = tareas_cola.popleft()  # Eliminar (dequeue) la primera tarea
print("Tarea atendida (cola):", tarea_atendida)
print("Cola actualizada:", list(tareas_cola))

# 4. Árbol: Tareas jerárquicas (usando un diccionario para simular un árbol)
tareas_arbol = {
    "Desarrollar módulo": {
        "Diseñar interfaz": {
            "Crear bocetos": {},
            "Validar con el equipo": {}
        },
        "Implementar lógica": {
            "Escribir código": {},
            "Realizar pruebas unitarias": {}
        }
    }
}

# Función para mostrar las tareas en el árbol
def mostrar_tareas_arbol(arbol, nivel=0):
    for tarea, subtareas in arbol.items():
        print("  " * nivel + "- " + tarea)
        mostrar_tareas_arbol(subtareas, nivel + 1)

print("Árbol de tareas (jerárquico):")
mostrar_tareas_arbol(tareas_arbol)
