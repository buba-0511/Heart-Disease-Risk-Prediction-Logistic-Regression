# Heart Disease Prediction Service (SageMaker)

| **Proyecto** | Clasificación de Riesgo Cardíaco mediante Regresión Logística |
|---|---|
| **Framework** | NumPy, AWS SageMaker SDK |
| **Infraestructura** | Amazon S3 + SageMaker Endpoint (ml.t2.medium) |
| **Dataset** | [Kaggle Heart Disease](https://www.kaggle.com/datasets/neurocipher/heartdisease) |

---

## 📋 Exercise Summary
Este repositorio contiene la implementación de un sistema de soporte de decisiones clínicas.
* **EDA:** Análisis de 303 pacientes y correlaciones de factores de riesgo.
* **Entrenamiento:** Regresión Logística con regularización L2 para optimizar la generalización.
* **Despliegue:** Inferencia en tiempo real mediante un Endpoint gestionado en AWS.

## 📊 Dataset Description
* **Muestra:** 303 pacientes (55% con presencia de enfermedad cardíaca).
* **Rangos Clave:** Edad (29-77 años), Colesterol (126-564 mg/dL), Presión Arterial (94-200 mmHg).
* **Variables:** 13 características clínicas incluyendo tipo de dolor torácico (cp) y frecuencia cardíaca máxima (thalach).

## 🚀 Deployment Evidence (Step 5)

> ### **Proceso Técnico**
> 1. **Exportación:** Pesos ($w$) y sesgo ($b$) guardados como arreglos `.npy`.
> 2. **Script de Inferencia:** `inference.py` cargado en el contenedor de SageMaker.
> 3. **Hosting:** Artefacto `model.tar.gz` alojado en Amazon S3.
> 4. **Endpoint:** Desplegado en instancia `ml.t2.medium`.

### **Evidencias Visuales**
1. **Status del Modelo:**  
   ![alt text](<Screenshot 2026-02-03 at 11.42.09 PM.png>)
2. **Configuración del Endpoint:**
   ![alt text](<Screenshot 2026-02-03 at 11.44.08 PM.png>)

### **Prueba de Invocación (Sample Output)**
```json
// Input: Age=60, Sex=1, CP=3, BP=145, Chol=300...
{
  "probability": 0.68,
  "risk_level": "High Risk",
  "latency": "45.2 ms"
}
```


### Autor: Santiago Diaz Rojas | buba-0511
