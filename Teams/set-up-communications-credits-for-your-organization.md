---
title: Настройка кредитов на связь для организации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 51885d80e698d0f47308c45110af83063e7bd7ba
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031395"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e8cb4-103">Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="e8cb4-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="e8cb4-p101">Если вы хотите использовать бесплатные номера в Skype для бизнеса и Microsoft Teams, необходимо настроить кредиты на связь. Кроме того, мы рекомендуем настроить кредиты на связь для пользователей планов звонков (для внутренних и международных звонков) и аудиоконференций, которым нужна возможность звонить в любую **точку назначения.** В подписки на план звонков или аудиоконференцию могут включаться многие страны и регионы, но некоторые назначения могут отключаться. Если вы не настроили выставление счета  за кредиты на связь и не назначили пользователям лицензию на кредиты на связь и у вашей организации законных минут (в зависимости от плана звонков или плана аудиоконференции в вашей стране или регионе), они не смогут звонить или звонить из аудиоконференции. Дополнительные сведения, в том числе рекомендуемые суммы оплаты, можно найти в окнах "Что [такое кредиты на связь"?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8cb4-109">Для получения сведений о стоимости [ознакомьтесь с тарифами здесь](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="e8cb4-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="e8cb4-110">Шаг 1. Назначение пользователям лицензии на аудиоконференцию или план звонков</span><span class="sxs-lookup"><span data-stu-id="e8cb4-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="e8cb4-p102">При регистрации вы получаете определенное количество минут в зависимости от страны или региона. Вы можете найти свою страну [](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) или регион в списке доступности "Страна или регион" для аудиоконференций и планов звонков, чтобы узнать количество минут, которые вы получите. После использования этих минут звонки отключаются. Чтобы этого не происходило, необходимо настроить кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p102">When you sign up, you get a certain number of minutes depending on your country/region. You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get. After you use those minutes, calls will be disconnected. To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="e8cb4-115">Для этого **нужно назначить лицензию на аудиоконференции или телефонную систему** своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="e8cb4-p103">**Назначьте пользователям лицензию на** аудиоконференцию. См. ["Назначение лицензий на надстройки Microsoft Teams".](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p103">Assign an **Audio Conferencing** license to your users. See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
    
    <span data-ttu-id="e8cb4-118">После назначения этой лицензии необходимо настроить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="e8cb4-119">Пошаговые инструкции см. в инструкциях по приобретению или попробуйте аудиоконференцию в [Microsoft 365 или Office 365.](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="e8cb4-p105">**Назначьте пользователям телефонную** систему и лицензию на **план** внутренних или международных и внутренних звонков. См. ["Назначение лицензий на надстройки Microsoft Teams".](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p105">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users. See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8cb4-122">Хотя это не требуется для кредитов на связь, вам также  необходимо назначить план внутренних звонков или лицензию на план внутренних и международных **звонков.**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="e8cb4-p106">После назначения указанных лицензий вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам. Пошаговые инструкции по настройке см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="e8cb4-125">Дополнительные сведения см. в [лицензировании надстройки Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-125">For more information, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e8cb4-126">Шаг 2. Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="e8cb4-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="e8cb4-127">Войте в [Центр администрирования Microsoft 365](https://portal.office.com/Adminportal) с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="e8cb4-128">В левой области навигации Центра администрирования Microsoft 365 перейдите в меню "Приобретение служб **вы**  >  **выставлений счета".**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="e8cb4-129">Прокрутите страницу вниз и выберите **"Надстройки".**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="e8cb4-130">Выберите **кредиты на связь.**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="e8cb4-131">На странице **подписки на кредиты** на связь в заполните данные и нажмите кнопку "Далее". </span><span class="sxs-lookup"><span data-stu-id="e8cb4-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="e8cb4-p108">**Добавить средства**. Введите сумму, которую следует добавить на счет. Если автоматическое пополнение счета отключено, после исчерпания этих средств функции звонков, реализуемые посредством кредитов на связь (например, услуга бесплатных входящих звонков), станут недоступны. Чтобы не пополнять счет кредитов на связь вручную каждый раз, когда остаток на нем достигает нуля, рекомендуем включить функцию автоматического пополнения счета.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p108">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="e8cb4-135">**Авт. пополнение счета**. Включение автоматического пополнения счета позволяет автоматически добавлять средства на ваш счет, когда остаток на нем опускается ниже заданного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="e8cb4-p109">Рекомендуем использовать функцию **Автоматическое пополнение счета**, чтобы, когда счет за кредиты на связь достигнет нуля, ваше обслуживание не прерывалось. Вы будете получать сообщения по электронной почте, когда транзакция с пополнением счета проходит успешно, когда она не проходит (например, из-за истекшего срока действия банковской карты), а также когда ваш счет за кредиты на связь достигает нуля.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p109">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="e8cb4-138">**Сумма пополнения**. В поле **Enter the amount in the (Пополнять счет с)** введите сумму, на которую требуется пополнить счет, когда остаток на нем достигает указанной ниже пороговой суммы.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="e8cb4-p110">**Пороговая сумма**. В поле **When the balance falls below (Когда баланс меньше)** введите сумму, которая будет использоваться для " *активации*  " функции автоматического пополнения счета. Когда остаток на счете опускается ниже этого значения, на ваш счет автоматически добавляется сумма, указанная в поле "Сумма пополнения".</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p110">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="e8cb4-p111">Средства будут расходоваться только на оплату кредитов на связь по опубликованным корпорацией Майкрософт тарифам при использовании служб. Средства, не израсходованные за 12 месяцев с даты приобретения, списываются и не могут использоваться для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-p111">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="e8cb4-143">Ежемесячное выставление счета за кредиты на связь будет применяться только в том случае, если уже использовался этот фонд. Чтобы узнать, как проверить ежемесячную оплату за использование, ознакомьтесь с отчетом об использовании услуг ПС [в Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e8cb4-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="e8cb4-144">Введите платежные данные и выберите команду **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="e8cb4-145">Если вы клиент корпоративного лицензирования, вы можете выбрать номер своего корпоративного соглашения для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="e8cb4-146">Если у вас несколько номеров корпоративных соглашений, вы сможете выбрать, какое корпоративное соглашение вы хотите использовать для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="e8cb4-147">Вам также будет предоставлена возможность указать номер заказа на покупку, который будет связываться с номером корпоративного соглашения (если применимо).</span><span class="sxs-lookup"><span data-stu-id="e8cb4-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="e8cb4-148">У каждой организации свой объем по плану звонков и свои тарифы.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="e8cb4-149">Эти сведения необходимо получить у своего текущего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="e8cb4-150">Организации, уже использующие в качестве поставщика услуг Skype для бизнеса Online, могут получить данные об использовании, просмотрев их в отчете об использовании услуг ННР в Центре администрирования **Microsoft**  >    >   Teams.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="e8cb4-151">При настройке кредитов на связь вам потребуется изучить использование параметров звонка в вашей организации, чтобы определить необходимую сумму.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="e8cb4-152">Сведения о звонках можно получить в отчете **Сведения об использовании ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="e8cb4-153">Этот отчет позволяет экспортировать записи данных об звонках в Excel, если требуется сохранить данные или создать настраиваемые отчеты.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="e8cb4-154">Чтобы узнать, как увидеть данные об использовании, ознакомьтесь с отчетом об [использовании ННР.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-154">To learn how to see usage, read [PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="e8cb4-155">Шаг 3. Назначение лицензии на кредиты на связь пользователям</span><span class="sxs-lookup"><span data-stu-id="e8cb4-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="e8cb4-156">Войте в [Центр администрирования Microsoft 365](https://portal.office.com/Adminportal) с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="e8cb4-157">В левой области навигации Центра администрирования Microsoft 365 перейдите к списку "Пользователи активных пользователей" и выберите  >  пользователя из списка.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="e8cb4-158">Выберите **"Лицензии и приложения".**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="e8cb4-159">Чтобы назначить эту лицензию, передать кредиты на связь в вкл., а затем выберите **"Сохранить".**  </span><span class="sxs-lookup"><span data-stu-id="e8cb4-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8cb4-160">Это рекомендуется делать даже в том случае, если у вас есть пользователи с назначенными лицензиями на выпуск **Корпоративный E5**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8cb4-161">С помощью [Powershell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) можно назначать лицензии и приложения нескольким пользователям с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-161">You can use [Powershell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="e8cb4-162">Что необходимо знать о планах и тарифах?</span><span class="sxs-lookup"><span data-stu-id="e8cb4-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="e8cb4-163">С планами и тарифами можно ознакомиться по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="e8cb4-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="e8cb4-164">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="e8cb4-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="e8cb4-165">Планы аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e8cb4-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="e8cb4-166">Планы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e8cb4-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="e8cb4-167">Вы также можете увидеть сведения, во входе в Центр администрирования [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) и переходить к добавлению подписок на подписки на выставление  >    >  **счета.**</span><span class="sxs-lookup"><span data-stu-id="e8cb4-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="e8cb4-168">Таблицу с лицензиями, необходимыми для каждой функции, см. в лицензировании [надстройки Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e8cb4-169">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e8cb4-169">Related topics</span></span>

- [<span data-ttu-id="e8cb4-170">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e8cb4-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="e8cb4-171">Настройка облачной голосовой почты — справка для администратора</span><span class="sxs-lookup"><span data-stu-id="e8cb4-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="e8cb4-172">[Настройка планов звонков](set-up-calling-plans.md) и планов [звонков для Microsoft 365 или Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e8cb4-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="e8cb4-173">Пополнение средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="e8cb4-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
