---
title: Teams плана обновления голосовой почты Contoso
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
description: 'Teams, как использовать голосовые команды для многоязычной корпорации: планирование обновления.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: a458f2c98b0f6de8bc2d3b3d23e2b68e4cadd931
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587448"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Пример: план обновления Teams Contoso

При переходе с Skype для бизнеса на Teams компания Contoso хочет обеспечить простой переход для конечных пользователей. Вместо того чтобы одновременно Teams все пользователи, они решили настроить гибридное подключение и использовать перекрывающиеся возможности для перемещения пользователей в Teams. Это позволило пользователям в Teams и Skype для бизнеса локально делиться информацией о присутствии и общаться. Когда пользователи ввели пилотный проект для телефонная система, они были перемещены в режим Teams только для пользователей.

Чтобы понять основные понятия обновления, методов и режимов, Contoso прочитает следующие статьи:

- [Начало перехода на Microsoft Teams](upgrade-start-here.md)
- [Стратегии обновления для ИТ-администраторов](upgrade-to-teams-on-prem-implement.md) 
- [Руководство по миграции и взаимосвязи](migration-interop-guidance-for-teams-with-skype.md)
 
Компания Contoso также участвовала в сеансе Ignite 2019, в котором был проектирование пути от Skype для бизнеса [до Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso узнал о:

- Основные понятия, такие как interoperability, federation и upgrade behavior 

- Режимы сосуществования и управление на основе TeamsUpgradePolicy 

- Пользовательский интерфейс для: 

  - Чат и вызовы 

  - Планирование собраний 

  - Доступность функций совместной работы в Teams клиентах 

Чтобы спланировать и настроить гибридное подключение, первым шагом в перемещении локальной [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) среды в [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) облако contoso является планирование гибридного подключения и Настройка гибридного подключения, чтобы понять, как это сделать: 

  - Настройте службу локальной среды для федерации с помощью Office 365. 

  - Настройте в своей локальной среде доверительные Office 365 и встройте общее адресное пространство SIP с Office 365 

  - Включить общее адресное пространство SIP в Office 365 клиента.

  - Используйте режим "Острова" во время технического пилотного проекта.

  - Переключение пользователей в режим TeamsOnly после включения телефонная система. Режим TeamsOnly требуется для планирования звонков и прямой маршрутации.
