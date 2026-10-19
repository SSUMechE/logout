# 실습실 GitHub 로그아웃

**조교·교수자용 · Windows / Anaconda Prompt**

주소: **github.com/SSUMechE/logout**

이 페이지는 로그인 없이 열 수 있음. 저장소 다운로드나 가상환경 활성화는 필요 없음.
각 명령 상자 오른쪽 위의 복사 버튼을 누른 뒤 **Anaconda Prompt**에 붙여넣고 Enter.
PowerShell에서는 실행하지 않음.

> **작업 저장·제출이 끝난 PC에서만 실행.**
> 현재 Windows 사용자에 대해 Git Credential Manager가 저장한 **모든 GitHub 계정**을 정리함. 교수자 계정도 포함됨.
> GitHub 계정 자체, 저장소, 코드 파일, Conda 환경은 삭제하지 않음.

## 1. Git 계정 전체 로그아웃

아래 **한 줄 전체**를 그대로 복사하여 실행. 계정 ID를 직접 입력할 필요 없음.

```bat
for /f "delims=" %G in ('git credential-manager github list --no-ui') do git credential-manager github logout "%G" --no-ui
```

## 2. Git 로그아웃 확인

```bat
git credential-manager github list --no-ui
```

- **오류 없이 계정 ID가 표시되지 않으면 Git 인증정보 정리 완료.**
- 계정이 남아 있거나 오류가 표시되면 완료로 처리하지 않음.
- `credential-manager` 명령을 찾을 수 없다면 Git for Windows / Git Credential Manager 설치 상태를 담당자에게 확인.

## 3. 웹 계정 로그아웃

**위 명령으로 브라우저의 GitHub 로그인은 해제되지 않음.**

1. GitHub 오른쪽 위 프로필 사진 선택.
2. **Sign out** 선택.
3. 여러 계정이 표시되면 **Sign out from all accounts** 선택.
4. LMS도 로그아웃. VS Code에 로그인한 경우 **Accounts → 해당 계정 → Sign Out**으로 별도 정리.

다른 브라우저나 브라우저 프로필을 사용했다면 해당 창에서도 로그아웃 확인.

---

[GitHub 공식 안내: 여러 계정 로그아웃](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/switching-between-accounts)

이 안내는 Git Credential Manager와 웹 로그인 정리용임. GitHub CLI(`gh`) 등 다른 앱의 로그인은 별도이며, 파일 삭제나 시험 자료 배포 기능은 없음.
