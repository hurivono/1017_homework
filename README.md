# 1017_homework
클테코 2기 241017 8일차 과제

1 K3S에 ArgoCD를 Helm으로 설치하기 (Network Policy 주의 하기 )
2.GitHub에 Project를 하나 생성한다.
   2.1 해당 프로젝트에 service.yaml , deployment.yaml를 생성한다. secret이 있으면 secret.yaml도 생성
3.Argocd 로 배포
   3.1 Argocd 에서 Repository 에 Github Repository를 추가한다.
   3.2 Argocd에 New App를 구성하고 위에서 구성한 repository로 app를 생성 ( Auto로 설정 하지 않는다 )
   3.3 Synchronized 를 하여 service.yaml , deployment.yaml , secret.yaml를 동기화 하여 가져와서 배포 한다.




순서
helm repo add로 argocd repo 추가
helm install로 namespace = argocd 만들고 argocd 설치와 동시에 실행.
github에 샘플 service.yaml, deployment.yaml, secret.yaml만들기.
port forwarding 하여 local에서 argocd server에 들어갈 수 있도록 만듬. (내부는 443 외부는 8080)
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo 명령어로 임시 비밀번호 확인
localhost:8080에 접속하여 비번 설정 
이후 container안에서 argocd repo add ~ 하여 원하는 repo를 argocd에 추가.


https://wlsdn3004.tistory.com/37 정리 굳
