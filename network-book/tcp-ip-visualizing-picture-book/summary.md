## TCP/IP가 보이는 그림책:국내 최초 그림으로 배우는 TCP/IP 입문서 정리
### 머릿말
TCP/IP(Transmission Control Protocol/Internet Protocol) : 인터넷을 사용할 수 있도록 컴퓨터 네트워크를 구현하는 통신 프로토콜군
- 인터넷에서 채택하고 있는 통신 프로토콜
### 0장 : TCP/IP 맛보기
컴퓨터 네트워크 : 컴퓨터끼리 데이터를 주고받을 수 있는 상태로 되어있는 것
- 케이블(구리선, 광섬유 케이블), 적외선, 전파 등 매개로 사용
규모에 따른 분류
- LAN(Local Area Network)
  - 비교적 좁은 공간에 있는 기기끼리 연결한 네트워크
  - 대학, 연구소, 기업 내 등
  - 주로 구리선을 짜 넣은 LAN 케이블 이용
- WAN(Wide Area Network)
  - 지리적으로 떨어져 있는 기기끼리 연결한 비교적 대규모의 네트워크
  - 회사의 지점간 등
  - 광섬유 케이블, 공중망(전화 회선) 등 사용
- 인터넷
  - 여러 개의 LAN이나 WAN을 연결한 전 세계 규모의 네트워크
  - 컴퓨터, 휴대 전화, 소형 휴대 단말기와도 데이터 서로 주고 받을 수 있음.
- 인트라넷
  - 인터넷 기술을 사용한 지역 한정판 LAN
  - 특정 회사나 지역 내의 컴퓨터끼리만 정보 공개 및 데이터 주고 받음.
  - 어떤 보안 대책으로 외부 컴퓨터에서 접근 불가하게 조치
### 1장 : TCP/IP 개요
TCP/IP : 엄밀히는 TCP와 IP라는 프로토콜이지만, 일반적으로는 인터넷에서 사용되는 통신 프로토콜군을 총칭
- 전 세계 공통 통신 프로토콜로 채택
데이터 송수신 과정 : 데이터를 디지털 신호로 변환 -> 보낼 곳에 전달 -> 디지털 신호를 데이터로 재변환
- 위의 과정을 5단계로 분할 : 사용자에 가까운 순서대로 애플리케이션, 트랜스포트, 네트워크, 데이터 링크, 물리 계층
패킷 통신 : 패킷을 이용한 통신 방법
- TCP/IP는 '데이터를 일정한 크기로 분할해서 보낸다'
- 패킷 : 작게 나눠진 데이터 하나
  - 보통 1024bit
  - 데이터, 데이터의 목적지, 주소, 제어 부호 등 포함
- 하나의 회선을 사용하여 여러 데이터를 거의 동시에 송수신 가능
- 통신 중 데이터의 일부가 손상되어도 해당하는 부분만 다시 보내면 됨
통신 프로토콜 : 컴퓨터 간 데이터를 주고 받기 위한 공통된 구조를 만들면 각각의 차이에 관계 없이 데이터 송수신 가능
- 송신측과 수신측의 컴퓨터가 미리 정해놓은 공통된 매뉴얼
#### TCP/IP의 구조
각 층의 역할과 구조
- 애플리케이션 계층
  - 애플리케이션에 맞춰 통신을 수행할 수 있도록 함
  - HTTP, SMTP, POP3, FTP, TELNET, NNTP, RCP ...
- 트랜스포트 계층
  - 송신된 데이터를 수신측 애플리케이션에 확실히 전달하기 위해 작동
  - TCP / UDP
- 네트워크 계층
  - 수신측 컴퓨터까지 데이터를 전달하기 위해 작동
  - 전달된 데이터가 손상됐는지, 수신측이 잘 받았는지에 관여하지 않음
  - IP
- 데이터 링크 계층
  - 네트워크에 직접 연결된 기기 간을 전송할 수 있도록 만듦.
  - 네트워크 계층과 물리 계층 간의 차이를 완전히 흡수하기 위한 다양한 프로토콜 존재
  - Ethernet, FDDI, ATM, PPP, PPPoE ...
- 물리 계층
  - 데이터를 신호로, 신호를 데이터로 변환
  - 변환방법은 통신 매체에 의존해 특정 프로토콜이 정해져 있지 않음
TCP/IP 프로토콜군 : 5계층 전체 나타내는 표현<br>
<br>

#### 계층간 연락 방법 <br>

송신측의 각 계층에서 수신측의 동일한 계층에서 필요한 정보를 공통된 서식으로 데이터에 추가해 나감
- 앞에는 헤더, 뒤에는 트레일러 추가
- 캡슐화 : 데이터와 정보를 하나로 묶어서 다루는 것
- 동일한 계층에서만 사용
- 상위 계층에서 추가된 헤더는 캡슐화되어 있으므로 다른 계층에서는 볼 수 없다.

