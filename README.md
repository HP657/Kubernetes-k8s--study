# 명령어 정리

## Pod

### 1

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
  
- kubectl describe pods [pod 이름]
  - pod가 생성되면서 발생한 이벤트 로그 출력 (디버깅 할떄 많이 쓰임)
  
- kubectl logs [pod 이름]
  - pod에서 발생한 로그 출력 (디버깅 할떄 많이 쓰임)

- kubectl logs [pod 이름]
  - pod에서 발생한 로그 출력 (디버깅 할떄 많이 쓰임)

### 2
- 이미지 풀 정책 (Image Pull Policy)
  - Always 로컬 이미지 가져오지 않고 레지스트리(DockerHup이나 외부의 이미지)를 가져오게됨 
  - IfNotPresent 로컬이미지를 가져오고 없다면 레지스트리에서 가져옴 
  - Never 로컬에서만 이미지 가져옴

- image에 latest거나 명시하지 않으면 Always로 설정 
- latest가 아니면 IfNotPresent로 설정

### 3 
- pod 내용 복사를 통한 pod 수평적 확장 진행

### 4
- 디플로이먼트(Deployment)
  - pod를 묶음으로 쉽게 관리하는 기능
  - pod를 자동 배포
  - pod의 수를 지정하는 대로 여러 파드를 쉽게 생성
  - pod의 비정상적인 종료가 되면 새로운 파드를 생성해 파드 수를 유지
  - 일괄된 파드를 일시중지, 삭제, 업데이트를 한번에 가능

- 디플로이먼트가 레플리카셋(ReplicaSet)을 관리하고, 레플리카셋이 여러 파드를 관리하는 구조
  - 레플리카(Replica): 복제본
  - 레플리카셋: 복제본끼리의 묶음