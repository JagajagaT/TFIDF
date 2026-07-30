[README.md](https://github.com/user-attachments/files/30548441/README.md)
# TF-IDF · 코사인 유사도 실험실

고등학교 「인공지능 수학」 텍스트 단원 수업용 웹앱.
영화 리뷰 두 편을 입력하면 토큰화 → 단어집합 → TF-IDF 벡터 → 코사인 유사도 계산 과정을
LaTeX 수식(KaTeX)으로 보여 줍니다. 6개 단계를 탭으로 넘기며 앞뒤로 자유롭게 이동할 수 있고,
좌우 방향키로도 넘길 수 있습니다.

예시 리뷰는 긍정 3편·부정 3편이 준비되어 있습니다. 긍정끼리 또는 부정끼리 비교하면
유사도가 0.7~0.8로 높게, 긍정과 부정을 비교하면 공유 단어가 없어 0.000(90°)이 나옵니다.

## 학습 정보

- 학습 데이터: 네이버 영화 리뷰(NSMC) `ratings_train.txt` 149,995건
- 평가 데이터: `ratings_test.txt` 49,997건 (학습에 쓰지 않음)
- 단어 사전: 학습 데이터에서 3회 이상 등장한 30,899개 단어의 DF와 감성 점수를 파일에 내장
- IDF = log₁₀(n ÷ DF), n = 149,995. 사전에 없는 단어는 DF = 1로 처리
- 감성 판정: 단어별 로그오즈(나이브베이즈) 합. 테스트 정확도 **81.4%**
- 파일 하나로 동작하는 정적 페이지 (index.html, 약 500KB · gzip 210KB)

수식 렌더링에 KaTeX CDN을 사용하므로 인터넷 연결이 필요합니다.

## GitHub Pages에 올리기

1. GitHub에서 새 저장소를 만듭니다. (예: `tfidf`, Public)
2. `index.html`을 업로드합니다. — 저장소 첫 화면 → **Add file → Upload files** → 파일 끌어다 놓기 → **Commit changes**
3. 저장소 **Settings → Pages** 로 이동합니다.
4. *Source* 를 **Deploy from a branch**, *Branch* 를 **main / (root)** 으로 두고 **Save**.
5. 1~2분 뒤 아래 주소로 접속됩니다.

```
https://<깃허브아이디>.github.io/tfidf/
```

`index.html`이라는 이름이면 주소 뒤에 파일명을 붙이지 않아도 바로 열립니다.
수업 자료에 넣을 QR 코드는 이 주소로 만들면 됩니다.
