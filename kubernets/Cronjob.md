##### Job에 대한 termination 옵션
```
apiVersion: batch/v1   
kind: Job   
metadata:   
name: pi-with-timeout   
spec:   
**backoffLimit: 5**     
**activeDeadlineSeconds: 100**   
```

기본적으로 Job은 Pod가 실패하거나(restartPolicy=Never) 컨테이너가 오류로 종료(restartPolicy=OnFailure)하지 않는 한 중단 없이 실행됩니다. 이때 Job은 위에서 설명한 .spec.backoffLimit를 따릅니다.   
**.spec.backoffLimit**에 도달하면 작업이 실패한 것으로 표시되고 실행 중인 모든 포드가 종료됩니다.   
작업을 종료하는 또 다른 방법은 활성 기한을 설정하는 것입니다. 작업의 **.spec.activeDeadlineSeconds** 필드를 초 단위로 설정하면 됩니다.   
Job이 activeDeadlineSeconds에 도달하면 실행 중인 모든 Pod가 종료되고 Job 상태는 Failed with 이유: DeadlineExceeded가 됩니다.
