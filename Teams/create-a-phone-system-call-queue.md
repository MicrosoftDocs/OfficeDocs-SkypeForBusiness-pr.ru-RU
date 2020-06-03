---
title: Создание очереди вызовов
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Сведения о том, как настроить телефонную систему для очередей облачных вызовов в Microsoft Teams, которые предоставляют сообщение приветствия, перенаправление музыки, переадресацию звонков и другие функции.
ms.openlocfilehash: 9c2593f657ae66a1dcde825ac7a783df10cd96d8
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523778"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="df246-103">Создание облачной очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="df246-103">Create a Cloud call queue</span></span>

<span data-ttu-id="df246-104">Очереди облачных вызовов предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="df246-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="df246-105">Сообщение приветствия.</span><span class="sxs-lookup"><span data-stu-id="df246-105">A greeting message.</span></span>
- <span data-ttu-id="df246-106">Воспроизведение музыки во время удержания звонка.</span><span class="sxs-lookup"><span data-stu-id="df246-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="df246-107">Переадресация звонков операторам с использованием почтовых списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="df246-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="df246-108">Задать различные параметры, такие как максимальный размер, таймаут и параметры обработки звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="df246-109">Общая Голосовая почта для вызывающих абонентов для выхода из сообщения для Организации.</span><span class="sxs-lookup"><span data-stu-id="df246-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="df246-110">Вы не можете напрямую связать номер телефона с очередью звонков, а номер телефона связан с [учетной записью ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="df246-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="df246-111">Вы можете набрать очередь звонков напрямую или получить доступ к ней с помощью выбранного элемента автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="df246-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="df246-112">Вызывающий абонент слышит музыку, пока они находятся на удержании, и Звонок подключается к агентам звонков в порядке " *первым вошел — первым вышел* " (FIFO).</span><span class="sxs-lookup"><span data-stu-id="df246-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="df246-113">Все звонки в очереди отправляются агентам одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="df246-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="df246-114">При использовании маршрутизации помощника первый вызов в очереди одновременно колец все агенты.</span><span class="sxs-lookup"><span data-stu-id="df246-114">With attendant routing, the first call in the queue rings all agents at the same time.</span></span>
- <span data-ttu-id="df246-115">При использовании последовательной маршрутизации первый вызов из очереди звонит по каждому из них по одному.</span><span class="sxs-lookup"><span data-stu-id="df246-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="df246-116">При циклическом перераспределении Маршрутизация входящих звонков сбалансирована таким образом, что каждый агент вызова получает одинаковое количество звонков из очереди.</span><span class="sxs-lookup"><span data-stu-id="df246-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="df246-117">Вы можете настроить параметры обработки звонков, такие как включение или отказ от агента, маршрутизация на основе присутствия, время ожидания вызова и время вызова для любого из описанных выше методов.</span><span class="sxs-lookup"><span data-stu-id="df246-117">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="df246-118">Только одно уведомление о входящем звонке (для звонка в заголовке очереди) в каждый момент времени отправляется агентам звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="df246-119">После того, как оператор принимает звонок, всем операторам поступает следующий входящий звонок из очереди.</span><span class="sxs-lookup"><span data-stu-id="df246-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="df246-120">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="df246-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="df246-121">Этап 1 — Начало работы</span><span class="sxs-lookup"><span data-stu-id="df246-121">Step 1 — Get started</span></span>