### 2장 : 통신 서비스와 프로토콜
서버 : 서비스를 제공하는 기능을 갖고 있는 프로그램 <br>
클라이언트 : 서비스를 받는 기능을 갖고 있는 프로그램 <br>
애플리케이션 프로토콜 : 서버와 클라이언트 간에 수행되는 서비스 고유의 주고받기 약속

#### 서버와 클라이언트
서버 : 서비스를 제공하는 측 <br>
- 서비스를 제공하는 기능을 갖고 있는 프로그램
- 서버에 데이터를 보내는 것을 업로드
클라이언트 : 서비스를 받는 측
- 서비스를 요청
- 사용자가 알 수 있는 형태로 표시하는 기능을 갖고 있는 프로그램
- 서버로부터 데이터를 받는 것을 다운로드
1대의 컴퓨터가 두 가지 이상의 서버를 담당할 수도 있음.
#### 데이터의 위치
URL(Uniform Resource Locator)의 구조 <br>
"http://www.cyber.co.kr:80/picbook/gabsoon/index.html" 
- "http" : 스킴명(scheme)
  - 서비스의 종류를 나타냄
  - http : WWW, https : www(SSL/TLS), ftp : 파일전송, mailto : 전자메일, telnet : 원격 로그인, file : 로컬 파일
- "WWW.cyber.co.kr" : 도메인
  - 서버를 나타냄. 숫자인 경우도 있음
  - WWW : 서버명, WWW 서버에 많이 사용
  - cyber : 조직명, 조직의 고유한 문자열
  - co : 조직 속성, co는 교육 기관이나 기업 등 조직의 속성을 나타내는 문자열, 나라마다 다름
  - kr : 국가 코드, 나라마다 정해진 코드
  - gTLD(general Top Level Domain)과 ccTLD
    - gTLD : com, org 처럼 나라에 관계 없이 사용할 수 있는 조직 속성, 국가 코드 불필요
      - 주요 gTLD : com, org, net, biz, info
      - 필수적으로 의미에 맞추어야 하는 건 아님.
    - ccTLD : 국내에서만 사용 가능한 조직 속성('co' 등)
- "80" : 포트 번호
  - 애플리케이션 프로토콜을 식별하는 번호
  - 스킴명에 의해 판단할 수 있으므로 생략가능
- "picbook" : 경로
  - 서버 내에서 파일의 주소
- "index.html" : 파일명
  - 파일명은 생략할 수도 있음
  - 
#### WWW

- WWW 서버 : 하이퍼텍스트나 이미지, 음성, 파일 등을 보관하고, WWW 브라우저의 요청에 맞게 전달<br>
- WWW 브라우저 : WWW 서버로부터 다운로드한 파일을 표시

#### 전자메일
송신자 -- SMTP -> 메일 서버 A -- SMTP -> 메일 서버 B -- POP -> 수신자(POP 서버에 메일 확인 요청 후 수신)
- SMTP(Simple Mail Transfer Protocol) 서버 : SMTP를 사용하여 메일 전송을 담당하는 프로그램
  - 받는 기능도 있긴 함, 잘 사용 안 하고 주로 POP가 
- POP(Post Office Protocol) 서버 : POP를 사용하여 클라이언트에게 메일 제공을 담당하는 프로그램
- 일반적으로 한 대의 컴퓨터가 SMTP 서버와 POP 서버 겸임

#### 파일 전송
- FTP 서버 : 특정 전송 공간이 있음. 서버 내 전부가 전송 공간일 수도
- 통신이 허용된 클라이언트만 데이터 전송 가능
- FTPS(File Transfer Protocol over SSL/TLS), SFTP(SSH File Transfer Protocol) 으로 암호화해서 전송 권장
- Anonymour FTP : 누구나 전송(보통은 다운로드 한정)할 수 있는 FTP 서비스
#### 원격 로그인
- 대표적인 서비스로 텔넷(TELNET)
- 텔넷 클라이언트
  - telnet 명령이나 테라 텀(Tera Term)이라는 애플리케이션
  - 기본적으로 CUI(Character User Interface) 환경 에서 작동
  - 클라이언트의 키보드로 입력한 명령이 서버로 보내져서 처리된 결과를 클라이언트로 반환
  - TELNET 프로토콜 기초로 수행
  - 서버 측의 OS에 맞춘 명령 사용
