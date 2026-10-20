# MoonlightMerchant 개발 규칙

## 프로젝트
- 실제 프로젝트 루트: /Users/usoku/MoonlightMerchant
- Unity 6000.6.6f1, Universal 2D, C#. 목표는 Steam Windows용 2D 픽셀아트 상점 경영 게임이다.
- 최초 출시는 싱글플레이 및 오프라인이다. 서버, 로그인, 온라인 거래는 현재 범위에서 제외한다.

## 작업 방식
- 한국어로 설명한다. 기본 프로그래밍 설명은 생략하되 Unity 개념과 메뉴 위치는 단계적으로 안내한다.
- 필요한 경우 Laravel의 Service/Model, Vue Component와 비교해 설명한다.
- 변경 전 기존 코드와 하위 AGENTS.md를 읽는다. 기능 중복과 불필요한 프레임워크를 피한다.
- 기존 파일, 씬, 설정을 임의로 삭제하거나 초기화하거나 교체하지 않는다.
- Assets 파일 이동 시 .meta와 GUID 참조를 보존한다. Library, Temp, Logs를 직접 수정하지 않는다.
- 한 번에 작은 기능을 완성하고 검증한다. 새로운 개발 단계의 범위와 설정 변경은 먼저 설명한다.
- 경제 및 재고 계산은 UnityEngine에 의존하지 않는 일반 C# 클래스로 구현한다.
- MonoBehaviour는 화면 연결, Unity 생명주기, 입력을 담당한다.
- 아이템 등 정의 데이터와 실행 중 상태를 구분한다. 데이터가 늘면 ScriptableObject를 검토한다.
- 게임 코드는 Assets/_Game/Scripts, 씬은 Assets/_Game/Scenes, 테스트는 Assets/_Game/Tests에 둔다.
- 자동 생성 파일 및 비밀정보는 커밋하지 않는다. 원격 게시와 배포는 요청된 경우에 진행한다.

## 검증과 보고
- 경제 로직의 성공 및 실패 경로는 Unity Test Framework로 검증한다.
- 소스 검사만으로 Unity 컴파일 또는 Play 실행이 성공했다고 주장하지 않는다.
- 변경 파일, 검증 결과, 미검증 사항, 사용자가 Unity에서 할 작업을 보고한다.
- Unity Console의 오류, 재고 부족, 골드 부족, 가격 변경을 기능 구현 시 확인한다.
- 첫 게임 기능 목표: 1,000G에서 약초 20G 매입 후 35G 판매하여 1,015G가 되는 흐름.
