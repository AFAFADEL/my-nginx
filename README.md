# 1. إنشاء مجلد المشروع
mkdir my-nginx
cd my-nginx

# 2. إنشاء مجلد لملفات HTML
mkdir html

# 3. (تحرير الملفات) — index.html, nginx.conf, Dockerfile, deployment.yaml

# 4. بناء الصورة من Dockerfile
docker build -t afaadel/my-nginx:1.0 .

# 5. تشغيل الحاوية محليًا
docker run -d -p 8000:8000 afaadel/my-nginx:1.0

# 6. التحقق من عمل الصورة
docker ps

# 7. تسجيل الدخول إلى DockerHub
docker login

# 8. رفع الصورة إلى DockerHub
docker push afaadel/my-nginx:1.0

# 9. تشغيل التطبيق في Kubernetes
kubectl apply -f deployment.yaml

# 10. التحقق من حالة البود
kubectl get pods

# 11. عمل port-forward لاختبار التطبيق
kubectl port-forward deployment/my-nginx-deployment 8000:8000
