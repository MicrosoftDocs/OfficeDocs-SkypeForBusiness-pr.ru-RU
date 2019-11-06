---
title: Настройка голосовой конференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Узнайте, как настроить телефонное подключение или конференц-связь для людей из вашей организации, которым нужно пользоваться телефоном для присоединения к конференциям. '
ms.openlocfilehash: d630f6f149f61609209cc4ead23ed7232647cb08
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "37925370"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="7ce56-103">Настройка голосовой конференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ce56-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="7ce56-104">В некоторых случаях пользователям в организации требуется телефон, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="7ce56-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="7ce56-105">В этой ситуации Microsoft Teams включает функцию голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="7ce56-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="7ce56-106">Пользователи могут звонить на собрания Teams с помощью телефона, вместо того чтобы использовать приложение Teams на мобильном устройстве или компьютере.</span><span class="sxs-lookup"><span data-stu-id="7ce56-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="7ce56-107">Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания.</span><span class="sxs-lookup"><span data-stu-id="7ce56-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="7ce56-108">Присоединяющимся к собранию по телефону участникам не требуются какие-либо назначенные им лицензии или другие настройки.</span><span class="sxs-lookup"><span data-stu-id="7ce56-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="7ce56-109">Часто задаваемые вопросы об аудиоконференции см. в статье [Общие вопросы о проведении аудиоконференций](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="7ce56-110">Шаг 1. Узнайте, доступна ли функция Аудиоконференции в вашей стране или регионе</span><span class="sxs-lookup"><span data-stu-id="7ce56-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="7ce56-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="7ce56-111"></span></span>

