# PLATAFORMA-APUESTAS-DEPORTIVAS
Un proyecto creado con el mejor equipo.
# 🏆 Plataforma de Analítica de Datos Deportivos

> Un ecosistema de datos que modela el ciclo completo de las apuestas deportivas: usuarios, eventos, resultados y boletos —sencillos y combinados— con trazabilidad financiera de punta a punta.

![Python](https://img.shields.io/badge/Python-Datos-3776AB?logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0%2B-4479A1?logo=mysql&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-T--SQL-CC2927?logo=microsoftsqlserver&logoColor=white)
![Estado](https://img.shields.io/badge/estado-en_construcci%C3%B3n-yellow)

---

## 📖 ¿Qué es este proyecto?

Es una plataforma de **analítica de datos deportivos** que reproduce, sobre un modelo relacional, el comportamiento de un operador de apuestas: registra el dinero de cada usuario, publica eventos de múltiples disciplinas, captura los resultados y liquida los boletos según lo que ocurrió en la cancha.

El corazón del proyecto es un **dataset simulado y reproducible** pensado para análisis: diez meses de calendario deportivo, cientos de usuarios y miles de boletos con historial transaccional completo, listo para responder preguntas de negocio como qué deportes concentran el mayor volumen apostado, dónde se pierden más combinadas, cuál es la cuota promedio por disciplina o cómo evoluciona el saldo de un usuario a lo largo del tiempo.

---

## 🎯 Capacidades principales

- **Apuestas sencillas y combinadas.** Un boleto puede apoyarse en un solo partido o encadenar hasta 9 selecciones, incluso de disciplinas distintas.
- **Control de saldo con doble registro.** Cada movimiento queda en el historial de transacciones *y* reflejado en el saldo disponible del usuario, de modo que nunca se puede gastar lo que no existe.
- **Liquidación automática de combinadas.** Un boleto combinado solo se paga si **todas** sus selecciones aciertan; basta un fallo para declararlo perdido.
- **Catálogos deportivos reales.** Ligas de fútbol de clubes de varios países, torneos continentales, selecciones nacionales para el Mundial y la UEFA Nations League, ligas profesionales norteamericanas y Grand Slams de tenis con ramas masculina y femenina separadas. Cada torneo de selecciones compite con su propio plantel.
- **Calendario coherente.** Ningún equipo ni jugador disputa más de un encuentro el mismo día.
- **Simulación reproducible.** Con una semilla fija, dos personas obtienen exactamente los mismos datos; con otra semilla, cambia el escenario pero no las reglas.

---

## 📊 Alcance de los datos simulados

| Dimensión | Volumen |
|---|---|
| Usuarios | 700 |
| Eventos deportivos | 1,200 |
| Apuestas | 5,000 (sencillas y combinadas de 1 a 9 selecciones) |
| Disciplinas | Fútbol, béisbol, fútbol americano, baloncesto y tenis |
| Ventana histórica | Enero a noviembre de 2026 |

Los resultados se generan únicamente para los eventos ya disputados; los encuentros futuros quedan programados, con lo que el dataset se mantiene coherente en cualquier momento de la ejecución.

---

## 🧰 Stack y herramientas

- **Python** — motor de simulación y generación de datos.
- **MySQL 8.0+ / Microsoft SQL Server** — dos dialectos del mismo modelo relacional.
- **Modelado E-R** — diseño entidad-relación normalizado, con restricciones de integridad, claves candidatas y columnas calculadas.

---

## 🗂️ Estructura del repositorio

```text
Proyecto integrador/
├── README.md                     ← Esta carta de presentación
├── REGLAS_Y_NORMAS.md            ← Fuente de verdad de negocio y modelo relacional
├── databsae/
│   ├── 01_schem.sql              ← Versión inicial del esquema (legado)
│   ├── 02_schem_mysql.sql        ← Esquema vigente · MySQL 8.0+
│   └── 02_schem_sqlserver.sql    ← Esquema vigente · SQL Server
├── docs/                         ← Documentación de diseño y algoritmos
├── src/                          ← Código fuente del generador de datos
├── data/                         ← Datos y scripts generados
└── Esquema-sql/                  ← Diagramas y material del modelo E-R
```

---

## 📚 Documentación

Las reglas de negocio en **pesos colombianos (COP)**, el modelo relacional, las restricciones de cuotas y concurrencia, y los parámetros de volumen están documentados en:

➡️ **[REGLAS_Y_NORMAS.md](REGLAS_Y_NORMAS.md)**

Ese documento es la **única fuente de verdad** del proyecto. Este README es solo la puerta de entrada.

---

## 🚀 Cómo empezar

1. **Crear la base de datos.** Ejecuta `databsae/02_schem_mysql.sql` (MySQL 8.0+) o `databsae/02_schem_sqlserver.sql` (SQL Server). Ambos crean el esquema `apuestas_deportivas` con sus tablas, llaves y restricciones.
2. **Configurar la conexión.** Ajusta los parámetros de acceso a tu motor local en el bloque de configuración del generador.
3. **Ajustar los IDs de inicio.** Antes de generar datos, define el ID numérico inicial de cada tabla para no chocar con registros ya existentes en la base de datos compartida.
4. **Ejecutar el generador.** Primero en modo piloto, para validar consistencia con un lote pequeño; después con los volúmenes completos.
5. **Revisar los reportes.** El generador imprime el conteo por tabla, los rangos de IDs utilizados y el resultado de las validaciones de integridad.

---

## 🗺️ Roadmap

- [x] Definición de reglas de negocio y modelo relacional
- [x] Esquema implementado en MySQL y SQL Server
- [ ] Generador de datos en Python *(en diseño)*
- [ ] Validaciones de integridad referencial y consistencia de saldos
- [ ] Carga completa de los volúmenes de simulación
- [ ] Análisis exploratorio y visualización de resultados

---

## 👥 Autores

> _Espacio reservado para el equipo del Proyecto Integrador._

---

## 📄 Licencia

> _Espacio reservado para definir la licencia del repositorio._
