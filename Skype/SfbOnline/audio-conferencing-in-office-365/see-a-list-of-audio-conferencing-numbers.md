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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как определить входящие номера конференц-связи в Skype для бизнеса Online. '
ms.openlocfilehash: f7343010cfdc34325d2f164b5560c542af0551ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114155"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Просмотр списка номеров для аудиоконференций в Skype для бизнеса Online

> [!NOTE]
> Сведения о номерах для аудиоконференций в Microsoft Teams см. в статье [Просмотра номеров для аудиоконференций в Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

При настройке аудиоконференций для пользователей Skype для бизнеса можно просматривать телефонные номера, доступные пользователям для участия в аудиоконференциях. Этот список будет содержать все номера телефонов для аудиоконференций, доступные вашей организации.
  
 **Ищете цены?** См. [цены на аудиоконференцию.](https://products.office.com/skype-for-business/audio-conferencing#Requirements)
  
> [!IMPORTANT]
> **Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.** Если вы хотите узнать, доступны ли телефонные номера для телефонного звонка в вашем регионе или стране или регионе, перейдите в Центр администрирования **Skype** для бизнеса на номер голосовой связи, нажмите кнопку "Добавить" и выберите "Новые номера  >    >  служб".   Для фильтрации поиска воспользуйтесь списками **Страна или регион**, **Область** и **Город**. Кроме того, если вы ищете бесплатные  номера служб, выберите их в списке **"Область или** регион".
  
Если в вашей организации доступен только один телефонный номер, он будет использоваться по умолчанию для всех пользователей. Если доступно несколько номеров телефонов, для каждого пользователя можно выбрать номер телефона по умолчанию. Этот номер по умолчанию будет использоваться в приглашениях на собрания в Skype для бизнеса.
  
Чтобы изменить входящий номер одного пользователя, можно просмотреть статью [Установка телефонных номеров, включенных при приглашении](set-the-phone-numbers-included-on-invites.md).
  
> [!NOTE]
> Внутренние входящие номера являются выделенными для вашей организации. В качестве номеров телефона по умолчанию можно установит только их. Однако международные входящие номера могут совместно использоваться несколькими организациями. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Просмотр номеров телефона для аудиоконференций

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в Центр администрирования > **Skype для бизнеса.**
    
3. В Центре **администрирования Skype** для бизнеса на левой навигации перейдите к мосту аудиоконференции  >  **Майкрософт,** а затем:
    
   - Вы можете просмотреть телефонные номера, доступные для аудиоконференции.
    
   - Вы также можете просмотреть расположение, основной и дополнительный языки, которые будет использовать автофиденциер аудиоконференции.
    
> [!NOTE]
> Вы можете перейти на сайт "Пользователи аудиоконференции" и выбрать свойства пользователя, чтобы изменить номер по умолчанию, выбрав новый номер в списке доступных номеров в  >   организации. См. ["Настройка номеров телефонов, включенных в приглашения".](set-the-phone-numbers-included-on-invites.md) 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время и автоматизировать процесс, используйте для этого [cmdlet Get-CsOnlineDialInConferencingServiceNumber.](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
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
