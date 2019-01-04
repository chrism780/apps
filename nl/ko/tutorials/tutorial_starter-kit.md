---

copyright:
  years: 2018
lastupdated: "2018-11-29"

---

{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# 스타터 킷을 사용한 앱 작성
{: #create_starterkit}

스타터 킷을 사용하여 앱을 사용 가능하도록 신속히 작성하고 이후의 개발을 위해 준비할 수 있습니다. 스타터 킷 및 프로그래밍 언어를 선택하고, 앱을 작성한 후 DevOps 도구 체인을 설정하여 앱을 자동으로 배치하십시오. 바로 검사하기 위해 코드를 다운로드할 수도 있습니다.
{: shortdesc}

빌드 옵션을 직접 사용자 정의하려는 경우 공백인 경우를 포함하여 스타터 킷 선택에서 앱을 작성할 수 있습니다. 어느 쪽이든 DevOps 도구 체인이 앱 배치를 위해 자동으로 작성됩니다. 바로 검사하기 위해 코드를 다운로드할 수도 있습니다.

스타터 킷은 다음 항목을 포함한 다양한 카테고리에서 사용 가능합니다.
* [Watson ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/watson/dashboard){:new_window}
* [Apple ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/appledevelopment/dashboard){:new_window}
* [모바일 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/mobile/dashboard){:new_window}
* [웹 앱 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/appservice/dashboard){:new_window}
* [보안 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/security/dashboard){:new_window}
* [재정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/finance/dashboard){:new_window}

## 1단계. 앱 작성
{: #create-app}

1. [{{site.data.keyword.cloud}} 대시보드](https://{DomainName})에서 **메뉴** 아이콘 ![메뉴 아이콘](../../icons/icon_hamburger.svg) > **웹 앱**을 클릭하십시오. 

2. **웹에서 시작** 섹션에서 **시작하기**를 클릭하십시오.

3. 원하는 스타터 킷을 선택하고, 세부사항을 읽은 후 **작성**을 클릭하십시오.
    
    스타터 킷에 무엇이 포함되어 있는지 보려면 [앱 서비스 스타터 킷 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/developer/appservice/starter-kits){:new_window} 대시보드에서 타일을 펼치십시오. "앱 작성" 스타터 킷 옵션은 공백 스타터 앱으로서 사용될 수 있으며, 사용자 요구사항에 맞게 추가로 사용자 정의가 가능합니다.
    {: tip}

4. 앱에 이름을 지정하고, 언어를 선택한 후 **작성**을 클릭하십시오.
    
    시작이 좋습니다! 앱이 작성되었습니다.

코드를 검사하려면, 앱 세부사항 페이지에서 **코드 다운로드**를 클릭하십시오. 다운로드된 압축 파일에 있는 `README.md` 파일을 확인하여 스타터 앱을 시작하고 실행하기 위해 추가 조치를 수행해야 하는지 알아보십시오.
{: tip}

자세한 정보는 [스타터 킷으로 기본 웹 앱 작성](/docs/apps/tutorials/tutorial_web.html)을 참조하십시오.

## 2단계. 리소스 추가
{: #add-services}

Watson의 코그너티브 기능으로 앱을 향상시키는 리소스를 추가하고 모바일 서비스 또는 보안 서비스를 추가할 수 있습니다. 이 튜토리얼의 경우 데이터를 관리할 위치를 추가하십시오.

1. 앱 서비스 창에서 **리소스 추가**를 클릭하십시오.
2. 원하는 서비스의 종류를 선택하십시오. 예를 들어, **데이터** > **다음** > **Cloudant** > **다음**을 선택하십시오.
3. 가격 플랜을 선택하십시오. 이 튜토리얼에 사용할 수 있는 무료 옵션이 있습니다.
4. **작성**을 클릭하십시오.

## 3단계. {{site.data.keyword.cloud_notm}}에 배치
{: #deploy}

앱 세부사항 페이지에서 **Cloud에 배치**를 클릭하고 배치 방법(예: Kubernetes 클러스터 또는 Cloud Foundry 앱)을 선택한 후 **작성**을 클릭하십시오. {{site.data.keyword.cloud_notm}}가 Git 저장소와 지속적 Delivery Pipeline을 모두 갖춘 공개 도구 체인을 자동으로 작성합니다. 새 도구 체인의 파이프라인 컴포넌트를 열어 초기 빌드 및 배치 프로세스를 시작하고 나면 몇 분 내에 새 앱을 확인할 수 있습니다.

명령행에서 앱을 배치하려면 `ibmcloud dev deploy`를 사용하십시오. 자세한 정보는 [CLI를 사용하여 앱 작성 및 배치](/docs/apps/create-deploy-cli.html)를 참조하십시오.