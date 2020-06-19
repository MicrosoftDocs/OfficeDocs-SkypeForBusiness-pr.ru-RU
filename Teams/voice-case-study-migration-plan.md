---
title: Исследование успеха в голосовых сообщениях в Teams contoso
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
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786090"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Исследование успеха Contoso: план обновления Teams

При принятии решения о переходе с Skype для бизнеса на Teams компания Contoso хотела бы предоставить для конечных пользователей простой интерфейс переходов. Вместо того чтобы переключаться между участниками в Teams, вы решили настроить гибридное подключение и использовать метод перекрытия для перемещения пользователей в Teams. Это позволило пользователям в Teams и Skype для бизнеса быть в локальной сети для совместного использования информации о присутствии и общении. После того как пользователи вводили пилотный проект для телефонной системы, они были перемещены в режим "только для Teams".

Для ознакомления с основными понятиями, посвященными обновлению, методам и режимам, компания Contoso прочитала следующие статьи:

- [Начало перехода на Microsoft Teams](upgrade-start-here.md)
- [Переход со Skype для бизнеса на Teams](upgrade-to-teams-on-prem-overview.md) 
- [Руководство по миграции и взаимодействию](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso также посетил сеанс Ignite 2019, [разрабатывая свой путь из Skype для бизнеса в Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). Сведения о том, что Contoso узнали:

- Основные понятия, такие как взаимодействие, интеграция и поведение обновления 

- Режимы сосуществования и управление на основе TeamsUpgradePolicy 

- Взаимодействие с пользователем: 

  - Чат и звонки 

  - Планирование собраний 

  - Доступность функций совместной работы в клиентах Teams 

Для планирования и настройки гибридного подключения сначала необходимо переместить локальную среду в облако, план чтения Contoso для [гибридного подключения](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) и [настроить гибридное подключение](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) , чтобы понять, как это сделать: 

  - Настройте локальную службу среды на Федерацию с Office 365. 

  - Настройка локальной среды для доверия к Office 365 и включение общего пространства адресов SIP с помощью Office 365 

  - Включите общее адресное пространство SIP в своем клиенте Office 365.

  - Использование режима "острова островов" во время технического проекта.

  - Переключение пользователей в режим TeamsOnly после включения пользователя для телефонной системы. Для тарифного плана и прямой маршрутизации требуется режим TeamsOnly. 
