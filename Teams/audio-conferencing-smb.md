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
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328443"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="d920d-103">Настройка голосовой конференции для малых и средних организаций</span><span class="sxs-lookup"><span data-stu-id="d920d-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="d920d-104">Благодаря голосовой конференции пользователи могут звонить на собрания Teams с помощью телефона, а не с помощью приложения Teams на мобильном устройстве или с компьютера.</span><span class="sxs-lookup"><span data-stu-id="d920d-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="d920d-105">Если вы используете не более 300 пользователей и не используете лицензий на голосовую связь, вы можете бесплатно подписаться на голосовую конференцию в течение одного года.</span><span class="sxs-lookup"><span data-stu-id="d920d-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="d920d-106">Это бесплатное предложение доступно начиная с 1 октября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="d920d-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="d920d-107">Лицензия на надстройку "звуковые конференции" может быть применена к пользователям, которые имеют лицензии Microsoft 365 Business Basic, Business E1, корпоративное и E3.</span><span class="sxs-lookup"><span data-stu-id="d920d-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="d920d-108">Дополнительные сведения можно найти в разделе [лицензии на надстройки для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="d920d-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="d920d-109">Если у вас Корпоративная голосовая связь в корпоративной среде или Microsoft 365, вы не сможете использовать бесплатные видеоконференции, так как в этих лицензиях уже есть голосовые конференции.</span><span class="sxs-lookup"><span data-stu-id="d920d-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="d920d-110">В этой статье мы рассмотрим, как настроить голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="d920d-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="d920d-111">Вам нужно только настроить аудиоконференции для пользователей, планирующих или проводящих собрания.</span><span class="sxs-lookup"><span data-stu-id="d920d-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="d920d-112">Участники собрания, вызывающие участие в собраниях, не нуждаются в лицензиях и других параметрах настройки.</span><span class="sxs-lookup"><span data-stu-id="d920d-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="d920d-113">Дополнительные сведения можно найти в статье [звуковые конференции](audio-conferencing-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d920d-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="d920d-114">Действие 1: получение лицензий на голосовую конференцию</span><span class="sxs-lookup"><span data-stu-id="d920d-114">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="d920d-115">Получите одну лицензию на голосовую конференцию для каждого человека, который будет руководит собраниями.</span><span class="sxs-lookup"><span data-stu-id="d920d-115">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="d920d-116">Для этого воспользуйтесь центром администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d920d-116">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="d920d-117">В центре администрирования Microsoft 365 перейдите в раздел Услуги по **выставлению счетов**  >  **Purchase services**, а затем в нижней части страницы выберите пункт **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="d920d-117">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span> 
2. <span data-ttu-id="d920d-118">Выберите **рекламный сведения о внедрении голосовой конференции Microsoft 365**  >  **Details**.</span><span class="sxs-lookup"><span data-stu-id="d920d-118">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**.</span></span>
3. <span data-ttu-id="d920d-119">Введите число лицензий, необходимых для собрания, организаторов, а затем заполните свой заказ.</span><span class="sxs-lookup"><span data-stu-id="d920d-119">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

> [!NOTE]
> <span data-ttu-id="d920d-120">Снимите или установите флажок **автоматически назначать лицензии всем пользователям без лицензий**, в зависимости от того, хотите ли вы автоматически назначать лицензию на голосовую конференцию всем пользователям, у которых нет лицензии.</span><span class="sxs-lookup"><span data-stu-id="d920d-120">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="d920d-121">Шаг 2: назначение лицензии на голосовую конференцию пользователям, ведущим к собраниям</span><span class="sxs-lookup"><span data-stu-id="d920d-121">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="d920d-122">Назначьте лицензию каждому человеку, который будет руководить собраниями.</span><span class="sxs-lookup"><span data-stu-id="d920d-122">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="d920d-123">Для этого воспользуйтесь центром администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d920d-123">Use the Microsoft 365 admin center to do this.</span></span>

### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="d920d-124">Назначение лицензии одному пользователю</span><span class="sxs-lookup"><span data-stu-id="d920d-124">Assign a license to one user</span></span>

1. <span data-ttu-id="d920d-125">В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.</span><span class="sxs-lookup"><span data-stu-id="d920d-125">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="d920d-126">Выберите строку пользователя, которому нужно назначить лицензию, а затем в области выберите пункт **лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="d920d-126">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="d920d-127">Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d920d-127">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span> 

### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="d920d-128">Назначение лицензий нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="d920d-128">Assign a license to multiple users</span></span>

1. <span data-ttu-id="d920d-129">В центре администрирования Microsoft 365 перейдите в раздел **Users**  >  **Активные пользователи**пользователей.</span><span class="sxs-lookup"><span data-stu-id="d920d-129">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="d920d-130">Выберите кружки рядом с пользователями, которым нужно назначить лицензию, а затем выберите **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="d920d-130">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="d920d-131">В области **Управление лицензиями на продукты** нажмите кнопку **назначить больше**.</span><span class="sxs-lookup"><span data-stu-id="d920d-131">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="d920d-132">Установите флажок **звуковые конференции Microsoft 365** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d920d-132">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a><span data-ttu-id="d920d-133">Шаг 3: Поиск или получение номера телефона для моста конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d920d-133">Step 3: Find or get a phone number for your conferencing bridge</span></span>

<span data-ttu-id="d920d-134">Для моста конференц-связи необходим номер телефона (номер службы), чтобы его можно было использовать в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="d920d-134">You'll need a phone number (also called a service number) for your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="d920d-135">Вы можете выбрать использование **общего номера** или **специального номера**.</span><span class="sxs-lookup"><span data-stu-id="d920d-135">You can choose to use a **shared number** or a **dedicated number**.</span></span> <span data-ttu-id="d920d-136">Оба типа номеров могут использоваться любым вызывающим абонентом для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="d920d-136">Both types of numbers can be used by any caller to join a meeting.</span></span>

### <a name="use-a-shared-number"></a><span data-ttu-id="d920d-137">Использование общего числа</span><span class="sxs-lookup"><span data-stu-id="d920d-137">Use a shared number</span></span>

<span data-ttu-id="d920d-138">Общедоступный номер — это число, которое совместно используются во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="d920d-138">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="d920d-139">Общие номера назначаются автоматически при настройке голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="d920d-139">Shared numbers are automatically assigned when you set up Audio Conferencing.</span></span> <span data-ttu-id="d920d-140">Эти общие номера – это платные номера, на которые может взиматься плата за междугородние звонки.</span><span class="sxs-lookup"><span data-stu-id="d920d-140">These shared numbers are toll numbers, in which long-distance charges may apply.</span></span>

<span data-ttu-id="d920d-141">Чтобы найти номер по умолчанию, назначенный мосту конференц-связи, в левой области навигации центра администрирования Microsoft Teams перейдите в **Meetings**  >  **мосты конференций**собраний, а затем найдите номер для ближайшего к вам расположению.</span><span class="sxs-lookup"><span data-stu-id="d920d-141">To find the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="get-a-dedicated-number"></a><span data-ttu-id="d920d-142">Получить выделенный номер</span><span class="sxs-lookup"><span data-stu-id="d920d-142">Get a dedicated number</span></span>

<span data-ttu-id="d920d-143">Выделенный номер — это число, доступное только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d920d-143">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="d920d-144">Выделенный номер может представлять собой платный номер или бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="d920d-144">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="d920d-145">Чтобы использовать выделенный номер, необходимо сначала получить номер, а затем назначить его мосту конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d920d-145">To use a dedicated number, you'll have to first get the number, and then assign it to your conferencing bridge.</span></span>  

<span data-ttu-id="d920d-146">Есть несколько способов получить выделенный номер.</span><span class="sxs-lookup"><span data-stu-id="d920d-146">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="d920d-147">Вы можете получить номер от корпорации Майкрософт или перевести (за один или несколько портов) от текущего поставщика услуг в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d920d-147">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="d920d-148">Дополнительные сведения о том, как это сделать, можно найти в статье [Получение номеров служб](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="d920d-148">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d920d-149">Если вы используете бесплатный номер, вы должны сначала назначить лицензию на кредиты для каждого человека, который будет руководит собраниями.</span><span class="sxs-lookup"><span data-stu-id="d920d-149">If you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="d920d-150">Дополнительные сведения можно найти в разделе [Настройка кредитов связи для вашей организации](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d920d-150">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="d920d-151">После того как вы захотите свой номер, назначьте его мосту конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d920d-151">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="d920d-152">Для этого воспользуйтесь центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d920d-152">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="d920d-153">В левой области навигации центра администрирования Microsoft Teams перейдите к **Meetings**  >  **мостам конференций**для собраний.</span><span class="sxs-lookup"><span data-stu-id="d920d-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d920d-154">Нажмите кнопку **Добавить**, а затем выберите **платный номер** или бесплатный **номер**.</span><span class="sxs-lookup"><span data-stu-id="d920d-154">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="d920d-155">В области **Добавить номер телефона** выберите номер, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d920d-155">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a><span data-ttu-id="d920d-156">Шаг 4: назначение номера для подключения пользователям, ведущим к собраниям</span><span class="sxs-lookup"><span data-stu-id="d920d-156">Step 4: Assign a dial-in number to users who lead meetings</span></span>

<span data-ttu-id="d920d-157">Назначьте номер для подключения каждому человеку, который будет руководить собраниями.</span><span class="sxs-lookup"><span data-stu-id="d920d-157">Assign a dial-in number for each person who will lead meetings.</span></span> <span data-ttu-id="d920d-158">Для этого воспользуйтесь центром администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d920d-158">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="d920d-159">В левой области навигации центра администрирования Microsoft Teams выберите **Пользователи**, щелкните отображаемое имя пользователя и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="d920d-159">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="d920d-160">Нажмите кнопку **изменить**   рядом с пунктом " **звуковые конференции**", а затем в области " **телеконференции**"   выберите номер в списке **платный**   или бесплатный **Toll-free**   номер, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d920d-160">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a><span data-ttu-id="d920d-161">Шаг 5: планирование собрания Teams в Outlook</span><span class="sxs-lookup"><span data-stu-id="d920d-161">Step 5: Schedule a Teams meeting in Outlook</span></span>

<span data-ttu-id="d920d-162">Чтобы запланировать собрание, в Outlook перейдите в раздел **Календарь**, а затем нажмите кнопку **создать собрание Teams** .</span><span class="sxs-lookup"><span data-stu-id="d920d-162">To schedule a meeting, in Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="d920d-163">Номера для телефонного подключения, заданные пользователем, и идентификатор конференции автоматически добавляются в приглашение на собрание, отправленное участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="d920d-163">The dial-in numbers that you set for the user and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span>

<span data-ttu-id="d920d-164">Дополнительные сведения можно найти [в разделе Планирование собрания Teams в Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="d920d-164">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="d920d-165">При желании вы можете настроить приглашения на собрание, чтобы добавить логотип компании, ссылки на веб-сайт службы поддержки и юридического лица, а также текстовый нижний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="d920d-165">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="d920d-166">См. [Настройка приглашений на собрания](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="d920d-166">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d920d-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d920d-167">Related topics</span></span>

- [<span data-ttu-id="d920d-168">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="d920d-168">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="d920d-169">Настройка голосовой конференции для групп</span><span class="sxs-lookup"><span data-stu-id="d920d-169">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="d920d-170">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="d920d-170">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="d920d-171">Идет загрузка служебных номеров</span><span class="sxs-lookup"><span data-stu-id="d920d-171">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="d920d-172">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="d920d-172">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d920d-173">Назначение лицензий пользователям</span><span class="sxs-lookup"><span data-stu-id="d920d-173">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
