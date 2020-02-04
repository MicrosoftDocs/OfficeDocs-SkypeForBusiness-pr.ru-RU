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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: fc2dd9fcbd120b5471228d0b2728f90b48622f73
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693904"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="cca81-103">Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="cca81-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="cca81-p101">Если вы хотите использовать бесплатные телефонные номера в Skype для бизнеса и Microsoft Teams, вам нужно будет настроить кредиты на связь. Кроме того, мы рекомендуем вам настроить кредитовое сопровождение для абонентских планов (внутренних и международных), а также пользователей голосовой конференции, которым требуется возможность звонить в **любую точку назначения**. Многие страны и регионы включены, но некоторые из них могут быть не включены в план звонков или на подписку на голосовую связь. Если вы не настроили выставление счетов на звонки и не назначаете лицензии на **подписку** для пользователей и не хотите, чтобы ваша организация выпустила дополнительные минуты (в зависимости от вашего тарифного плана или плана видеоконференций в вашей стране или регионе), пользователи не смогут звонить и звонить из собраний с голосовой связью. Чтобы получить дополнительные сведения, в том числе рекомендованные суммы финансирования, прочитайте, [что такое кредиты?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="cca81-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="cca81-109">Для получения сведений о стоимости [ознакомьтесь с тарифами здесь](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="cca81-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="cca81-110">Шаг 1: Назначение лицензий на голосовую конференцию или план звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="cca81-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="cca81-p102">При регистрации вы получите определенное количество минут в зависимости от страны или региона. Вы можете просмотреть количество минут, в которых вы сможете найти страну [или регион.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) После того как вы пользуетесь этими минутами, звонки будут разорваны. Чтобы не допустить этого, вам нужно настроить кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="cca81-p102">When you sign up, you get a certain number of minutes depending on your country/region. You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). After you use those minutes, calls will be disconnected. To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="cca81-115">Для этого **нужно назначить лицензию на аудиоконференции или телефонную систему** своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="cca81-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="cca81-p103">Назначение лицензии на **голосовую конференцию** для пользователей. Ознакомьтесь с разделами [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="cca81-p103">Assign an **Audio Conferencing** license to your users. See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="cca81-118">После назначения этой лицензии вам потребуется настроить голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="cca81-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="cca81-119">Пошаговые инструкции вы можете найти в статье Использование [и приобретение звуковых конференций в Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cca81-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="cca81-p105">Назначение лицензии на **телефонную систему** и **внутренний или внутренний и Международный** план звонков для пользователей. Ознакомьтесь с разделами [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="cca81-p105">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users. See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cca81-122">Несмотря на то что это не требуется для кредитов на связь, вам также необходимо назначить лицензию на **внутренние звонки** или **план внутренних и международных звонков** .</span><span class="sxs-lookup"><span data-stu-id="cca81-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="cca81-p106">После назначения указанных лицензий вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам. Пошаговые инструкции по настройке см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cca81-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="cca81-125">Дополнительные сведения можно найти [в разделе Лицензирование надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="cca81-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="cca81-126">Шаг 2. Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="cca81-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="cca81-127">Войдите на новый портал Office 365 с помощью своей рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cca81-127">Sign in to the new Office 365 portal with your work or school account.</span></span>
    
2. <span data-ttu-id="cca81-128">В левой области навигации центра администрирования Microsoft 365 перейдите к разделу**подписки** > на план **выставления счетов** > **Добавление подписок**.</span><span class="sxs-lookup"><span data-stu-id="cca81-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="cca81-129">Разверните раздел **подписки на надстройки**, а затем выберите пункт **кредиты** > \*\*\*\* на связь.</span><span class="sxs-lookup"><span data-stu-id="cca81-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="cca81-130">На странице Подписка на подписку на **связь** введите данные и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cca81-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="cca81-p107">**Добавить средства**. Введите сумму, которую следует добавить на счет. Если автоматическое пополнение счета отключено, после исчерпания этих средств функции звонков, реализуемые посредством кредитов на связь (например, услуга бесплатных входящих звонков), станут недоступны. Чтобы не пополнять счет кредитов на связь вручную каждый раз, когда остаток на нем достигает нуля, рекомендуем включить функцию автоматического пополнения счета.</span><span class="sxs-lookup"><span data-stu-id="cca81-p107">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="cca81-134">**Авт. пополнение счета**. Включение автоматического пополнения счета позволяет автоматически добавлять средства на ваш счет, когда остаток на нем опускается ниже заданного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="cca81-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="cca81-p108">Рекомендуем использовать функцию **Автоматическое пополнение счета**, чтобы, когда счет за кредиты на связь достигнет нуля, ваше обслуживание не прерывалось. Вы будете получать сообщения по электронной почте, когда транзакция с пополнением счета проходит успешно, когда она не проходит (например, из-за истекшего срока действия банковской карты), а также когда ваш счет за кредиты на связь достигает нуля.</span><span class="sxs-lookup"><span data-stu-id="cca81-p108">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="cca81-137">**Сумма пополнения**. В поле **Enter the amount in the (Пополнять счет с)** введите сумму, на которую требуется пополнить счет, когда остаток на нем достигает указанной ниже пороговой суммы.</span><span class="sxs-lookup"><span data-stu-id="cca81-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="cca81-p109">**Пороговая сумма**. В поле **When the balance falls below (Когда баланс меньше)** введите сумму, которая будет использоваться для " *активации*  " функции автоматического пополнения счета. Когда остаток на счете опускается ниже этого значения, на ваш счет автоматически добавляется сумма, указанная в поле "Сумма пополнения".</span><span class="sxs-lookup"><span data-stu-id="cca81-p109">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="cca81-p110">Средства будут расходоваться только на оплату кредитов на связь по опубликованным корпорацией Майкрософт тарифам при использовании служб. Средства, не израсходованные за 12 месяцев с даты приобретения, списываются и не могут использоваться для оплаты.</span><span class="sxs-lookup"><span data-stu-id="cca81-p110">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="cca81-142">Ежемесячное выставление счетов за кредитные звонки будут применяться только в том случае, если вы используете использованный фонд, чтобы узнать, как проверить месячное использование, ознакомиться с [отчетом использование PSTN в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="cca81-142">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="cca81-143">Введите платежные данные и выберите команду **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="cca81-143">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="cca81-144">Если вы являетесь заказчиком корпоративного лицензирования, вы можете выбрать номер своего корпоративного соглашения для оплаты.</span><span class="sxs-lookup"><span data-stu-id="cca81-144">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="cca81-145">Если у вас несколько номеров корпоративных соглашений, вы сможете выбрать Корпоративное соглашение, которое вы хотите использовать для оплаты.</span><span class="sxs-lookup"><span data-stu-id="cca81-145">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="cca81-146">Вы также можете указать номер заказа на покупку, который будет связан с корпоративным номером соглашения (если применимо).</span><span class="sxs-lookup"><span data-stu-id="cca81-146">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="cca81-p112">У каждой организации свой объем по плану звонков и свои тарифы. Эти сведения необходимо получить у своего текущего поставщика услуг. Организации, уже использующие в качестве поставщика услуг Skype для бизнеса Online, могут получить данные по использованию в отчете ( **Центр администрирования Skype для бизнеса** > **Отчеты** > **Сведения об использовании ТСОП**).</span><span class="sxs-lookup"><span data-stu-id="cca81-p112">Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="cca81-150">Если вы настраиваете кредиты на связь, вам потребуется изучить использование звонков для вашей организации, чтобы определить необходимые Вам суммы.</span><span class="sxs-lookup"><span data-stu-id="cca81-150">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="cca81-151">Сведения о звонках можно получить в отчете **Сведения об использовании ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="cca81-151">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="cca81-152">Этот отчет позволяет экспортировать записи данных о звонках в Excel, если требуется сохранить данные или создать пользовательские отчеты.</span><span class="sxs-lookup"><span data-stu-id="cca81-152">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="cca81-153">Узнать о том, как просмотреть сведения об использовании, читайте в статье [Использование КТСОП в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span><span class="sxs-lookup"><span data-stu-id="cca81-153">To learn how to see usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="cca81-154">Шаг 3. Назначение лицензии на кредиты на связь пользователям</span><span class="sxs-lookup"><span data-stu-id="cca81-154">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="cca81-155">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="cca81-155">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="cca81-156">В левой области навигации центра администрирования Microsoft 365 перейдите в раздел**Активные пользователи** **пользователей** > , а затем выберите пользователя или пользователей из списка.</span><span class="sxs-lookup"><span data-stu-id="cca81-156">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="cca81-157">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cca81-157">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="cca81-158">На странице **лицензии на продукты** **выберите для него** значение в поле **вкл** ., чтобы назначить эту лицензию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cca81-158">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cca81-159">Это рекомендуется делать даже в том случае, если у вас есть пользователи с назначенными лицензиями на выпуск **Корпоративный E5**.</span><span class="sxs-lookup"><span data-stu-id="cca81-159">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="cca81-160">Что необходимо знать о планах и тарифах?</span><span class="sxs-lookup"><span data-stu-id="cca81-160">Want to know about plans and pricing?</span></span>

<span data-ttu-id="cca81-161">С планами и тарифами можно ознакомиться по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="cca81-161">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="cca81-162">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="cca81-162">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="cca81-163">Планы голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="cca81-163">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="cca81-164">Планы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="cca81-164">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="cca81-165">Вы также можете просмотреть сведения, [войдя в центр администрирования Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) и перейдя на \*\*\*\* > **подписку** > на план**подписки.**</span><span class="sxs-lookup"><span data-stu-id="cca81-165">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="cca81-166">Чтобы просмотреть таблицу с лицензией или лицензиями, которые понадобятся для каждой функции, ознакомьтесь со страницей [Лицензирование Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="cca81-166">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cca81-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cca81-167">Related topics</span></span>

- [<span data-ttu-id="cca81-168">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cca81-168">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="cca81-169">Настройка облачной голосовой почты — справка для администратора</span><span class="sxs-lookup"><span data-stu-id="cca81-169">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="cca81-170">[Настройка в Тарифных планов](set-up-calling-plans.md) и [Тарифные планы для Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="cca81-170">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="cca81-171">Пополнение средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="cca81-171">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
