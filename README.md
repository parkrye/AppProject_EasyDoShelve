# EasyDoShelve

무료 공개 웹소설을 TXT로 받아 한국어로 번역해 두고, 원문과 번역을 문단별로 나란히 읽는 안드로이드 앱. 사이트마다 파서를 만들지 않고, 페이지를 보며 "쓸 텍스트 · 따라갈 링크"를 고르면 그 선택을 **규칙**으로 저장해 같은 주소 패턴에 다시 씀. 하멜른(`syosetu.org`) 규칙 내장. EasyDo 시리즈.

## 다운로드

최신 버전 0.2.6 — [Releases 페이지](https://github.com/parkrye/AppProject_EasyDoShelve/releases)에서 `EasyDoShelve-<버전>.apk`를 받아 설치. Android 8.0 이상, 64비트 · 32비트 ARM 기기.

- 처음 설치 시 "출처를 알 수 없는 앱" 설치 허용 필요. Play 프로텍트가 검사 화면을 띄울 수 있음
- 업데이트는 새 APK를 같은 방식으로 덮어 설치. 서재 · 규칙 · 사전 유지
- 새 버전은 앱 안 `설정 → 앱 정보 → 새 버전 받기` 또는 Releases 페이지에서 확인
- 서명 인증서 SHA-256: `b6e8f043f50b1cc026b8351fa9121f3348fac26fb099ddcf8635bde6ab3184cd`
  (`apksigner verify --print-certs EasyDoShelve-<버전>.apk`로 확인). 각 Release 본문에 APK SHA-256 기재
- 버그 · 제안은 [Issues](https://github.com/parkrye/AppProject_EasyDoShelve/issues)에

## 기능

| 탭 | 내용 |
|---|---|
| 홈 | 주소 입력 → 맞는 규칙으로 받기(없으면 규칙 만들기), 받는 중 항목 · 진행률 · 취소, 규칙 목록 · 수정 · 삭제 |
| 다운로드 | 받는 중 · 대기 · 이력 구분, 항목별 취소 · 지우기, 이력 모두 지우기. 항목을 눌러 링크 복사 · 다시 받기 · 실패 목록(받기 / 본문 없음 / 번역 실패, 소설 · 화, 서재에 있는지) |
| 서재 | 받은 소설 · 화 목록(원어 · 번역 제목), 화 보기(원문 문단 위 · 번역 아래), 다시 번역(전체 · 일부 화 범위, 이번에 쓸 번역 수단 선택), 삭제, 작품 링크 복사 · 공유. 화 목록 길게 눌러 그대로 끌면 여러 화 선택(가장자리에서 자동 스크롤) 후 다시 번역 · 번역 제거 · 화 삭제(원문 · 번역 파일에서 함께 삭제, 다시 받으면 새로 받음). 다운로드 · 번역 작업 중엔 화 편집 불가. 번역 지운 중간 화는 다음 미번역 번역 · 다시 번역 때 제자리에 끼워 번역. 목록 위에서 보기 방식(원작별: 첫 화면은 원작 폴더만, 열면 그 원작 작품 목록 · 원작 여럿인 작품은 각 폴더에 · 원작 없음 폴더는 맨 끝 / 작품별: 한 줄 목록)과 정렬(이름순(번역 제목 우선) · 최신 로드순 · 최신 번역순, 원작 폴더도 같은 기준) 선택, 앱을 다시 열어도 유지. 길게 눌러 여러 개 선택 후 일괄 삭제 · 다시 번역(번역 수단 선택) · 미번역 번역. 상단 메뉴 미번역 번역(서재 전체) · 폴더 정리(작품 폴더를 지금 원작 폴더로 옮김) |
| 사전 | 고유명사 등 고정 번역 추가 · 수정 · 삭제. 범위는 공통 · 원작 · 작품(작품 > 원작 > 공통 순 우선). 원작 관리, 소설 화면에서 원작 여러 개 지정. 받을 때 원작 필드가 있으면 사이트 표기로 원작을 찾아 지정, 없으면 `원어 (번역)` 이름으로 만듦(이름을 바꿔도 사이트 표기로 계속 매칭). 원작 하나에 사이트 표기 여러 개: 원작 이름을 이미 있는 원작 이름으로 바꾸면 그 원작에 합치고(작품 연결 · 사이트 표기 · 사전 단어 이동, 겹치는 단어는 기존 쪽 유지) 이후 어느 표기로 받아도 같은 원작에 지정. 원작 관리에서 표기 개별 삭제. 화 보기에서 소제목 · 문단을 길게 눌러 단어 추가 |
| 설정 | 다운로드 폴더, 와이파이만, 번역(별도 화면: 번역 켜기 · 수단 순서 · 켜기 · 키), 화면(배경화면 색 사용, 기본 꺼짐), 데이터(백업 만들기 · 백업에서 복원), 앱 정보(앱 정보 · 새 버전 받기 · 오픈소스 라이선스) |

- 저장: 다운로드 폴더 안 `원작 이름/소설 제목/소설 제목.txt` · `소설 제목 (번역).txt`. 원작은 원작 관리의 이름(여럿이면 처음 지정한 원작), 원작이 없으면 `소설 제목/` 바로 아래. 다시 받으면 새 화만 이어 씀
- 폴더 정리: 원작 지정 · 이름이 바뀐 작품만 옮김. 같은 이름이 있으면 `제목 (2)`. 받기 · 번역과 같은 작업 대기열에서 차례가 되면 백그라운드로 실행(앱을 닫아도 계속), 알림에 진척 · 취소. 정리 중에는 앱 전체를 덮개로 막고 진척 · 취소만 둠. 이미 대기 중이면 다시 요청해도 하나만. 비게 된 원작 폴더는 남김
- 받기는 백그라운드(알림 표시)에서 진행. 와이파이만이면 끊길 때 멈추고 연결되면 이어 받음
- 받기 → 번역 2단계. 먼저 새 화를 모두 받고(진행률은 소설 단위), 끝나면 서재의 미번역 화(이전에 실패한 화 포함)를 모아 번역. 이미 받은 화는 다시 받지 않고 기존 원문 · 번역은 유지
- 번역: 설정 순서대로 켜진 수단을 시도(기본: Gemini → DeepL → 구글 웹 → Edge → Azure → 기기 내). 실패한 수단만 10분 쉬고 다음 수단으로 넘어감. 모두 막히면 그 화는 남겨 두었다가 다시 시도. 다시 번역은 쉬는 동안 '번역 대기'로 기다렸다 이어 가고, 끝날 때까지 기존 번역본 유지. 다시 번역의 일부 화 범위는 범위 안 화만 다시 번역하고 범위 밖은 기존 번역 유지(번역 안 된 화는 함께 번역), 머리말은 1화가 범위에 들 때만 다시 번역. 고른 번역 수단은 키 있는 것만, 설정 순서대로 시도. 기기 내(ML Kit)로 번역한 화는 화 목록에 표시
- 미번역 번역: 번역 안 된 화가 있는 작품만, 그 화만 번역(번역된 화는 유지). 번역 수단이 모두 쉬는 동안은 기다렸다 이어 감
- 번역 작업: 미번역 번역 · 다시 번역은 고른 작품을 한 작업으로 묶어 차례로 번역. 다운로드 · 홈 탭에 전체 진척(막대 · 소설 n / N · 번역 화 수 · %)과 작품별 진척(막대 · 화 x / y · 대기 / 번역 중 / 완료 / 실패), 알림에 전체 진척과 지금 작품. 한 작품이 실패하면 실패 목록에 남기고 다음 작품으로 넘어감
- 키가 필요한 수단(Gemini · DeepL · Azure)은 켤 때 키 입력, 키가 없으면 꺼짐. 키는 백업에 넣지 않음
- 사전: Gemini는 지시문으로 전달, 기기 내(ML Kit)는 원문 단어를 라틴 토큰으로 바꿔 번역한 뒤 번역어로 되돌리고 뒤 조사를 받침에 맞춤(토큰이 남거나 번역어가 빠진 줄은 번역어를 넣어 다시 번역), 나머지는 원문 단어를 번역어로 바꿔 넣은 뒤 번역. 단어 찾기는 전각 · 반각 차이 무시. 번역어가 빠지면 로그만 남김
- 루비는 원문에 `瞳(モノアイ)`로 남기고 번역 때는 읽기 제거(머리말 포함)

### 이용 시 주의

- 사이트 이용 약관과 저작권을 지켜 개인 감상 용도로만 사용
- 요청 간격 3초 + 무작위 0~1초. 사이트가 거부하면 간격을 늘리고, 반복되면 중지

## 개인정보

인터넷 사용(받기 · 번역) · 광고 없음 · 앱 자체 수집 없음

EasyDo 시리즈는 인터넷 권한을 쓰지 않는 것이 원칙이지만, 이 앱은 웹소설을 받는 앱이라 **예외로 인터넷을 씀**. 광고 · 계정 · 앱 자체 통계 · 오류 보고는 없음.

| 연결 대상 | 보내는 것 | 언제 |
|---|---|---|
| 사용자가 입력한 소설 사이트 | 일반 브라우저와 같은 페이지 요청 | 규칙 만들기 · 받기 |
| 구글 번역(`translate.googleapis.com`) | 번역할 원문 텍스트 | 구글 웹 번역 켜짐(기본) |
| Microsoft Edge 번역(`edge.microsoft.com`) | 번역할 원문 텍스트 | Edge 번역 켜짐(기본) |
| Gemini API(`generativelanguage.googleapis.com`) | 번역할 원문 텍스트 · 사전 단어, 사용자 키 | Gemini 켜짐 + 키 |
| DeepL API(`api-free.deepl.com` · `api.deepl.com`) | 번역할 원문 텍스트, 사용자 키 | DeepL 켜짐 + 키 |
| Azure Translator(`api.cognitive.microsofttranslator.com`) | 번역할 원문 텍스트, 사용자 키 | Azure 켜짐 + 키 |
| 구글 ML Kit | 번역 모델 다운로드(처음 한 번), ML Kit의 사용 통계 | 기기 내 번역 차례가 올 때 |

- 구글 웹 · Edge 번역은 비공식 방식. 많이 쓰면 막히거나 예고 없이 바뀔 수 있음
- Gemini 무료 등급은 보낸 글이 구글 모델 개선에 쓰일 수 있음
- 광고 · 추적 도메인 요청은 차단
- 받은 파일 · 규칙 · 사전은 기기 안에만 저장. 구글 클라우드 백업 제외, 앱 안 백업 · 복원(파일 하나) 제공
- 앱 안 `설정 → 앱 정보`에 같은 내용 요약

## EasyDo 시리즈

| 앱 | 용도 | 플랫폼 |
|---|---|---|
| [EasyDoDraw](https://github.com/parkrye/MultiProject_EasyDoDraw) | 그림 · 애니메이션 | Android · Windows |
| [EasyDoWrite](https://github.com/parkrye/AppProject_EasyDoWrite) | 소설 · 글쓰기 | Android |
| [EasyDoRead](https://github.com/parkrye/AppProject_EasyDoRead) | 책 · 문서 읽기 | Android |
| [EasyDoShelve](https://github.com/parkrye/AppProject_EasyDoShelve) | 웹 소설 서재 | Android |
| [EasyDoPhoto](https://github.com/parkrye/AppProject_EasyDoPhoto) | 카메라 · 사진 편집 | Android |
| [EasyDoDiet](https://github.com/parkrye/AppProject_EasyDoDiet) | 식단 · 운동 기록 | Android |
| [EasyDoZip](https://github.com/parkrye/AppProject_EasyDoZip) | 파일 · 압축 관리 | Android |
| [EasyDoGame](https://github.com/parkrye/AppProject_EasyDoGame) | 미니 게임 모음 | Android |
| [EasyDoMix](https://github.com/parkrye/AppProject_EasyDoMix) | 영상 · 오디오 편집 | Android |
| [EasyDoRecord](https://github.com/parkrye/AppProject_EasyDoRecord) | 녹음 | Android |
| [EasyDoStudio](https://github.com/parkrye/DesktopProject_EasyDoStudio) | 화면 녹화 · 영상 편집 | Windows |
| [EasyDoMusic](https://github.com/parkrye/MultiProject_EasyDoMusic) | MIDI 연주 · 작곡 | Android · Windows |

## 라이선스

MIT License · © parkrye. 포함된 서드파티 라이브러리 고지는 앱 안 `설정 → 앱 정보 → 오픈소스 라이선스`에서 확인. ML Kit은 오픈소스가 아니며 [ML Kit 이용 약관](https://developers.google.com/ml-kit/terms)을 따름.
