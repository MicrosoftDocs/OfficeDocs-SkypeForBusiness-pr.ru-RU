---
title: Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Получите информацию относительно длины и требований к ПИН-коду, а также узнайте, как устанавливать необходимую длину кода для совещаний в Skype для бизнеса.
ms.openlocfilehash: a9a7ec819fef23aac0ff334aebae95a83180316c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012903"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Установка длины ПИН-кода для аудиоконференций в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> Для получения информации об установке длины ПИН-кода в Microsoft Teams см. статью [Установка длины ПИН-кода для аудиоконференций в Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).

При установке аудиоконференций в Skype для бизнеса вы получите мост аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Установленный номер телефона будет указан в приглашениях на собрания в приложении Skype для бизнеса.
  
Мост аудиоконференцсвязи отвечает на вызов людей, которые звонят на собрание с помощью телефона. Она отвечает вызываемой звоняке с помощью голосовых подсказок автозаверхлителей, а затем (в зависимости от параметров) может воспроизведения уведомлений и попросить вызывающего человека записать свое имя. **Параметры моста Microsoft** позволяют изменять параметры уведомлений о собрании и присоединения к собранию, а также устанавливать длину ПИН-кодов, которые используются организаторами собраний. Организаторы собраний используют ПИН-коды для начала собраний, если они не могут присоединиться к собранию с помощью приложения Skype для бизнеса.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Установка длины ПИН-кода
 
1. В центре **Skype для бизнеса** администрирования на левой навигации перейдите в параметры моста  >  **Аудиоконференция Майкрософт**.
    
2. В **области Длина**  >  **ПИН-кода** безопасности выберите нужное число цифр и нажмите кнопку **Сохранить.**
    
> [!NOTE]
> ПИН-код отличается от идентификатора конференции. Идентификаторы конференции используются абонентами для присоединения к собранию. Они используются для идентификации собрания. ПИН-код используется для проверки подлинности вызывающего абонента в качестве организатора собрания. 

## <a name="want-to-know-more-about-pin-settings"></a>Хотите узнать больше о параметрах ПИН-кода?

- ПИН-коды могут иметь от 4 до 12 цифр. по умолчанию — 5. При создании ПИН-кода используются только цифры. Буквы и специальные символы не используются.
    
- ПИН-код требуется только для организатора собрания, если пользователь Skype для бизнеса еще не начал собрание. Если пользователи подключаются к собранию, организатору собрания потребуется ПИН-код для начала собрания.
    
- Параметры безопасности ПИН-кода применяются ко всем номерам телефона, связанными с мостом Microsoft. Они будут применяться ко всем собраниям, которые используют номера телефонов, связанные с указанным мостом. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время или автоматизировать эту функцию, можно использовать для этого [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)
    
- Для установки в качестве ПИН-кода 8 цифр выполните следующие действия.  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт на веб-сайте Загрузка и установить [модуль Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="see-also"></a>См. также

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
