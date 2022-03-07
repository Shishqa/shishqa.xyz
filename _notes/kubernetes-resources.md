---
---

# Resources

- **Limits** -- Верхняя граница ресурсов для Pod'а
- **Requests** -- Зарезервированные ресурсы для Pod'а (~системные требования)

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: frontend
spec:
  containers:
  - name: app
    image: images.my-company.example/app:v4
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
  - name: log-aggregator
    image: images.my-company.example/log-aggregator:v6
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
```

- `cpu: <N>m` значит, что $\frac{N}{1000}$ доля времени CPU будет отдана этому приложению

- **Важно понимать**, что kubernetes смотрит только на requests/limits при 
планированиии запуска сервисов. Нужно задавать эти параметры и для master-компонент!