<span data-ttu-id="7ce56-112">Перейдите в раздел [Страны и регионы, для которых доступны аудиоконференции и тарифные планы](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) и выберите страну или регион, чтобы получить сведения о доступности функции Аудиоконференции, а также сведения о телефонной системе, тарифных планах, платных и бесплатных телефонных номерах и кредитах на связь.</span><span class="sxs-lookup"><span data-stu-id="7ce56-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="7ce56-113">Шаг 2. Покупка и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="7ce56-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="7ce56-114">Для аудиоконференции требуется лицензия для каждого пользователя, который будет настраивать собрания с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7ce56-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="7ce56-115">Чтобы узнать, какие лицензии нужно приобрести для голосовой конференции и сколько они будут стоить, ознакомьтесь со сведениями о [лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="7ce56-116">Голосовые конференции входят в состав лицензий Office 365 Enterprise, а также как надстройка.</span><span class="sxs-lookup"><span data-stu-id="7ce56-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="7ce56-117">После покупки лицензий на голосовую конференцию вам потребуется назначить их сотрудникам вашей организации, которые будут планировать или проводить собрания.</span><span class="sxs-lookup"><span data-stu-id="7ce56-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="7ce56-118">Ознакомьтесь с [разрешениями Назначение лицензий пользователям в Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , которые вы приобрели для пользователей в вашей организации, которые планируют планировать собрания или дают к ним интерес.</span><span class="sxs-lookup"><span data-stu-id="7ce56-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="7ce56-119">Мы также рекомендуем вам назначить лицензии на кредиты на связь (они ничего не стоят) тем же сотрудникам, которым вы назначили лицензии на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7ce56-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="7ce56-120">Подробнее об этом см. в статье [Настройка кредитов на связь для организации](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ce56-121">Вы также можете настроить [оплату на голосовую конференцию в минуту](audio-conferencing-pay-per-minute.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="7ce56-122">Шаг 3. Получение служебных номеров для мостов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="7ce56-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="7ce56-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="7ce56-123"></span></span>

<span data-ttu-id="7ce56-124">Для аудиоконференции нельзя использовать номера телефонов для пользователей. Необходимо получить служебные номера.</span><span class="sxs-lookup"><span data-stu-id="7ce56-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="7ce56-125">Вы можете получить либо платные, либо бесплатные служебные номера для мостов аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="7ce56-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="7ce56-126">Существует три способа получения платных и бесплатных служебных номеров.</span><span class="sxs-lookup"><span data-stu-id="7ce56-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="7ce56-127">**Используйте центр администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="7ce56-128">В некоторых странах и регионах вы можете получать номера служб для мостов конференц-связи с помощью центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7ce56-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="7ce56-129">Смотрите раздел [Знакомство с телефонными номерами служб](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="7ce56-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="7ce56-130">**Перенос существующих номеров служб**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="7ce56-131">Перенос существующих номеров из текущего поставщика услуг или оператора телефонного номера в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ce56-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="7ce56-132">Чтобы получить дополнительные сведения о [переносе номеров телефонов](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) для Организации, вы можете просмотреть их в Teams или [управлять телефонными номерами](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="7ce56-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="7ce56-133">**Используйте форму запроса для новых номеров**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="7ce56-134">Иногда (в зависимости от страны или региона) вы не сможете получить новые номера служб, используя центр администрирования Microsoft Teams, или вам понадобятся конкретные номера телефонов или коды города.</span><span class="sxs-lookup"><span data-stu-id="7ce56-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="7ce56-135">В таких случаях необходимо скачать соответствующую форму, заполнить ее и отправить в нашу службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="7ce56-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="7ce56-136">Для получения дополнительных сведений см. статью [Управление номерами телефонов организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="7ce56-137">Шаг 4. Назначение служебного телефонного номера мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7ce56-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="7ce56-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="7ce56-138"></span></span>

<span data-ttu-id="7ce56-139">После получения платных и/или бесплатных телефонных номеров для моста конференц-связи необходимо назначить номера, чтобы их можно было использовать в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="7ce56-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="7ce56-140">Выполните указанные ниже действия, чтобы назначить новый телефонный номер своему мосту голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="7ce56-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="7ce56-141">![Значок, показывающий логотип](media/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса:**</span><span class="sxs-lookup"><span data-stu-id="7ce56-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="7ce56-142">Перейдите на**портал**администрирования **центра администрирования Microsoft 365** > \*\*\*\* > **Teams** > Center.</span><span class="sxs-lookup"><span data-stu-id="7ce56-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="7ce56-143">Выберите номера **голосовых** > **телефонов**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="7ce56-144">Выберите номер телефона и нажмите кнопку **назначить**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="7ce56-145">Дополнительные сведения можно найти [в разделе изменение номеров телефонов для вашего моста звуковых конференций](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="7ce56-146">Шаг 5. Настройка языка по умолчанию и альтернативных языков для моста аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7ce56-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="7ce56-147"><a name="__top"></a> Затем вы захотите [настроить языки автосекретаря для голосовой конференции в Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) , которые должен использовать автосекретарь конференц-связи для приветствия звонков при подключении к телефонному номеру для голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="7ce56-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="7ce56-148">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="7ce56-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="7ce56-149">На панели мониторинга перейдите к**мостам конференций**для **собраний** > .</span><span class="sxs-lookup"><span data-stu-id="7ce56-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="7ce56-150">Выберите номер телефона моста конференц-связи, нажмите кнопку **изменить**, а затем выберите язык по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ce56-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="7ce56-151">Шаг 6. Настройка параметров моста аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7ce56-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="7ce56-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="7ce56-152"></span></span>
    
<span data-ttu-id="7ce56-153">После настройки моста аудиоконференции убедитесь, что значения параметров по умолчанию, например, уведомления при входе и выходе, а также длина ПИН-кода настроены правильно. При необходимости их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="7ce56-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="7ce56-154">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="7ce56-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="7ce56-155">На панели мониторинга перейдите к**мостам конференций**для **собраний** > .</span><span class="sxs-lookup"><span data-stu-id="7ce56-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="7ce56-156">Выберите **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-156">Select **Bridge settings**.</span></span> <span data-ttu-id="7ce56-157">Откроется панель **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="7ce56-158">Подробнее см. статью [Изменение параметров моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="7ce56-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="7ce56-159">Шаг 7. Назначение телефонных номеров для пользователей, которые проводят собрания</span><span class="sxs-lookup"><span data-stu-id="7ce56-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="7ce56-160">После создания моста аудиоконференции необходимо настроить платные и бесплатные служебные номера для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ce56-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="7ce56-161">Необходимо сделать это для всех сотрудников вашей организации, которые проводят или планируют собрания.</span><span class="sxs-lookup"><span data-stu-id="7ce56-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="7ce56-162">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="7ce56-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="7ce56-163">На панели мониторинга щелкните **Пользователи**, выберите пользователя из списка и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="7ce56-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="7ce56-164">Нажмите кнопку **изменить** рядом с пунктом " **звуковые конференции**", а затем в области **звуковые конференции** **выберите номер в** поле **платный** номер и бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="7ce56-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="7ce56-165">Подробнее см. в разделе [Назначение Майкрософт в качестве поставщика услуг аудиоконференций](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="7ce56-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="7ce56-166">Шаг 8. Настройка приглашений на собрания (необязательно)</span><span class="sxs-lookup"><span data-stu-id="7ce56-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="7ce56-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="7ce56-167"></span></span>
 
<span data-ttu-id="7ce56-168">Настроенные для пользователя телефонные номера будут автоматически добавляться к приглашениям на собрания, которые отправляются участникам.</span><span class="sxs-lookup"><span data-stu-id="7ce56-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="7ce56-169">Тем не менее, при желании, вы можете добавить свои собственные справочные и официальные ссылки, текстовое сообщение и небольшой логотип компании.</span><span class="sxs-lookup"><span data-stu-id="7ce56-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="7ce56-170">Дополнительные сведения: [Настройка приглашений на собрания](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="7ce56-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="7ce56-171">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ce56-171">Related topics</span></span>

[<span data-ttu-id="7ce56-172">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="7ce56-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="7ce56-173">Телефонные номера для аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ce56-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="7ce56-174">Установка параметров для онлайн-собраний и конференций</span><span class="sxs-lookup"><span data-stu-id="7ce56-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
