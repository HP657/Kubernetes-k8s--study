# 명령어 정리

## Pod

- kubectl apply -f [yaml 파일]
    - YAML 파일에 정의된 리소스(Pod 등)를 생성하거나 수정하는 명령어

- kubectl get pods
    - 위와 동일 (pod의 복수형 표현)

- kubectl exec -it [pod 이름] -- bash
    - 실행 중인 Pod 내부 컨테이너에 접속 (bash 셸 실행)

- kubectl logs [pod 이름]
    - Pod의 로그 출력

- kubectl logs -f [pod 이름]
    - Pod 로그를 실시간 스트리밍으로 확인

- kubectl port-forward pod/[pod 이름] [로컬포트]:[컨테이너포트]
    - 로컬 PC 포트를 Pod 포트와 연결 (포트포워딩)

- kubectl delete pod [pod 이름]
    - 특정 Pod 삭제

- kubectl delete -f [yaml 파일]
    - YAML 파일로 생성한 리소스 삭제
