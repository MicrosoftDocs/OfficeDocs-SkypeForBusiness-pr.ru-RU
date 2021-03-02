---
title: Обновление локального приложения Skype для бизнеса до Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Узнайте, как обновить организацию до Microsoft Teams с помощью локального развертывания Skype для бизнеса.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bd7d2fad4e4c35a26bcbb435caba5898dd54534
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397554"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Обновление локального приложения Skype для бизнеса до Teams

![Схема пути обновления с акцентом на развертывании и внедрении](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")

Эта статья является частью этапа развертывания и внедрения, которое вы на пути обновления. Прежде чем продолжается, подтвердим, что вы выполнили следующие действия:

-   [Привлечение заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
-   [Определение области проекта](https://aka.ms/SkypetoTeams-Scope)
-   [Понимание сосуществования и совместной работы Skype для бизнеса и Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Выбранный путь обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Подготовлена среда](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Подготовив организацию](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Проводится пилотный проект](https://aka.ms/SkypeToTeams-Pilot)

Если вы развернули локальное развертывание Skype для бизнеса Server или Microsoft Lync и хотите перейти на Teams, следуйте указаниям в этой статье. Вам необходимо настроить гибридное подключение к организации Microsoft 365 или Office 365 и определить требования к сосуществованию при поэтапном перемещении пользователей в Teams.

Прежде чем начать, [ИТ-специалисты](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) и администраторы должны и далее в этой статье рассмотреть важные аспекты, которые необходимо учитывать при работе с локальной сервером Skype для бизнеса Server.

> [!IMPORTANT]
> Поддержка Skype для бизнеса Online будет прекращена 31 июля 2021 г., после чего эта служба больше не будет доступна. Чтобы максимально расширить реализацию преимуществ и убедиться, что у вашей организации есть время на реализацию обновления, мы рекомендуем приступить к использованию Microsoft Teams уже сегодня. Помните, что успешное обновление соответствует технической и пользовательской готовности, поэтому при переходе к Microsoft Teams обязательно используйте эти рекомендации.

## <a name="step-1-configure-hybrid-connectivity"></a>Шаг 1. Настройка гибридного подключения 

Для обновления локального пользователя до Teams необходимо настроить гибридное подключение для локального развертывания Skype для бизнеса Server. 

Начните с чтения [плана гибридного подключения](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и выполните задачи, описанные в описании [настройки гибридного подключения.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Шаг 2. Настройка режима сосуществования (необязательно)

Сосуществование и взаимодействия между клиентами Skype для бизнеса и Teams и пользователями определяются режимами обновления Teams.  По умолчанию организации работают в режиме "О-ва", в котором пользователи могут одновременно использовать одновременно клиенты Teams и Skype для бизнеса.

Режим TeamsOnly является конечным пунктом назначения для каждого пользователя в организации, хотя не всем пользователям необходимо одновременно на назначение TeamsOnly (или любого другого режима).

Прежде чем пользователи будут переначлены в режим TeamsOnly, организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые находятся в режиме TeamsOnly, и пользователями, которых еще нет.  Режимы сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsColetings) обеспечивают простой и предсказуемый опыт для конечных пользователей при переходе организаций со Skype для бизнеса на Teams. 

Когда пользователь находится в любом из режимов Skype для бизнеса, все входящие чаты и звонки перенанаются его клиенту Skype для бизнеса. Чтобы избежать путаницы с конечными пользователями и обеспечить правильную маршрутику, функции звонков и чата в клиенте Teams отключаются, когда пользователь находится в любом из режимов Skype для бизнеса. Кроме того, планирование собраний в Teams явным образом отключается, когда пользователи работают в режиме SfBOnly или SfBWithTeamsCollab, и явно включено, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.

В зависимости от ваших требований можно назначить соответствующий режим сосуществования в зависимости от пути обновления, выбранного вашей организацией. Дополнительные сведения см. в руководстве по миграции и совместной работе организаций, использующих Teams вместе со [Skype](migration-interop-guidance-for-teams-with-skype.md) для бизнеса, а также настройке параметров сосуществования и [обновления.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Шаг 3. Перемещение пользователей из локальной сети Skype для бизнеса в Teams

В конечном итоге необходимо переместить пользователей в режим TeamsOnly. В зависимости от вашей локальной среды это может быть связано с одним или двумя шагами.  

Дополнительные сведения см. в [сведениях](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) о том, как переместить пользователей из локальной сети в облако и переместить пользователей из локальной сети [в Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Шаг 4. Отключение гибридного решения для завершения миграции в облако

После того как вы переместите всех пользователей из локальной службы в облако, вы можете вы эксплуатации локального развертывания Skype для бизнеса. Дополнительные сведения см. в [теме "Отключение гибридного решения для завершения миграции в облако".](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Параметры телефонной системы и связи через ДНР

Телефонная система с Teams поддерживается после того, как пользователь работает в режиме TeamsOnly. (Если пользователь работает в режиме "Острова", телефонная система поддерживается только в Skype для бизнеса.) 

### <a name="pstn-connectivity-options"></a>Параметры подключения через ДНР

При рассмотрите варианты подключения к телефонной сети общего перейти на TeamsOnly в двух возможных сценариях:

- Пользователь в локальной службе Skype для Корпоративная голосовая связь, который будет передвигаться на веб-сайт и использовать план Microsoft Calling. Для переноса этого пользователя в Teams требуется переместить его локальное приложение Skype для бизнеса в облако и координировать перенос с помощью A) переноса номера телефона этого пользователя в план звонков Майкрософт или Б), назначая новый абонентский номер из доступных регионов.  Дополнительные сведения см. в локальной службе Skype для бизнеса Server с Корпоративная голосовая связь [до плана звонков Майкрософт.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Пользователь в локальной службе Skype для Корпоративная голосовая связь, который будет передвигаться на веб-сайт и хранить локальное подключение по ННР. Для переноса этого пользователя в Teams требуется переместить его локальное приложение Skype для бизнеса в облако и координировать переход с миграции пользователя на Direct Routing. Дополнительные сведения см. в локальной Корпоративная голосовая связь Skype для бизнеса Server и [прямой маршрутинге.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Важные моменты для организаций с локальной учетной записью Skype для бизнеса Server

- В следующих статьях описаны важные понятия обновления и сосуществование.
    - [Совместное сосуществование Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
    - [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Для перехода в режим TeamsOnly необходимо настраивать гибридное приложение Skype для бизнеса. Хотя можно использовать Teams в режиме "О-ва" без гибридного решения, переход в режим TeamsOnly невозможен, пока пользователь не будет перемещен из локальной системы Skype для бизнеса в Skype для бизнеса Online (с помощью [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Дополнительные сведения см. [в сведениях о настройке гибридного подключения.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Если в вашей организации используется Skype для бизнеса Server и вы не настроили гибридное подключение, но все равно хотите использовать Teams, для администрирования функций Teams необходимо использовать учетную запись администратора с доменом .onmicrosoft.com. 

- Пользователи Teams с локальной учетной записью Skype для бизнеса (то есть еще не перемещены в облако с помощью Move-CsUser) не могут работать с пользователями Skype для бизнеса и не могут федерироваться с внешними пользователями. Эта функция доступна только после того, как пользователи перемещаются в облако (в режиме "Острова" или как пользователи TeamsOnly). 

- Если у вас есть пользователи с локальной учетной записью Skype для бизнеса, назначить режим TeamsOnly на уровне клиента невозможно. Для завершения миграции в облако необходимо сначала переместить всех пользователей с локальной учетной записью Skype для бизнеса в облако, а затем отключить гибридную `Move-CsUser` [долю.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` не будет работать на уровне клиента, если обнаружена запись DNS lyncdiscover, которая указывает на расположение, которое не является Office 365.

- Убедитесь, что пользователи правильно синхронизированы с Azure AD с правильными атрибутами Skype для бизнеса. Все эти атрибуты являются префиксами msRTCSIP-. Если пользователи не синхронизированы с Azure AD надлежащим образом, средства управления в Teams не смогут управлять этими пользователями. (Например, вы не сможете назначать политики Teams пользователям локальной сети, если не синхронизируете эти атрибуты надлежащим образом.) Дополнительные сведения см. в [настройках Azure AD Connect для Teams и Skype для бизнеса.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Чтобы создать нового пользователя TeamsOnly или Skype для бизнеса Online в гибридной организации, необходимо сначала включить его в локальной организации Skype для бизнеса *Server,* а затем переместить его из локальной сети в облако с помощью Move-CsUser.  При создании пользователя в локальной сети все остальные оставшиеся пользователи Skype для бизнеса смогут перенау числеть созданному пользователю маршрут. После того как все пользователи будут перемещены в интернет-сеть, их больше не нужно будет сначала включить в локальной сети.

- При перемещении пользователя из локальной службы в облако собрания, организованные этим пользователем, переносются в Skype для бизнеса Online или Teams в зависимости от того, указан ли переключатель -MoveToTeams.

- Если вы хотите, чтобы в клиенте Skype для бизнеса отображались уведомления для пользователей локальной сети, используйте TeamsUpgradePolicy в локальном средстве. Для пользователей локальной сети имеет значение только параметр NotifySfbUsers.  Пользователи локальной сети получают свой режим от интернет-экземпляров TeamsUpgradePolicy. См. примечания [в Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Все новые клиенты, созданные после 3 сентября 2019 г., создаются как клиенты TeamsOnly, если в организации не развернуто локальное развертывание Skype для бизнеса Server. Корпорация Майкрософт использует записи DNS для идентификации локальной организации Skype для бизнеса Server. Если в вашей организации есть локальное приложение Skype для бизнеса Server без общедоступных записей DNS, вам потребуется позвонить в службу поддержки Майкрософт, чтобы получить более новую ссылку на клиент. 

## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)