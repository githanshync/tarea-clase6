🚀 Kubernetes - Clase 6: Introducción
Este repositorio contiene la solución a la tarea de casa del curso Docker & Kubernetes BUSA.

📌 Objetivo de la tarea
Desplegar una aplicación web en Kubernetes.

Usar un Deployment con 3 réplicas.

Exponer la aplicación mediante un Service tipo NodePort en el puerto 30200.

Documentar el proceso con capturas y pruebas de escalado/auto-healing.

🛠️ Archivos principales
deployment.yaml → define el Deployment con 3 réplicas de Nginx.

service.yaml → expone la aplicación vía NodePort.

screenshots/ → evidencia del despliegue, escalado y acceso web.

Pasos para ejecutar
Clonar este repositorio:

bash
git clone https://github.com/<tu-usuario>/<tu-repo>.git
cd <tu-repo>

Aplicar los manifiestos:

bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
Verificar recursos:

bash
kubectl get all
Acceder a la aplicación:

bash
minikube service webapp-service --url
O abrir en navegador: http://<IP>:30200

🔄 Escalado y Auto-healing
Escalar a 5 réplicas:

bash
kubectl scale deployment webapp-deployment --replicas=5
kubectl get pods
Eliminar un pod y observar cómo Kubernetes lo recrea:

bash
kubectl delete pod <nombre-pod>
kubectl get pods -w
📸 Evidencias
screenshots/resources.png → salida de kubectl get all.

screenshots/webapp.png → aplicación corriendo en navegador.

screenshots/scaling.png → escalado a 5 réplicas.

screenshots/autohealing.png → recreación automática de un pod eliminado.
✅ Conclusiones
Se desplegó correctamente una aplicación web en Kubernetes con 3 réplicas.

El Service tipo NodePort permitió acceso externo en el puerto 30200.

Se comprobó el escalado manual y el auto-healing de pods.
