---
title: Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Узнайте, как для настройки конференц-связи или аудио для пользователей в вашей организации, которым необходимо присоединиться к конференции с помощью телефона. '
ms.openlocfilehash: 5d069822bf818db63ed35545a34a0bfa2eeee672
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562671"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Часто задаваемые вопросы об аудиоконференции см. в статье [Общие вопросы о проведении аудиоконференций](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Шаг 1. Узнайте, доступна ли функция Аудиоконференции в вашей стране или регионе
<a name="__top"> </a>


Перейдите в раздел [Страны и регионы, для которых доступны аудиоконференции и тарифные планы](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) и выберите страну или регион, чтобы получить сведения о доступности функции Аудиоконференции, а также сведения о телефонной системе, тарифных планах, платных и бесплатных телефонных номерах и кредитах на связь. 
 
## <a name="step-2-get-and-assign-licenses"></a>Шаг 2. Покупка и назначение лицензий
 
1. For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.
    
3. We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Шаг 3. Получение служебных номеров для мостов аудиоконференций
<a name="__top"> </a>

For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers: 
  
- **Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.  
  
- **Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Шаг 4. Назначение служебного телефонного номера мосту аудиоконференции
<a name="__top"> </a>

После получения платных и/или бесплатных телефонных номеров для моста аудиоконференции, необходимо назначить номера, чтобы их можно было использовать на приглашениях на собрания.  

Назначение нового телефонного номера мосту ауидоконференции

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса:**

 Перейдите в **Центр администрирования Office 365** > **Центры администрирования** > **Skype для бизнеса** > **Голосовая связь** > **Номера телефонов**, выберите номер телефона и нажмите кнопку **Назначить**.

Для получения дополнительных сведений см. статью [Изменение номеров телефонов для моста аудиоконференций](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Шаг 5. Настройка языка по умолчанию и альтернативных языков для моста аудиоконференции
<a name="__top"> </a>

Далее следует [настроить языки автосекретаря для аудиоконференций](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), которые используется автосекретарем для приветствия вызывающего абонента. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**

На информационной панели последовательно выберите пункты **Собрания** > **Мосты конференции**, выберите телефонный номер моста аудиоконференции, нажмите кнопку **Изменить** и выберите язык по умолчанию.

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса:**

Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **Скайп для бизнеса** > **аудиоконференции** > **Microsoft bridge**, выберите номер телефона bridge конференц-связи и нажмите кнопку ** Установка языков**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Шаг 6. Настройка параметров моста аудиоконференции
<a name="__top"> </a>
    
После настройки моста аудиоконференции убедитесь, что значения параметров по умолчанию, например, уведомления при входе и выходе, а также длина ПИН-кода настроены правильно. При необходимости их можно изменить. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**

From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса:**

Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Шаг 7. Назначение телефонных номеров для пользователей, которые проводят собрания

После создания моста аудиоконференции необходимо настроить платные и бесплатные служебные номера для пользователей.

You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**

На информационной панели щелкните элемент **Пользователи**, выберите пользователя в списке, нажмите кнопку **Изменить**, нажмите кнопку **Изменить** рядом с пунктом **Аудиоконференции**, а затем на панели **Аудиоконференции** выберите номер в списках **Платный номер** и **Бесплатный номер**.

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса:**

Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Шаг 8. Настройка приглашений на собрания (необязательно)
<a name="__top"> </a>
 
The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Связанные разделы

[Общие вопросы об аудиоконференциях](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Номера телефонов для аудиоконференций](phone-numbers-for-audio-conferencing.md)
  
[Установка параметров для онлайн-собраний и конференций](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
