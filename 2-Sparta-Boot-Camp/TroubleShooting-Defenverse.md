- 메타버스 취지에 맞게 멀티 플레이 환경을 구축하려 Netcode 라이브러리를 사용한다. 일단, 사용 자체는 간단한데 동기화, 데이터 보존 등의 문제는 쉽게 해결되지 않는다. 해결할 수 있는 방법으로 Client-Side Prediction, Reconciliation, NetworkTransform, Interpolation을 얻었다. 그 중 Tick 기반 Fixed Update랑 Reconciliation은 로켓 리그나 발로란트에서도 사용하는 방식이라고 하ㅓㄴ다.

- 넷코드 패키지를 받았는데, Network Manager와 Network Object가 추적되지 않는 문제. 삭제하고 유니티 재부팅 후 다시 인스톨하니까 된다.

- 투표 시스템을 통해 클라이언트 전원히 투표하면 게임에 참가하는 시스템을 만들었다. 클라이언트 측에서 NetworkManager에 접근하려 하면 오류가 발생하고, NetworkVariable은 그냥 수정한다고 되는 게 아니가 ServerRpc를 사용해야 한다는 걸 알았다.