SSH(Secure Shell)
- 다른 컴퓨터에 로그인할 때 통신을 암호화하는 프로토콜
- 텔넷에는 암호화 기능이 없어서 도청 위험
- 패킷이 탈취돼도 통신 내용 쉽게 해독할 수 없음
데스크톱 공유
- 네트워크 상의 다른 컴퓨터의 데스크톱 환경에 접속해 파일이나 애플리케이션을 조작하는 기술
- 원격 데스크톱 연결 조건
  - 전원이 켜져 있다
  - 네트워크에 연결돼 있다
  - 원격 데스크톱 기능이 활성화 되어 있고 액세스를 허가했다.
- 통신 프로토콜은 RDP(remote Desktop Protocol) 사용
#### 파일 공유
파일이나 애플리케이션 등을 다른 사용자와 함께 사용할 수 있도록 하는 통신 서비스
- 프로토콜은 OS에 따라 달라짐
- UNIX와 Windows 사이에 공유하는 경우 UNIX는 Samba라는 애플리케이션 필요, 같은 OS끼린 필요 없음
- 클라이언트가 수행한 조작을 서버로 실시간으로 보냄
- 프로토콜 : Windows의 경우 SMB(Server Message Block), CIFS(common Interface File System), UNIX의 경우 NFS(Network File System) 등 이용
#### 기타 서비스
IP 전화나 인스턴트 메신저 등 통신 서비스
- VoIP(Voice over IP) : 상대의 전화번호나 음성 데이터를 패킷화시켜 전달하는 기술
- 이 기술을 사용해 인터넷이나 독자적인 네트워크에서 통신하는 전화 서비스
- 회선을 독점하지 않음
- SIP(session Initiation Protocol) : 상대에게 다이얼을 돌려서 호출하기까지
- RTP(Real-time Transport Protocol), RTCP(RTP Control Protocol) : 실제로 대화 시작된 후
인스턴트메신저(IM)
- 미리 등록한 다른 클라이언트(멤버)가 통신할 수 있는 상태인지 아닌지 확인하여 그 상태를 표시하고 실시간으로 통신할 수 있는 서비스
- 끊임없이 멤버의 상태를 확인
  - 자리비움, 오프랑니, 온라인 등
- 기능마다 개별 프로토콜 사용
- 주요 클라이언트 : Skype, LINE 등
- 프로토콜이 통일되어 있지 않음 -> 다른 클라이언트끼리 통신 불가
### 3장 : 애플리케이션 계층
애플리케이션 계층
- 역할 : '통신 서비스를 실현하는 것'
- 애플리케이션 프로토콜
프로토콜 + 편리한 구조
- 프로토콜과 조합해서 사용함으로써 서비스를 편리하게 하는 구조 소개
  - SMTP, POP 는 텍스트만 취급
  - MIME(Multipurpose Internet Mail Extensions)를 통해 여러 형식의 정보를 SMTP에서 다룰 수 있는 형태로 변환
  - MIME 타입 : text, application, image, audio, video 등 7개
### 애플리케이션 계층의 역할
애플리케이션 계층의 역할
- 컴퓨터끼리의 송수신을 사용자가 이용할 수 있는 '통신 서비스'의 형태로 만드는 것
- 사용자가 해석할 수 있도록 만듦
- 통신 서비스의 실현
- 애플리케이션 프로토콜 : 통신 서비스를 하는 서버와 클라이언트가 주고받기로 정한 프로토콜
#### 애플리케이션 헤더
애플리케이션 계층에서 추가되는 헤더
- 요청과 응답에 관한 정보
- 프로토콜에 따라 헤더 사용하지 않는 경우도 있음
- 프토로콜에 따라 텍스트 기반(영문자, 숫자만) 또는 바이너리 기반으로 작성
- 클라이언트가 서버에 서비스 요청 시 구체적 데이터 주고받지 않고 연락만 취할 때는 데이터 부분이 비어 있는 상태로 보냄
#### HTTP 프로토콜
HTTP 프로토콜 : 하나의 요청에 대해 하나의 응답 반환하는 아주 간단한 프로토콜
- 페이지를 구성하는 파일 수만큼 이 작업 반복
- 요청(request)과 응답(response)이라는 두 종류 패킷 사용해 텍스트 형식으로 주고받기 수행.
요청 패킷
- 클라이언트가 서버에게 보내는 패킷
- 헤더 : GET /home/index.html HTTP/1.1
  - 메소드 : 요청의 종류
  - GET, PUT 등..
