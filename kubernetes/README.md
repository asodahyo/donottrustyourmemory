# Start

## About Helm Chart

- Helm으로 구동한 deployments 목록

```bash
    # list
    helm list --all --tiller-namespace [namespace-name]
    helm list --all --tiller-namespace devai-cluster
```

- Helm으로 구동한 deployments 삭제  
🚨 del 한 실행 했을 경우 deployment 가 delete status 와 함께 남아 있음 purge를 해야함

```bash
    # delete
    helm del --tiller-namespace [namespace-name] [pod-name]
    helm del --tiller-namespace devai-cluster jupyterhub-py37-mmocr-1-1-7-6
```

``` bash
    # purge
    helm del --purge [pod-name] --tiller-namespace [namespace-name] 
    helm del --purge --tiller-namespace devai-cluster jupyterhub-py37-mmocr-1-1-7-6 
```

## Using for monitoring,  debuging and etc

```bash
    # get all pod list
    kubectl get pod --all-namespaces

    # describe po, cm etc
    kubectl describe po [pod-name] -n [namespace-name]

    # po yaml 파일
    kubectl get po [pod-name] -n [namespace-name] -o yaml
    
    # get pod logs
    kubectl logs [pod-name] -n [namespace-name]

    # get specific container log
    kubectl logs [pod-name] -n [namespace-name] -c [container-name]

    # delete pod evicted
    kubectl delete pod [pod-name] -n [namespace-name]
    kubectl get pod -n devai-cluster | grep Evicted | awk '{print $1}' | xargs kubectl delete pod -n devai-cluster    
```
