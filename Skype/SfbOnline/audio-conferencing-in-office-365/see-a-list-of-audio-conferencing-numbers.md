---
title: Просмотр списка номеров для аудиоконференций в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Узнайте, как определить входящие номера конференц-связи в Skype для бизнеса Online. '
ms.openlocfilehash: e152cd5d54cd9e1e318027c57cbc4ffda938360b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012103"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Просмотр списка номеров для аудиоконференций в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Сведения о номерах для аудиоконференций в Microsoft Teams см. в статье [Просмотра номеров для аудиоконференций в Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

При настройке аудиоконференций для пользователей Skype для бизнеса можно просматривать телефонные номера, доступные пользователям для участия в аудиоконференциях. Этот список будет содержать все номера телефонов для аудиоконференций, доступные вашей организации.
  
 **Ищете цены?** См. [аудиоконференция] https://www.microsoft.com/microsoft-teams/audio-conferencing) .
  
> [!IMPORTANT]
> **Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.** Если вы хотите узнать, есть ли телефонные номера для телефонного звонка, доступные в вашем регионе или стране или регионе, перейдите в Центр администрирования **Skype** для бизнеса Номера голосовых телефонов , нажмите кнопку Добавить и выберите Новые номера служб  >    >  .   Для фильтрации поиска воспользуйтесь списками **Страна или регион**, **Область** и **Город**. Кроме того, если вы ищете бесплатные  номера служб, выберите Бесплатный в списке Область **или** регион.
  
Если в вашей организации доступен только один телефонный номер, он будет использоваться по умолчанию для всех пользователей. Если доступно несколько номеров телефонов, для каждого пользователя можно выбрать номер телефона по умолчанию. Этот номер по умолчанию будет использоваться в приглашениях на собрания в Skype для бизнеса.
  
Чтобы изменить входящий номер одного пользователя, можно просмотреть статью [Установка телефонных номеров, включенных при приглашении](set-the-phone-numbers-included-on-invites.md).
  
> [!NOTE]
> Внутренние входящие номера являются выделенными для вашей организации. В качестве номеров телефона по умолчанию можно установит только их. Однако международные входящие номера могут совместно использоваться несколькими организациями. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Просмотр номеров телефона для аудиоконференций

1. Во войти с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в Центр администрирования > **Skype для бизнеса**.
    
3. В Центре **администрирования Skype** для бизнеса на левой навигации перейдите в аудиоконференцию Microsoft  >  **bridge**, а затем:
    
   - Вы можете просмотреть телефонные номера, доступные для аудиоконференции.
    
   - Вы также можете просмотреть расположение, а также основной и дополнительный языки, которые будут использоваться автоконферентором аудиоконференации.
    
> [!NOTE]
> Вы можете перейти в список Пользователи аудиоконференции и выбрать свойства пользователя, чтобы изменить номер по умолчанию, выбрав новый номер из списка доступных номеров  >   в организации. См. [настройка номеров телефонов, включенных в приглашения.](set-the-phone-numbers-included-on-invites.md) 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время или автоматизировать эту функцию, можно использовать для этого [cmdlet Get-CsOnlineDialInConferencingServiceNumber.](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт по ссылке Скачивание и установка [модуля Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>См. также

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
