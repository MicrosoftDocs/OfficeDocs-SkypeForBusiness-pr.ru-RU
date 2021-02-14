---
title: Пример дела с голосовой почтой Contoso в Teams
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
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786114"
---
# <a name="contoso-case-study-audio-conferencing"></a>Пример работы с Contoso: аудиоконференция

Чтобы получить общее представление об аудиоконференциях, их стоимости, доступности и работе в Contoso, мы просмотрели их в &mdash; &mdash; Office [365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Обзор 

Для аудиоконференции в Contoso использовались номера телефонов, хорошо известные как для организации, так и для внешних организаций. Так как компания Contoso хочет обслуживать эти номера по возможности, она просмотрела сведения о назначении выделенных и общих номеров телефонов мосту аудиоконференции. 

На основе исследований компания Contoso принимает следующие решения: 

- Лицензии на аудиоконференцию получит только та часть людей, которые регулярно проводят аудиоконференцию. 

- Contoso использует выделенные телефонные номера и переносит существующие номера для использования с аудиоконференцией.   

Так как пользователи Contoso использовали Skype для бизнеса, а почтовые ящики всех пользователей находятся в сети, у многих пользователей уже запланировано собрание. Если вы используете службу переноса собраний [(MMS),](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) contoso прочитает статью о том, что существующие собрания для Contoso обновляются автоматически при смене пользователя на режим TeamsOnly.  


## <a name="configuration"></a>Конфигурация

Телефонные номера, связанные с аудиоконференцией, называются номерами служб в телефонной системе. 

- Для местоположений, использующих планы звонков, для переноса существующих номеров телефонов от оператора связи в Office 365 компания Contoso, как и при получении номеров телефонов службы, придерживается [действий.](getting-service-phone-numbers.md)

- Чтобы назначить лицензию на аудиоконференцию пользователю в пилотном проекте, администратор Contoso следовал за действиями, которые были предприняты в параметрах аудиоконференции для вашей [организации.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- В пилотном проекте и миграции Компания Contoso использовала групповое лицензирование с помощью действий, следующих в процедуре назначения лицензий пользователям по признаку участия в группах [в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

 