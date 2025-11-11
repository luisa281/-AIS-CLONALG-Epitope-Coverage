# -AIS-CLONALG-Epitope-Coverage
Implementación del algoritmo CLONALG para cobertura de epítopos - Grupo 8
readme # -AIS-CLONALG-Epitope-Coverage
Implementación del algoritmo Artificial Immune System (AIS) para optimización y selección de péptidos. Sistema bioinspirado.

# Google Colab: abrir el enlace notebook https://colab.research.google.com/drive/1hrnP5Ca0LAchAWpxhG07m-in_TXm8naS?usp=sharing ejecute todas las celdas en orden, los resultados se  generaran autamaticamente.

# Entorno Local
# https://colab.research.google.com/drive/1hrnP5Ca0LAchAWpxhG07m-in_TXm8naS?usp=sharing
cd Grupo8_AIS_Epitopos
pip install numpy matplotlib
jupyter notebook notebooks/Grupo8_AIS_Cobertura_Epitopos.ipynb

# Prerequisitos 
python >= 3.8
numpy >= 2.0.2
matplotlib >= 3.10.0

 # Resultados Obtenidos
 Métricas de Rendimiento
Mejor fitness alcanzado: 23.40
Media del fitness: 23.07 ± 0.47
Convergencia: Alcanzada en 150 iteraciones
Semilla principal: 6

# Cobertura del Antígeno
Longitud del antígeno: 600 aminoácidos
Péptidos posibles (k=8): 591
Cobertura única alcanzada: 24/600 posiciones (4.00%)
Cobertura total (con solapamientos): 30 posiciones
Porcentaje de cobertura: 4.00%

 # Péptidos Seleccionados
Péptidos seleccionados: 4.96 de 591 posibles
Tasa de selección: 0.84%
Eficiencia de cobertura: 0.8000
Cobertura promedio por péptido: 6.05 posiciones
Eficiencia relativa: 60.5%

# Análisis de Solapamientos
Posiciones con solapamiento: 6
Máximo solapamiento: 2.0 péptidos en una posición
Cobertura única (ideal): 20 posiciones (3.3%)
Solapamiento moderado (2-3): 2 posiciones (0.3%)

# Configuración principal
D = 15                   Dimensión del problema
N = 40                   Tamaño de población
beta = 2                 Factor de clonación
d_rate = 0.1              Tasa de diversificación
T = 150                    Iteraciones
SEED = 6                   Semilla para reproducibilidad

# Función de fitness implementada
def fitness(x, seq=antigen_seq, k=10, gamma=0.1):
    """
    Calcula el fitness basado en:
    - Cobertura de epítopos del antígeno
    - Penalización por solapamientos redundantes
    - Eficiencia en la selección de péptidos
    """
    return score_final
		# Función fitness 

# Flujo de Trabajo
Carga de Datos: Antígeno de 600 aminoácidos desde archivo FASTA
Generación de Péptidos: 591 péptidos posibles de longitud k=8
Ejecución de CLONALG: 150 iteraciones con semilla controlada
Evaluación: Cálculo de métricas de cobertura y eficiencia
Visualización: Gráficas de convergencia y distribución espacial

# Evaluación con Múltiples Semillas
Semilla 6: Fitness = 22.40
Semilla 42: Fitness = 23.40
Semilla 123: Fitness = 23.40
Media del fitness: 23.07 ± 0.47


# Resultados visuales 
<img width="455" height="269" alt="image" src="https://github.com/user-attachments/assets/126d41dc-ee04-4725-883c-20a1768fad4c" />
<img width="776" height="336" alt="image" src="https://github.com/user-attachments/assets/9c15ba0b-f959-435f-bf47-30f22215371f" />
<img width="446" height="286" alt="image" src="https://github.com/user-attachments/assets/d6f44c75-c237-4167-8eeb-374bbb84e643" />
`
# Comparativos
Métrica	   CLONALG	Solución Aleatoria	   Solución Completa
Fitness	23.40	         368.70	                       69.00
Cobertura	4.0%	        99.0%	                       99.7%
Péptidos	4.96	        288	                          591
Eficiencia	33.9%     	-93.7%	                    100%

# Análisis de Brechas
Número de brechas sin cobertura: 1
Brecha más larga: 576 posiciones
Brecha promedio: 576.0 posiciones
Porcentaje del antígeno en brechas: 96.0%
Interpretación: El algoritmo demostró alta eficiencia al identificar un subconjunto mínimo de péptidos

# Significado Biológico: Esto simula la capacidad del sistema inmune de reconocer patógenos con un número limitado de anticuerpos

2. Reproducibilidad Robusta. Media de fitness = 23.07 ± 0.47 across 3 semillas diferentes. Resultados predecibles y confiables para aplicaciones prácticas
3. Solapamientos. Solo 6 posiciones con solapamiento, máximo 2 péptidos por posición
Significado Biológico: Evita el "desperdicio" de recursos en reconocer las mismas regiones múltiples veces.
Interpretación: El algoritmo demostró alta eficiencia al identificar un subconjunto mínimo de péptidos

Significado Biológico: Esto simula la capacidad del sistema inmune de reconocer patógenos con un número limitado de anticuerpos

El análisis de los resultados obtenidos mediante la implementación del algoritmo CLONALG muestra un desempeño con matices significativos. Desde una perspectiva computacional, el algoritmo demostró una eficiencia notable en la optimización de recursos, seleccionando únicamente 4.96 péptidos de los 591 disponibles (0.84% de utilización). La reproducibilidad robusta, con una variabilidad mínima del fitness (23.07 ± 0.47) across múltiples semillas, confirma la estabilidad del enfoque y su adecuación para aplicaciones que requieren consistencia en resultados. Sin embargo, el análisis espacial de la cobertura revela una limitación: la concentración del 100% de los péptidos seleccionados en el segmento inicial del antígeno (posiciones 0-120), generando una brecha de 576 aminoácidos sin cobertura (96% del antígeno), lo que sugiere un desbalance en la exploración del espacio de soluciones y posiblemente una penalización excesiva en la función fitness que inhibe la diversificación regional. Biológicamente, si bien el manejo de solapamientos fue efectivo (solo 6 posiciones con redundancia), la cobertura global del 4% resulta insuficiente para una respuesta inmune comprehensiva, indicando que la optimización puramente geométrica, no captura la complejidad immunológica requerida para aplicaciones prácticas en diseño de vacunas. En conclusión, mientras el algoritmo establece un marco sólido para problemas de optimización combinatoria, su transferencia a dominios biológicos reales necesitaría incorporar capas adicionales de información estructural y funcional del antígeno para alcanzar relevancia traslacional.