---
title: Как выполнить развертывание Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
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
ms.openlocfilehash: 48756dc6fdcbe2c289abb08b803b169fdb6cee58
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928432"
---
# <a name="how-to-roll-out-microsoft-teams"></a>Как выполнить развертывание Microsoft Teams

## <a name="start-here"></a>С чего начать
Не имеет значения, является ли ваша организация представителем малого бизнеса или транснациональной корпорацией, развертывание Teams необходимо начать со знакомства со статьей [Начало работы](get-started-with-teams-quick-start.md). В ней рассматривается мелкомасштабное развертывание Teams, которого может быть достаточно для вас, если вы представитель малого бизнеса или развертываете Teams на скорую руку в рамках первой рабочей нагрузки в Office 365 для поддержки **удаленных сотрудников**. Если вы являетесь крупной организацией, используйте информацию в статье [Начало работы](get-started-with-teams-quick-start.md) для пилотного развертывания Teams в небольшой группе первых пользователей, что позволит получить представление о Teams и узнать, как спланировать развертывание в масштабе всей организации. 

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
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-teams.svg" alt="Migration arrow symbol" height="50" width="50">|В настоящее время я использую Skype для бизнеса Online, и все готово к переходу на Teams. |Перейдите в раздел [Переход на Teams](upgrade-start-here.md).        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-teams.svg" alt="Hybrid symbol" height="50" width="50">|В настоящий момент моя организация использует Skype для бизнеса Server, и я хочу выполнить развертывание Teams. |Для полномасштабного развертывания Teams необходимо настроить гибридное соединение между вашей локальной средой и Microsoft 365. Начните со знакомства со статьей [Планирование гибридного соединения Skype для бизнеса Server и Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). <br><br>Вам также следует изучить [Переход на Teams](upgrade-start-here.md).   |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises-teams.svg" alt="On premises symbol" height="50" width="50">|У меня нет Skype для бизнеса Server, но я использую локального решение PSTN. Я хочу выполнить развертывание Teams, но хочу сохранить мое локальное решение PSTN. |Выполните развертывание Teams согласно [рекомендуемому пути](#recommended-path-to-teams) выше.<br><br>Затем ознакомьтесь со статьей [Планирование прямой маршрутизация](direct-routing-plan.md), чтобы получить представление об использовании прямой маршрутизации телефонной системы для подключения локального решение PSTN к Teams.|
|


