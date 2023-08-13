# kubernetes-study

dashboard 설정
https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/

```
# 대쉬보드 설치
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

# 계정 설정
kubectl apply -f @deploy/dashboard

# 토큰 취득
kubectl -n kubernetes-dashboard create token admin-user

# 접속
kubectl proxy

실행 후
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/workloads?namespace=default
링크에서 취득한 토큰으로 로그인
```

---

nginx 인그레스 컨트롤러 설치
참조 : https://kubernetes.github.io/ingress-nginx/

설치
`helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace`

---

그라파나 설치
https://github.com/prometheus-operator/kube-prometheus

추천 대시보드
https://grafana.com/grafana/dashboards/15758-kubernetes-views-namespaces/
