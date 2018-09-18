---
title: Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
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
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892094"
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

1. В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы щелкните на элементе **Изменить**.

3. В области **Аудиоконференции** щелкните на элементе **Отправить сведения о конференции по эл. почте**.


## <a name="what-else-should-you-know-about-this-email"></a>Что еще нужно знать о таких сообщениях?

- Когда пользователям в вашей организации разрешены аудиоконференции, им направляется несколько сообщений электронной почты в следующих случаях.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - Сброс ПИН-кода аудиоконференции пользователя вручную.
    
  - Сброс идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - Изменение поставщика услуг аудиоконференций с Майкрософт на другого поставщика или на значение **Нет**.
    
  - Изменение поставщика услуг аудиоконференций на Майкрософт.
    
- По умолчанию эти сообщения электронной почты отправляются из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell. Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Оцените или приобретите аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
