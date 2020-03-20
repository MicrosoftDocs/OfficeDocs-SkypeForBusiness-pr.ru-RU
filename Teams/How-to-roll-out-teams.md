---
title: Как выполнить развертывание Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 1/28/2019
ms.reviewer: LolaJ
audience: admin
description: Найдите подходящий способ развертывания Microsoft Teams в вашей организации.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd2610b5c536c1e00ae127f83a3e03942f2b6c03
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858544"
---
# <a name="how-to-roll-out-microsoft-teams"></a>Как выполнить развертывание Microsoft Teams

## <a name="start-here"></a>С чего начать
Не имеет значения, является ли ваша организация представителем малого бизнеса или транснациональной корпорацией, развертывание Teams необходимо начать со знакомства со статьей [Начало работы](get-started-with-teams-quick-start.md). Это поможет вам выполнить развертывание Teams в небольших масштабах, чего бывает достаточно, если у вас небольшая компания. Если вы являетесь крупной организацией, используйте информацию в статье [Начало работы](get-started-with-teams-quick-start.md) для пилотного развертывания Teams в небольшой группе первых пользователей, что позволит получить представление о Teams и узнать, как спланировать развертывание в масштабе всей организации. 

## <a name="recommended-path-to-teams"></a>Рекомендуемый способ развертывания Teams


Мы рекомендуем выполнять развертывание Teams поэтапно, от рабочей нагрузки к рабочей нагрузке, по мере готовности вашей организации. **Вам не придется ждать завершения одного этапа для перехода к следующему.** Некоторым организациям может потребоваться развертывание всех функций Teams одновременно, тогда как другие предпочитают поэтапный подход. Ниже приведены рабочие нагрузки Teams в порядке, в котором мы рекомендуем выполнять их развертывание.

- [Начало работы](get-started-with-teams-quick-start.md)
- [Чат, команды, каналы и приложения](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Собрания и конференции](deploy-meetings-microsoft-teams-landing-page.md)
- [Голосовая связь в облаке](cloud-voice-landing-page.md)

[Хаб адаптации](adopt-microsoft-teams-landing-page.md): во время развертывания Teams обязательно воспользуйтесь данными ресурсами для ускорения внедрения Teams.

![Схема, иллюстрирующая пути развертывания Teams](media/how-to-roll-out-teams-image1.png)


## <a name="if-youre-starting-from-skype-for-business-on-premises-or-hybrid-deployments"></a>Если вы начинаете работу со Skype для бизнеса, используйте локальное или гибридное развертывание

Если вы пришли к Teams через Skype для бизнеса (онлайн версия или локальная версия) или вам нужна гибридная конфигурация, мы все равно рекомендуем следовать указанному выше [рекомендованному пути](#recommended-path-to-teams) при развертывании Teams, но в этом случае вам потребуется дополнительное планирование. Начните со знакомства с инструкциями, приведенным в таблице ниже, которые отвечают профилю вашей организации.



|  |Профиль вашей организации|Рекомендации  |
|---------|---------|---------|
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-blue.svg" alt="An icon representing migration" height="50" width="50">|В настоящее время я использую Skype для бизнеса Online, и все готово к переходу на Teams. |Перейдите в раздел [Переход на Teams](upgrade-start-here.md).        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-blue.svg" alt="An icon representing hybrid connectivity" height="50" width="50">|В настоящий момент моя организация использует Skype для бизнеса Server, и я хочу выполнить развертывание Teams. |Для полномасштабного развертывания Teams необходимо настроить гибридное соединение между вашей локальной средой и Microsoft 365. Начните со знакомства со статьей [Планирование гибридного соединения Skype для бизнеса Server и Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). <br><br>Вам также следует изучить [Переход на Teams](upgrade-start-here.md).    |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises.svg" alt="An icon representing an on-premises solution" height="50" width="50">|У меня нет Skype для бизнеса Server, но я использую локального решение PSTN. Я хочу выполнить развертывание Teams, но хочу сохранить мое локальное решение PSTN. |Выполните развертывание Teams согласно [рекомендуемому пути](#recommended-path-to-teams) выше.<br><br>Затем ознакомьтесь со статьей [Планирование прямой маршрутизация](direct-routing-plan.md), чтобы получить представление об использовании прямой маршрутизации телефонной системы для подключения локального решение PSTN к Teams.|
|


