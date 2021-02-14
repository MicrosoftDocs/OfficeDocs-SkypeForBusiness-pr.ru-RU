---
title: Настройка аудиоконференций для малого и среднего бизнеса
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
description: 'Узнайте, как настроить аудиоконференцию в своем малом или среднем бизнесе для людей, которым требуется телефон для звонков на собрания. '
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821289"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="c5434-103">Настройка аудиоконференций для малого и среднего бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5434-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="c5434-104">С помощью аудиоконференции люди могут звонить на собрания Teams с помощью телефона, а не с мобильного устройства или с компьютера.</span><span class="sxs-lookup"><span data-stu-id="c5434-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="c5434-105">Если у вас малый или средний бизнес с количеством пользователей до 300 человек и в настоящее время у вас нет лицензий на аудиоконференцию, вы можете бесплатно получить аудиоконференцию в течение года.</span><span class="sxs-lookup"><span data-stu-id="c5434-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="c5434-106">Это бесплатное предложение доступно с 1 октября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="c5434-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="c5434-107">Лицензия на надстройку для аудиоконференции может применяться к пользователям, у которых есть лицензии на Microsoft 365 бизнес базовый, бизнес стандартный, бизнес премиум, корпоративный E1 или E3.</span><span class="sxs-lookup"><span data-stu-id="c5434-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="c5434-108">Подробнее см. в лицензиях [на надстройки Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="c5434-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="c5434-109">Если у вас есть корпоративная голосовая система E5 или Microsoft 365 Business Voice, вы не сможете использовать бесплатное предложение аудиоконференций, так как эти лицензии уже включают аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="c5434-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="c5434-110">В этой статье вы найдете повесток о том, как настроить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="c5434-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="c5434-111">Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="c5434-112">Участникам собрания, которые звонят на собрания, не требуются лицензии или другие настройки.</span><span class="sxs-lookup"><span data-stu-id="c5434-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="c5434-113">Дополнительные узнать об этом см. в [записи аудиоконференции.](audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c5434-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="c5434-114">Настройка аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="c5434-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="c5434-115">При настроить аудиоконференцию мосту аудиоконференции автоматически будет назначен номер телефона, который будет использоваться в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="c5434-116">Номер телефона, который назначен в качестве номера по умолчанию для моста conferencing, будет номером из страны или региона вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c5434-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="c5434-117">Этот номер телефона является платным номером, на который может взиматься плата за междугородние и междугородние связи.</span><span class="sxs-lookup"><span data-stu-id="c5434-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="c5434-118">Вы также можете использовать бесплатный номер, который потребует нескольких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="c5434-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="c5434-119">Дополнительные информацию о номерах телефонов для моста [](#audio-conferencing-phone-numbers) аудиоконференций см. далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c5434-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="c5434-120">Шаг 1. Получить лицензии на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="c5434-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="c5434-121">Получите одну лицензию на аудиоконференцию для каждого человека, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="c5434-122">Для этого используйте Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5434-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="c5434-123">В Центре администрирования Microsoft 365 перейдите в службы покупки вы выставлений счета, а затем в нижней части страницы выберите "Надстройки".   >   </span><span class="sxs-lookup"><span data-stu-id="c5434-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="c5434-124">Выберите **промокод Microsoft 365 Audio Conferencing Adoption Promo Details,** а затем выберите  >   **"Получить сейчас".**</span><span class="sxs-lookup"><span data-stu-id="c5434-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="c5434-125">Введите количество лицензий, необходимых для организаторов собраний, а затем заполните заказ.</span><span class="sxs-lookup"><span data-stu-id="c5434-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Снимок экрана: лицензия на аудиоконференцию с промолицами для внедрения аудиоконференции":::

    > [!NOTE]
    > <span data-ttu-id="c5434-127">В зависимости от того, хотите ли вы автоматически назначить лицензию на аудиоконференцию всем пользователям, у которых нет лицензии, отключите или выберите автоматическое назначение лицензии всем пользователям, у которых нет лицензии.</span><span class="sxs-lookup"><span data-stu-id="c5434-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="c5434-128">Шаг 2. Назначение лицензии на аудиоконференцию пользователям, которые ведут собрания</span><span class="sxs-lookup"><span data-stu-id="c5434-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="c5434-129">Назначьте лицензию каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="c5434-130">Для этого используйте Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5434-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="c5434-131">Назначение лицензии одному пользователю</span><span class="sxs-lookup"><span data-stu-id="c5434-131">Assign a license to one user</span></span>

1. <span data-ttu-id="c5434-132">В Центре администрирования Microsoft 365 перейдите на сайт **"Пользователи,**  >  **активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="c5434-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="c5434-133">Выберите строку пользователя, лицензию который вы хотите назначить, а затем в области выберите **"Лицензии и приложения".**</span><span class="sxs-lookup"><span data-stu-id="c5434-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="c5434-134">Выберите поле "Аудиоконференцию **Microsoft 365"** и выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="c5434-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="c5434-135">Назначение лицензии нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c5434-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="c5434-136">В Центре администрирования Microsoft 365 перейдите на сайт **"Пользователи,**  >  **активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="c5434-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="c5434-137">Выберите круги рядом с пользователями, которые хотите назначить лицензии, а затем выберите "Управление **лицензиями на продукты".**</span><span class="sxs-lookup"><span data-stu-id="c5434-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="c5434-138">В области **"Управление лицензиями на** продукты" выберите **"Назначить больше".**</span><span class="sxs-lookup"><span data-stu-id="c5434-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="c5434-139">Выберите поле "Аудиоконференцию **Microsoft 365"** и выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="c5434-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="c5434-140">Расписание собраний Teams в Outlook</span><span class="sxs-lookup"><span data-stu-id="c5434-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="c5434-141">Организаторы собраний теперь могут планировать собрания в Outlook.</span><span class="sxs-lookup"><span data-stu-id="c5434-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="c5434-142">В Outlook перейдите в **календарь** и выберите кнопку **"Новое собрание Teams".**</span><span class="sxs-lookup"><span data-stu-id="c5434-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="c5434-143">Номера для телефонного дозвона и номер конференции автоматически добавляются в приглашение на собрание, которое отправляется участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="c5434-144">Дополнительные узнать см. [в дополнительных советах по расписанию собрания Teams в Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)</span><span class="sxs-lookup"><span data-stu-id="c5434-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="c5434-145">При этом вы можете настроить приглашения на собрания, чтобы добавить логотип компании, ссылки на веб-сайт службы поддержки и юридическое заявление, а также текстовый притязатель.</span><span class="sxs-lookup"><span data-stu-id="c5434-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="c5434-146">Подробнее см. в [настройках приглашений на собрания.](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="c5434-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="c5434-147">Номера телефонов для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c5434-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="c5434-148">Существует два типа номеров, которые можно использовать для моста conferencing.</span><span class="sxs-lookup"><span data-stu-id="c5434-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="c5434-149">Можно использовать **как** общие номера [](#set-up-audio-conferencing) (как в разделе "Настройка аудиоконференции" ранее в этой статье), так и **выделенные номера.**</span><span class="sxs-lookup"><span data-stu-id="c5434-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="c5434-150">Вот дополнительные сведения о каждом из них.</span><span class="sxs-lookup"><span data-stu-id="c5434-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="c5434-151">Общие номера</span><span class="sxs-lookup"><span data-stu-id="c5434-151">Shared numbers</span></span>

<span data-ttu-id="c5434-152">Общий номер — это число, совместное с другими организациями.</span><span class="sxs-lookup"><span data-stu-id="c5434-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="c5434-153">Общие номера являются платными и автоматически устанавливаются при настроить аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="c5434-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="c5434-154">Чтобы узнать номер по умолчанию, присвоенный мосту конференц-связь, на левой навигации Центра администрирования Microsoft Teams перейдите к мостам конференц-залов собраний и найдите номер ближайшего к вам   >  места.</span><span class="sxs-lookup"><span data-stu-id="c5434-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="c5434-155">Выделенные числа</span><span class="sxs-lookup"><span data-stu-id="c5434-155">Dedicated numbers</span></span>

<span data-ttu-id="c5434-156">Выделенное число — это число, доступное только пользователям.</span><span class="sxs-lookup"><span data-stu-id="c5434-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="c5434-157">Выделенный номер может быть платным или бесплатным.</span><span class="sxs-lookup"><span data-stu-id="c5434-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="c5434-158">Чтобы использовать выделенный номер, необходимо сначала получить номер, назначить его мосту для проведения собраний, а затем назначить номер каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="c5434-159">Существует несколько способов получить выделенное число.</span><span class="sxs-lookup"><span data-stu-id="c5434-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="c5434-160">Вы можете получить номер от Майкрософт или перенести (порт) существующий номер от текущего поставщика услуг в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5434-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="c5434-161">Дополнительные информацию о том, как это сделать, см. в подмножении ["Получение номеров служб".](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="c5434-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="c5434-162">Имейте в виду, что если вы используете бесплатный номер, сначала необходимо назначить лицензию на кредиты на связь каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="c5434-163">Дополнительные узнать см. в сообщении о том, как настроить кредиты на связь [для вашей организации.](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="c5434-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="c5434-164">Получив номер, назначьте его мосту конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="c5434-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="c5434-165">Для этого воспользуйтесь Центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c5434-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="c5434-166">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** мостам  >  **конференц-залов собраний.**</span><span class="sxs-lookup"><span data-stu-id="c5434-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="c5434-167">Выберите **"Добавить",** а затем — **"Платный"** или **"Бесплатный номер".**</span><span class="sxs-lookup"><span data-stu-id="c5434-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="c5434-168">В области **"Добавление номера** телефона" выберите номер и выберите "Применить". </span><span class="sxs-lookup"><span data-stu-id="c5434-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="c5434-169">Затем назначьте номер каждому человеку, который будет вести собрания.</span><span class="sxs-lookup"><span data-stu-id="c5434-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="c5434-170">Для этого воспользуйтесь Центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c5434-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="c5434-171">В левой области навигации Центра администрирования Microsoft Teams выберите "Пользователи", щелкните отображаемого имени пользователя и выберите команду "Изменить". </span><span class="sxs-lookup"><span data-stu-id="c5434-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="c5434-172">Выберите **"Изменить"** рядом с аудиоконференцией, а затем в области "Аудиоконференция" выберите номер в списках платных или бесплатных номеров и выберите     "Применить". </span><span class="sxs-lookup"><span data-stu-id="c5434-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5434-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c5434-173">Related topics</span></span>

- [<span data-ttu-id="c5434-174">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c5434-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="c5434-175">Настройка аудиоконференций для Teams</span><span class="sxs-lookup"><span data-stu-id="c5434-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="c5434-176">Номера телефонов для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c5434-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="c5434-177">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="c5434-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="c5434-178">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="c5434-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="c5434-179">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="c5434-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="c5434-180">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="c5434-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
