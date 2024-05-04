# 0502 과제 풀이

## HTML
> ### 구조 파악
> - 모든 요소를 정리할 main.main을 생성하였습니다.
> - 완성 사진을 보고 여자 프로필, 남자 프로필을 div로 각각 묶어 정렬하면 깔끔할 것 같다는 생각이 들어 이를 .faces1 .faces2로 지정하였습니다.
> - 두 개의 div 안에 여자 프로필 4장, 남자 프로필 4장을 div.face-img > img로 작성하고, alt를 활용하여 각 이미지의 정보를 제공하고자 하였습니다.
> - div.face-img 안에는 프로필 유저의 상태를 알 수 있도록 span.status를 삽입한 후 online인 유저는 .online 클래스를 추가하여 오프라인과 온라인 유저를 더욱 쉽게 지정할 수 있도록 하였습니다. aria-label을 활용하여 온/오프라인 상태 설명을 작성하였습니다.

## CSS
> - ### float 를 사용한 레이아웃
> - main에서는 display: flow-root를 이용하여 각 요소들의 플로우 컨텍스트를 리셋하였습니다. position은 absolute로 설정하여 화면의 가운데 쯤 위치하도록 하였습니다.
> - face-img(각 이미지를 감싸는 div)는 float: left로 요소를 왼쪽으로 띄워 정렬되도록 하고, position은 relative로 지정하여 이후 지정할 status가 각각 img 우측 하단에 붙을 수 있도록 하였습니다.
> - face-img:nth-child(n + 2)를 활용하여 2번째 face-img 부터는 margin-left, bottom를 20px씩 지정하여 프로필 이미지들의 간격을 맞추어 주었습니다.

> - ### @supports (display: flex)를 사용한 레이아웃
> - .main 요소가 flex를 지원하는 브라우저에서 flex 컨테이너로 동작합니다. flex-flow 를 row wrap으로 지정하여 행으로 나란히 배치되고, 필요한 경우 아래에 추가됩니다. 가운데 정렬이 되도록 하였습니다.
> - .faces2의 order값을 -1로 지정하여 flex를 지원하는 브라우저에서는 플렉스 아이템의 순서를 변경하여 남자 프로필이 첫번째 줄에 오도록 하였습니다.