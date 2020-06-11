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
description: Узнайте о параметрах длины и требований ПИН-кода и Узнайте, как установить продолжительность собраний в Microsoft Teams.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691105"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams

При настройке аудиоконференций для Microsoft Teams вы получите мост аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Заданный номер телефона будет включен в приглашения на собрание для приложения Microsoft Teams.
  
Мост аудиоконференций отвечает на звонок для людей, подключающихся к собранию по телефону. Он отвечает вызывающему абоненту с помощью голосовых подсказок от автосекретаря, а затем, в зависимости от ваших настроек, может воспроизводить уведомления и просить вызывающего абонента записать свое имя. **Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний. Организаторы собраний используют ПИН-коды для начала собраний, когда им не удается присоединиться с помощью приложения Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Настройка длины ПИН-кода

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**. 

3. В области **Параметры моста** в разделе **длина ПИН-** кода выберите нужное количество цифр.

4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> ПИН-код отличается от идентификатора конференции. Идентификаторы конференции используются абонентами для присоединения к собранию. Они используются для идентификации собрания. ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания. 

## <a name="want-to-know-more-about-pin-settings"></a>Хотите узнать больше о параметрах ПИН-кода?

- ПИН-коды могут содержать от 4 до 12 цифр; значение по умолчанию — 5. При создании ПИН-кода используются только цифры. Буквы и специальные символы не используются.
    
- PIN-код требуется только для организатора собрания, если собрание еще не запущено пользователем Microsoft Teams. Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.
    
- Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft. Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
