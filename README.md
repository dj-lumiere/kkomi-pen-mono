# KNPS Kkomi Pen Mono

국립공원공단의 **국립공원 꼬미체**(KNPS Kkomi)를 획 중심선으로 나누고, 둥근 펜 하나로 모든 글자를 다시 그린 고정폭 가변 폰트입니다.

- 라틴 문자와 기호는 한 칸(500), 한글은 두 칸(1000)입니다(UPM 1000).
- 굵기 100~900의 가변 폰트입니다. 굵기는 펜의 굵기라서 모든 굵기에서 같은 모양이 이어집니다. 라틴은 900까지, 현대 한글은 700까지, 옛한글은 600까지 굵어지고, 그보다 굵은 굵기에서는 그 모양을 씁니다.
- 현대 한글 11,172자와 옛한글(첫가끝 자모를 이어 쓴 모든 조합, 채움 문자 포함)을 같은 조합기로 그립니다.
- 정적 폰트 18벌(100~900 × 똑바름·이탤릭)과 가변 폰트 2벌이 있습니다.
- [웹에서 미리보기](https://dj-lumiere.github.io/kkomi-pen-mono/) · [내려받기](https://github.com/dj-lumiere/kkomi-pen-mono/releases/latest)

이 폰트는 [KNPS Kkomi Mono](https://github.com/dj-lumiere/kkomi-mono)의 후속입니다. Kkomi Mono는 원본 윤곽을 고쳐 쓴 폰트이고, 1.8.3에서 개발을 마쳤습니다. 두 폰트는 이름이 달라서 함께 설치해 쓸 수 있습니다.

## 설치

`fonts/`의 정적 폰트나 `fonts/variable/`의 가변 폰트 중 하나를 설치합니다. 둘을 함께 설치하면 같은 이름이 겹칩니다.

| 파일 | 굵기 |
|---|---|
| `KNPSKkomiPenMono-Thin.ttf` ~ `KNPSKkomiPenMono-Black.ttf` | 100 ~ 900 |
| `KNPSKkomiPenMono-ThinItalic.ttf` ~ `KNPSKkomiPenMono-BlackItalic.ttf` | 100 ~ 900, 13° 기울임 |
| `variable/KNPSKkomiPenMono-VF.ttf`, `variable/KNPSKkomiPenMono-Italic-VF.ttf` | 가변 100 ~ 900 |

400과 700은 Regular, Bold, Italic, Bold Italic 이름이라 편집기의 굵게·기울임 설정이 그대로 동작합니다.

VS Code 예:

```json
"editor.fontFamily": "'KNPS Kkomi Pen Mono'",
"editor.fontLigatures": true,
"terminal.integrated.fontFamily": "'KNPS Kkomi Pen Mono'"
```

### 웹에서 쓰기

`fonts/woff2/`에 정적 폰트와 가변 폰트의 woff2 파일이 있습니다. 가변 폰트 하나로 모든 굵기를 쓸 수 있습니다.

```css
@font-face { font-family: "KNPS Kkomi Pen Mono"; src: url("KNPSKkomiPenMono-VF.woff2") format("woff2"); font-weight: 100 900; font-style: normal; }
@font-face { font-family: "KNPS Kkomi Pen Mono"; src: url("KNPSKkomiPenMono-Italic-VF.woff2") format("woff2"); font-weight: 100 900; font-style: italic; }
code, pre { font-family: "KNPS Kkomi Pen Mono", monospace; }
```

## 만든 방법

**펜**
- 원본 꼬미의 글자를 획 중심선으로 나누고, 그 위에 둥근 펜을 입혀 다시 그렸습니다. 굵기마다 바뀌는 것은 펜 굵기뿐입니다.
- 획 사이 흰 공간이 굵기를 올려도 막히지 않도록 글자마다 펜 굵기의 상한을 둡니다. 괄호·동그라미 글자처럼 부품이 촘촘한 글자는 600에서 멈춥니다.

**한글**
- 현대 한글과 옛한글을 하나의 조합기로 만듭니다. 자모 모양은 꼬미가 직접 그린 글자에서 고른 대표 모양이고, 배치는 원본에서 잰 간격과 크기를 따릅니다.
- 자모 사이에는 20px에서 흰 공간 1px 이상을 남깁니다. 자음끼리는 원본 간격을 지키고, 자리가 모자랄 때만 붙입니다.
- 옛한글은 자모마다 문맥별 꼴을 두고 OpenType 문맥 치환으로 고릅니다. 첫가끝 자모를 이어 쓰면 어떤 조합이든 한 음절로 그립니다. 초성 채움(U+115F)과 중성 채움(U+1160)이 든 조합은 그 자리에 ㅇ과 ㅣ가 있는 것처럼 배치한 뒤 그 글자만 지웁니다.
- 아래아(ᆞ ᆢ)는 속을 채운 점입니다. 가벼운 소리(ᄛ ᄫ ᄝ 등)는 ㅇ을 작게 아래에 붙여 ㅎ과 구별됩니다.

**라틴과 기호**
- 원본 꼬미와 Kkomi Mono 1.8.3의 중심선에서 다시 그렸습니다. 헷갈리기 쉬운 글자는 1.8.3의 구별(가운데 점 있는 `0`, 마름모 점의 `i j`, 꼬리 있는 `l`, `6 9 8 1`의 모양)을 따릅니다.
- 리거처(`calt`): `->` `<-` `<->` `=>` `<=>` `-->` `==>` `==` `===` `!=` `!==` `<=` `>=` 등. 리거처는 원래 글자 수만큼의 칸을 차지해서 열이 어긋나지 않습니다.
- `—`(em dash)와 `―`(가로줄)은 칸 끝까지 그어서 이어 쓰면 한 줄이 됩니다. `–`(en dash)는 칸의 85%입니다.
- 분수는 분자, 가로줄, 분모를 쌓아 한 칸에 넣었습니다. `㎟ ㎥` 같은 단위의 2와 3은 위첨자입니다.

**이탤릭**
- 모든 글자를 13° 기울입니다. 박스 선, 블록, 점자, Powerline은 위아래·좌우가 이어지도록 똑바로 둡니다.
- 일부 소문자(`a d f h k l m n o p u x y z` 등)는 필기체 모양입니다.

**한자는 아직 없습니다.** 시스템 폰트로 나옵니다. 일본 한자(상용·인명용 2,999자)부터 넣을 계획입니다.

## 라이선스와 출처

- **폰트** (`fonts/`, `source/`): 본 저작물은 국립공원공단에서 2021년 작성하여 공공누리 제1유형으로 개방한 국립공원공단 꼬미(작성자: 국립공원공단)를 이용하였으며, 해당 저작물은 국립공원공단, <http://www.knps.or.kr> 에서 무료로 다운받으실 수 있습니다. ([공공누리 안내](https://www.kogl.or.kr/recommend/recommendDivView.do?recommendIdx=41248&division=font))
  이 폰트를 쓰거나 다시 배포할 때도 이 출처를 함께 밝혀야 합니다. 만든 방법은 `출처.txt`에도 정리되어 있습니다.
- 이 폰트는 국립공원공단이 만들거나 후원한 것이 아닙니다.
- **빌드 스크립트** (`tools/`): MIT 라이선스입니다(`tools/LICENSE`).
