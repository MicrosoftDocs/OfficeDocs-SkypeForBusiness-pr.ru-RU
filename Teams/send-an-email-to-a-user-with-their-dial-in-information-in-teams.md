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
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012323"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams

В некоторых случаях Microsoft группами пользователей может потребоваться отправить свои данные для конференции аудио. Это можно сделать, нажав кнопку **Отправить сведения о конференции по электронной почте** в разделе свойства для пользователя. При отправке это сообщение, он будет содержать все сведения аудиоконференций, включая:
  
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
    
- По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell. В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Оцените или приобретите аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
