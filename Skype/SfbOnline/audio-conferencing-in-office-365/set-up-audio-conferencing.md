---
title: Настройка голосовой конференции в Skype для бизнеса
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Узнайте, как настроить телефонное подключение или конференц-связь для людей из вашей организации, которым нужно пользоваться телефоном для присоединения к конференциям. '
ms.openlocfilehash: ea254da1f742db602d396868aad36a0c20951128
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680366"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="3b25c-103">Настройка голосовой конференции в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3b25c-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="3b25c-p101">Иногда сотрудникам вашей организации потребуется использовать телефон для звонка на собрание. В этой ситуации Skype для бизнеса включает функцию голосовой конференции. Пользователи могут звонить на собрания Skype для бизнеса с помощью телефона, вместо того чтобы использовать приложение Skype для бизнеса на мобильном устройстве или компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b25c-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business includes the audio conferencing feature for just this situation! People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="3b25c-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="3b25c-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="3b25c-109">Часто задаваемые вопросы об аудиоконференции см. в статье [Общие вопросы о проведении аудиоконференций](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="3b25c-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="3b25c-110">Шаг 1. Узнайте, доступна ли функция Аудиоконференции в вашей стране или регионе</span><span class="sxs-lookup"><span data-stu-id="3b25c-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="3b25c-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-111"><a name="__top"> </a></span></span>

