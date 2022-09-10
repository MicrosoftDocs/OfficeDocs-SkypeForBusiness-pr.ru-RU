---
title: Установка длины ПИН-кода для аудиоконференции
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте о параметрах длины и требований ПИН-кода и узнайте, как задать длину собраний в Microsoft Teams.
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641960"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Установка длины ПИН-кода для собраний аудиоконференций в Microsoft Teams

При настройке аудиоконференций для Microsoft Teams вы получите мост аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Указанный вами номер телефона будет включен в приглашения на собрания для приложения Microsoft Teams.
  
Мост аудиоконференцсвязи отвечает на вызов людей, которые звонят на собрание с помощью телефона. Он отвечает вызывающей стороне с помощью голосовых запросов от автосекретаря, а затем, в зависимости от параметров, может воспроизводить уведомления и запрашивать у вызывающих абонентов запись их имени. **Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний. Организаторы собраний используют ПИН-коды для начала собраний, если не могут присоединиться к собранию с помощью приложения Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Установка длины ПИН-кода

С помощью Центра администрирования Microsoft Teams:

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.

2. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.

3. В области **параметров моста** в разделе **длины ПИН-кода** выберите нужное число цифр для ПИН-кода.

4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> ПИН-код отличается от идентификатора конференции. Идентификаторы конференции используются абонентами для присоединения к собранию. Они используются для идентификации собрания. ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания.

## <a name="want-to-know-more-about-pin-settings"></a>Хотите узнать больше о параметрах ПИН-кода?

- Пин-коды могут содержать от 4 до 12 цифр; Значение по умолчанию — 5. При создании ПИН-кода используются только цифры. Буквы и специальные символы не используются.

- ПИН-код требуется только для организатора собрания, если пользователь Microsoft Teams еще не начал собрание. Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.

- Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft. Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом.

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретите аудиоконференции в Microsoft 365 для Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
