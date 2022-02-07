
## keystore 만들기

```bash
> cd C:\Users\your_user_name\.android\
> keytool -genkey -v -keystore key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
키 저장소 비밀번호 입력:
새 비밀번호 다시 입력:
이름과 성을 입력하십시오.
  [Unknown]:  WHATWANT
조직 단위 이름을 입력하십시오.
  [Unknown]:  ONLYONE
조직 이름을 입력하십시오.
  [Unknown]:  ONLYONE
구/군/시 이름을 입력하십시오?
  [Unknown]:  SEOUL
시/도 이름을 입력하십시오.
  [Unknown]:  SEOUL
이 조직의 두 자리 국가 코드를 입력하십시오.
  [Unknown]:  82
CN=WHATWANT, OU=ONLYONE, O=ONLYONE, L=SEOUL, ST=SEOUL, C=82이(가) 맞습니까?
  [아니오]:  예

다음에 대해 유효 기간이 10,000일인 2,048비트 RSA 키 쌍 및 자체 서명된 인증서(SHA256withRSA)를 생성하는 중
        : CN=WHATWANT, OU=ONLYONE, O=ONLYONE, L=SEOUL, ST=SEOUL, C=82
[key.jks을(를) 저장하는 중]
```

## key.properties 저장하기
- android/ 폴더 밑에 `key.properties` 저장

```
storePassword=<password from previous step>
keyPassword=<password from previous step>
keyAlias=key
storeFile=C:\Users\User_Name\key.jks
```
