# Supervisor difuso multivariable para la gestión térmica de una batería de flujo redox de vanadio

Implementación en Python de un supervisor basado en lógica difusa (inferencia de tipo Mamdani, `scikit-fuzzy`) que calcula tres consignas normalizadas — actuador de acondicionamiento térmico, bomba de recirculación y potencia de carga/descarga — a partir de cuatro entradas: temperatura del electrolito, temperatura ambiente, estado de carga (SoC) y una señal normalizada del estado de la red.

El sistema se evalúa únicamente mediante simulación: no incorpora datos experimentales de una batería real ni un modelo dinámico de planta. Las funciones de pertenencia, los umbrales y la tabla de decisión son hipótesis de diseño que deben calibrarse para una batería concreta antes de cualquier aplicación experimental.

## Contenido

El notebook [`supervisor_difuso_VRFB.ipynb`](./supervisor_difuso_VRFB.ipynb) incluye, en orden:

1. Configuración
2. Variables de entrada (antecedentes)
3. Riesgo térmico efectivo
4. Variables de salida (consecuentes)
5. Base de reglas (27 decisiones → 81 reglas difusas)
6. Funciones de pertenencia
7. Escenarios de evaluación
8. Agregación y desfusificación de un caso
9. Verificación de cobertura
10. Superficies estáticas
11. Efecto de la temperatura ambiente
12. Comprobaciones de consistencia
13. Trayectoria sintética de 24 horas
14. Comparación con controladores por umbrales
15. Contraste de los umbrales con literatura publicada
16. Traducción ilustrativa a magnitudes físicas

## Requisitos

```
python>=3.10
numpy
scipy
pandas
matplotlib
scikit-fuzzy==0.5.0
```

## Ejecución

```
pip install numpy scipy pandas matplotlib scikit-fuzzy==0.5.0
jupyter nbconvert --to notebook --execute supervisor_difuso_VRFB.ipynb
```

## Licencia

MIT
