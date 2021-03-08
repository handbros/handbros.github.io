---
title: C# 기초 강좌 - 2편(개발 환경 구축)
date: 2021-03-07 00:09:18 +/-1000
categories: [프로그래밍, C# 기초 강좌]
tags: [c#, .net, ide, 개발 환경]
---

# 통합 개발 환경이란?
소스코드라는 것은 말은 거창해보이지만, 그냥 단순한 텍스트의 나열인지라 간단한 메모장 프로그램으로도 충분히 작성이 가능합니다.

하지만 프로그램을 프로그램 답게 만들어주려면 소스코드를 기계어로 번역해주는 '컴파일러', 다른 사람들이 만들어 둔 라이브러리를 가져오는 '패키지 관리자', 디버깅을 도와주는 '디버깅 툴' 등 생각보다 필요한게 많아집니다. 옛날에는 실제로 이런 도구들을 전부 따로 구해서 사용해야했고, 그만큼 프로그래머들의 피로도가 높았었죠.

그런데 어느날 한 프로그래머가 이런 생각을 하게됩니다. '그냥 다 묶어서 하나로 만들어버리는건 어떨까?' 이렇게 해서 등장한 **통합 개발 환경**(이하 'IDE', Integrated Development Environment)은 컴파일러, 디버거, 패키지 관리자, 인텔리 센스 등 수많은 편의기능들을 제공해주며 프로그래머들의 삶에 안락함을 더해줍니다. 아마 IDE가 없었다면 프로그래머들의 수명이 절반은 줄어들지 않았을까요?

# C#을 위한 통합 개발 환경
그렇다면 C#을 위한 IDE에는 어떤 것들이 있을지 한번 알아보도록 합시다.

| 기능 | Visual Studio | Rider |
|:--------------------|:----------:|:----------:|
| 멀티플랫폼 지원 | X | O |
| 유니티 지원 | O | O(강력) |
| 코드 분석 규칙 개수 | 440+ | 1400+ |
| 리팩토리 기능 | 150+ | 1300+ |
| 한국어 지원 | O | X |

개발자의 취향에 따라 다를 수는 있겠지만, 오늘날 가장 많이 쓰이는 C# IDE는 단연 **Visual Studio**와 **Rider**라고 할 수 있겠습니다.

C#의 고향이라 할 수 있는 마이크로소프트 사에서 만든 Visual Studio는 많은 제품들의 순정 버전이 그렇듯이 기본에 충실한 편이고, C#의 새로운 기능에 대한 지원이 빠른 편입니다. 반면에 JetBrains 사의 Rider는 마이크로소프트 중심의 C# 생태계에서 살아남은 만큼, 멀티플랫폼과 강력한 수정 기능을 지원하는 등 다양한 추가기능들을 제공하고 있습니다.

각 IDE마다 장단점이 뚜렷한 만큼 자신이 사용할 IDE를 고르는 것은 개발자 개개인의 자유이지만, 이번 강의에서는 Visual Studio를 중심으로 진행하도록 하겠습니다.

# Visual Studio IDE 설치
우선 아래의 사이트에 접속하여 Visual Studio Community 2019 버전을 다운로드합니다.
 > Visual Studio : <https://visualstudio.microsoft.com/>
 
다운로드 받은 인스톨러를 설치한 뒤 실행시키면 아래와 같은 설치 창이 나타날 것입니다. **'워크로드'** 탭에서는 각 개발 분야에 따라 미리 정의된 도구 모음을 선택할 수 있고, **'개별 구성 요소'** 탭에서는 여러분의 필요에 따라 다른 구성 요소들을 추가하거나 제거할 수도 있습니다.

![Desktop View](https://cdn.jsdelivr.net/gh/handbros/blog-images/contents/csharp_basic/csharp_basic02_01.jpg)
_Visual Studio Installer_

하지만 우리는 C# 개발의 가장 기초가 되는 **콘솔 애플리케이션**을 만들어 볼 예정이므로, .NET 데스크톱 개발 워크로드를 선택하고 설치를 진행해줍시다.

 > **※ 콘솔 애플리케이션(CLI, CUI Application)** : 콘솔 애플리케이션은 텍스트로 이루어진 '콘솔' 내에서 사용자가 지정한 입출력을 처리하는 애플리케이션을 의미함.
 
![Desktop View](https://cdn.jsdelivr.net/gh/handbros/blog-images/contents/csharp_basic/csharp_basic02_02.jpg)
_Visual Studio Installer_

설치 버튼을 누르면 위와 같이 설치가 진행될 것입니다. 이후 설치가 모두 완료될 때까지 기다려줍시다.

![Desktop View](https://cdn.jsdelivr.net/gh/handbros/blog-images/contents/csharp_basic/csharp_basic02_03.jpg)
_Visual Studio Installer_

설치가 완료되었다면, 이제 VisualStudio를 실행할 수 있습니다. 인스톨러의 시작 버튼 또는 시작 메뉴에 등록된 바로가기를 통해 VisualStudio를 실행해봅시다.

![Desktop View](https://cdn.jsdelivr.net/gh/handbros/blog-images/contents/csharp_basic/csharp_basic02_04.jpg)
_Visual Studio Community 2019_

Visual Studio를 실행하면 위와 같은 창이 나타나게됩니다. 저는 어두운 테마를 적용해서 검은색으로 되어있지만, 여러분들은 다른 색으로 되어있을 수도 있으니 참고해주시기 바랍니다.

 > **※ 테마 설정 방법** : '도구(T) > 옵션(O) > 환경 > 일반 > 시각적 효과 > 색 테마(C)'에서 수정 가능

다음 강좌부터는 본격적으로 C# 프로젝트를 만들어보고, C#의 문법과 기능들에 대해 차근차근 알아보도록 하겠습니다.

여기까지 따라오시느라 다들 수고하셨고, 앞으로도 더 좋은 강좌로 찾아뵙도록 하겠습니다.

감사합니다.