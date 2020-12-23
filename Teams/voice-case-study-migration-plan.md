---
title: Пример дела с голосовой командой Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Пример голосовой работы Teams для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786090"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Пример: план обновления Teams

При переходе со Skype для бизнеса на Teams компания Contoso хотела предоставить пользователям простой способ перехода. Вместо одновременного переключения всех пользователей в Teams было принято решение настроить гибридное подключение и использовать метод перекрывания для перемещения пользователей в Teams. Это позволило пользователям в локальной сети Teams и Skype для бизнеса обмениваться информацией о присутствии и общаться. Когда пользователи ввели пилотный проект для телефонной системы, они были перемещены в режим только Teams.

Чтобы понять основные понятия обновления, методов и режимов, Contoso прочитает следующие статьи:

- [Начало перехода на Microsoft Teams](upgrade-start-here.md)
- [Переход со Skype для бизнеса на Teams](upgrade-to-teams-on-prem-overview.md) 
- [Руководство по миграции и интерперсивности](migration-interop-guidance-for-teams-with-skype.md)
 
Компания Contoso также участвовала в сеансе Ignite 2019, в котором вы можете найти путь от Skype для бизнеса [до Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Мы узнали о:

- Основные понятия, такие как взаимосвязи, федерация и обновление 

- Режимы сосуществования и управление на основе TeamsUpgradePolicy 

- Пользовательский интерфейс для: 

  - Чат и вызовы 

  - Планирование собраний 

  - Доступность функций совместной работы в клиентах Teams 

Чтобы спланировать и настроить гибридное подключение, первым этапом перемещения локальной среды [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) в облако contoso читайте статью "Планирование гибридного подключения" и "Настройка гибридного подключения", чтобы понять, как это сделать: [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

  - Настройка локальной службы среды для федерации с помощью Office 365. 

  - Настройка доверия к Office 365 в локальной среде и включить общее адресное пространство SIP в Office 365 

  - Включить общее адресное пространство SIP в клиенте Office 365.

  - Используйте режим "Острова" во время технического пилотного проекта.

  - Переключение пользователей в режим TeamsOnly после включения телефонной системы. Режим TeamsOnly требуется для планов звонков и прямой маршрутации. 