- 요청 헤더 : 
  > Host : www.cyber.co.kr:443
  > Accept : text/html,application/xhtml+xml,application/xml;q=0.9,image/
  > webp,image/apng,*/*;q=0.8
  > Upgrade-Insecure-Requests: 1
  > User-Agent: Mozilla/5.0 (Macintosh: Intel Mac OS X 10_14_4)
  > AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.86
  > Safari/537.86
  - 서버에 전달하는 클라이언트의 정보(처리 가능한 파일 종류, 문자 코드, 언어)
  - 항목명과 정보는 콜론(:)으로 구분
- 공백 줄 : 헤더와 본문의 경계
- 본문 : 요청 시 필요한 데이터
- 메소드가 GET인 경우 비어 있음
응답 패킷
- 서버가 클라이언트에게 보내는 패킷
- 상태 줄 : HTTP/1.1 200 OK
  - 클라리언트의 요청에 대한 처리 결과. 정상적으로 처리한 경우 200번대
- 응답 헤더 :
  > Cache-Control: no-store, no-cache, must-
  > revalidate, post-check=0, pre-check=0
  > Connection: Keep-Alive Content-Type: text/html; charset=euc-kr
  > Date: Fri, 29 Mar 2019 00:30:57 GMT
  > Expires: Thu, 19 Nov 1981 08:52:00 GMT
  > Keep-Alive: timeout=5 max=100
  > Last-Modified: Fri, 29 Mar 2019 00:30:57 GMT
  - 클라이언트에게 전달할 데이터에 관한 정보
  - 공백 줄 : 헤더와 본문의 경계
  - 본문 : 클라이엉ㄴ트에게 전달할 데이터
#### 통신을 유지하는 구조
- HTTP 프로토콜은 '요청된 데이터를 반환하는 것'만을 목적으로 만들어짐
- 한 번의 요청과 응답으로 통신
- 과거에 수행한 통신과 관련 맺는 경우는 없음
- 통신 연결 -> 요청 -> 응답 -> 해제
- 상태 비보존형 프로토콜(stateless protocol) : 한 번으로 끝나는 프로토콜
쿠키(Cookie)
- HTTP 프로토콜의 주고받기에 관한 정보를 클라이언트측에 저장
- 다음 통신 때 그 정보를 서버에게 제시
- 서버는 이를 통해 사용자를 지정, 이전 회에서 이어진 통신으로 취급
- HTTP 프로토콜의 정규 장치가 아님
- 보통 CGI(Common Gateway Interface) 등 클라이언트로부터 요청에 맞게 웹 페이지를 작성하는 장치와 함께 사용
CGI
- 일반 웹 페이지의 경우 : 서버는 미리 저장하고 있는 웹 페이지를 반환. 서버가 응답 패킷 준비
- CGI를 사용한 경우 : CGI 프로그램이 서버로부터 요청을 받아서 응답 패킷 준비.
  - 쿠키를 사용하는 경우
  - 헤더 부분에 쿠키와 '클라이언트에서 쿠키를 저장하기 위한 명령'을 써 넣음.
- 쿠키 주고받기
  - CGI 프로그램에서 응답 패킷의 응답 헤더에 쿠키의 저장을 의뢰
  - 클라이언트가 부여된 쿠키 저장
  - 다시 동일한 웹 사이트 요청 시 요청 헤더에 이전에 부여 받은 쿠키 써 넣음
  - CGI 프로그램이 쿠키를 보고 사용자를 지정하여 처리한 웹 페이지 작성
- 쿠키는 유효기간 있음
- 기간이 지난 쿠키는 클라이언트에 의해 자동 삭제
- 유효기간 설정은 쿠키 제작자가, 디폴트는 '브라우저가 닫힐 때'
#### SSL/TLS
- SSL(Secure Sockets Layer) : 인터넷 상에서 데이터 통신을 암호화하는 프로토콜
- TLS(Transport Layer Security) : SSL을 바탕으로 표준화한 것
- HTTPS에서는 HTTP와 다른 포트 사용(보통 443)
- SSL/TLS의 구조
  - WWW클라이언트 : SSL/TLS를 적용한 웹 페이지를 요청
  - WWW 서버 : 증명서를 보내오게 해서 공개키(로그인 전용), 비밀키(해제 전용) 준비
    - 공개키로 로그인한 것은 비밀키로 해제 가능
    - '공개키'와 인증서 발행
    - 키와 증명서의 관리는 인증기관(CA)이 수행
  - 클라 : 증명서가 신뢰할 수 있는지 확인
    - 열고 닫기가 가능한 '공통키' 만듦
    - 데이터를 '공통키'로 암호화
    - '공통키'를 '공개키'로 암호화
    - 암호화한 키와 데이터를 송신
  - 서버 : 암호화된 '공통키'를 '비밀키'로 해제
    - 암호화된 데이터를 '공통키'로 해제
  - 이후부터는 '공통키'로 암호화하고 주고받음
#### 전자메일 주고받기
