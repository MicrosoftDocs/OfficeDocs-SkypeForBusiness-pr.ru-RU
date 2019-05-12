---
title: Обновление Скайп для бизнеса локальных групп, корпорация Майкрософт | Развертывание | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группам из Скайп for Business локальное развертывание.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7c5c4bfe6cf1ecac0e37600854941741a837480
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911428"
---
![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")

В этой статье является частью развертывания и внедрения этапа обновления пути. Прежде чем продолжить, убедитесь, что вы выполните следующие действия:

- [Прикреплено другие заинтересованные стороны проекта](upgrade-enlist-stakeholders.md)
- [Определенные области проекта](https://aka.ms/SkypetoTeams-Scope)
- [Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбранные обновления пути](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовка среды](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Подготовлено вашей организации](https://aka.ms/SkypeToTeams-UserReadiness)
- [Проведение пилотного проекта](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Обновление с Скайп для локального развертывания Business по группам

Следуйте рекомендациям в статье в этой статье, если развернута Скайп для бизнеса или Microsoft Lync локальные пользователи и организации необходимо обновить групп, либо выборочно — с помощью нескольких режимах совместная работа — или файловый. Первым этапом является настройка гибридного подключения с помощью клиента Office 365 и переместите пользователей Скайп для бизнеса в Интернет и назначить их соответствующие сосуществования и режим обновления.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Шаг 1: Развертывание гибридного подключения

Ключевые необходимые компоненты для обновления пользователей группам — для развертывания гибридного подключения. Для этого может потребоваться развертывание нового внешнего подключения для вашего существующего Скайп развертывания для бизнеса или Lync или просто Настройка гибридных связь с помощью клиента Office 365.

Дополнительные сведения можно [Развернуть гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-move-users-to-skype-for-business-online"></a>Шаг 2: Перемещение пользователей в Скайп для бизнеса в Интернет

По завершении настройки гибридной перемещение пользователей в Скайп для бизнеса в Интернет.

Дополнительные сведения можно [переместить пользователей из локально на Скайп для бизнеса в Интернет](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Шаг 3: Назначьте сосуществования и режим обновления

После переноса пользователей к Скайп для бизнеса в Интернет, их можно назначить соответствующие сосуществования режим по пути обновления, принято решение вашей организации. Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> С Скайп Business Server 2019 и будущих накопительного обновления Скайп для Business Server 2015 можно будет выполнять шаг 2 (переход на Скайп для бизнеса в Интернет) и шаг 3 (обновления пользователей группам) за один шаг. Дополнительные сведения будут предоставлены после выпуска Скайп для Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системой и рабочих групп

При переносе данных вашей Скайп для локального развертывания Business от корпоративной голосовой связи для телефонной системы с помощью вызова планы и Майкрософт будет ваш поставщик телефонной сети (общего пользования PSTN), и при условии, что вы выполнили номер телефона Перенос — обновление пользователей группам автоматический переход входящих звонков ТСОП для групп.

Вызов планы недоступен, требуется ли перенос развертывания корпоративной голосовой связи для прямой маршрутизации Microsoft телефонной системы. Обновление пользователей в группы, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).
