---
title: Teams плана обновления голосовой связи Contoso
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
description: 'Teams примера голосовой связи для нескольких национальных корпораций: планирование обновления.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822988"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Пример использования Contoso: Teams плана обновления

При принятии решения о переходе с Skype для бизнеса на Teams компания Contoso хочет обеспечить простой переход для конечных пользователей. Вместо того чтобы переключение всех пользователей Teams одновременно, они решили настроить гибридное подключение и использовать метод перекрывающихся возможностей для перемещения пользователей Teams. Это позволило пользователям в Teams и Skype для бизнеса локально делиться сведениями о присутствии и общаться. Когда пользователи ввели пилотный проект для телефонная система, они были перемещены в режим Teams "Только".

Чтобы понять основные понятия об обновлении, методах и режимах, компания Contoso прочитает следующие статьи:

- [Начало перехода на Microsoft Teams](upgrade-start-here.md)
- [Стратегии обновления для ИТ-администраторов](upgrade-to-teams-on-prem-implement.md) 
- [Руководство по миграции и взаимодействию](migration-interop-guidance-for-teams-with-skype.md)
 
Компания Contoso также участвовала в сеансе Ignite 2019, настроив путь от Skype для бизнеса [к Teams](https://myignite.microsoft.com/archives/IG20-OD251). Компания Contoso узнала о следующем:

- Основные понятия, такие как взаимодействие, федерация и поведение обновления 

- Режимы сосуществования и управление на основе TeamsUpgradePolicy 

- Взаимодействие с конечным пользователем для: 

  - Чат и звонки 

  - Планирование собраний 

  - Доступность функций совместной работы в Teams клиентах 

Чтобы спланировать и настроить гибридное подключение, первым шагом в перемещении локальной среды в облако contoso является чтение плана гибридного подключения и настройка гибридного подключения, чтобы понять, как:[](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

  - Настройте локальную службу среды для федерации с Office 365. 

  - Настройте локальную среду для доверия Office 365 и включите общее адресное пространство SIP с Office 365 

  - Включите общее адресное пространство SIP в Office 365 клиента.

  - Используйте режим "Острова" во время технического пилотного проекта.

  - Переключите пользователей в режим TeamsOnly после включения телефонная система. Режим TeamsOnly требуется для плана звонков и прямой маршрутизации.
