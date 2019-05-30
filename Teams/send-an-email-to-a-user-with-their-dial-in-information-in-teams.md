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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения об отправке пользователям сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 95dd6d562400630c5848484bd0081deeb3092abc
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494742"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams

Иногда пользователям Microsoft Teams требуется, чтобы вы отправляли им информацию об аудиоконференциях. Вы можете сделать это, выбрав пункт **Отправить сведения о конференции по эл. почте** в свойствах для пользователя. Отправляемое сообщение будет содержать всю информацию об аудиоконференции, включая следующее:
  
- телефонный номер конференции или номер телефонного подключения для пользователя;
    
- идентификатор конференции пользователя.
    
   
Далее приведен пример отправляемого сообщения электронной почты:
  
![Пример сообщения электронной почты конференц-связи с телефонным подключением](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](media/teams-logo-30x30.png) Использование центра администрирования Microsoft Teams

1. На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку **изменить**.

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.


## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- После включения поддержки голосовой конференции у пользователей вашей организации есть несколько сообщений электронной почты, которые отправляются пользователям.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При ручном сбросе ПИН-кода голосовой конференции пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - Когда поставщик видеоконференций для пользователя будет изменен с Microsoft на другого поставщика или **нет**.
    
  - После изменения поставщика голосовой конференции для пользователя на Microsoft.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Платная или пробная версия аудиоконференций в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
