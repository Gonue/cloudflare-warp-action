# cloudflare-warp-action

### 예시 1:

클라이언트 warp+doh 모드

```yaml
- name: WARP 설정
  uses: gonue/cloudflare-warp-action@v1
  with:
    stack: dual # 선택사항. [ ipv4, ipv6, dual ] 중 하나 지원. 기본값 = dual
```

### 예시 2:

#### 적용 전

```yaml
jobs:
  cron:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up JDK
        uses: actions/setup-java@v3
        with:
          java-version: "17"
          distribution: "adopt"
```

#### 적용 후

```yaml
jobs:
  cron:
    runs-on: ubuntu-latest
    steps:
      - name: WARP 설정
        uses: gonue/cloudflare-warp-action@v1
      - uses: actions/checkout@v3
      - name: Set up JDK
        uses: actions/setup-java@v3
        with:
          java-version: "17"
          distribution: "adopt"
```
