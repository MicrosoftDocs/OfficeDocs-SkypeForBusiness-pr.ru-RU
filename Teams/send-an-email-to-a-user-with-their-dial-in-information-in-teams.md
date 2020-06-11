---
title: Отправка пользователю сведений о голосовой конференции по электронной почте
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Сведения о том, как отправлять пользователям сообщения электронной почты с помощью голосовой конференции в Microsoft Teams.
ms.openlocfilehash: 5f281071dd4ae9a21f9148ac86943d4ab4ce36b8
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691145"
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

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

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

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
