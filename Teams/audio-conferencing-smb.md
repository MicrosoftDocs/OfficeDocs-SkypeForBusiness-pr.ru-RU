---
title: Настройка аудиоконференций для компаний малого и среднего бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как настроить аудиоконференцию для малого или среднего бизнеса для людей, которым требуется использовать телефон для звонков на собрания. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122353"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="586de-103">Настройка аудиоконференций для компаний малого и среднего бизнеса</span><span class="sxs-lookup"><span data-stu-id="586de-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="586de-104">Используя аудиоконференцию, люди могут звонить на собрания Teams с помощью телефона, а не с помощью приложения Teams на мобильном устройстве или с компьютера.</span><span class="sxs-lookup"><span data-stu-id="586de-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="586de-105">Если вы малый или средний бизнес с 300 пользователями и у вас нет лицензий на аудиоконференцию, вы можете бесплатно получить аудиоконференцию в течение одного года.</span><span class="sxs-lookup"><span data-stu-id="586de-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="586de-106">Это бесплатное предложение доступно с 1 октября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="586de-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="586de-107">Лицензия на надстройку аудиоконференции может применяться к пользователям с лицензиями на Microsoft 365 бизнес базовый, бизнес-стандарт, бизнес-Premium, Enterprise E1 или Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="586de-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="586de-108">Подробнее см. в Teams [надстройки](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="586de-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="586de-109">Если вы Enterprise E5 или Голосовая связь Microsoft 365 бизнес, вы не сможете использовать бесплатное предложение аудиоконференций, так как эти лицензии уже включают аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="586de-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="586de-110">В этой статье мы построим аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="586de-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="586de-111">Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="586de-112">Участникам собрания, которые звонят на собрания, не требуются лицензии или другая настройка.</span><span class="sxs-lookup"><span data-stu-id="586de-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="586de-113">Дополнительные узнать см. в записи [Аудиоконференция.](audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="586de-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="586de-114">Настройка аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="586de-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="586de-115">При настройках аудиоконференции мосту аудиоконференций автоматически устанавливается номер телефона, который можно использовать в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="586de-116">Номер телефона, который назначен мосту для связи по умолчанию, будет номером из страны или региона вашей организации.</span><span class="sxs-lookup"><span data-stu-id="586de-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="586de-117">Этот номер телефона является платным номером, на который могут распространяться расходы на междугородние и междугородние связи.</span><span class="sxs-lookup"><span data-stu-id="586de-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="586de-118">Вы также можете использовать бесплатный номер, который потребует нескольких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="586de-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="586de-119">Дополнительные информацию о номерах телефонов для моста [](#audio-conferencing-phone-numbers) аудиоконференций см. в статье Номера телефонов для аудиоконференции далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="586de-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="586de-120">Шаг 1. Получить лицензии на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="586de-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="586de-121">Получите одну лицензию на аудиоконференцию для каждого человека, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="586de-122">Для этого Microsoft 365 центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="586de-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="586de-123">В Microsoft 365 администрирования перейдите в страницу Приобретение служб вы выставлений счета , а затем в нижней части страницы выберите  >   **Надстройки**.</span><span class="sxs-lookup"><span data-stu-id="586de-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="586de-124">Выберите **Microsoft 365 аудиоконференцию с** подробными сведениями о внедрении аудиоконференции , а затем выберите Получить  >   **сейчас**.</span><span class="sxs-lookup"><span data-stu-id="586de-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="586de-125">Введите количество лицензий, необходимых организаторам собраний, а затем заполните свой заказ.</span><span class="sxs-lookup"><span data-stu-id="586de-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Снимок экрана: лицензия на аудиоконференцию adoption Promo":::

    > [!NOTE]
    > <span data-ttu-id="586de-127">В зависимости от того, хотите ли вы автоматически назначить лицензию на аудиоконференцию всем пользователям без лицензий, отключите или выберите автоматически назначать лицензию на аудиоконференцию всем пользователям, у которых нет этой лицензии.</span><span class="sxs-lookup"><span data-stu-id="586de-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="586de-128">Шаг 2. Назначение лицензии на аудиоконференцию пользователям, которые ведут собрания</span><span class="sxs-lookup"><span data-stu-id="586de-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="586de-129">Назначьте лицензию каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="586de-130">Для этого Microsoft 365 центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="586de-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="586de-131">Назначение лицензии одному пользователю</span><span class="sxs-lookup"><span data-stu-id="586de-131">Assign a license to one user</span></span>

1. <span data-ttu-id="586de-132">В центре Microsoft 365 пользователей перейдите в **группу Пользователи**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="586de-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="586de-133">Выберите строку пользователя, лицензию на который вы хотите назначить, а затем в области выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="586de-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="586de-134">Выберите  Microsoft 365 аудиоконференцию и выберите Сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="586de-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="586de-135">Назначение лицензии нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="586de-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="586de-136">В центре Microsoft 365 пользователей перейдите в **группу Пользователи**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="586de-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="586de-137">Выберите круги рядом с пользователями, которые хотите назначить лицензию, а затем выберите **Управление лицензиями продуктов**.</span><span class="sxs-lookup"><span data-stu-id="586de-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="586de-138">В области **Управление лицензиями продуктов** выберите **Назначить больше**.</span><span class="sxs-lookup"><span data-stu-id="586de-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="586de-139">Выберите  Microsoft 365 аудиоконференцию и выберите Сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="586de-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="586de-140">Запланировать Teams собрания в Outlook</span><span class="sxs-lookup"><span data-stu-id="586de-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="586de-141">Организаторы собраний теперь могут планировать собрания в Outlook.</span><span class="sxs-lookup"><span data-stu-id="586de-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="586de-142">В Outlook перейдите в **календарь** и выберите кнопку **Teams собрание.**</span><span class="sxs-lookup"><span data-stu-id="586de-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="586de-143">Номера для телефонного дозвона и номер конференции автоматически добавляются в приглашение на собрание, которое отправляется участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="586de-144">Дополнительные информации см. в [Teams собрания в Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)</span><span class="sxs-lookup"><span data-stu-id="586de-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="586de-145">При этом вы можете настроить приглашения на собрания, чтобы добавить логотип компании, ссылки на веб-сайт службы поддержки и юридическое заявление, а также текстовый прикладный.</span><span class="sxs-lookup"><span data-stu-id="586de-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="586de-146">Подробнее см. в [настройках приглашений на собрания.](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="586de-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="586de-147">Номера телефонов для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="586de-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="586de-148">Существует два типа номеров, которые можно использовать для мостаконференций.</span><span class="sxs-lookup"><span data-stu-id="586de-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="586de-149">Вы можете использовать **как** общие [](#set-up-audio-conferencing) номера (как в разделе Настройка аудиоконференции ранее в этой статье), так и **выделенные номера.**</span><span class="sxs-lookup"><span data-stu-id="586de-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="586de-150">Дополнительные сведения о каждом из них.</span><span class="sxs-lookup"><span data-stu-id="586de-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="586de-151">Общие номера</span><span class="sxs-lookup"><span data-stu-id="586de-151">Shared numbers</span></span>

<span data-ttu-id="586de-152">Общий номер — это число, которое совместно с другими организациями.</span><span class="sxs-lookup"><span data-stu-id="586de-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="586de-153">Общие номера — это платные номера, которые автоматически устанавливаются при настроить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="586de-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="586de-154">Чтобы узнать номер по умолчанию, который назначен мосту конференц-связь, на левой навигации Центра администрирования Microsoft Teams перейдите к мосту Конференц-связь собраний и найдите номер ближайшего  >  расположения.</span><span class="sxs-lookup"><span data-stu-id="586de-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="586de-155">Выделенные числа</span><span class="sxs-lookup"><span data-stu-id="586de-155">Dedicated numbers</span></span>

<span data-ttu-id="586de-156">Выделенное число — это число, доступное только пользователям.</span><span class="sxs-lookup"><span data-stu-id="586de-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="586de-157">Выделенный номер может быть платным или бесплатным.</span><span class="sxs-lookup"><span data-stu-id="586de-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="586de-158">Чтобы использовать выделенный номер, необходимо сначала получить номер, назначить его мосту для проведения собраний, а затем назначить номер каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="586de-159">Существует несколько способов получить выделенное число.</span><span class="sxs-lookup"><span data-stu-id="586de-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="586de-160">Вы можете получить номер от Майкрософт или перенести (перенос) существующего номера от текущего поставщика услуг в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="586de-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="586de-161">Дополнительные информацию о том, как это сделать, см. в теме [Получение номеров служб.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="586de-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="586de-162">Имейте в виду, что если вы используете бесплатный номер, сначала необходимо назначить лицензию на кредиты на связь каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="586de-163">Дополнительные см. в настройках кредитов на [связь для организации.](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="586de-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="586de-164">После того как у вас есть номер, назначьте его мосту конференц-залов.</span><span class="sxs-lookup"><span data-stu-id="586de-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="586de-165">Для этого Microsoft Teams центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="586de-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="586de-166">В левой области навигации Центра администрирования Microsoft Teams перейдите к **мосту**  >  **конференции собраний**.</span><span class="sxs-lookup"><span data-stu-id="586de-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="586de-167">Выберите **Добавить**, а затем — **Платный или** **Бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="586de-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="586de-168">В области **Добавление номера** телефона выберите номер и выберите **применить**.</span><span class="sxs-lookup"><span data-stu-id="586de-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="586de-169">Затем назначьте номер каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="586de-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="586de-170">Для этого Microsoft Teams центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="586de-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="586de-171">В левой области навигации Центра Microsoft Teams выберите **Пользователи**, щелкните отображаемого имени пользователя и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="586de-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="586de-172">Выберите **Изменить** рядом с функцией Аудиоконференция, а затем в области Аудиоконференция выберите номер в списках Платный номер или Бесплатный номер и выберите **Применить**.    </span><span class="sxs-lookup"><span data-stu-id="586de-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="586de-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="586de-173">Related topics</span></span>

- [<span data-ttu-id="586de-174">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="586de-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="586de-175">Настройка аудиоконференций для Teams</span><span class="sxs-lookup"><span data-stu-id="586de-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="586de-176">Номера телефонов для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="586de-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="586de-177">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="586de-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="586de-178">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="586de-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="586de-179">Teams надстройки</span><span class="sxs-lookup"><span data-stu-id="586de-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="586de-180">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="586de-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)