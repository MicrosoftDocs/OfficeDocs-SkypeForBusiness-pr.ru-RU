---
title: См. список пользователей, которые могут включить аудиоконференцию в Skype для бизнеса Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как просмотреть список пользователей в вашей организации, которые активированы для телефонных конференций, из центра администрирования Skype для бизнеса. '
ms.openlocfilehash: b1138d80798791a433956e7b53db2569e1667e3126a81c3744c85a9604475012
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327075"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>См. список пользователей, которые могут включить аудиоконференцию в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Для получения сведений об активированных пользователях в Microsoft Teams см. [Просмотр списка пользователей, активированных для аудиоконференций в Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

После активации пользователей Skype для бизнеса в вашей организации для аудиоконференции, вы можете просмотреть список тех пользователей, которые были активированы. При просмотре списка вы также сможете увидеть тип используемого поставщика услуг аудиоконференций для каждого пользователя в списке, телефонный номер для каждого пользователя по умолчанию, узнать, включены ли динамические идентификаторы конференции для вашей организации, а также статические идентификаторы конференции для аудиоконференций, которые проводят пользователи.

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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
