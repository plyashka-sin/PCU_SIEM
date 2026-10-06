## iptables 정책 재부팅 후 유지


재부팅 후에도 규칙을 영구적으로 유지하려면 운영체제(OS) 환경에 맞는 패키지나 서비스를 이용한다.  
Debian/Ubuntu 계열의 iptables-persistent 방식을 사용하였다.(kali linux)


Step 1. 패키지 설치
터미널을 열고 아래 명령어로 iptables-persistent 패키지를 설치합니다.

`sudo apt update`  
`sudo apt install iptables-persistent`  


Step 2. 방화벽 규칙 수정 및 추가 저장
패키지를 한 번 설치하고 나면, 향후 iptables 명령어로 규칙을 수정하거나 새로 추가했을 때 아래 명령어를 실행해야 재부팅 후에도 유지됩니다.

`sudo netfilter-persistent save`  


Step 3. (선택 사항) 제대로 부팅 시 켜지는지 확인
만약 재부팅 후에도 규칙이 돌아오지 않는다면, 해당 서비스가 활성화되어 있는지 확인해 보세요.

`sudo systemctl enable netfilter-persistent`  
`sudo systemctl start netfilter-persistent`
