# 은철의 포트폴리오

[공개 사이트](https://xilver2918.github.io/portfolio/)는 Hugo와 [Port Hugo 테마](https://github.com/tylersayshi/port-hugo)로 제작했습니다.

## 로컬 실행 및 빌드

Git과 Hugo extended를 설치합니다. Windows에서는 `winget install --id Hugo.Hugo.Extended -e`로 Hugo를 설치할 수 있습니다. 로컬 확인에는 Hugo extended 0.169.0을, GitHub Actions에서는 0.167.0을 사용합니다. 설치 후 `hugo version`으로 버전과 extended 여부를 확인하세요.

저장소를 처음 받는 경우 아래 명령을 실행합니다.

```powershell
git clone https://github.com/xilver2918/portfolio.git
cd portfolio/site
```

이미 저장소 루트에 있다면 `cd site`로 이동합니다. 미리보기 서버를 켠 뒤 [로컬 사이트](http://localhost:1313/portfolio/)를 엽니다. 종료하려면 `Ctrl+C`를 누릅니다.

```powershell
hugo server --config hugo.toml,pages.json --baseURL http://localhost:1313/portfolio/
```

정적 파일을 생성하려면 같은 폴더에서 아래 명령을 실행합니다. 홈 파일은 `site/public/index.html`에 생성됩니다.

```powershell
hugo --config hugo.toml,pages.json --minify
```

## 콘텐츠 수정 및 재배포

- 첫 화면, 자기소개, 대표 활동은 `site/data/content.yml`에서 수정합니다.
- 사이트 제목, 메뉴, 소셜 링크는 `site/hugo.toml`에서 수정합니다. 배포 주소와 테마 설정은 `site/pages.json`에 있습니다.
- 프로필과 배경 이미지는 `site/static/images/`, 대표 활동 이미지는 `site/assets/images/portfolio/`에 둡니다.
- 로컬 확인 후 수정 파일을 커밋하고 `git push origin main`을 실행합니다. [GitHub Actions](https://github.com/xilver2918/portfolio/actions)에서 해당 커밋의 `build`와 `deploy` 성공을 확인한 뒤 공개 사이트에서 변경을 확인합니다.

## 이미지와 웹폰트 출처

| 자료 | 사용 위치 | 제작 및 출처 |
| --- | --- | --- |
| 도시 배경 이미지 | 첫 화면 · `site/static/images/hero-city.png` | 포트폴리오 작성자가 AI로 생성한 이미지 |
| 구름 로고 | 상단 메뉴 · `site/static/images/cloud-logo.png` | 포트폴리오 작성자가 AI로 생성한 이미지 |
| 프로필 아바타 | 자기소개 · `site/static/images/profile-avatar.png` | 포트폴리오 작성자가 AI로 생성한 원본을 이미지 편집 도구로 투명 배경 처리 |
| 이:음 시연 화면 | 대표 활동 · `site/assets/images/portfolio/ieum-cover.png`, `ieum-demo.png` | [이:음 웹앱](https://education-data.vercel.app/)의 시연 화면 캡처 |
| Paperlogy 5 Medium | 대표 활동 상세 제목 | [Paperlogy 제작자 페이지](https://freesentation.blog/paperlogyfont) · [웹폰트 배포처](https://github.com/fonts-archive/Paperlogy) |
| Port Hugo | 사이트 테마 | [테마 원본](https://github.com/tylersayshi/port-hugo) · [MIT 라이선스](LICENSE) |

## Port Hugo 원본 안내

currently tested with hugo v0.141.0

This theme is a simple, customizable portfolio for designers or web developers.

![Thumbnail](https://raw.githubusercontent.com/tylersayshi/port-hugo/master/images/tn.png)

![Screenshot](https://raw.githubusercontent.com/tylersayshi/port-hugo/master/images/screenshot.png)

## Features

- Responsive portfolio
- Easy sections to use
- Hugo image processing for optimization
- [Hugrid](https://github.com/aerohub/hugrid) based portfolio section
- [Somrat](https://github.com/somratpro/somrat) based design

## Install theme on your hugo site

```
hugo new site your-site-name # if you already have a site ignore this line and the next
cd your-site-name
cd themes
git clone https://github.com/tylersayshi/port-hugo.git
cd ..
hugo serve
```

Once you have done this, you may use the `exampleSite` folder as an example for how to set your project up. The two main things to pay attention to is to first set this in your `config.toml` file:

```toml
theme = "port-hugo"
```

Then you will need to replicate the data used in the `exampleSite/data/content.yaml` file to fill in the fields for your portfolio. Please also see the `exampleSite/config.toml` for guidance on setting up the more general site configurations.

### Logo support

Images named `logo.svg` and `logo-dark.svg` are meant to be used for the logos. They should be stored in `static/images` as seen in [./exampleSite/static/images](./exampleSite/static/images). If you wish to change this, the code to control the images is in `assets/js/script.js`.

## Credits

I'd like to express gratitude to [somrat](https://github.com/somratpro/somrat) and [hugrid](https://github.com/aerohub/hugrid) for creating wonderful themes that I have used as a jumping off point. You may notice this theme is very similar in design to somrat, however it has distinct differences by using a manipulated version of hugrid for the portfolio section. I have also trimmed down the features of somrat, to only include what I wanted for a simple theme.

## Contributing

Please feel free to post issues or make pull requests at any time. I am always open to collaboration.
