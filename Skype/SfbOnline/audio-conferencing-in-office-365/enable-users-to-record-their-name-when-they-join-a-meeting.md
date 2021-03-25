---
title: Возможность записи имени пользователя при подступе к собранию в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Узнайте, как включить или отключить возможность записи имен пользователями при подступе к собранию в Skype для бизнеса Online.
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114245"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Возможность записи имени пользователя при подступе к собранию в Skype для бизнеса Online

> [!Note]
> Если требуется предоставить пользователям возможность записывать свое имя в Microsoft Teams, ознакомьтесь со статьей [Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

При настройке аудиоконференции в Microsoft 365 или Office 365 вы будете получать номера телефонов и мост аудиоконференции. Мост для conferencing может содержать один или несколько телефонных номеров, которые могут быть выделенным или общим номером телефона.
  
Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.

## <a name="set-whether-callers-should-record-their-name"></a>Настройка записи имени вызывателям
    
1. В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**
    
2. В разделе **Присоединение к собранию** включите параметр **Включить уведомления о входе и выходе из собрания**.
    
   - **Флажок установлен**  вызывающим сторонам будет выдан запрос о вводе имени перед входом в собрание. Выбрано по умолчанию.
    
   - **Флажок снят**  вызывающим сторонам не будет выдаваться запрос о вводе имени перед входом в собрание.
    
3. После внесения изменений нажмите кнопку **Сохранить**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно использовать [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell все о том, как управлять пользователями и что им разрешено делать. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)