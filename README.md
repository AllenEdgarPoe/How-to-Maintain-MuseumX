# How-to-Maintain-MuseumX
개발괴발 만든 코드 싹 다 고치기, maintenance tracker 
** 모든 레포 Readme.md 정리 

## SketcherX 
- 키보드 전역 Hooking 점검
    -> 리모컨 모드 3가지 있음. 그 중 하나가 KEY_UP 이 있고 다른 두 개는 KEY_UP 이 눌리지 않아서 발생하는 문제.
    -> Keyboard 라이브러리는 전역 hooking 제공하는 거 맞음
- venv 라이브러리 구축.. 제일 큰 문제.. SketcherX_P 에서만 라이브러리 살아있음.
    -> C++ 라이브러리들 윈도우 환경에서 깔기 너무 힘듬. 특히 dlib, fused.op 등 얼굴 detection 관련 라이브러리들.
      op 파일들의 경우 직접 컴파일해서 미리 깔아버려서 해결.
- QR 버전으로 돌릴 경우 프로그램 다운되는 현상. Thread 충돌 에러일까? CES 때도 비슷하게 thread 간 충돌 이벤트가 있었음..
  -> 이벤트 뷰어 모니터링 필요.

## Ensemble & Composer 
- 데이터 관리하기. 회사 슬랙에 연동? 혹은 드라이버 에 연동해서 넣는 방식
    -> PNG INFO 에 diffusion 정보 (prompt, cfg 등) 넣어서 정리
- 로그 관리 : Logger 라이브러리 활용하기
    -> API Request & Respond 
    
- Try & Except 다시 정리. 샘플 이미지가 제대로 나오지 않고 있음. 마음대로 아무 이미지나 나오는거 방지.
- AWS 이미지 업로더 살아있는지? 확인하는 시스템 필요.

## Ensemble
- detectmap(149), info(150), results(152)
- 공유 폴더 로 연동 되어있기 때문에 PC가 한 대라도 안 켜져 있으면 모든 PC에서 에러 남.
- Redis 서버가 다운 되어있을 경우. check connection 등으로 모니터링 할 수 있는 방법 고안 (다스콘 OMS 로 확인)


## Symphony
- NSFW filter !! base image 에만 걸어서 detect 되면 뉴스 기사들 다시 크롤링해서 다시 모든 비디오 생성하기.
- 뉴스 기사 더 다양하게 ? YTN 말고 다른 뉴스도?
- 고유 명사가 나올 경우 이해하지 못 해서 아무 이미지 나 던져버리는 Hallucination 문제 연구하기
- 151 PC 자동 shut down 되는지 확인 

## Naver Crawling 
- 사용자 db (guest.csv) 파일 관리 : 10일 지나면 expire 되는 거 확인하기


---

<8/17>
CLI(Command line interface)
CRLF / LF
XML serialize / deserialize 
OOP 
