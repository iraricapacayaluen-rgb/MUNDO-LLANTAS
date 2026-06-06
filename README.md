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

## TRELLO
https://trello.com/b/XggL294J/mundo-llantas


## FIGMA
https://www.figma.com/design/HbDLsjrG3iVDceRRa4rj2f/mi-proyecto-senati?node-id=0-1&p=f&t=bJnc4zzqmT0e6EGc-0

## logo de la empresa 
![Uploading image.png…](c1fd908606027b511e6eb44b219ef23c74bcd436)


## BASE DE DATOS 
```sql
create database senai_asistencia;
use senai_asistencia;


create table cargo (
id_cargo int auto_increment primary key,
nombre_cargo varchar(50) not null
)ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

create table empleado(
id_empleado int primary key auto_increment,
nombre varchar(100) not null,
apellido varchar(100) not null,
dni varchar(8) unique not null,
celular varchar(20),
correo varchar (100) not null unique,
id_cargo int not null,
fecha_registro timestamp default current_timestamp,
foreign key (id_cargo) references cargo(id_cargo)
)ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

create table usuario(
id_usuario int auto_increment primary key,
roles enum('admin', 'superadmin') default 'admin',
nombre_usuario varchar (150) not null,
clave varchar(250) not null
)ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

create table asistencia(
id_asistencia int auto_increment primary key,
fecha date not null,
hora_entrada timestamp default current_timestamp not null,
hora_salida timestamp default current_timestamp not null,
estado enum('asistio', 'tardanza', 'falto') default 'falto' not null,
id_empleado int not null,
foreign key (id_empleado) references empleado(id_empleado) ON DELETE CASCADE
)ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;



