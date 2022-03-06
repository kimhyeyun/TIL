__22.03.06__

# DNS와 작동원리

### DNS란?
___
사전적 정의
> 도메인 네임 시스템 (Domain Name System, DNS)은 호스트의 도메인 이름을 호스트의 네트워크 주소로 바꾸거나 그 반대의 변환을 수행할 수 있도록 하기 위해 개발되었다.

자주 접하는 naver.com, google.com 모두 DNS을 가진 DN(Domain Name)이라고 할 수 있다.  
이들은 모두 문자열의 탈을 쓴 IP  

google.com ping 테스트
![img_18.png](img_18.png)

### DNS의 작동원리
___
![img_19.png](img_19.png)

1. 웹 브라우저에 www.naver.com을 입력하면 먼저 Local DNS에게 "www.naver.com"이라는 hostname에 대한 IP주소를 질의하여 Local DNS에 없으면 다른 DNS name 서버 정보를 받음 `(Root DNS 정보 전달 받음)`

#### Root DNS 란?
> `Root DNS(루트 네임서버)`는 인터넷의 도메인 네임 시스템의 루트 존  
> 루트 존의 레코드의 요청에 직접 응답하고 적절한 최상위 도메인에 대해 권한이 있는 네임 서버 목록을 반환함으로써 다른 요청에 응답함  
> 전 세계에 961개의 루트 DNS가 운영되고 있음

2. Root DNS 서버에 "www.naver.com" 질의
3. Root DNS 서버로부터 "com 도메인"을 관리하는 `TLD(Top-Level Domain)` 이름 서버 정보 전달 받음
> 여기서 TLD는 .com을 관리하는 서버

4. TLD에 "www.naver.com" 질의
5. TLD에 "naver.com" 관리하는 DNS 정보 전달
6. "naver.com" 도메인을 관리하는 DNS 서버에 "www.naver.com" 호스트네임에 대한 IP 주소 질의
7. Local DNS 서버에게 www.naver.com에 대한 IP주소 (222.122.195.6) 응답
8. Local DNS는 www.naver.com에 대한 IP 주소를 캐싱하고 IP 주소 정보 전달

[ TLD의 구조 ]
![img_20.png](img_20.png)