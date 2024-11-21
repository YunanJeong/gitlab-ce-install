# gitlab-ce-install

## 설치

<https://about.gitlab.com/install/>

## 업그레이드

### 업그레이드 경로(Upgrade path)와 the required upgrade stop

- [Gitlab 공식문서](https://docs.gitlab.com/ee/update/upgrade_paths.html)는 업그레이드시 안정적인 마이그레이션을 위해, 특정 버전으로 한 번에 가지말고, 여러 정해진 버전을 거쳐서 가는 것을 권고한다. 각 중간단계 버전을 required upgrade stop이라고 표현하고 있다.
- 특정 버전에서 특정 버전으로 업그레이드시 필요한 중간단계 버전을 아래 링크에서 확인가능하다.
- <https://gitlab-com.gitlab.io/support/toolbox/upgrade-path>

### 서드파티 패키지 저장소 에러

- Ubuntu 기준, Gitlab 업그레이드도 `apt update`, `apt install`을 이용하는데, 설치할 때와 마찬가지로 서드파티 저장소인 Gitlab 패키지 저장소를 로컬시스템에 추가해야 한다.
- 위 설치 페이지에서 패키지 저장소 추가 명령어를 찾아서 입력한다.
- 오래된 시스템의 경우 GPG 키 처리과정에서 에러가능성이 높은데, 반드시 현재 기준 공식 설치페이지의 명령어를 가장 먼저 시도해보자.
- 공식문서의 대부분 명령어는 gitlab-ee(엔터프라이즈) 기준으로 작성되나, gitlab-ce(커뮤니티)로 바꿔써도 모두 호환된다.

```sh
# 2024.11.21 저장소 추가  # gitlab-ee는 gitlab-ce로 변경
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
```
