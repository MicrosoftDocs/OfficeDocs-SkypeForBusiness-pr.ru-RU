---
title: Установка длины ПИН-кода для аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте параметры длины и требований ПИН-кода и узнайте, как установить длительность собраний в Microsoft Teams.
ms.openlocfilehash: cab8976ab0c92a3594dbf881426606288fb611a4dbc286ba0c3d36a1c2096133
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348734"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams

При настройке аудиоконференций для Microsoft Teams вы получите мост аудиоконференции. Мост конференц-связи может содержать один или несколько телефонных номеров. Номер телефона, который вы настроили, будет включен в приглашения на собрание для Microsoft Teams приложения.
  
Мост аудиоконференцсвязи отвечает на вызов людей, которые звонят на собрание с помощью телефона. Она отвечает вызывающего звоняку с помощью голосовых подсказок автозаверха, а затем (в зависимости от параметров) может воспроизведения уведомлений и попросить вызывающего человека записать свое имя. **Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний. Организаторы собраний используют ПИН-ны для начала собраний, если не могут присоединиться к собранию с помощью Microsoft Teams приложения.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Установка длины ПИН-кода

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**. 

3. В области **Параметры моста** в области Длина **ПИН-кода** выберите нужное число цифр.

4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> ПИН-код отличается от идентификатора конференции. Идентификаторы конференции используются абонентами для присоединения к собранию. Они используются для идентификации собрания. ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания. 

## <a name="want-to-know-more-about-pin-settings"></a>Хотите узнать больше о параметрах ПИН-кода?

- ПИН-коды могут иметь от 4 до 12 цифр. по умолчанию — 5. При создании ПИН-кода используются только цифры. Буквы и специальные символы не используются.
    
- ПИН-код требуется только организатору собрания, Microsoft Teams пользователь еще не начал собрание. Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.
    
- Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft. Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)