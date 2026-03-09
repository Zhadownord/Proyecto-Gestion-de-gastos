# Sistema de gestión de gastos
Un gestor de gastos tiene como propósito principal ayudarte a organizar, controlar y optimizar tus finanzas personales o empresariales-
# 📊 Gestor de Gastos en Solana (Anchor)

Este proyecto implementa un **CRUD de gastos** sobre la blockchain de Solana utilizando el framework **Anchor**.  
Permite crear una cuenta de gastos asociada a un usuario y realizar operaciones de **crear, consultar, actualizar y eliminar** gastos.

*Registro ordenado: Anotar ingresos y egresos de manera sistemática.
*Clasificación: Agrupar gastos por categorías (alimentación, transporte, ocio, vivienda, etc.).
*Control del presupuesto: Comparar lo que planeaste gastar con lo que realmente gastaste.
*Detección de fugas de dinero: Identificar en qué áreas se gasta más de lo necesario.
*Proyección financiera: Ayudar a planear metas de ahorro o inversión.
*Toma de decisiones: Brindar información clara para reducir gastos innecesarios y mejorar hábitos financieros.

El gestor perimitirá lo siguiente , basandose en el modelo CRUD:

  Create → Registrar un nuevo gasto.

  Read → Consultar gastos guardados.

  Update → Modificar un gasto existente.

  Delete → Eliminar un gasto.


---

## 🚀 Funcionalidades

- **Crear cuenta**: Inicializa una cuenta `CuentaGastos` asociada a un `owner`.
- **Añadir gasto**: Inserta un gasto con descripción, monto y fecha.
- **Consultar gastos**: Muestra todos los gastos almacenados en la cuenta.
- **Actualizar gasto**: Modifica un gasto existente por índice.
- **Eliminar gasto**: Elimina un gasto del vector por índice.

---


## 📂 Definiciones principales

### Cuenta principal
```rust
#[account]
#[derive(InitSpace)]
pub struct CuentaGastos {
    owner: Pubkey,              // Dueño de la cuenta
    #[max_len(50)]
    gasto: Vec<Gasto>,          // Lista de gastos (máx. 50)
}
