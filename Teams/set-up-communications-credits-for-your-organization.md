---
title: Настройка кредитов на связь для организации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 0570c454cdc3fc98fa6dfa4a8fe571714263421e
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "30048287"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e4bf4-103">Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="e4bf4-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="e4bf4-104">Необходимо будет настроить кредитов коммуникаций, если вы хотите использовать бесплатные номера с Скайп для бизнеса и группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="e4bf4-105">Кроме того рекомендуется настроить кредитов коммуникаций для вызова планы (Россия или международный) и аудиоконференции пользователей, которым требуется возможность выполнять звонки в **любое место назначения**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="e4bf4-106">Подписки на планы звонков и аудиоконференции охватывают множество стран и регионов, но некоторые точки могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="e4bf4-107">При не Настройка кредитов Communications выставления счетов и назначение лицензии **Кредитов коммуникации** для пользователей и выполнения масштабирование минут для вашей организации (в зависимости от вызова план или аудиоконференции плана в Страна или регион), этих пользователей не будут иметь возможность выполнения звонков или звонков из собрания конференц-связи звука.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="e4bf4-108">Можно получить дополнительные сведения, включая рекомендуемые финансирования сумм, прочитав статью [Каковы кредитов коммуникации?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="e4bf4-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4bf4-109">Для получения сведений о стоимости [ознакомьтесь с тарифами здесь](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="e4bf4-110">Шаг 1. Назначение пользователям лицензий на планы звонков и аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e4bf4-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="e4bf4-111">При регистрации вы получаете определенное количество минут, которое зависит от страны/региона.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="e4bf4-112">Число минут, вы получите поиска для страны или региона, можно увидеть [здесь](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-112">You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> <span data-ttu-id="e4bf4-113">После использования всех этих минут звонки отключаются.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="e4bf4-114">Во избежание такой ситуации следует настроить кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="e4bf4-115">Для этого **нужно назначить лицензию на аудиоконференции или телефонную систему** своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="e4bf4-116">Назначение лицензии **Звук конференц-связи** для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="e4bf4-117">В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-117">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>
    
    <span data-ttu-id="e4bf4-118">После назначения данной лицензии, необходимо будет настроить аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="e4bf4-119">Пошаговые инструкции в разделе [Попробуйте или Покупка Audio конференция в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365).</span></span>
    
- <span data-ttu-id="e4bf4-120">Назначение **Телефона системы** и внутри страны или внутреннее и международное лицензии вызов планирование для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="e4bf4-121">В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-121">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4bf4-122">Хотя это не является обязательным для коммуникаций кредитов, по-прежнему необходимо также назначить **Планирование внутренних звонков** или **Внутренний и вызов планирование International** лицензии.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="e4bf4-p106">После назначения указанных лицензий вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам. Пошаговые инструкции по настройке см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="e4bf4-125">Дополнительные сведения см. в статье [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-125">For more information, see [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e4bf4-126">Шаг 2. Настройка кредитов на связь для организации</span><span class="sxs-lookup"><span data-stu-id="e4bf4-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="e4bf4-127">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e4bf4-128">В левой области переходов центра администрирования Office 365, перейдите к **выставления счетов** > **подписки** > **Добавить подписки**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="e4bf4-129">Разверните **дополнительный компонент подписки**, а затем выберите **Кредитов Communications** > **купить**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="e4bf4-130">На странице подписки **Кредитов Communications** заполните данные и нажмите кнопку **Далее**:</span><span class="sxs-lookup"><span data-stu-id="e4bf4-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="e4bf4-p107">**Добавить средства**. Введите сумму, которую следует добавить на счет. Если автоматическое пополнение счета отключено, после исчерпания этих средств функции звонков, реализуемые посредством кредитов на связь (например, услуга бесплатных входящих звонков), станут недоступны. Чтобы не пополнять счет кредитов на связь вручную каждый раз, когда остаток на нем достигает нуля, рекомендуем включить функцию автоматического пополнения счета.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p107">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="e4bf4-134">**Авт. пополнение счета**. Включение автоматического пополнения счета позволяет автоматически добавлять средства на ваш счет, когда остаток на нем опускается ниже заданного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="e4bf4-p108">Рекомендуем использовать функцию **Автоматическое пополнение счета**, чтобы, когда счет за кредиты на связь достигнет нуля, ваше обслуживание не прерывалось. Вы будете получать сообщения по электронной почте, когда транзакция с пополнением счета проходит успешно, когда она не проходит (например, из-за истекшего срока действия банковской карты), а также когда ваш счет за кредиты на связь достигает нуля.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p108">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="e4bf4-137">**Сумма пополнения**. В поле **Enter the amount in the (Пополнять счет с)** введите сумму, на которую требуется пополнить счет, когда остаток на нем достигает указанной ниже пороговой суммы.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="e4bf4-p109">**Пороговая сумма**. В поле **When the balance falls below (Когда баланс меньше)** введите сумму, которая будет использоваться для " *активации*  " функции автоматического пополнения счета. Когда остаток на счете опускается ниже этого значения, на ваш счет автоматически добавляется сумма, указанная в поле "Сумма пополнения".</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p109">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="e4bf4-p110">Средства будут расходоваться только на оплату кредитов на связь по опубликованным корпорацией Майкрософт тарифам при использовании служб. Средства, не израсходованные за 12 месяцев с даты приобретения, списываются и не могут использоваться для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p110">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
5. <span data-ttu-id="e4bf4-142">Введите платежные данные и выберите команду **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-142">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="e4bf4-143">Если вы являетесь клиентом корпоративного лицензирования, можно выбрать номер соглашение enterprise для платежа.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-143">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="e4bf4-144">Если у вас есть несколько номеров соглашение enterprise, вы сможете выбрать соглашение enterprise вы хотите использовать для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-144">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="e4bf4-145">Вы также получит возможность указать номер заказа на покупку для связи с номером соглашение enterprise (если применимо).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-145">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="e4bf4-p112">У каждой организации свой объем по плану звонков и свои тарифы. Эти сведения необходимо получить у своего текущего поставщика услуг. Организации, уже использующие в качестве поставщика услуг Skype для бизнеса Online, могут получить данные по использованию в отчете ( **Центр администрирования Skype для бизнеса** > **Отчеты** > **Сведения об использовании ТСОП**).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-p112">Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="e4bf4-149">При настройке кредитов на связь нужно проанализировать объем звонков в своей организации, чтобы определить сумму пополнения счета.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-149">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="e4bf4-150">Сведения об объеме звонков можно получить в отчете **Сведения об использовании ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-150">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="e4bf4-151">Если требуется сохранить данные по звонкам или создавать специализированные отчеты, можно экспортировать записи из этого отчета в Excel.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-151">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="e4bf4-152">Об использовании см [Скайп для отчета об использовании PSTN бизнеса](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="e4bf4-152">To see usage, see [Skype for Business PSTN usage report](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="e4bf4-153">Шаг 3. Назначение лицензии на кредиты на связь пользователям</span><span class="sxs-lookup"><span data-stu-id="e4bf4-153">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="e4bf4-154">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e4bf4-155">В центре администрирования Office 365 на панели навигации слева выберите **Пользователи** > **Активные пользователи**, затем укажите одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-155">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="e4bf4-156">На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-156">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="e4bf4-157">На странице **лицензий на продукт** включения и отключения **Кредитов коммуникаций** **на** назначение данной лицензии и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-157">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4bf4-158">Это рекомендуется делать даже в том случае, если у вас есть пользователи с назначенными лицензиями на выпуск **Корпоративный E5**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-158">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="e4bf4-159">Что необходимо знать о планах и тарифах?</span><span class="sxs-lookup"><span data-stu-id="e4bf4-159">Want to know about plans and pricing?</span></span>

<span data-ttu-id="e4bf4-160">С планами и тарифами можно ознакомиться по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="e4bf4-160">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="e4bf4-161">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="e4bf4-161">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="e4bf4-162">Планы аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e4bf4-162">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="e4bf4-163">Планы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e4bf4-163">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="e4bf4-164">Чтобы просмотреть дополнительную информацию, [войдите в центр администрирования Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) и выберите **Выставление счетов** > **Подписки** > **Добавить подписки**.</span><span class="sxs-lookup"><span data-stu-id="e4bf4-164">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="e4bf4-165">Таблицу с описанием лицензий, необходимых для использования различных компонентов, см. в разделе [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="e4bf4-165">To see a table with the license or licenses you will need for each feature, see [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4bf4-166">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e4bf4-166">Related topics</span></span>

- [<span data-ttu-id="e4bf4-167">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e4bf4-167">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="e4bf4-168">Настройка голосовой почты телефонной системы  справка для администратора</span><span class="sxs-lookup"><span data-stu-id="e4bf4-168">Set up Phone System voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="e4bf4-169">[Настройка в Тарифных планов](set-up-calling-plans.md) и [Тарифные планы для Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e4bf4-169">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="e4bf4-170">Добавление средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="e4bf4-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
- <span data-ttu-id="e4bf4-171">[Настройка соединителя облако](https://technet.microsoft.com/library/mt605228.aspx) и [Загрузите соединитель облако](https://aka.ms/CloudConnectorInstaller)</span><span class="sxs-lookup"><span data-stu-id="e4bf4-171">[Configure the Cloud Connector](https://technet.microsoft.com/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)</span></span>

  
 