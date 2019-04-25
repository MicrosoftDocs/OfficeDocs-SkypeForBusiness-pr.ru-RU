---
title: Просмотреть список пользователей, которые включены в Скайп для аудиоконференции для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как просмотреть список пользователей в вашей организации, которые активированы для телефонных конференций, из центра администрирования Skype для бизнеса. '
ms.openlocfilehash: 722f9e411e1781529ea68f6995a2109f58d39cb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229264"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Просмотреть список пользователей, которые включены в Скайп для аудиоконференции для бизнеса в Интернет

> [!NOTE]
> Для получения сведений об активированных пользователях в Microsoft Teams см. [Просмотр списка пользователей, активированных для аудиоконференций в Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

After you have enabled Skype for Business users in your organization for Audio Conferencing, you can view the list of those users who have been enabled. When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Просмотр списка пользователей

   
- В панели навигации слева перейдите к секции **Аудиоконференции** > **Пользователи**.

## <a name="what-else-should-i-know"></a>Дополнительные сведения

- При просмотре списка активированных пользователей вы можете выбрать пользователя в списке и использовать область действий для изменения параметров аудиоконференций для этого пользователя.
    
- Если выбрать одного пользователя, у которого в качестве поставщика услуг аудиоконференций указан Майкрософт, вы можете просмотреть телефонный номер по умолчанию, узнать, включены ли динамические идентификаторы конференции для вашей организации, а также сбросить идентификатор конференции для собраний, которые проводит этот пользователь.
    
- Если выбрать одного пользователя, который пользуется услугами стороннего поставщика аудиоконференций, вы можете просмотреть название стороннего поставщика аудиоконференций, платный телефонный номер и бесплатный телефонный номер (если они настроены).
    
- Вы можете использовать параметры фильтра для отображения пользователей, у которых:
    
  - **Аудиоконференция включена**
    
  - **Аудиоконференция выключена**
    
  - **Поставщик услуг аудиоконференций — Майкрософт**
    
  - **Поставщик услуг аудиоконференций — прочие**
    
- Вы можете использовать кнопку поиска, чтобы найти определенного пользователя в списке.
    
- Вы можете выбрать несколько пользователей и выполнить следующие действия:
    
  - Выбрать другой номер по умолчанию для этих пользователей.
    
  - Отключить аудиоконференции для пользователя, выбрав к качестве поставщика значение **Нет**.
    
  - Выбрать Майкрософт в качестве поставщика услуг аудиоконференций, если пользователю назначена лицензия **Аудиоконференции**.
    
  - Разрешить или запретить анонимным пользователям делать активными телефонные собрания выбранных пользователей.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Статьи по теме

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
