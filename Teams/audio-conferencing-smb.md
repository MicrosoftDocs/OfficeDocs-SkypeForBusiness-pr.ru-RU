---
title: Настройка голосовой конференции для малых и средних организаций
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как настроить голосовую конференцию в малых или средних организациях для пользователей, которые должны использовать телефон для звонков в собрании. '
ms.openlocfilehash: 13dd6812d6eaf51d2f88ac6d8831552cb63d5a9d
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389947"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="ccd5f-103">Настройка голосовой конференции для малых и средних организаций</span><span class="sxs-lookup"><span data-stu-id="ccd5f-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="ccd5f-104">Благодаря голосовой конференции пользователи могут звонить на собрания Teams с помощью телефона, а не с помощью приложения Teams на мобильном устройстве или с компьютера.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="ccd5f-105">Если вы используете не более 300 пользователей и не используете лицензий на голосовую связь, вы можете бесплатно подписаться на голосовую конференцию в течение одного года.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="ccd5f-106">Это бесплатное предложение доступно начиная с 1 октября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="ccd5f-107">Лицензия на надстройку "звуковые конференции" может быть применена к пользователям, которые имеют лицензии Microsoft 365 Business Basic, Business E1, корпоративное и E3.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="ccd5f-108">Дополнительные сведения можно найти в разделе [лицензии на надстройки для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="ccd5f-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="ccd5f-109">Если у вас Корпоративная голосовая связь в корпоративной среде или Microsoft 365, вы не сможете использовать бесплатные видеоконференции, так как в этих лицензиях уже есть голосовые конференции.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="ccd5f-110">В этой статье мы рассмотрим, как настроить голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="ccd5f-111">Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="ccd5f-112">Участники собрания, вызывающие участие в собраниях, не нуждаются в лицензиях и других параметрах настройки.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="ccd5f-113">Дополнительные сведения можно найти в статье [звуковые конференции](audio-conferencing-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ccd5f-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="ccd5f-114">Настройка аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="ccd5f-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="ccd5f-115">При настройке голосовой конференции телефонный номер автоматически назначается своему мосту конференц-связи, чтобы его можно было использовать в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="ccd5f-116">Номер телефона, назначенный по умолчанию для моста конференц-связи, будет относиться к одной из стран или регионов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="ccd5f-117">Этот номер телефона – это платный номер, на который может взиматься плата за междугородние звонки.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="ccd5f-118">Вы также можете использовать бесплатный номер, для которого требуется выполнить несколько дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="ccd5f-119">Чтобы узнать больше о номерах телефонов для моста конференц-связи, ознакомьтесь со статьей ниже в этой статье приведены [номера телефонов для голосовой](#audio-conferencing-phone-numbers) связи.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="ccd5f-120">Действие 1: получение лицензий на голосовую конференцию</span><span class="sxs-lookup"><span data-stu-id="ccd5f-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="ccd5f-121">Получите одну лицензию на голосовую конференцию для каждого человека, который будет руководит собраниями.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="ccd5f-122">Для этого воспользуйтесь центром администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="ccd5f-123">В центре администрирования Microsoft 365 перейдите в раздел Услуги по **выставлению счетов**  >  **Purchase services**, а затем в нижней части страницы выберите пункт **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="ccd5f-124">Выберите **рекламный сведения о программе голосовой конференции Microsoft 365**  >  **Details**, а затем нажмите кнопку **получить прямо сейчас**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="ccd5f-125">Введите число лицензий, необходимых для собрания, организаторов, а затем заполните свой заказ.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Снимок экрана: лицензия на использование голосовой конференции в рекламный":::

    > [!NOTE]
    > <span data-ttu-id="ccd5f-127">Снимите или установите флажок **автоматически назначать лицензии всем пользователям без лицензий**, в зависимости от того, хотите ли вы автоматически назначать лицензию на голосовую конференцию всем пользователям, у которых нет лицензии.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="ccd5f-128">Шаг 2: назначение лицензии на голосовую конференцию пользователям, ведущим к собраниям</span><span class="sxs-lookup"><span data-stu-id="ccd5f-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="ccd5f-129">Назначьте лицензию каждому человеку, который будет руководить собраниями.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="ccd5f-130">Для этого воспользуйтесь центром администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="ccd5f-131">Назначение лицензии одному пользователю</span><span class="sxs-lookup"><span data-stu-id="ccd5f-131">Assign a license to one user</span></span>

1. <span data-ttu-id="ccd5f-132">В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="ccd5f-133">Выберите строку пользователя, которому нужно назначить лицензию, а затем в области выберите пункт **лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="ccd5f-134">Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="ccd5f-135">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="ccd5f-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="ccd5f-136">В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="ccd5f-137">Выберите кружки рядом с пользователями, которым нужно назначить лицензию, а затем выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="ccd5f-138">В области **Управление лицензиями на продукты** нажмите кнопку **назначить больше**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="ccd5f-139">Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="ccd5f-140">Планирование собраний Teams в Outlook</span><span class="sxs-lookup"><span data-stu-id="ccd5f-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="ccd5f-141">Теперь организаторов собрания смогут планировать собрания в Outlook.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="ccd5f-142">В Outlook откройте меню **Календарь**и выберите команду **создать собрание Teams** .</span><span class="sxs-lookup"><span data-stu-id="ccd5f-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="ccd5f-143">Номера для подключения к собранию и идентификатор конференции автоматически добавляются в приглашение на собрание, отправленное участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="ccd5f-144">Дополнительные сведения можно найти [в разделе Планирование собрания Teams в Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="ccd5f-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="ccd5f-145">При желании вы можете настроить приглашения на собрание, чтобы добавить логотип компании, ссылки на веб-сайт службы поддержки и юридического лица, а также текстовый нижний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="ccd5f-146">Дополнительные сведения можно найти в разделе [Настройка приглашений на собрания](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="ccd5f-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="ccd5f-147">Номера телефонов для голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="ccd5f-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="ccd5f-148">Существует два типа чисел, которые можно использовать для моста конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="ccd5f-149">Вы можете использовать **Общие номера** (рассмотренные ранее в этой статье) или **выделенные номера**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-149">You can use **shared numbers** (discussed earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="ccd5f-150">Дополнительные сведения о каждом из них.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="ccd5f-151">Общие номера</span><span class="sxs-lookup"><span data-stu-id="ccd5f-151">Shared numbers</span></span>

<span data-ttu-id="ccd5f-152">Общедоступный номер — это число, которое совместно используются во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="ccd5f-153">Общие номера – это платные номера и они автоматически назначаются при настройке голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="ccd5f-154">Чтобы просмотреть номер по умолчанию, назначенный мосту конференц-связи, в левой области навигации центра администрирования Microsoft Teams перейдите в **Meetings**  >  **мосты конференций**собраний и найдите номер для ближайшего к вам расположению.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="ccd5f-155">Выделенные номера</span><span class="sxs-lookup"><span data-stu-id="ccd5f-155">Dedicated numbers</span></span>

<span data-ttu-id="ccd5f-156">Выделенный номер — это число, доступное только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="ccd5f-157">Выделенный номер может представлять собой платный номер или бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="ccd5f-158">Чтобы использовать выделенный номер, необходимо сначала получить номер, назначить его мосту конференц-связи, а затем назначить номер каждому человеку, который будет руководить собраниями.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="ccd5f-159">Есть несколько способов получить выделенный номер.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="ccd5f-160">Вы можете получить номер от корпорации Майкрософт или перевести (за один или несколько портов) от текущего поставщика услуг в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="ccd5f-161">Дополнительные сведения о том, как это сделать, можно найти в статье [Получение номеров служб](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="ccd5f-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="ccd5f-162">Имейте в виду, что если вы используете бесплатный номер, вам нужно сначала назначить лицензию на кредиты для каждого человека, который будет руководит собранием.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="ccd5f-163">Дополнительные сведения можно найти в разделе [Настройка кредитов связи для вашей организации](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ccd5f-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="ccd5f-164">После того как вы захотите свой номер, назначьте его мосту конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="ccd5f-165">Для этого воспользуйтесь центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="ccd5f-166">В левой области навигации центра администрирования Microsoft Teams перейдите к **Meetings**  >  **мостам конференций**для собраний.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ccd5f-167">Нажмите кнопку **Добавить**, а затем выберите **платный номер** или бесплатный **номер**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="ccd5f-168">В области **Добавить номер телефона** выберите номер, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="ccd5f-169">Затем назначьте номер каждому человеку, который будет интересен для собраний.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="ccd5f-170">Для этого воспользуйтесь центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="ccd5f-171">В левой области навигации центра администрирования Microsoft Teams выберите **Пользователи**, щелкните отображаемое имя пользователя и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="ccd5f-172">Нажмите кнопку **изменить**   рядом с пунктом " **звуковые конференции**", а затем в области " **телеконференции**"   выберите номер в списке **платный**   или бесплатный **Toll-free**   номер, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ccd5f-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccd5f-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ccd5f-173">Related topics</span></span>

- [<span data-ttu-id="ccd5f-174">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="ccd5f-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="ccd5f-175">Настройка голосовой конференции для групп</span><span class="sxs-lookup"><span data-stu-id="ccd5f-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="ccd5f-176">Номера телефонов для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="ccd5f-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="ccd5f-177">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="ccd5f-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="ccd5f-178">Идет загрузка служебных номеров</span><span class="sxs-lookup"><span data-stu-id="ccd5f-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="ccd5f-179">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="ccd5f-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="ccd5f-180">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="ccd5f-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
