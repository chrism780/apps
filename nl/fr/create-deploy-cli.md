---

copyright:
  years: 2018
lastupdated: "2018-11-29"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Création et déploiement d'applications à l'aide de l'interface de ligne de commande
{: #developing}

Vous pouvez utiliser l'interface de ligne de commande (CLI) {{site.data.keyword.cloud}} pour créer et déployer votre application. 

Vous pouvez soit créer une toute nouvelle application, soit activer sur le cloud votre code d'application existant.
{: note}

## Avant de commencer
{: #prereqs}

Vous devez installer l'interface CLI {{site.data.keyword.cloud_notm}}, le plug-in d'interface CLI {{site.data.keyword.dev_cli_notm}} et d'autres plug-in et outils recommandés. Pour plus d'informations, voir [Initiation à l'interface de ligne de commande IBM Cloud](/docs/cli/index.html). 

## Création d'une toute nouvelle application de démarrage
{: #create}

La création d'une toute nouvelle application est utile si vous ne disposez pas déjà d'un code existant pour commencer et préférez utiliser un modèle de démarrage de langage ou de structure.

1. Exécutez la commande [`ibmcloud dev create`](/docs/cli/idt/commands.html#create) dans le répertoire de votre choix.
2. Sélectionnez **Service de back-end / Appli Web** comme type d'application.
3. Sélectionnez **Node** comme type de langage.
4. Sélectionnez **Node.js Web App with Express.js (Web App)** comme kit de démarrage à utiliser.
5. Entrez un nom pour votre application et sélectionnez le groupe de ressources à utiliser (si nécessaire). N'ajoutez pas de service pour l'instant.
6. Sélectionnez l'option **IBM DevOps, en utilisant des packs de construction Cloud Foundry** pour créer une chaîne d'outils DevOps. Vous devrez peut-être configurer des clés SSH pour finaliser cette étape.
7. Entrez un nom d'hôte unique, par exemple, `abc-devhost`. Ce nom d'hôte correspond à la route de votre application, `abc-devhost.mybluemix.net`.

La création de l'application et de la chaîne d'outils dure quelques secondes.

## Génération d'actifs de déploiement et d'activation de cloud
{: #byoc}

Cette option peut être utilisée si vous disposez déjà d'un codebase et que vous souhaitez générer des actifs de déploiement et d'activation de cloud pour un microservice ou une application Web en utilisant [`ibmcloud dev enable`](/docs/cli/idt/commands.html#enable). Notez que cette commande est à la version Bêta et que tous les langages et/ou structures d'application ne sont pas pris en charge. Les instructions suivantes présentent comment utiliser cette fonctionnalité avec un référentiel exemple mais la procédure est quasiment identique pour votre propre codebase.

1. Connectez-vous à IBM Cloud en exécutant ibmcloud login puis sélectionnez une organisation et un espace.
2. Clonez l'application [Hello World sample app](https://github.com/IBM-Cloud/node-helloworld) en exécutant la commande suivante dans le répertoire de votre choix.

  ```
  git clone https://github.com/IBM-Cloud/node-helloworld.git
  ```
  {: codeblock}

3. Accédez au répertoire dans lequel vous avez cloné le modèle d'application et exécutez la commande [`ibmcloud dev enable`](/docs/cli/idt/commands.html#enable).
4. Choisissez de continuer sans valider les modifications pour l'instant (si nécessaire).
5. Choisissez de continuer lorsque vous êtes invité à poursuivre avec la langue de noeud qui est détectée.
6. Sélectionnez le groupe de ressources à utiliser (si nécessaire). 
7. Sélectionnez l'option permettant de créer une application {{site.data.keyword.Bluemix_notm}} liée à ce référentiel Git. Pour plus de détails, voir **Remarques importantes**.
8. N'ajoutez pas de service pour l'instant.
9. Attendez quelques secondes que les opérations soient terminées. 
10. Une fois les opérations terminées, vous pouvez fusionner les fichiers de déploiement et d'activation de cloud sauvegardés dans le répertoire de l'application. Tout nouveau fichier marqué `.merge` doit être fusionné en utilisant `git diff` ou un outil similaire.

### Remarques importantes
 - Si vous avez déjà créé une application {{site.data.keyword.cloud_notm}} à l'aide de la console {{site.data.keyword.cloud_notm}}, suivez les étapes 2 à 5 de la section précédente dans votre répertoire de l'application. Pour l'étape 6, vous pouvez choisir de connecter votre code local à une application existante.
 - Vous pouvez également choisir de générer uniquement les fichiers de déploiement et d'activation de cloud sans les connecter à une application {{site.data.keyword.cloud_notm}} en exécutant [`ibmcloud dev enable --no-create`](/docs/cli/idt/commands.html#enable).
 - Pour configurer manuellement une chaîne d'outils et des fichiers de déploiement, suivez [ce guide.](/docs/apps/tutorials/tutorial_byoc_kube.html#tutorial) Cela peut être utile si vous tentez de configurer une chaîne d'outils Continuous Delivery pour plusieurs microservices ou applications Web interconnectés.
 - Si votre codebase existant ne se trouve pas déjà dans un référentiel Git, suivez les étapes 2 à 5 de la section précédente dans votre répertoire de l'application. Pour l'étape 6, vous pouvez choisir de créer une application {{site.data.keyword.cloud_notm}} et de la déployer dans une chaîne d'outils DevOps (qui a un référentiel GitLab nouvellement créé).

## Génération de votre application et exécution de celle-ci localement
{: #build-run}

Quelle que soit l'option que vous avez utilisée pour créer votre application, vous pouvez désormais la générer et l'exécuter localement.

1. Accédez à votre répertoire d'application et assurez-vous que Docker est en cours d'exécution sur votre système.
2. Exécutez la commande [`ibmcloud dev build`](/docs/cli/idt/commands.html#build) pour générer votre application.
3. Exécutez la commande [`ibmcloud dev run`](/docs/cli/idt/commands.html#run) pour commencer à exécuter votre application localement.
4. Visualisez votre application qui s'exécute localement en vous connectant à l'URL `http://localhost:3000` ou à une URL similaire.
5. Appuyez sur les touches **Ctrl+C** pour arrêter votre application.

Vous pouvez également utiliser des [commandes composées](/docs/cli/idt/commands.html#compound), par exemple, `ibmcloud dev build/run`, pour émettre de façon séquentielle une version suivie d'une exécution.
{: tip}

## Ajout d'un service et modification du code
{: #add-service}

Maintenant que votre application peut s'exécuter localement, vous pouvez ajouter un service et modifier du code. 

1. Exécutez la commande [`ibmcloud dev edit`](/docs/cli/idt/commands.html#edit).
2. Suivez les invites pour créer et connecter à votre application un service lié aux données, par exemple, {{site.data.keyword.cloudant_short_notm}}. Il peut être nécessaire de sélectionner une région et un plan pour le service.
3. Vous pouvez choisir de fusionner manuellement les fichiers de configuration sauvegardés dans le répertoire de l'application lors de la création du service. Ou, vous pouvez ignorer cette étape pour le moment.
4. Modifiez votre code. Par exemple, modifiez le fichier `/public/index.html` ou un fichier similaire. Si vous utilisez le modèle d'application `ExpressJS`, vous pouvez remplacer la chaîne `Congratulations!` par `Hello World!`, par exemple.
5. Sauvegardez les fichiers que vous avez modifiés.

## Déploiement d'{{site.data.keyword.Bluemix_notm}}
{: #deploy}

Vous pouvez déployer votre application {{site.data.keyword.Bluemix_notm}} en utilisant une des méthodes ci-dessous, en fonction de la manière dont votre application est configurée. 

### Déploiement de votre application à l'aide d'une chaîne d'outils DevOps
Si vous n'avez pas encore créé de chaîne d'outils DevOps pour votre application et que cette dernière n'est pas encore dans un référentiel Git, vous pouvez exécuter la commande [`ibmcloud dev edit`](/docs/cli/idt/commands.html#edit). Suivez les invites pour configurer DevOps et pour effectuer le déploiement dans une nouvelle chaîne d'outils (et pour créer un nouveau référentiel GitLab).

Une fois que vous avez créé une chaîne d'outils DevOps pour votre application, déployer une nouvelle version revient tout simplement à valider et envoyer votre code vers le répertoire dans votre chaîne d'outils. 

1. Exécutez la commande `git add` .
2. Exécutez la commande `git commit -m "made changes"` pour valider les modifications.
3. Exécutez la commande `git push origin master` pour un envoi vers la branche maître.
4. Affichez la chaîne d'outils DevOps pour votre application à partir de la console {{site.data.keyword.Bluemix_notm}}. Vous pouvez afficher les détails de la chaîne d'outils à partir de l'écran Détails de l'application de la console {{site.data.keyword.Bluemix_notm}} en exécutant la commande [`ibmcloud dev console`](/docs/cli/idt/commands.html#console) à partir du répertoire de l'application.
5. Affichez le pipeline au sein de la chaîne d'outils pour vérifier qu'une nouvelle version a démarré.

### Déploiement manuel de votre application

Vous pouvez déployer manuellement votre application à l'aide de la commande [`deploy`](/docs/cli/idt/commands.html#deploy). Par exemple, procédez comme suit pour déployer manuellement votre application dans Kubernetes.

1. Vérifiez que vous [avez créé un cluster Kubernetes](https://{DomainName}/containers-kubernetes/overview).
2. Exécutez la commande [`ibmcloud dev deploy -t container`](/docs/cli/idt/commands.html#deploy).
3. Lorsque vous y êtes invité, confirmez le nom de l'image de conteneur et de cluster à utiliser.
4. Le déploiement est effectué au bout de quelques minutes.

## Affichage de votre application
{: #view}

1. Pour afficher l'URL de votre application qui s'exécute sur {{site.data.keyword.Bluemix_notm}}, exécutez la commande [`ibmcloud dev view`](/docs/cli/idt/commands.html#view).
2. Pour afficher les détails relatifs aux données d'identification, aux services et à la chaîne d'outils de votre application à partir de la console {{site.data.keyword.Bluemix_notm}}, exécutez la commande [`ibmcloud dev console`](/docs/cli/idt/commands.html#console). 

**Pour signaler des problèmes ou donner votre avis, vous pouvez utiliser le [canal IBM Cloud Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com) - Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**