<span data-ttu-id="df246-122">Перед началом работы с очередями звонков необходимо запомнить следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="df246-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="df246-123">Для связи с учетной записью ресурса требуется очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="df246-124">Дополнительные сведения об учетных записях ресурсов содержатся [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="df246-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="df246-125">После назначения номера телефона для учетной записи ресурса теперь вы можете использовать [лицензию на виртуальную систему пользователей](teams-add-on-licensing/virtual-user.md)с бесплатной платой.</span><span class="sxs-lookup"><span data-stu-id="df246-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="df246-126">Телефонная система позволяет использовать номера телефонов на уровне Организации для автосекретаря по низким тарифам и для службы очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

  > [!NOTE]
  > <span data-ttu-id="df246-127">Номера услуг прямой маршрутизации для очередей звонков поддерживаются только для пользователей и агентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df246-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

  > [!NOTE]
  > <span data-ttu-id="df246-128">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="df246-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="df246-129">Ознакомьтесь [с Разназначением лицензий на надстройки Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="df246-129">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="df246-130">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df246-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="df246-131">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="df246-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="df246-132">Чтобы узнать больше о тарифных планах Office 365, ознакомьтесь со статьями [телефонные системы и](calling-plan-landing-page.md) планы звонков и [планы звонков для Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="df246-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="df246-133">Вы можете назначить очереди облачных звонков только платными телефонными номерами, которые были получены в **центре администрирования Microsoft Teams** или переданы из другого поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="df246-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="df246-134">Для платных номеров услуг требуются кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="df246-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df246-135">Номера телефонов пользователей (абонентов) нельзя назначить очередям звонков  можно использовать платные или бесплатные номера телефонов служб.</span><span class="sxs-lookup"><span data-stu-id="df246-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="df246-136">Для агентов звонков, связанных с облачной очередью звонков, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="df246-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="df246-137">Настольный клиент 2016 для настольных компьютеров Skype для бизнеса (32-разр и 64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="df246-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="df246-138">Классическое приложение Lync 2013 (32-разр и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="df246-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="df246-139">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df246-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="df246-140">Узнайте о том, как [получить телефоны в Skype для бизнеса Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="df246-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="df246-141">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="df246-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="df246-142">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="df246-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="df246-143">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="df246-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="df246-144">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="df246-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="df246-145">Клиент Microsoft Teams для Windows (32-разрядная версия и 64-разр.)</span><span class="sxs-lookup"><span data-stu-id="df246-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="df246-146">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="df246-146">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="df246-147">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="df246-147">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="df246-148">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="df246-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="df246-149">Очереди звонков, которым назначен прямой номер маршрутизации, не поддерживают клиентов Skype для бизнеса, клиентов Lync и IP-телефоны Skype для бизнеса в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="df246-149">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="df246-150">Этап 2 — получение или передача платных и бесплатных телефонных номеров услуги</span><span class="sxs-lookup"><span data-stu-id="df246-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="df246-151">Прежде чем вы сможете создавать и настраивать очереди звонков, вам нужно получить или переадресовать существующие платные или бесплатные номера сервисных услуг.</span><span class="sxs-lookup"><span data-stu-id="df246-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="df246-152">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md) или перенесите существующий номер Услуги в разделе [Перенос номеров телефонов в Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="df246-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="df246-153">После получения платных и бесплатных телефонных номеров в **центре администрирования Microsoft Teams**они будут отображаться в  >  **Voice**  >  **номерах телефонов**.</span><span class="sxs-lookup"><span data-stu-id="df246-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="df246-154">Бесплатные телефонные номера будут перечислены в списке с **типом** **услуги (** бесплатный номер телефона).</span><span class="sxs-lookup"><span data-stu-id="df246-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="df246-155">За пределами США нельзя использовать центр администрирования Microsoft Teams для получения номеров служб.</span><span class="sxs-lookup"><span data-stu-id="df246-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="df246-156">Чтобы узнать, как сделать это из за пределами США, перейдите в раздел [Управление телефонными номерами в Организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="df246-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="df246-157">При настройке нескольких автосекретарей обычно назначается номер телефона основной учетной записи автоматического ассистента.</span><span class="sxs-lookup"><span data-stu-id="df246-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="df246-158">Для учетных записей ресурсов, связанных с вложенными автосекретарем или очередями звонков, часто не нужны номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="df246-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="df246-159">Этот автоматический секретарь может перенаправлять абонентов в очереди звонков или на вложенные автоматические ассистенты, даже если у них нет номера телефона.</span><span class="sxs-lookup"><span data-stu-id="df246-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="df246-160">В этих случаях вы можете создать все автосекретарей и очереди звонков в системе без назначения параметров панель набора номера и затем изменить параметры позже.</span><span class="sxs-lookup"><span data-stu-id="df246-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="df246-161">Чтобы настроить ее как параметр меню, должна существовать очередь звонков или автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="df246-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="df246-162">Шаг 3: создание очереди звонков</span><span class="sxs-lookup"><span data-stu-id="df246-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="df246-163">Каждая очередь звонков должна иметь связанную [учетную запись ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="df246-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="df246-164">Сначала необходимо создать учетную запись ресурса, после чего вы сможете связать ее с очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="df246-165">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df246-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="df246-166">В **центре администрирования Microsoft Teams**выберите очередь **голосовых**  >  **звонков**и нажмите кнопку **+ Добавить новый**:</span><span class="sxs-lookup"><span data-stu-id="df246-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="df246-167">Настройка отображаемого имени и учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="df246-167">Set the display name and resource account</span></span>

![Снимок экрана: новая очередь звонков с пронумерованными выносками](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="df246-169">![Значок цифры 1 — ссылка на выноску в предыдущем имени снимка экрана ](media/teamscallout1.png)
 **Name** введите описательное отображаемое имя для очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-169">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="df246-170">Это имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="df246-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="df246-171">Это имя будет отображаться в уведомлении о входящем звонке.</span><span class="sxs-lookup"><span data-stu-id="df246-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="df246-172">![Значок числа 2 — ссылка на выноску на предыдущем снимке экрана ](media/teamscallout2.png)
 .**Добавить учетные записи** выберите учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="df246-172">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="df246-173">Все очереди звонков должны иметь учетные записи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="df246-173">All call queues are required to have a resource account.</span></span> <span data-ttu-id="df246-174">Для учетных записей ресурсов не требуется сервисный платный или бесплатный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="df246-174">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="df246-175">Если вы не в списке, получите номера служб и назначьте их учетной записи ресурсов перед созданием очереди звонков, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="df246-175">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="df246-176">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="df246-176">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="df246-177">Сведения о назначении номера телефона можно найти [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="df246-177">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="df246-178">Если вы хотите или вам нужно назначить **домен** , вы назначаете его учетной записи ресурса для очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-178">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="df246-179">Настройка приветствия и музыки, воспроизводимой во время удержания</span><span class="sxs-lookup"><span data-stu-id="df246-179">Set the greeting and music played while on hold</span></span>

![снимок экрана: параметры приветствия и музыки с пронумерованными выносками](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="df246-181">![Значок цифры 1 — ссылка на выноску в предыдущем ](media/teamscallout1.png)
 **приветственном** зауглу экрана, которая воспроизводится для пользователей, вызывающих номер очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-181">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="df246-182">Вы можете добавить звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="df246-182">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="df246-183">![Icon для числа 2 — ссылка на выноску на предыдущем снимке экрана ](media/teamscallout2.png)
 **музыка на удержании** . Вы можете использовать музыку по умолчанию для удержания музыки с помощью очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-183">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="df246-184">Вы также можете добавить звуковой файл в формате WAV, MP3 или WMA, чтобы использовать его в качестве особой музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="df246-184">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="df246-185">Выбор параметров ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="df246-185">Select the call answering options</span></span>

![Снимок экрана: варианты ответа на звонки](media/teams-cq-call-answering-options.png)

<span data-ttu-id="df246-187">![Значок с номером 1 — ссылка на выноску в предыдущем снимке экрана ](media/teamscallout1.png)
 **и группах** для добавления отдельных агентов непосредственно, не добавляя их в группу, нажмите кнопку **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="df246-187">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="df246-188">Разместите отдельные агенты в том порядке, в котором они должны получать звонок.</span><span class="sxs-lookup"><span data-stu-id="df246-188">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="df246-189">Вы можете добавить до 20 отдельных агентов (чтобы добавить больше 20, поместить их в группу).</span><span class="sxs-lookup"><span data-stu-id="df246-189">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="df246-190">Звонки сначала перенаправляются на отдельные агенты, затем на агенты в группах.</span><span class="sxs-lookup"><span data-stu-id="df246-190">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="df246-191">Вы можете выбрать до 200 агенты звонков, которые относятся к любому из указанных ниже списков рассылки или групп.</span><span class="sxs-lookup"><span data-stu-id="df246-191">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="df246-192">Группа Office 365</span><span class="sxs-lookup"><span data-stu-id="df246-192">Office 365 group</span></span>
- <span data-ttu-id="df246-193">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="df246-193">Security group</span></span>
- <span data-ttu-id="df246-194">Список рассылки</span><span class="sxs-lookup"><span data-stu-id="df246-194">Distribution list</span></span>

<span data-ttu-id="df246-195">Выбранные агенты звонков должны быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="df246-195">Call agents selected must be one of the following:</span></span>

- <span data-ttu-id="df246-196">Пользователи в сети с лицензией на телефонную систему и включенной корпоративной голосовой связью</span><span class="sxs-lookup"><span data-stu-id="df246-196">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="df246-197">Пользователи в сети с помощью тарифного плана</span><span class="sxs-lookup"><span data-stu-id="df246-197">Online users with a Calling Plan</span></span>
- <span data-ttu-id="df246-198">Локальные пользователи Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="df246-198">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="df246-199">Это также применимо, если вы хотите перенаправить звонки на пользователей в вашей организации, которые находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="df246-199">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="df246-200">Эти люди должны иметь лицензию на **телефонную систему** , а также включить поддержку голосовой связи в рамках Skype *или* получить план звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-200">These individuals must have a **Phone System** license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="df246-201">Дополнительные сведения можно найти в статье [Назначение лицензий Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Назначение лицензий на Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses), а также [для каких абонентов](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="df246-201">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

   <span data-ttu-id="df246-202">Для включения агента для корпоративного голосовой связи можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df246-202">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="df246-203">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="df246-203">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="df246-204">Пользователи с лицензией на **телефонную систему** или планом звонков, которые добавляются в группу Office 365; Список рассылки, поддерживающий почту; или группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="df246-204">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="df246-205">При добавлении агента в список рассылки или группу безопасности в качестве агента очереди звонков для первого звонка может потребоваться до трех часов.</span><span class="sxs-lookup"><span data-stu-id="df246-205">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="df246-206">Чтобы вновь созданный список распределения или группа безопасности стали доступными для использования с очередями вызовов, может потребоваться до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="df246-206">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="df246-207">Вновь созданные группы Microsoft 365 доступны практически сразу.</span><span class="sxs-lookup"><span data-stu-id="df246-207">Newly created Microsoft 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="df246-208">Если агенты используют приложение Microsoft Teams для вызова очереди звонков, они должны находиться в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="df246-208">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="df246-209">![Icon (число 2), который ссылается на выноску в предыдущем режиме конференции в ](media/teamscallout2.png)
 **режиме** конференции, значительно сокращает время, необходимое для подключения вызывающего абонента к агенту, после того как агент допускает звонок.</span><span class="sxs-lookup"><span data-stu-id="df246-209">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Conference mode** Conference mode significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="df246-210">Если у вас несколько очередей звонков, вы можете включить режим конференции для некоторых или всех очередей звонков; Включение или отключение режима конференции в одной очереди звонков не влияет на другие очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-210">If you have more than one call queue, you can enable conference mode on some or all of your call queues; enabling or disabling conference mode on one call queue doesn't impact any other call queues.</span></span>

<span data-ttu-id="df246-211">Режим конференции по умолчанию отключен, но его можно включить в любое время, если соблюдены следующие требования:</span><span class="sxs-lookup"><span data-stu-id="df246-211">Conference mode is disabled by default but can be enabled at any time if the following requirements are met:</span></span>

- <span data-ttu-id="df246-212">Агенты, добавленные в очередь звонков, должны использовать один из указанных ниже клиентов.</span><span class="sxs-lookup"><span data-stu-id="df246-212">Agents added to the call queue need to use one of the following clients:</span></span>
  - <span data-ttu-id="df246-213">Новейшая версия клиента Microsoft Teams для настольных компьютеров, приложения Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="df246-213">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="df246-214">Microsoft Teams Phone версии 1449/1.0.94.2020051601 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="df246-214">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
- <span data-ttu-id="df246-215">Учетные записи Teams должны быть установлены в режим "только для Teams"</span><span class="sxs-lookup"><span data-stu-id="df246-215">Agents' Teams accounts need to be set to Teams-only mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df246-216">Если указанные выше требования к агентам не выполнены и режим конференции включен в очередь звонков, агенты, которые не соответствуют требованиям, не включаются в список маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-216">If the agent requirements above aren't met and conference mode is enabled on a call queue, agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="df246-217">Агенты, которые не входят в список маршрутизации звонков, не будут получать звонки.</span><span class="sxs-lookup"><span data-stu-id="df246-217">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="df246-218">Если у вас есть агенты, которые не соответствуют указанным выше требованиям агента, не включайте режим конференции в очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-218">If you have agents who don't meet the agent requirements above, don't enable conference mode on the call queue.</span></span>

<span data-ttu-id="df246-219">Если режим конференции включен в очередь звонков, звонки с более высокой скоростью подключения будут выгодны, если они получили один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="df246-219">After conference mode is enabled on a call queue, calls will benefit from the faster connection time if they're received via one of the following methods:</span></span>

- <span data-ttu-id="df246-220">Звонки VoIP из другого клиента Microsoft Teams Desktop</span><span class="sxs-lookup"><span data-stu-id="df246-220">VoIP calls from another Microsoft Teams desktop client</span></span>
- <span data-ttu-id="df246-221">Тарифный план звонков по КОММУТИРУЕМой телефонной связи</span><span class="sxs-lookup"><span data-stu-id="df246-221">Calling Plan PSTN calls</span></span>
- <span data-ttu-id="df246-222">Прямые маршруты для КОММУТИРУЕМых звонков</span><span class="sxs-lookup"><span data-stu-id="df246-222">Direct Routing PSTN calls</span></span>

<span data-ttu-id="df246-223">Большинство звонков принимаются одним из описанных выше способов.</span><span class="sxs-lookup"><span data-stu-id="df246-223">The majority of calls are received via one of the methods listed above.</span></span> <span data-ttu-id="df246-224">Если звонок получен через другой метод (например, вызов VoIP из клиента Skype для бизнеса), этот вызов будет по-прежнему добавлен в очередь звонков, но это не выгодно для более быстрой связи.</span><span class="sxs-lookup"><span data-stu-id="df246-224">If a call is received via another method (such as a VoIP call from a Skype for Business client), the call will still be added to the call queue, however, it won't benefit from the faster connection time.</span></span>

<span data-ttu-id="df246-225">![Значок "цифра 3" — ссылка на выноску в предыдущем ](media/teamscallout3.png)
 **методе маршрутизации** для снимка экрана. Вы можете выбрать в качестве метода распространения элемент " **секретарь**", " **последовательный**" или " **циклический** ".</span><span class="sxs-lookup"><span data-stu-id="df246-225">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="df246-226">По умолчанию для всех новых и существующих очередей звонков выбрана маршрутизация участников.</span><span class="sxs-lookup"><span data-stu-id="df246-226">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="df246-227">Когда используется маршрутизация участников, первый вызов из очереди звонит все агенты.</span><span class="sxs-lookup"><span data-stu-id="df246-227">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="df246-228">Вызов вызывается агентом первого вызова для выбора звонка.</span><span class="sxs-lookup"><span data-stu-id="df246-228">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="df246-229">Если вы перезвоните в **службу** , первый звонок в очереди будет звонить всем агентам звонков одновременно.</span><span class="sxs-lookup"><span data-stu-id="df246-229">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="df246-230">Вызов вызывается агентом первого вызова для выбора звонка.</span><span class="sxs-lookup"><span data-stu-id="df246-230">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="df246-231">Входящие звонки по **последовательному маршруту** звоните всем агентам по одному, от начала списка агента звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-231">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="df246-232">Агенты нельзя заказать в списке агента звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-232">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="df246-233">Если агент закрывает или не берет на себя звонок, Звонок будет поступать на следующий агент и будет пытаться выполнить все агенты до тех пор, пока не будет выбрано или истечет время ожидания.</span><span class="sxs-lookup"><span data-stu-id="df246-233">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="df246-234">**Round robin** Подставляются маршруты для входящих звонков, так что каждый агент вызывает одинаковое количество звонков из очереди.</span><span class="sxs-lookup"><span data-stu-id="df246-234">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="df246-235">Это может быть предпочтительнее в входящей среде продаж для обеспечения возможной возможности между всеми агентами звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-235">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="df246-236">![Icon (номер 4) — ссылка на выноску в маршруте, основанном на ](media/teamscallout4.png)
 возможностях, вызываемом службой доступа на**основе присутствия,** для определения того, должен ли агент быть включен в список маршрутизации звонков для выбранного метода маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="df246-236">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="df246-237">Агенты звонков, состояние доступности которых равно " **доступен** ", включаются в список маршрутизации звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="df246-237">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="df246-238">Агенты с состоянием доступности, для которого задано другое состояние, исключаются из списка маршрутизации звонков и не будут получать звонки до тех пор, пока их состояние доступности не изменится на " **недоступно**".</span><span class="sxs-lookup"><span data-stu-id="df246-238">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>

<span data-ttu-id="df246-239">Вы можете включить маршрутизацию звонков на основе присутствия, используя любой из методов маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="df246-239">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="df246-240">Если агент выводит из приема звонков, они не включаются в список маршрутизации звонков независимо от того, какое состояние доступности установлено.</span><span class="sxs-lookup"><span data-stu-id="df246-240">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df246-241">Агенты, которые используют клиента Skype для бизнеса, не включаются в список маршрутизации звонков, когда включена маршрутизация на основе присутствия, независимо от состояния доступности.</span><span class="sxs-lookup"><span data-stu-id="df246-241">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="df246-242">Агенты, которые не входят в список маршрутизации звонков, не будут получать звонки.</span><span class="sxs-lookup"><span data-stu-id="df246-242">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="df246-243">Если у вас есть агенты, использующие Skype для бизнеса, не включайте маршрутизацию звонков на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="df246-243">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="df246-244">Выбор варианта отказа от агента</span><span class="sxs-lookup"><span data-stu-id="df246-244">Select an agent opt-out option</span></span>

![Снимок экрана: параметры отказа от агента с пронумерованными выносками](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="df246-246">![Значок с номером 1 — ссылка на выноску в предыдущем агенте снимка экрана ](media/teamscallout1.png)
 **может отказаться от получения звонков** . Вы можете разрешить агентам очереди вызовов отказаться от принятия вызовов из конкретной очереди, включив этот параметр.</span><span class="sxs-lookup"><span data-stu-id="df246-246">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="df246-247">Если включить этот параметр, все агенты в этой очереди смогут начать или прекратить прием звонков из этой очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-247">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="df246-248">Сняв данный флажок, привилегию отказа от получения вызовов можно отменить в любое время, в результатае чего операторы снова будут выбраны для работы с этой очередью в автоматическм режиме (это значение по умолчанию применяется для всех операторов).</span><span class="sxs-lookup"><span data-stu-id="df246-248">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="df246-249">Для получения доступа к параметру отказа агенты могут:</span><span class="sxs-lookup"><span data-stu-id="df246-249">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="df246-250">Открыть секцию  **Параметры** на своем рабочем столе клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="df246-250">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="df246-251">На вкладке **Переадресация вызовов** нажать на ссылку **Изменить параметры при подключении к сети** .</span><span class="sxs-lookup"><span data-stu-id="df246-251">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="df246-252">На странице Параметры пользователя нажмите кнопку **очереди звонков**, а затем снимите флажки, чтобы отказаться от использования очередей.</span><span class="sxs-lookup"><span data-stu-id="df246-252">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df246-253">Агенты, использующие приложения или конечные точки, отличные от Skype для бизнеса, могут получить доступ к параметрам отказов на портале параметров пользователя [https://aka.ms/cqsettings](https://aka.ms/cqsettings) .</span><span class="sxs-lookup"><span data-stu-id="df246-253">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="df246-254">Если агенты находятся в настольных клиентах Microsoft Teams, они могут отказаться от использования параметров звонка.</span><span class="sxs-lookup"><span data-stu-id="df246-254">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="df246-255">![Значок числа 2 — ссылка на выноску в предыдущем ](media/teamscallout2.png)
 **параметре оповещения агента** снимка экрана</span><span class="sxs-lookup"><span data-stu-id="df246-255">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="df246-256">Это значение определяет продолжительность агента, уведомленного о вызове, перед тем как будут переноситься методы маршрутизации последовательного или циклического передвижения к следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="df246-256">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="df246-257">Значение по умолчанию составляет 30 секунд, но его можно задать не более чем на 3 минуты.</span><span class="sxs-lookup"><span data-stu-id="df246-257">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="df246-258">Настройка параметров обработки переполнения и времени ожидания звонка</span><span class="sxs-lookup"><span data-stu-id="df246-258">Set the call overflow and timeout handling options</span></span>

![Снимок экрана: параметры обработки переполнения с пронумерованными выносками](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="df246-260">![Значок с номером 1 — ссылается на выноску в предыдущем максимальном количестве снимков экрана ](media/teamscallout1.png)
 **в очереди** . Этот параметр используется для задания максимального количества звонков, которые могут ожидать в очереди.</span><span class="sxs-lookup"><span data-stu-id="df246-260">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="df246-261">Значение по умолчанию — 50, но может принимать значения от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="df246-261">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="df246-262">По достижении этого предела Звонок обрабатывается так, как вы настроили, **когда достигнуто максимальное количество звонков** .</span><span class="sxs-lookup"><span data-stu-id="df246-262">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="df246-263">![Icon для числа 2 — ссылка на выноску на предыдущем снимке экрана, ](media/teamscallout2.png)
 **когда достигнуто максимальное количество звонков** , когда очередь звонков достигает максимального размера (установлен с использованием **максимального числа звонков в** параметрах очереди), вы можете выбрать, что произойдет для новых входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-263">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="df246-264">**Отключение** Звонок прерван.</span><span class="sxs-lookup"><span data-stu-id="df246-264">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="df246-265">**Перенаправить на** Выбрав это, выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="df246-265">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="df246-266">**Сотрудники компании**. Пользователи, подключенные к сети, обладающие лицензией на **телефонную систему** и имеющие доступ к корпоративной голосовой связи, либо тарифный план.</span><span class="sxs-lookup"><span data-stu-id="df246-266">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="df246-267">Вы можете настроить его таким образом, чтобы вызывающий абонент мог отправлять голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="df246-267">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="df246-268">Для этого выберите **пользователя в компании** и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="df246-268">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="df246-269">Сведения о лицензиях, необходимых для голосовой почты, можно найти в статье [Настройка голосовой почты в облаке](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="df246-269">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="df246-270">**Голосовое приложение** Выберите имя учетной записи ресурса, связанной с уже созданной очередью звонков или автоматическим ассистентом.</span><span class="sxs-lookup"><span data-stu-id="df246-270">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

<span data-ttu-id="df246-271">![Значок с номером 3. указывает на выноску в предыдущем ](media/teamscallout3.png)
 **таймауте: максимальное время ожидания** . Кроме того, можно выбрать время, в течение которого звонок может быть заблокирован в очереди до истечения времени ожидания, и его необходимо переадресовать или отключить.</span><span class="sxs-lookup"><span data-stu-id="df246-271">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="df246-272">Там, где он перенаправляется, зависит от того, как вы задаете время истечения **времени вызова** .</span><span class="sxs-lookup"><span data-stu-id="df246-272">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="df246-273">Вы можете установить время в интервале от 0 до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="df246-273">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="df246-274">Значение тайм-аута можно указать в секундах, с интервалом 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="df246-274">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="df246-275">Это позволяет управлять потоком вызовов с более высоким уровнем детализации.</span><span class="sxs-lookup"><span data-stu-id="df246-275">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="df246-276">Например, вы можете указать, что любой звонок, не отвеченный агентом в течение 30 секунд, будет открывать автоматический секретарь поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="df246-276">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="df246-277">![Icon (число 4), который ссылается на выноску на предыдущем снимке экрана, когда ](media/teamscallout4.png)
 **When call times out** Звонок достигает предела, установленного на время **ожидания звонка в очереди** , вы можете выбрать, что произойдет с этим звонком:</span><span class="sxs-lookup"><span data-stu-id="df246-277">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="df246-278">**Отключение** Звонок прерван.</span><span class="sxs-lookup"><span data-stu-id="df246-278">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="df246-279">**Перенаправлять этот звонок** Выбрав этот вариант, вы можете использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="df246-279">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="df246-280">**Сотрудники компании**. Пользователи, подключенные к сети, обладающие лицензией на **телефонную систему**  и имеющие доступ к корпоративной голосовой связи, либо имеющие тарифный план.</span><span class="sxs-lookup"><span data-stu-id="df246-280">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="df246-281">Чтобы настроить голосовую связь в голосовой почте, выберите **пользователя в компании** и настройте его переадресацию прямо на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="df246-281">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="df246-282">Сведения о лицензиях, необходимых для голосовой почты, можно найти в статье [Настройка голосовой почты в облаке](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="df246-282">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="df246-283">**Голосовое приложение** Выберите имя учетной записи ресурса, связанной с уже созданной очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="df246-283">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="df246-284">Изменение идентификатора вызывающего абонента для исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="df246-284">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="df246-285">Чтобы защитить удостоверение агента звонков, измените идентификатор вызывающего абонента для исходящих звонков на очередь звонков, автосекретарь или любой номер службы с помощью командлета **New-CsCallingLineIdentity** , как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df246-285">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="df246-286">Затем примените политику к пользователю с помощью командлета **Grant-CallingLineIdentity** , как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df246-286">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="df246-287">Дополнительные сведения о том, [как можно использовать идентификатор вызывающего абонента в вашей организации](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="df246-287">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="df246-288">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="df246-288">Call queue cmdlets</span></span>

<span data-ttu-id="df246-289">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df246-289">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="df246-290">Ниже приведены командлеты, которые вы используете для управления очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="df246-290">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="df246-291">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="df246-291">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="df246-292">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="df246-292">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="df246-293">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="df246-293">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="df246-294">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="df246-294">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="df246-295">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df246-295">More about Windows PowerShell</span></span>

- <span data-ttu-id="df246-296">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="df246-296">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="df246-297">С помощью Windows PowerShell можно управлять Office 365 и Microsoft Teams с помощью одной точки администрирования.</span><span class="sxs-lookup"><span data-stu-id="df246-297">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="df246-298">Это может упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="df246-298">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="df246-299">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="df246-299">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="df246-300">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="df246-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="df246-301">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="df246-301">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="df246-302">Windows PowerShell обладает большим количеством преимуществ в центре администрирования Microsoft Teams, если вы вносите изменения сразу для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="df246-302">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="df246-303">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="df246-303">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="df246-304">Управление Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df246-304">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="df246-305">Настройка компьютера для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df246-305">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="df246-306">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="df246-306">Related topics</span></span>

[<span data-ttu-id="df246-307">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="df246-307">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="df246-308">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="df246-308">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="df246-309">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="df246-309">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="df246-310">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="df246-310">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
