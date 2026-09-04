# Family Sync (너와나 캘린더) 정책 문서 저장소

가족 일정 공유 앱 **Family Sync (너와나 캘린더)** 의 공개 정책 페이지를 보관하는 저장소입니다.
앱 설정 화면과 Google Play 스토어 등록 정보(개인정보 처리방침 URL, 데이터 삭제 URL)에서 이 페이지들을 연결합니다.

- 대상 앱 패키지명: `com.familysync.family_sync`
- 문서 언어: 한국어

## 공개 URL (GitHub Pages)

| 문서 | URL |
|---|---|
| 홈 | https://jjanghyoson.github.io/familysync_app_policy/ |
| 개인정보 처리방침 | https://jjanghyoson.github.io/familysync_app_policy/privacy-policy.html |
| 서비스 이용약관 | https://jjanghyoson.github.io/familysync_app_policy/terms-of-service.html |
| 계정 및 데이터 삭제 안내 | https://jjanghyoson.github.io/familysync_app_policy/account-deletion.html |

> **GitHub Pages가 아직 꺼져 있다면**: 저장소 **Settings > Pages**에서
> Source를 **Deploy from a branch**, Branch를 **`main`**, 폴더를 **`/ (root)`** 로 선택하고 Save 하세요.
> 저장 후 1~2분 내에 위 URL이 활성화됩니다.

## 파일 구성

```text
index.html                  # 정책 문서 홈 (카드형 링크)
privacy-policy.html/.md     # 개인정보 처리방침
terms-of-service.html/.md   # 서비스 이용약관
account-deletion.html/.md   # 계정 및 데이터 삭제 안내 (Google Play Data deletion 링크용)
assets/style.css            # 공통 스타일 (외부 CDN 의존 없음)
```

HTML은 스토어/앱 연결용 공개 페이지이고, Markdown은 동일 내용의 원본(리뷰·수정용)입니다.
**내용을 수정할 때는 md와 html을 함께 갱신하세요.**

## 문서 작성 기준

- 2026-08-27 기준 앱 코드(`/workspace/family_sync`)를 다시 대조해 **실제 기능·실제 수집 항목 기준**으로 갱신했습니다.
- 앱이 수집하지 않는 정보(위치정보, 광고 식별자, 연락처 등)는 수집하지 않는다고 명시했습니다.
- 위치 공유 기능은 보류(dormant, UI 비노출) 상태이며, 문서에는 "현재 위치정보를 수집하지 않음 + 향후 도입 시 별도 동의/정책 개정" 원칙으로 반영했습니다.
- 기기 권한 표는 `android/app/src/main/AndroidManifest.xml`에 선언된 권한을 **하나도 빠짐없이** 옮긴 것입니다. 권한을 더하거나 뺄 때 개인정보 처리방침 9항도 함께 고쳐야 합니다.
- **사용자 콘텐츠를 제3자에게 넘기는 경로가 없습니다.** 한때 있던 콘텐츠 번역 기능(문장을 Microsoft 번역 서비스로 전송)은 2026-08-27에 앱에서 제거했고, 처방침 7항에 그 사실을 적어 두었습니다. 이 상태라야 Play 데이터 보안 신고의 "제3자와 공유: 아니요"가 사실과 맞습니다. 번역을 다시 넣는다면 **데이터 보안 신고부터 갱신**해야 합니다.

## 출시 전 운영 확인

- [x] 운영자명 / 연락처 이메일 / 사업자 정보 반영
- [x] 시행일 반영
- [ ] 출시 전 운영자/법무 검토
- [ ] Google Play Console **Data safety** 입력값과 문서 내용 대조
- [x] 앱 내 30일 유예 계정 삭제 기능 및 account-deletion 문서 반영

## 주의

⚠️ 실제 출시 전에 개인정보 처리 리전과 스토어 콘솔의 데이터 보안 응답을 최종 대조하세요.

## Play 심사용 자료

| 자료 | 주소 |
|---|---|
| 포그라운드 서비스(알람) 동작 영상 | https://jjanghyoson.github.io/familysync_app_policy/assets/play-review/foreground-service-alarm.mp4 |

Play Console의 **앱 콘텐츠 > 포그라운드 서비스 권한** 선언은 해당 기능을 보여 주는
동영상 링크를 요구한다. 유튜브 대신 이 저장소(GitHub Pages)에 두는 이유는,
처방침과 같은 자리에서 함께 관리되고 링크가 계정 사정으로 사라지지 않기 때문이다.

영상은 일정 알람을 설정하고 → 울리고 → 끄는 과정을 담는다.
`AlarmRingService`가 `specialUse` 전경 서비스로 도는 근거 자료다.
