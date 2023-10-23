### REST API

**RE**presentational **S**tate **T**ransfer의 약자로 네트워크 상 자원을 주고받는 규약을 의미합니다.

이때 네트워크에서 Server-Client 위상 구조를 가집니다.

자원을 이름과 상태를 주고 받는 API 구조라고 할 수 있습니다.

HTTP URI(Uniform Resource Indentifier)를 통해 자원을 명시합니다.

HTTP Method(GET, POST, PUT, DELETE)를 통해 자원에 대한 상태 조작이 가능합니다.

### REST API의 특징

1) Server-Client 구조

- 자원을 제공하는 서버
- 자원을 요청하는 클라이언트

2) Stateless

- 이전의 상태 정보를 저장하지 않는 Statless 구조의 특징을 가집니다.
- 별도의 State가 없기에, 스케일 업이 비교적 쉽습니다.

3) Cacheable

4) Layered System

5) Uniform Interface

### REST API의 장점

REST API의 장점은 기존의 웹 구조를 그대로 사용하므로 별도의 인프라 구축이 필요하지 않습니다.

HTTP 표준을 지키는 대부분의 플랫폼에서도 이용 가능한 범용성을 가지고 있으며, HTTP Method를 사용해 비교적 쉽게 API 사용이 가능합니다.

### RESTful

REST API의 원칙을 준수하고, 일관적인 구조를 가진 웹 서비스를 말합니다.