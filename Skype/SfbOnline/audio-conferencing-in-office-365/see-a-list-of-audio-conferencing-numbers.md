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
ms.openlocfilehash: 48cca375f2039a1cebbd07100a8bcd8d275f55f0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164688"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Просмотр списка номеров для аудиоконференций в Skype для бизнеса Online

> [!NOTE]
> Сведения о номерах для аудиоконференций в Microsoft Teams см. в статье [Просмотра номеров для аудиоконференций в Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

When you set up Audio Conferencing for Skype for Business users, you can view the phone numbers that are available to them for audio conferencing. This list will have all of the audio conferencing phone numbers that are available to your organization.
  
 **Looking for prices?** See [Pricing for Audio Conferencing](https://products.office.com/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.** If you are looking to see if there are dial-in phone numbers available in your area or country/region, go to **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
If there is only one phone number available in your organization, it will be used as the default number for all of your users. When multiple phone numbers are available, you can select the default phone number for each user. This default number will be included in Skype for Business meeting invitations.
  
Чтобы изменить входящий номер одного пользователя, можно просмотреть статью [Установка телефонных номеров, включенных при приглашении](set-the-phone-numbers-included-on-invites.md).
  
> [!NOTE]
> Domestic dial-in numbers are dedicated to your organization and are the only ones that can be set as a default phone number. However, international dial-in numbers may be shared across multiple organizations. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Просмотр номеров телефона для аудиоконференций

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в Центр администрирования > **Skype для бизнеса.**
    
3. В Центре **администрирования Skype** для бизнеса на левой навигации перейдите к мосту аудиоконференции  >  **Майкрософт,** а затем:
    
   - Вы можете просмотреть телефонные номера, доступные для аудиоконференции.
    
   - Вы также можете просмотреть расположение, а также основной и дополнительный языки, которые будут использоваться автопочетом аудиоконференции.
    
> [!NOTE]
> You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number by choosing a new number from the list of available numbers in your organization. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время и автоматизировать процесс, используйте для этого [cmdlet Get-CsOnlineDialInConferencingServiceNumber.](https://go.microsoft.com/fwlink/?LinkId=617691)
    
- Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
