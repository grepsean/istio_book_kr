# 카오스 엔지니어링이란?

Chaos 그림.

서비스 운영에 있어 숙명과 같은 존재가 장애입니다. 구글 검색으로 서비스이름에 장애라는 검색어를 추가하고 검색하면 상당히 많은 기사가 나오는 것을 알 수 있습니다. 우리가 잘 아는 서비스들도 장애를 겪고 있습니다. [Gmail](https://it.donga.com/28827/), [GitHub](https://github.blog/2020-02-28-february-service-disruptions/), [CloudFlare](https://www.krcert.or.kr/data/trendView.do?bulletin_writing_sequence=1972), [AWS](https://aws.amazon.com/ko/blogs/korea/follow-up-to-the-november-22-event-in-aws-seoul-region/) 등. 한번 넷플릭스\(Netfilx\)를 살펴볼까요?

장애 투성이 아닌가? 싶지만, 이것이 실제 서비스의 모습입니다. 이처럼 장애는 어느 회사나 발생할 수 있는 일입니다. 또한, 장애는 빨리 전파되고, 늦게 복구되는 특징을 가지고 있습니다. 그래서 각 서비스마다 서비스 가용성을 보여주는 웹 페이지를 제공하기도 합니다.

그렇다고, 서비스를 운영하며, 장애가 발생하기까지기다리고 있다가, 발생하면 급하게 해결할 필요는 없습니다. 실 서비스에서 원하는 시간에 부분적으로 장애를 일으켜 보고 해결해 가면 됩니다. 이런 관점에서 넷플릭스에서는 카오스 몽키라는 오픈 소스 프로젝트를 내 놓았습니다. 이 코드를 작성하는 기본적인 아이디어는 실제 환경에서 다양한 서비스를 죽이는 것이었습니다\(실제 구현은 서비스를 수행하는 가상 머신을 셧다운시키는\). 많은 팀에서 서비스 가용시간을 유지하려 애쓰는데, 도리어 자신의 서비스를 볼모로 삼고 스스로를 공격하는 것은 미친 짓처럼 보입니다. 이렇게 장애를 일으켜도 될까요? 괜찮습니다. 이는 장애를 발생시키는 것이 아니라, 그것을 드러내는 것이기 때문입니다. 실제 서비스에서 장애가 발생하여 많은 비용을 소모하는 것보다 낫습니다. 이러한 카오스 몽키가 나온 뒤에, 카오스 엔지니어링이라는 새로운 분야가 등장하기 시작했습니다.

카오스 엔지니어링 원리라는 웹사이트에 따르면, 카오스 엔지니어링은 휘몰아치는 조건들을 견딜수 있는 시스템 기능에 대한 신뢰를 구축하기 위해 분산 시스템을 실험하는 학문이라 합니다\([http://principlesofchaos.org/](http://principlesofchaos.org/)\). 이는 실서비스에 장애를 주입하여, 출시 전 테스트에서 드러나지 않는 아키텍처 상의 문제를 직접 드러내는 엔지니어링으로, 실제 서비스의 각종 장애 조건을 견딜 수 있는 시스템 신뢰성을 확복하기 위해 분산 시스템을 실험하는 분야입니다. 작은 서비스 혹은 컴포넌트에서 시작해서, 점진적으로 전체 시스템으로 적용하며 신뢰성을 구축해갑니다.

이에 목적은 복잡한 시스템에서는 각 시스템이 문제가 발생하고 실패할 수 있지만, 긍극적으로는 전체 시스템의 치명적인 실패를 막는 것입니다. 보통 이러한 시스템의 특성을 흔히 탄력적\(elastic\)이라 하는데, 그럼 마이크로 서비스 기반인 네트워크의 전체 시스템이 탄력적인지 어떻게 확인할 수 있을까요?

[https://www.pagerduty.com/blog/injecting-failure-at-netflix-staying-reliable-for-40-million-customers/](https://www.pagerduty.com/blog/injecting-failure-at-netflix-staying-reliable-for-40-million-customers/)

