---
title: Обновление локальной версии Skype для бизнеса на Microsoft Teams | Развертывание | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Рекомендации по обновлению до Teams в локальной среде Skype для бизнеса.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b41de8f54eb0e2a09e7e3700b25cba1e5564f0a
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "34288190"
---
![Этапы поездки на обновление, акцент на этапе развертывания и реализации] (media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")

Эта статья входит в стадию развертывания и внедрения вашего путешествия по обновлению. Перед продолжением убедитесь, что выполнены следующие действия:

- [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
- [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
- [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовка среды](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Подготовка Организации](https://aka.ms/SkypeToTeams-UserReadiness)
- [Пробные испытания](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Переход с локального развертывания Skype для бизнеса на Teams

Следуйте указаниям, приведенным в этой статье, если вы разработали Skype для бизнеса или Microsoft Lync в локальной среде, и ваша организация хочет выполнить обновление до Microsoft Teams с использованием нескольких режимов сосуществования или все. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Действие 1: развертывание гибридного подключения

Ключевым условием для обновления пользователей до Teams является развертывание гибридного подключения.

Дополнительные сведения можно найти в разделе [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Шаг 2: реализация выбранного пути обновления для Организации

После того как вы закончите развертывание гибридной конфигурации, вы можете запланировать перенос пользователей в Office 365.

Дополнительные сведения можно найти в следующих случаях:

- [Теамсупградеполици: управление миграцией и](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)сосуществованием.

- [Переместить пользователей из локальной сети в Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и команды

Переход с локальной телефонной системы на Teams позволит вам использовать возможности прямой маршрутизации ("прямая маршрутизация") или планы звонков, предоставленные корпорацией Майкрософт для Office 365.

Если вы не используете тарифные планы в Office 365, вам нужно перевести свое развертывание по своему раскладю на телефонную систему с прямой маршрутизацией в рамках обновления до Teams.

Дополнительные сведения можно найти в разделе [Дополнительные рекомендации по прямой маршрутизации телефонной системы](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Если вы планируете использовать планы звонков в Office 365, ознакомьтесь с нашими рекомендациями по [переносу ваших номеров телефонов в office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).