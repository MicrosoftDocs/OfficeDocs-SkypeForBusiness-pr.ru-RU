---
title: Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения об отправке пользователям сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: dc48f427fa0b2013332c5ef34d40bad94cea0a75
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754699"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams

Иногда пользователям Microsoft Teams требуется, чтобы вы отправляли им информацию об аудиоконференциях. Вы можете сделать это, выбрав пункт **Отправить сведения о конференции по эл. почте** в свойствах для пользователя. Отправляемое сообщение будет содержать всю информацию об аудиоконференции, включая следующее:
  
- телефонный номер конференции или номер телефонного подключения для пользователя;
    
- идентификатор конференции пользователя.
    
   
Далее приведен пример отправляемого сообщения электронной почты:
  
![Сообщение о конференц-связи с телефонным подключением](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![команды логотип 30x30.png](media/teams-logo-30x30.png) С помощью центра администрирования группами Майкрософт

1. На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.

2. В верхней части страницы нажмите кнопку **Изменить**.

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.


## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе вручную аудиоконференций ПИН-код пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - Поставщик услуг аудиоконференций для пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.
    
  - При изменении поставщика аудиоконференций для пользователя в корпорацию Майкрософт.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Пробная и платная аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