<span data-ttu-id="3b25c-112">Перейдите в раздел [Страны и регионы, для которых доступны аудиоконференции и тарифные планы](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) и выберите страну или регион, чтобы получить сведения о доступности функции Аудиоконференции, а также сведения о телефонной системе, тарифных планах, платных и бесплатных телефонных номерах и кредитах на связь.</span><span class="sxs-lookup"><span data-stu-id="3b25c-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="3b25c-113">Шаг 2. Покупка и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="3b25c-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="3b25c-p103">Для проведения голосовой конференции вам понадобится лицензия для каждого пользователя, который будет настраивать собрания с телефонным подключением. Чтобы узнать, какие лицензии нужно приобрести для проведения голосовой конференции и сколько они стоимость, ознакомьтесь с [дополнительным лицензированием Skype для бизнеса](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="3b25c-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="3b25c-116">Голосовые конференции входят в состав лицензий Office 365 Enterprise, а также как надстройка.</span><span class="sxs-lookup"><span data-stu-id="3b25c-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="3b25c-117">После покупки лицензий на голосовую конференцию вам потребуется назначить их сотрудникам вашей организации, которые будут планировать или проводить собрания.</span><span class="sxs-lookup"><span data-stu-id="3b25c-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="3b25c-118">См. [Управление лицензиями Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), которые вы приобрели для сотрудников вашей организации, которые будут планировать или вести собрания.</span><span class="sxs-lookup"><span data-stu-id="3b25c-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="3b25c-119">Мы также рекомендуем вам назначить лицензии на кредиты на связь (они ничего не стоят) тем же сотрудникам, которым вы назначили лицензии на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="3b25c-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="3b25c-120">Подробнее об этом см. в статье [Настройка кредитов на связь для организации](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3b25c-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b25c-121">Вы также можете настроить [оплату на голосовую конференцию в минуту](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="3b25c-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="3b25c-122">Шаг 3. Получение служебных номеров для мостов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="3b25c-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="3b25c-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-123"><a name="__top"> </a></span></span>

<span data-ttu-id="3b25c-124">Для аудиоконференции нельзя использовать номера телефонов для пользователей. Необходимо получить служебные номера.</span><span class="sxs-lookup"><span data-stu-id="3b25c-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="3b25c-125">Вы можете получить либо платные, либо бесплатные служебные номера для мостов аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="3b25c-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="3b25c-126">Существует три способа получения платных и бесплатных служебных номеров.</span><span class="sxs-lookup"><span data-stu-id="3b25c-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="3b25c-127">**Используйте центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="3b25c-128">В некоторых странах и регионах вы можете получать номера служб для мостов конференц-связи с помощью центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3b25c-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="3b25c-129">Смотрите раздел [Знакомство с телефонными номерами служб](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="3b25c-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="3b25c-130">**Перенос существующих номеров служб**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="3b25c-131">Перенос существующих номеров из текущего поставщика услуг или оператора телефонного номера в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b25c-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="3b25c-132">Чтобы получить дополнительные сведения о [переносе номеров телефонов](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) для Организации, вы можете просмотреть их в Teams или [управлять телефонными номерами](/microsoftteams/manage-phone-numbers-for-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="3b25c-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="3b25c-133">**Используйте форму запроса для новых номеров**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="3b25c-134">Иногда (в зависимости от страны или региона) вы не сможете получить новые номера служб с помощью центра администрирования Skype для бизнеса, или вам понадобятся конкретные номера телефонов или коды города.</span><span class="sxs-lookup"><span data-stu-id="3b25c-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="3b25c-135">В таких случаях необходимо скачать соответствующую форму, заполнить ее и отправить в нашу службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="3b25c-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="3b25c-136">Для получения дополнительных сведений см. статью [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3b25c-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="3b25c-137">Шаг 4. Назначение служебного телефонного номера мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3b25c-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="3b25c-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-138"><a name="__top"> </a></span></span>

<span data-ttu-id="3b25c-139">После получения платных и/или бесплатных телефонных номеров для моста конференц-связи необходимо назначить номера, чтобы их можно было использовать в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="3b25c-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="3b25c-140">Назначение нового телефонного номера мосту ауидоконференции</span><span class="sxs-lookup"><span data-stu-id="3b25c-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="3b25c-141">![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса:**</span><span class="sxs-lookup"><span data-stu-id="3b25c-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="3b25c-142">Перейдите на**портал**администрирования **центра администрирования Microsoft 365** > \*\*\*\* > **Teams** > Center.</span><span class="sxs-lookup"><span data-stu-id="3b25c-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="3b25c-143">Выберите **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="3b25c-144">Выберите номер телефона и нажмите кнопку **назначить**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="3b25c-145">Для получения дополнительных сведений см. статью [Изменение номеров телефонов для моста аудиоконференций](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3b25c-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="3b25c-146">Шаг 5. Настройка языка по умолчанию и альтернативных языков для моста аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3b25c-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="3b25c-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-147"><a name="__top"> </a></span></span>

<span data-ttu-id="3b25c-148">Затем вы хотите [настроить языки автосекретаря для голосовой конференции](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) , которые будут использовать автосекретарь конференц-связи для приветствия абонентов, находящихся в телефонном номере для голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="3b25c-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="3b25c-149">![Значок с логотипом](../images/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3b25c-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3b25c-150">На панели мониторинга перейдите к**мостам конференций**для **собраний** > .</span><span class="sxs-lookup"><span data-stu-id="3b25c-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="3b25c-151">Выберите номер телефона моста конференц-связи, нажмите кнопку **изменить**, а затем выберите язык по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b25c-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="3b25c-152">![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса**:</span><span class="sxs-lookup"><span data-stu-id="3b25c-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="3b25c-153">Перейдите в центр администрирования > портал \*\*\*\* > **групп** > ,**наследуемых**центром администрирования.</span><span class="sxs-lookup"><span data-stu-id="3b25c-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3b25c-154">Выберите мост для **звуковых конференций** > **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="3b25c-155">Выберите номер телефона для моста конференц-связи, нажмите кнопку **задать языки**и выберите язык по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b25c-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="3b25c-156">Шаг 6. Настройка параметров моста аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3b25c-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="3b25c-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="3b25c-158">После настройки моста аудиоконференции убедитесь, что значения параметров по умолчанию, например, уведомления при входе и выходе, а также длина ПИН-кода настроены правильно. При необходимости их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="3b25c-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="3b25c-159">![Значок с логотипом](../images/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3b25c-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3b25c-160">На панели мониторинга перейдите к**мостам конференций**для **собраний** > .</span><span class="sxs-lookup"><span data-stu-id="3b25c-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="3b25c-161">Выберите **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-161">Select **Bridge settings**.</span></span> <span data-ttu-id="3b25c-162">Откроется панель **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="3b25c-163">Подробнее см. статью [Изменение параметров моста аудиоконференций](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3b25c-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="3b25c-164">![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса:**</span><span class="sxs-lookup"><span data-stu-id="3b25c-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="3b25c-165">Перейдите на**портал**администрирования **центра администрирования Microsoft 365** > \*\*\*\* > **Teams** > Center.</span><span class="sxs-lookup"><span data-stu-id="3b25c-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3b25c-166">Выберите**Параметры моста Microsoft**для **звуковых конференций** > .</span><span class="sxs-lookup"><span data-stu-id="3b25c-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="3b25c-167">Откроется страница **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="3b25c-168">Подробнее см. статью [Изменение параметров моста аудиоконференций](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3b25c-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="3b25c-169">Шаг 7. Назначение телефонных номеров для пользователей, которые проводят собрания</span><span class="sxs-lookup"><span data-stu-id="3b25c-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="3b25c-170">После создания моста аудиоконференции необходимо настроить платные и бесплатные служебные номера для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b25c-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="3b25c-171">Необходимо сделать это для всех сотрудников вашей организации, которые проводят или планируют собрания.</span><span class="sxs-lookup"><span data-stu-id="3b25c-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="3b25c-172">![Значок с логотипом](../images/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="3b25c-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="3b25c-173">На панели мониторинга щелкните **Пользователи**, выберите пользователя из списка и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="3b25c-174">Нажмите кнопку **изменить** рядом с пунктом " **звуковые конференции**", а затем в области **звуковые конференции** **выберите номер в** поле **платный** номер и бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="3b25c-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="3b25c-175">![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса:**</span><span class="sxs-lookup"><span data-stu-id="3b25c-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="3b25c-176">Перейдите на портал **администрирования Microsoft 365** > **Teams** > Center**Legacy**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="3b25c-177">Выберите пункт**Пользователи** **голосовой конференции** > и выберите пользователя из списка и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3b25c-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="3b25c-178">Подробнее см. в разделе [Назначение Майкрософт в качестве поставщика услуг аудиоконференций](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3b25c-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="3b25c-179">Шаг 8. Настройка приглашений на собрания (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3b25c-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="3b25c-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3b25c-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="3b25c-181">Настроенные для пользователя телефонные номера будут автоматически добавляться к приглашениям на собрания, которые отправляются участникам.</span><span class="sxs-lookup"><span data-stu-id="3b25c-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="3b25c-182">Тем не менее, при желании, вы можете добавить свои собственные справочные и официальные ссылки, текстовое сообщение и небольшой логотип компании.</span><span class="sxs-lookup"><span data-stu-id="3b25c-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="3b25c-183">Дополнительные сведения: [Настройка приглашений на собрания](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="3b25c-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="3b25c-184">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3b25c-184">Related topics</span></span>

[<span data-ttu-id="3b25c-185">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="3b25c-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="3b25c-186">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3b25c-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="3b25c-187">Телефонные номера для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="3b25c-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="3b25c-188">Установка параметров для онлайн-собраний и конференций</span><span class="sxs-lookup"><span data-stu-id="3b25c-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
