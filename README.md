## SISTEMAS DE CONTROL DE ASISTENCIA DE  MUNDO LLANTAS-LLANTAS 
Sistema de control de asistencia de empleados
Aplicación web para el registro y gestión de asistencia del personal, desarrollada en PHP puro con arq
uitectura MVC desde cero , Programación Orientada a Objetos (POO) , PDO y MariaDB como base de dato
##1 :Descripción dela empresa 
Mundo Llantas es un taller mecánico especializado en reparación y mantenimiento automotriz, que ofrece servicios como arreglo de carros, parche de cámaras y alineamiento de ruedas. En la actualidad, el taller necesita digitalizar y centralizar la gestión de sus órdenes de servicio y el control de los trabajos realizados por turno, reemplazando los registros en hojas sueltas o cuadernos físicos. Este sistema elimina problemas como:

Órdenes de servicio ilegibles, incompletas o extraviadas.

Dificultad para calcular comisiones o rendimiento por técnico.

Pérdida de historial de reparaciones por vehículo o cliente.

Falta de control sobre los tiempos reales de atención (entrada, salida, duración de cada servicio).

Dependencia de la memoria del personal para saber qué trabajos están pendientes o qué insumos (parches, válvulas, etc.) se usaron en cada reparación
## 2: Problema y Solución
Problema Identificado
Mundo Llantas registra la asistencia de sus empleados manualmente en Excel y no controla el inventario de productos (parches, cámaras, etc.), lo que genera pérdida de stock e imprecisiones en el pago de horas trabajadas.

Causas
Asistencia manual en Excel sin control horario exacto.

No hay un sistema que descuente automáticamente los insumos usados en cada reparación.

Efectos
Pérdida de stock de productos por falta de trazabilidad.

Pago incorrecto de horas trabajadas y dificultad para generar reportes.

Solución Propuesta
Desarrollar una aplicación web con PHP + POO + MVC que permita:

Registrar asistencia con hora exacta (PDO + MariaDB).

Controlar inventario con descuento automático de insumos al registrar una reparación.

Consultar historial de asistencias y stock mínimo con alertas.

