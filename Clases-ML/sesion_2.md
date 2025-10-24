## Notas sobre Learning Curve en ML learning_curve

> **Notas sobre Learning Curve en ML**
>
> - Permite observar cómo cambia el desempeño (train y validación) al aumentar el tamaño del conjunto de entrenamiento.
> - Ayuda a detectar **underfitting** (ambas curvas bajas y cercanas).
> - Ayuda a detectar **overfitting** (curva de train alta, validación más baja con brecha grande).
> - Permite evaluar si más datos mejorarían el modelo (curva de validación aún sube y no se estabiliza).
> - Facilita juzgar si el problema es falta de datos o exceso/deficiencia de complejidad del modelo.
> - Permite comparar modelos/pipelines en términos de estabilidad y necesidad de regularización.
> - Ayuda a estimar el punto de rendimientos decrecientes (cuando añadir muestras ya casi no mejora el desempeño).
>
> **Cómo leerla:**
>
> - **Eje X:** número de ejemplos usados para entrenar en cada punto.
> - **Curva Train:** accuracy (u otra métrica) promedio en los folds sobre los datos de entrenamiento. Normal que baje ligeramente al crecer el tamaño.
> - **Curva CV (validación):** desempeño en datos no vistos (folds de validación). Debe subir, luego estabilizarse (plateau).
>
> **Patrones clave:**
>
> - **Overfitting:** Train alta, CV claramente menor con brecha amplia que no se cierra.
> - **Underfitting:** Ambas bajas y cercanas.
> - **Buen ajuste:** Ambas altas y con brecha pequeña.
> - **Más datos útiles:** CV aún sube y no llega a plateau.
> - **Rendimientos decrecientes:** CV plana; agregar datos aporta poco.
>
> **Bandas de sombra (desviación):**
>
> - Anchas en tamaños pequeños (alta varianza).
> - Se estrechan al crecer (modelo más estable).
>
> **Acciones:**
>
> - Gap grande: reducir complejidad / más regularización.
> - Ambas bajas: aumentar complejidad / mejores features.
> - CV ascendente: priorizar recolectar más datos.
> - Plateau con buen gap: afinar hiperparámetros finos o probar otro algoritmo.