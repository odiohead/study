### Trivy
container image 취약점 점검하는 Tool

##### Trivy 설치 URL
https://aquasecurity.github.io/trivy/v0.50/getting-started/installation/


### Sysdig
##### Sysdig 설치방법
https://github.com/annulen/sysdig-wiki/blob/master/How-to-Install-Sysdig-for-Linux.md

포맷 예: sysdig -M 5 "[%evt.time],[%user.uid],[%proc.name]" container.id=xxxx


### Apparmor
Systemcall 제한을 통해 프로그램 동작을 제한
### Kube-bench
