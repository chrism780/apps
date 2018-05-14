---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"

---

{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Tutorial Introdução
{: #create}

No {{site.data.keyword.Bluemix}}, é possível construir aplicativos móveis e da web no nível corporativo e aproveitar as extensões de nuvem hospedadas pelo {{site.data.keyword.Bluemix_notm}}. É possível usar o console do {{site.data.keyword.Bluemix}} e as ferramentas de linha de comandos para construir, executar e implementar seus aplicativos. É possível começar com uma das duas maneiras: criar um projeto com um kit do iniciador que gerencia o processo para você ou, se souber o que deseja, construir seu app com os recursos necessários.
{:shortdesc}

É possível usar um kit do iniciador para iniciar rapidamente o seu app e prepará-lo para desenvolvimento futuro. Escolha um kit do iniciador e linguagem de programação, crie um projeto e, em seguida, faça download do código para inspeção imediata. Também é possível criar uma cadeia de ferramentas do DevOps para implementar seu app rapidamente.

Os kits do iniciador estão disponíveis em várias categorias, incluindo:

* [Watson](https://console.bluemix.net/developer/watson){:new_window}
* [Apple](https://console.bluemix.net/developer/appledevelopment){:new_window}
* [Dispositivo móvel](https://console.bluemix.net/developer/mobile){:new_window}
* [App da web](https://console.bluemix.net/developer/appservice){:new_window}
* [Segurança](https://console.bluemix.net/developer/security){:new_window}
<!--* [Watson Data Platform developer console](https://console.bluemix.net/developer/dataplatform)-->
* [Finança](https://console.bluemix.net/developer/finance){:new_window}

## Antes de começar

[Inscreva-se](https://console.bluemix.net){: new_window} para uma conta do {{site.data.keyword.cloud_notm}}. Insira seu e-mail, nome, empresa, região e número do telefone.

Um cartão de crédito não é necessário para a inscrição em uma conta grátis, mas se você inserir um, terá acesso a mais recursos e será fácil entender completamente tudo que o {{site.data.keyword.cloud_notm}} tem a oferecer.

## Etapa 1: Criar um projeto
{: #project}

1. Clique no ícone **Menu** ![Ícone Menu](../icons/icon_hamburger.svg) > **Apps da web**.

2. Clique em **Introdução** na seção **Iniciar na web**.

3. Selecione um kit do iniciador de sua escolha, leia os detalhes e clique em **Criar projeto**.

  Para visualizar o que está incluído no kit do iniciador, expanda o tile no painel Kits do iniciador do serviço de aplicativo.
  {: tip}

4. Nomeie seu projeto, selecione sua linguagem e clique em **Criar projeto**.

Ótimo início! Você acabou de criar um app.

Para inspecionar seu código, clique em **Fazer download do código** na página de detalhes do projeto. Veja o `README.md` no arquivo compactado transferido por download para descobrir se precisa executar mais ações para que seu app entre em execução.
{: tip}

## Etapa 2: Incluir recursos
{: #addResources}

A maioria dos kits do iniciador instrui o {{site.data.keyword.cloud_notm}} a provisionar recursos automaticamente para você. Também é possível associar mais recursos a seu app clicando em **Incluir recurso** na página de detalhes do projeto.

Para desenvolver e executar seu app localmente, use o [{{site.data.keyword.dev_cli_notm}}](../cli/idt/index.html)
{: tip}

## Etapa 3: Implementar no {{site.data.keyword.cloud_notm}}
{: #deploy}

Clique em **Implementar no Cloud** na página de detalhes do projeto, selecione um método de implementação (por exemplo, Cluster do Kubernetes ou App Cloud Foundry) e clique em **Criar**. O {{site.data.keyword.cloud_notm}} cria automaticamente uma cadeia de ferramentas aberta que está completa com um repositório Git e pipeline de entrega contínua. Visualize o componente de pipeline de sua nova cadeia de ferramentas para iniciar o processo inicial de construção e implementação para que seja possível visualizar seu novo app em execução em minutos.

Agora você tem o desenvolvimento iterativo e a entrega contínua configurados.