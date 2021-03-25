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
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121307"
---
# <a name="contoso-case-study-audio-conferencing"></a>Пример: аудиоконференция в Contoso

Чтобы получить общее представление об аудиоконференции, ее стоимости, доступности и работе в Contoso, она была рассмотрена в &mdash; &mdash; Office [365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Обзор 

Для аудиоконференции в Contoso использовались номера телефонов, хорошо известные как для организации, так и для внешних организаций. Так как компания Contoso хочет обслуживать эти номера по возможности, она просмотрела сведения о назначении выделенных и общих номеров телефонов мосту аудиоконференции. 

На основе исследований компания Contoso принимает следующие решения: 

- Лицензии на аудиоконференцию получит только та часть людей, которые регулярно проводят аудиоконференцию. 

- Contoso использует выделенные телефонные номера и переносит существующие номера для использования с аудиоконференцией.   

Так как пользователи Contoso использовали Skype для бизнеса, а почтовые ящики всех пользователей находятся в сети, у многих пользователей уже запланировано собрание. Если вы используете службу переноса собраний [(MMS),](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) contoso прочитает статью о том, что существующие собрания для Contoso обновляются автоматически при смене пользователя на режим TeamsOnly.  


## <a name="configuration"></a>Конфигурация

Телефонные номера, связанные с аудиоконференцией, называются номерами служб в телефонной системе. 

- Для местоположений, использующих планы звонков, для переноса существующих номеров телефонов от оператора связи в Office 365 компания Contoso, как и при получении номеров телефонов службы, придерживается [действий.](getting-service-phone-numbers.md)

- Чтобы назначить лицензию на аудиоконференцию пользователю в техническом пилотном проекте, администратор Contoso следовал за действиями, которые были предприняты в области "Управление настройками аудиоконференций" для вашей [организации.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- В пилотном проекте и миграции компания Contoso использовала групповое лицензирование, выровнив по шагам из процедуры назначения лицензий пользователям по признаку участия в группах [в Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

