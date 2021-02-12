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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578172"
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

> [!IMPORTANT]
> Поддержка Skype для бизнеса Online будет прекращена 31 июля 2021 г., после чего эта служба больше не будет доступна. Чтобы максимально расширить реализацию преимуществ и убедиться, что у вашей организации есть время на реализацию обновления, мы рекомендуем приступить к использованию Microsoft Teams уже сегодня. Помните, что успешное обновление соответствует технической и пользовательской готовности, поэтому при переходе к Microsoft Teams обязательно используйте эти рекомендации.

## <a name="step-1-configure-hybrid-connectivity"></a>Шаг 1. Настройка гибридного подключения 

Для обновления локального пользователя до Teams необходимо настроить гибридное подключение для локального развертывания Skype для бизнеса Server. 

Начните с чтения [плана гибридного подключения](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и выполните задачи, описанные в описании [настройки гибридного подключения.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Шаг 2. Настройка режима сосуществования (необязательно)

Сосуществование и взаимодействия между клиентами и пользователями Skype для бизнеса и Teams определяются режимами обновления Teams.  По умолчанию организации работают в режиме "О-ва", в котором пользователи могут одновременно использовать одновременно клиенты Teams и Skype для бизнеса.

Режим TeamsOnly является конечным пунктом назначения для каждого пользователя в организации, хотя не всем пользователям необходимо одновременно на назначение TeamsOnly (или любого другого режима).

До того как пользователи не достигнете режима TeamsOnly, организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые находятся в режиме TeamsOnly, и пользователями, которых еще нет.  Режимы сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsColetings) обеспечивают простой и предсказуемый опыт для конечных пользователей при переходе организаций со Skype для бизнеса на Teams. 

Когда пользователь находится в любом из режимов Skype для бизнеса, все входящие чаты и звонки перенанаются его клиенту Skype для бизнеса. Чтобы избежать путаницы с конечными пользователями и обеспечить правильную маршрутику, функции звонков и чата в клиенте Teams отключаются, когда пользователь находится в любом из режимов Skype для бизнеса. Кроме того, планирование собраний в Teams явным образом отключается, когда пользователи работают в режиме SfBOnly или SfBWithTeamsCollab, и явно включено, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.

В зависимости от ваших требований можно назначить соответствующий режим сосуществования в зависимости от пути обновления, выбранного вашей организацией. Дополнительные сведения см. в руководстве по миграции и совместной работе организаций, использующих Teams вместе со [Skype](migration-interop-guidance-for-teams-with-skype.md) для бизнеса, а также настройке параметров сосуществования и [обновления.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Шаг 3. Перемещение пользователей из локальной сети Skype для бизнеса в Teams

В конечном итоге необходимо переместить пользователей в режим TeamsOnly. Это может быть связано с одним или двумя шагами в зависимости от вашей локальной среды.  

Дополнительные сведения см. в [сведениях](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) о том, как переместить пользователей из локальной сети в облако и переместить пользователей из локальной сети [в Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Шаг 4. Отключение гибридного решения для завершения миграции в облако

После того как вы переместите всех пользователей из локальной службы в облако, вы можете вы эксплуатации локального развертывания Skype для бизнеса. Дополнительные сведения см. в [теме "Отключение гибридного решения для завершения миграции в облако".](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Параметры телефонной системы и связи через ДНР

Телефонная система с Teams поддерживается после того, как пользователь работает в режиме TeamsOnly. (Если пользователь работает в режиме "Острова", телефонная система поддерживается только в Skype для бизнеса.) 

### <a name="pstn-connectivity-options"></a>Параметры подключения через ДНР

При рассмотрите варианты подключения к телефонной сети общего перейти на TeamsOnly в двух возможных сценариях:

- Пользователь в локальной службе Skype для Корпоративная голосовая связь, который будет передвигаться на веб-сайт и использовать план Microsoft Calling. Для переноса этого пользователя в Teams требуется переместить его локальное приложение Skype для бизнеса в облако и координировать перенос с помощью A) переноса номера телефона этого пользователя в план звонков Майкрософт или Б), назначая новый абонентский номер из доступных регионов.  Дополнительные сведения см. в локальной службе Skype для бизнеса Server с Корпоративная голосовая связь [до плана звонков Майкрософт.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Пользователь в локальной службе Skype для Корпоративная голосовая связь, который будет передвигаться на веб-сайт и хранить локальное подключение по ННР. Для переноса этого пользователя в Teams требуется переместить его локальное приложение Skype для бизнеса в облако и координировать переход с миграцией пользователя на Direct Routing. Дополнительные сведения см. в локальной Корпоративная голосовая связь Skype для бизнеса Server и [прямой маршрутинге.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
