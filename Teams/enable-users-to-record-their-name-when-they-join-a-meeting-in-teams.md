---
title: Разрешить пользователям записывать свое имя для собрания
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Узнайте, как включить или отключить возможность записи имен пользователей при присоединении к собранию в Microsoft Teams.
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641730"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams

При настройке аудиоконференций в Microsoft 365 или Office 365 вы получите номера телефонов и так называемый мост аудиоконференций. Мост конференц-связи может содержать один или несколько номеров телефонов, которые могут быть выделенными или общими номерами телефонов.
  
Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.

## <a name="set-whether-callers-should-record-their-name"></a>Укажите, должны ли вызывающие объекты записывать свое имя

С помощью Центра администрирования Microsoft Teams:

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.

2. В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста"**.

3. Включение или отключение **уведомлений о входе и выходе из собрания**.

4. При включении уведомлений выберите  "Имена" или "Номера телефонов" в разделе "Тип объявления о входе или выходе **", а** затем включите функцию "Попросить вызывающих абонентов" записать свое имя перед **присоединением к собранию.**

5. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
