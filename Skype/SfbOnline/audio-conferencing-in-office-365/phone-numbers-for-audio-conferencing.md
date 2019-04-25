---
title: Номера телефонов для аудиоконференций в приложении Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Узнайте, какие страны и регионы имеют телефонные номера для конференц-связи и как они автоматически назначаются.
ms.openlocfilehash: 4ba3cea0b009ae91c2df1954cdee283397bf2037
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229150"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Номера телефонов для аудиоконференций в приложении Skype для бизнеса Online

> [!NOTE]
> Сведения о телефонных номерах Microsoft Teams см. в разделе [Номера телефонов для аудиоконференций в Microsoft Teams](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams).

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Зона покрытия и тарифы аудиоконференций

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Телефонные номера для подключения в приглашении на собрание

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Чтобы просмотреть другие номера для подключения, перейдите по ссылке **Найти местный номер** в приглашении на собрание.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Телефонных номеров телефонов на звукового конференц-канала

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **Выделенные телефонные номера**  это номера, доступные только для пользователей внутри организации. Вы можете изменить языки, которые используются при звонках на эти номера.
  
 **Общедоступные телефонные номера**  это номера, доступ к которым можно предоставлять другим организациям Office 365. Изменить языки, которые используются при звонках на эти номера, нельзя.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Автоматически назначаются аудиоконференций телефонных номеров

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> Страна или регион местонахождение вашей организации можно найти, вход в **Центр администрирования Office 365** и посмотрев под **Профиля организации**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Toll-free numbers from these locations are available depending on available inventory. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).
  
Список этих стран или регионов, имеющих номера телефонов, автоматически назначаемых для организаций, приведен в разделе [Страны и регионы, для которых доступны аудиоконференции и тарифные планы](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
  
## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Чтобы просмотреть список поддерживаемых языков для аудиоконференций, см [аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Командлет [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) видеть выделенные номера телефонов для аудиоконференции для ваша организация.
    
- Можно использовать командлет [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684), чтобы просмотреть список языков, поддерживаемых в выделенных телефонных номерах для конференц-связи с подключением.
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- [Задайте телефона, приглашает номера, находящимся на](set-the-phone-numbers-included-on-invites.md)телефонные номера для пользователя, см.
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Статьи по теме

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
