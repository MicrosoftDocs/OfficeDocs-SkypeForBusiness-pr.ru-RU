---
title: Отправить сообщение электронной почты для пользователя с помощью их аудиоконференции сведения в группах Майкрософт
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
localization_priority: Priority
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Отправьте сообщение электронной почты с их аудиоконференций сведения пользователей в группах Майкрософт.
ms.openlocfilehash: 3ee0d5f7eda551e5231cae535dec08439c19e081
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850779"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Отправить сообщение электронной почты для пользователя с помощью их аудиоконференции сведения в группах Майкрософт

В некоторых случаях Microsoft группами пользователей может потребоваться отправить свои данные для конференции аудио. Это можно сделать, нажав кнопку **Отправить сведения о конференции по электронной почте** в разделе свойства для пользователя. При отправке это сообщение, он будет содержать все сведения аудиоконференций, включая:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
   
Ниже приведен пример сообщения электронной почты:
  
![Сообщение о конференц-связи с телефонным подключением](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправить сообщение электронной почты с информацией аудиоконференций для пользователя

1. На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.

2. В верхней части страницы нажмите кнопку **Изменить**.

3. В разделе **Audio конференц-связи**нажмите кнопку **Отправить сведения о конференции по электронной почте**.


## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.
    
  - Если для них назначена лицензия на **Аудиоконференции** .
    
  - При сбросе вручную аудиоконференций ПИН-код пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если лицензия на **Аудиоконференции** удаляется из их.
    
  - Поставщик услуг аудиоконференций для пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.
    
  - При изменении поставщика аудиоконференций для пользователя в корпорацию Майкрософт.
    
- По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell. В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.
    
  
## <a name="related-topics"></a>См. также:

[Пробная и платная аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
