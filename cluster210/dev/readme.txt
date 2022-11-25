// 네임스페이스에 대한 기본 CPU 요청량과 상한 구성
k get LimitRange -A

// Node별 자원 사용량 확인
kubectl top node
kubectl top node --show-capacity=true

// pod별 자원 사용량 확인
kubectl top pod

// 모든 pod별 자원 리소스 설정 확인
kubectl get po -A -o custom-columns="Name:metadata.name,CPU-Requet:spec.containers[*].resources.requests.cpu,CPU-limit:spec.containers[*].resources.limits.cpu,MEM-Request:spec.containers[*].resources.requests.memory,MEM-limit:spec.containers[*].resources.limits.memory"

// NameSpace별 resourcequota 설정 확인
k get resourcequota -A

// Node별 리소스 확인
k describe node worker1