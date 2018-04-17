---
title: Phone numbers for Audio Conferencing
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned.
ms.openlocfilehash: 9b1fca6a576a9de77e74bcab8df740b5106cf5bc
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="phone-numbers-for-audio-conferencing"></a>Phone numbers for Audio Conferencing

When you are setting up **Audio Conferencing** for Skype for Business and Microsoft Teams, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Для фильтрации поиска воспользуйтесь списками **Страна или регион**, **Область** и **Город**. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Audio Conferencing coverage and pricing

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). For pricing information, see 
  
[Тарифы на аудиоконференции](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Телефонные номера для подключения в приглашении на собрание

When a Skype for Business Online or Microsoft Teams user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Чтобы просмотреть другие номера для подключения, перейдите по ссылке **Найти местный номер** в приглашении на собрание.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Dial-in phone numbers set on an audio conferencing bridge

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **Выделенные телефонные номера**  это номера, доступные только для пользователей внутри организации. Вы можете изменить языки, которые используются при звонках на эти номера.
  
 **Общедоступные телефонные номера**  это номера, доступ к которым можно предоставлять другим организациям Office 365. Изменить языки, которые используются при звонках на эти номера, нельзя.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. Список номеров, которые можно использовать для подключения к собранию, открывается при переходе по ссылке **Найти местный номер**, которая включена во все приглашения.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Automatically assigned audio conferencing phone numbers

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. Полученные номера телефонов назначаются мосту аудиоконференции в качестве номеров по умолчанию. Номер телефона, назначенный по умолчанию мосту, должен соответствовать стране или региону нахождения организации.
  
> [!NOTE]
> The country or region location of your organization can be found by signing in to the **Office 365 admin center** and looking under **Organization Profile**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Бесплатные номера доступны для этих стран независимо от существующих ограничений. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
  
To see a list of those countries/regions that have phone numbers automatically assigned to organizations, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## <a name="what-else-should-you-know"></a>Дополнительные сведения

- To see the list of supported languages for audio conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- You can use the [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet to see the dedicated phone numbers for audio conferencing for you organization.
    
- Можно использовать командлет [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684), чтобы просмотреть список языков, поддерживаемых в выделенных телефонных номерах для конференц-связи с подключением.
    
- You can set up to 4 languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- To set the dial-in phone number for a user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
