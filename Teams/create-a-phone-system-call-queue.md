---
title: Создание очереди вызовов
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Сведения о том, как настроить телефонную систему для очередей облачных вызовов в Microsoft Teams.
ms.openlocfilehash: 887c92e398487d3e42f9fc560610683008760105
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207185"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="b7815-103">Создание облачной очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="b7815-103">Create a Cloud call queue</span></span>

<span data-ttu-id="b7815-104">Очереди облачных вызовов предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="b7815-104">Cloud call queues can provide:</span></span>
 
- <span data-ttu-id="b7815-105">Сообщение приветствия.</span><span class="sxs-lookup"><span data-stu-id="b7815-105">A greeting message.</span></span>
- <span data-ttu-id="b7815-106">Воспроизведение музыки во время удержания звонка.</span><span class="sxs-lookup"><span data-stu-id="b7815-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="b7815-107">Перенаправление вызовов в списки рассылки и группы безопасности с поддержкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b7815-107">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="b7815-108">Параметры разных параметров, такие как максимальный размер, таймаут и параметры обработки звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-108">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="b7815-109">Когда кто-то звонит на номер телефона, связанный со очередью звонков через [учетную запись ресурса](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="b7815-109">When someone calls a phone number that is associated with a call queue via a [resource account](manage-resource-accounts.md):</span></span> 
1. <span data-ttu-id="b7815-110">Они прослушивают приветствие (если все настроено)</span><span class="sxs-lookup"><span data-stu-id="b7815-110">They  hear a greeting (if any is set up)</span></span> 
2. <span data-ttu-id="b7815-111">Их вызов помещается в очередь для ожидания следующего доступного агента звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-111">Their call is put in the queue to wait for the next available call agent.</span></span> 
 

<span data-ttu-id="b7815-112">Вызывающий абонент слышит музыку, пока они находятся на удержании, и Звонок подключается к агентам звонков в порядке " *первым вошел — первым вышел* " (FIFO).</span><span class="sxs-lookup"><span data-stu-id="b7815-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>
 
<span data-ttu-id="b7815-113">Все звонки в очереди отправляются агентам одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b7815-113">All calls in the queue are sent to agents by one of the following methods:</span></span>
 
- <span data-ttu-id="b7815-114">При использовании маршрутизации помощника первый вызов в очереди одновременно колец все агенты.</span><span class="sxs-lookup"><span data-stu-id="b7815-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="b7815-115">При использовании последовательной маршрутизации первый вызов из очереди звонит по каждому из них по одному.</span><span class="sxs-lookup"><span data-stu-id="b7815-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="b7815-116">При циклическом перераспределении Маршрутизация входящих звонков сбалансирована таким образом, что каждый агент вызова получает одинаковое количество звонков из очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7815-117">Агенты звонков, которые находятся в **автономном режиме**, имеют состояние " **не беспокоить** " или не переносятся в очередь звонков, не будут получать звонки.</span><span class="sxs-lookup"><span data-stu-id="b7815-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
 
- <span data-ttu-id="b7815-118">Только одно уведомление о входящем звонке (для звонка в заголовке очереди) в каждый момент времени отправляется агентам звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="b7815-119">После того, как оператор принимает звонок, всем операторам поступает следующий входящий звонок из очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="b7815-120">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b7815-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="b7815-121">Этап 1 — Начало работы</span><span class="sxs-lookup"><span data-stu-id="b7815-121">Step 1 — Get started</span></span>

<span data-ttu-id="b7815-122">Перед началом работы с очередями звонков необходимо запомнить следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="b7815-122">To get started using call queues, it's important to remember a few things:</span></span>
 
- <span data-ttu-id="b7815-123">Для связи с учетной записью ресурса требуется очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="b7815-124">Дополнительные сведения об учетных записях ресурсов содержатся [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="b7815-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="b7815-125">После назначения номера телефона для учетной записи ресурса теперь вы можете использовать лицензию на виртуальную систему [пользователей](teams-add-on-licensing/virtual-user.md)с бесплатной платой.</span><span class="sxs-lookup"><span data-stu-id="b7815-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="b7815-126">Телефонная система позволяет использовать номера телефонов на уровне Организации для автосекретаря по низким тарифам и для службы очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="b7815-127">Номера услуг прямой маршрутизации для очередей звонков поддерживаются только для пользователей и агентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b7815-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="b7815-128">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7815-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b7815-129">В разделе [Назначение лицензий на Skype для бизнеса](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) или [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="b7815-129">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="b7815-130">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7815-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b7815-131">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b7815-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
 
- <span data-ttu-id="b7815-132">Чтобы узнать больше о тарифных планах Office 365, ознакомьтесь со статьями [телефонные системы и](calling-plan-landing-page.md) планы звонков и [планы звонков для Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b7815-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="b7815-133">Вы можете назначить очереди облачных звонков только платными телефонными номерами, которые были получены в **центре администрирования Microsoft Teams** или переданы из другого поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="b7815-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="b7815-134">Для платных номеров услуг требуются кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="b7815-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7815-135">Номера телефонов пользователей (абонентов) нельзя назначить очередям звонков  можно использовать платные или бесплатные номера телефонов служб.</span><span class="sxs-lookup"><span data-stu-id="b7815-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
 
- <span data-ttu-id="b7815-136">Для агентов звонков, связанных с облачной очередью звонков, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="b7815-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="b7815-137">Настольный клиент 2016 для настольных компьютеров Skype для бизнеса (32-разр и 64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="b7815-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="b7815-138">Классическое приложение Lync 2013 (32-разр и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="b7815-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="b7815-139">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b7815-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="b7815-140">Узнайте о том, как [получить телефоны в Skype для бизнеса Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b7815-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="b7815-141">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="b7815-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="b7815-142">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="b7815-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="b7815-143">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="b7815-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b7815-144">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="b7815-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b7815-145">Клиент Microsoft Teams для Windows (32-разрядная версия и 64-разр.)</span><span class="sxs-lookup"><span data-stu-id="b7815-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="b7815-146">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="b7815-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="b7815-147">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="b7815-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="b7815-148">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="b7815-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="b7815-149">Шаг 2. Получение или перенос платных или бесплатных номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="b7815-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="b7815-150">Прежде чем вы сможете создавать и настраивать очереди звонков, вам нужно получить или переадресовать существующие платные или бесплатные номера сервисных услуг.</span><span class="sxs-lookup"><span data-stu-id="b7815-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b7815-151">После получения платных и бесплатных телефонных номеров, они будут отображаться в\*\*\*\*\*\*\*\* >  **центре** > администрирования Microsoft Teams в Интернете для**голосовой связи** > с другими абонентами, а **тип номера** будет указан в списке как **Услуга**– бесплатный.</span><span class="sxs-lookup"><span data-stu-id="b7815-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b7815-152">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md) или перенесите существующий номер Услуги в разделе [Перенос номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b7815-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
 
> [!NOTE]
> <span data-ttu-id="b7815-153">За пределами США нельзя использовать центр администрирования Microsoft Teams для получения номеров служб.</span><span class="sxs-lookup"><span data-stu-id="b7815-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="b7815-154">Чтобы узнать, как сделать это из за пределами США, перейдите в раздел [Управление телефонными номерами в Организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="b7815-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="b7815-155">Если вы настраиваете несколько автосекретарей, вам может потребоваться только назначить номер телефона основной учетной записи для автосекретаря, которая может перенаправлять абонентов в очереди звонков или на вложенные автоматические ассистенты.</span><span class="sxs-lookup"><span data-stu-id="b7815-155">If you are setting up multiple auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="b7815-156">В этих случаях вы должны создать все автосекретарей и очереди звонков в системе без назначения параметров панель набора номера и затем изменить параметры позже.</span><span class="sxs-lookup"><span data-stu-id="b7815-156">In those situations you should create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="b7815-157">Это необходимо, так как вы не можете создать ссылку на очередь звонков или автосекретарь, который пока еще не существует.</span><span class="sxs-lookup"><span data-stu-id="b7815-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>
 
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="b7815-158">Шаг 3: создание новой очереди звонков</span><span class="sxs-lookup"><span data-stu-id="b7815-158">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="b7815-159">Каждая очередь звонков должна иметь связанную учетную [запись ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b7815-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="b7815-160">Сначала необходимо создать учетную запись ресурса, после чего вы сможете связать ее с очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7815-161">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7815-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b7815-162">В **центре администрирования Microsoft Teams**выберите очередь **голосовых** > **звонков**и нажмите кнопку **+ Добавить новый**:</span><span class="sxs-lookup"><span data-stu-id="b7815-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="b7815-163">Настройка отображаемого имени и учетной записи ресурса очереди звонков</span><span class="sxs-lookup"><span data-stu-id="b7815-163">Set the call queue display name and resource account</span></span>

![снимок экрана: новая очередь звонков с пронумерованными выносками](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="b7815-165">![Значок цифра 1: ссылка на выноску в предыдущем](media/sfbcallout1.png)
**имени** снимка экрана введите описательное отображаемое имя для очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="b7815-166">Это имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="b7815-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="b7815-167">Это имя будет отображаться в уведомлении о входящем звонке.</span><span class="sxs-lookup"><span data-stu-id="b7815-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="b7815-169">**Добавление учетных записей** Выберите учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b7815-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="b7815-170">Учетная запись ресурса может быть связана со службой Service платный или бесплатный номер в очереди звонков, но для каждой очереди звонков требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b7815-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="b7815-171">Если в списке нет списка, необходимо получить номера служб и назначить их учетной записи ресурса, прежде чем можно будет создать эту очередь звонков, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="b7815-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="b7815-172">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="b7815-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="b7815-173">Вам потребуется создать учетную запись ресурса, как описано в разделе [Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) , если вы хотите, чтобы в очередь звонков сопоставлены номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="b7815-173">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="b7815-174">Если вы хотите или вам нужно назначить **домен** , назначая его учетной записи ресурса для очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="b7815-175">Настройка приветствия и музыки, воспроизводимой во время удержания</span><span class="sxs-lookup"><span data-stu-id="b7815-175">Set the greeting and music played while on hold</span></span>

![снимок экрана: параметры приветствия и музыки с пронумерованными выносками](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
 
* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="b7815-178">**Приветствие**  необязательное поле.</span><span class="sxs-lookup"><span data-stu-id="b7815-178">**Greeting** is optional.</span></span> <span data-ttu-id="b7815-179">Это приветствие, которое воспроизводится для абонентов, которые вызывают номер очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="b7815-180">Вы можете добавить звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="b7815-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="b7815-182">**Музыка на удержании** Вы можете использовать музыку по умолчанию на удержании с помощью очереди звонков, а также можно добавить звуковой файл в формате WAV, MP3 или WMA, чтобы использовать его в качестве музыкальной музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="b7815-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="b7815-183">Выбор параметров ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="b7815-183">Select the call answering options</span></span>

![снимок экрана: параметры ответа на звонки с пронумерованными выносками](media/5d249515-d532-4af2-90da-011404028b89.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="b7815-186">Вы можете выбрать до 200 агенты звонков, которые относятся к любому из указанных ниже списков рассылки или групп.</span><span class="sxs-lookup"><span data-stu-id="b7815-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="b7815-187">Группа Office 365</span><span class="sxs-lookup"><span data-stu-id="b7815-187">Office 365 group</span></span>
- <span data-ttu-id="b7815-188">Группа безопасности</span><span class="sxs-lookup"><span data-stu-id="b7815-188">Security group</span></span>
- <span data-ttu-id="b7815-189">Список рассылки</span><span class="sxs-lookup"><span data-stu-id="b7815-189">Distribution list</span></span>

<span data-ttu-id="b7815-190">Выбранные агенты звонков должны \*\*\*\* быть подключены к сети с помощью лицензии на **телефонную систему** , а также с включенным корпоративным голосом **или** абонентским планом.</span><span class="sxs-lookup"><span data-stu-id="b7815-190">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b7815-191">Это также применимо, если вы хотите перенаправить звонки на пользователей в вашей организации, которые находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="b7815-191">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="b7815-192">Эти люди должны иметь лицензию на **телефонную систему** , а также включить поддержку голосовой связи в рамках Skype **или** получить план звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-192">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="b7815-193">Дополнительные сведения можно найти в статье [Назначение лицензий Skype для бизнеса](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Назначение лицензий Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), а также [план звонков.](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b7815-193">For more information see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="b7815-194">Для включения агента для корпоративного голосовой связи можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7815-194">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b7815-195">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b7815-195">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="b7815-196">Сетевые пользователи с лицензией на **телефонную систему** или планом на звонки, добавленные в группу Office 365; Список рассылки, поддерживающий почту; или группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7815-196">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="b7815-197">Недавно добавленный агент в списке рассылки или группе безопасности может занять до 3 часов, чтобы начать получать звонки из очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-197">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="b7815-198">Чтобы вновь созданный список распределения или группа безопасности стали доступными для использования с очередями вызовов, может потребоваться до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="b7815-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="b7815-199">Вновь созданные группы Office 365 становятся доступными незамедлительно.</span><span class="sxs-lookup"><span data-stu-id="b7815-199">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="b7815-200">Если агенты используют приложение Microsoft Teams для приема вызовов из очереди звонков, они должны находиться в режиме Теамсонли.</span><span class="sxs-lookup"><span data-stu-id="b7815-200">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![снимок экрана: область "Добавление агентов по звонку"](media/skype-for-business-add-agents-to-call-queue.png)

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="b7815-203">**Метод маршрутизации** Вы можете выбрать **участника**, последовательного или **циклического** перераспределения для метода распространения очереди звонков. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b7815-203">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="b7815-204">По умолчанию для всех новых и существующих очередей вызовов выбирается  маршрутизация автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b7815-204">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="b7815-205">При использовании маршрутизации для участия первый звонок в очереди будет звонить всем агентам звонков одновременно.</span><span class="sxs-lookup"><span data-stu-id="b7815-205">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="b7815-206">Вызов вызывается агентом первого вызова для выбора звонка.</span><span class="sxs-lookup"><span data-stu-id="b7815-206">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="b7815-207">Если вы перезвоните в **службу** , первый звонок в очереди будет звонить всем агентам звонков одновременно.</span><span class="sxs-lookup"><span data-stu-id="b7815-207">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="b7815-208">Вызов вызывается агентом первого вызова для выбора звонка.</span><span class="sxs-lookup"><span data-stu-id="b7815-208">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="b7815-209">Входящие звонки последовательного **порта** будут звонить по одному агенту, начиная с начала списка.</span><span class="sxs-lookup"><span data-stu-id="b7815-209">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="b7815-210">Агенты нельзя заказать в списке "агент вызова".</span><span class="sxs-lookup"><span data-stu-id="b7815-210">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="b7815-211">Если оператор отклоняет или не принимает вызов, то он перенаправляется следующему оператору в списке. Вызов поочередно поступает операторам до тех пор, пока он не будет принят, или пока не истечет тайм-аут по ожиданию в очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-211">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="b7815-212">При последовательной маршрутизации пропускаются те операторы, которые имеют статус **Не в сети**, характеризуют свою доступность с помощью опции **Не беспокоить** или **отказались** от получения вызовов из этой очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-212">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="b7815-213">\*\*\*\* Функция циклического перераспределения обеспечивает маршрутизацию входящих звонков, чтобы каждый агент вызова получил одинаковое количество звонков из очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-213">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="b7815-214">Это может быть очень желательным в среде входящей продажи для обеспечения возможной возможности между всеми агентами звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-214">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="b7815-215">Выбор варианта отказа от агента</span><span class="sxs-lookup"><span data-stu-id="b7815-215">Select an agent opt-out option</span></span>

![снимок экрана: параметры отказа от агента с пронумерованными выносками](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
 
* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="b7815-218">**Агент может отказаться от звонков** Вы можете разрешить агентам очереди звонков отказаться от приема звонков из определенной очереди, включив этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b7815-218">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="b7815-219">Если включить этот параметр, все агенты в этой очереди смогут начать или прекратить прием звонков из этой очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-219">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="b7815-220">Сняв данный флажок, привилегию отказа от получения вызовов можно отменить в любое время, в результатае чего операторы снова будут выбраны для работы с этой очередью в автоматическм режиме (это значение по умолчанию применяется для всех операторов).</span><span class="sxs-lookup"><span data-stu-id="b7815-220">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="b7815-221">Для доступа к функции отказа операторы могут выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b7815-221">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="b7815-222">Открыть секцию  **Параметры** на своем рабочем столе клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b7815-222">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="b7815-223">На вкладке **Переадресация вызовов** нажать на ссылку **Изменить параметры при подключении к сети** .</span><span class="sxs-lookup"><span data-stu-id="b7815-223">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="b7815-224">На странице Параметры пользователя нажмите кнопку **очереди звонков**, а затем снимите флажки для всех очередей, для которых нужно отказаться от них.</span><span class="sxs-lookup"><span data-stu-id="b7815-224">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7815-225">Агенты, использующие приложения или конечные точки, отличные от Skype для бизнеса, могут получить доступ к параметрам отказов [https://aka.ms/cqsettings](https://aka.ms/cqsettings)на портале параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7815-225">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="b7815-226">![Значок числа 2 с ссылкой на выноску в предыдущем](media/sfbcallout2.png)
**параметре оповещения агента** снимка экрана</span><span class="sxs-lookup"><span data-stu-id="b7815-226">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="b7815-227">Это значение определяет продолжительность агента, уведомленного о вызове, перед тем как будут переноситься методы маршрутизации последовательного или циклического передвижения к следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="b7815-227">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="b7815-228">Значение по умолчанию составляет 30 секунд, но его можно задать не более чем на 3 минуты.</span><span class="sxs-lookup"><span data-stu-id="b7815-228">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="b7815-229">Настройка параметров обработки переполнения и времени ожидания звонка</span><span class="sxs-lookup"><span data-stu-id="b7815-229">Set the call overflow and timeout handling options</span></span>

![снимок экрана: параметры обработки переполнения с пронумерованными выносками](media/3f018734-16fe-458b-827d-71fc25155cde.png)
 
* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="b7815-232">**Максимальное количество вызовов в очереди** Используйте этот параметр для настройки максимального количества звонков, которые могут ожидать в очереди.</span><span class="sxs-lookup"><span data-stu-id="b7815-232">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="b7815-233">Значение по умолчанию — 50, но может принимать значения от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="b7815-233">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="b7815-234">По достижении этого ограничения звонок будет обработан так, как установлено в параметре **Когда достигается максимальное число звонков** (см. ниже).   </span><span class="sxs-lookup"><span data-stu-id="b7815-234">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="b7815-236">**При достижении максимально допустимого количества звонков** Когда очередь звонков достигает максимального размера (с использованием **максимального количества звонков в** параметрах очереди), вы можете выбрать, что произойдет для новых входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-236">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="b7815-237">**Отключить**. Звонок отключается.   </span><span class="sxs-lookup"><span data-stu-id="b7815-237">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b7815-238">**Перенаправить на** Выбрав это, выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="b7815-238">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="b7815-239">**Сотрудники компании**. Пользователи, подключенные к сети, обладающие лицензией на **телефонную систему** и имеющие доступ к корпоративной голосовой связи, либо тарифный план.</span><span class="sxs-lookup"><span data-stu-id="b7815-239">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="b7815-240">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="b7815-240">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b7815-241">Для этого выберите **пользователя в компании** и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="b7815-241">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b7815-242">Сведения о лицензировании, требуемом для голосовой почты, можно найти в разделе [Настройка голосовой почты](set-up-phone-system-voicemail.md)в облаке.</span><span class="sxs-lookup"><span data-stu-id="b7815-242">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="b7815-243">**Голосовое приложение** Выберите имя либо очереди звонков, либо автосекретаря, который уже создан.</span><span class="sxs-lookup"><span data-stu-id="b7815-243">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="b7815-245">**Таймаут вызова: максимальное время ожидания** Кроме того, можно выбрать время, в течение которого звонок может быть задержан в очереди, прежде чем истекает время ожидания, и его необходимо переадресовать или отключить.</span><span class="sxs-lookup"><span data-stu-id="b7815-245">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="b7815-246">Там, где оно будет перенаправлено, зависит от того, как вы задаете время истечения **времени вызова** .</span><span class="sxs-lookup"><span data-stu-id="b7815-246">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="b7815-247">Вы можете установить время в интервале от 0 до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="b7815-247">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="b7815-248">Значение тайм-аута можно указать в секундах, с интервалом 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="b7815-248">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="b7815-249">Это позволяет управлять потоком вызовов с более высоким уровнем детализации.</span><span class="sxs-lookup"><span data-stu-id="b7815-249">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="b7815-250">Например, вы можете указать, что любой звонок, не отвеченный агентом в течение 30 секунд, будет открывать автоматический секретарь поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="b7815-250">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="b7815-252">Время **ожидания звонка** Когда звонок достигает ограничения, установленного на **время ожидания звонка в очереди** , вы можете выбрать, что произойдет с этим звонком:</span><span class="sxs-lookup"><span data-stu-id="b7815-252">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="b7815-253">**Отключить**. Звонок отключается.   </span><span class="sxs-lookup"><span data-stu-id="b7815-253">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b7815-254">**Перенаправлять этот звонок** При выборе этого параметра будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7815-254">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="b7815-255">**Сотрудники компании**. Пользователи, подключенные к сети, обладающие лицензией на **телефонную систему**  и имеющие доступ к корпоративной голосовой связи, либо имеющие тарифный план.</span><span class="sxs-lookup"><span data-stu-id="b7815-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="b7815-256">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="b7815-256">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b7815-257">Для этого выберите **пользователя в компании** и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="b7815-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b7815-258">Сведения о лицензировании, требуемом для голосовой почты, можно найти в разделе [Настройка голосовой почты](set-up-phone-system-voicemail.md)в облаке.</span><span class="sxs-lookup"><span data-stu-id="b7815-258">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="b7815-259">**Голосовое приложение** Выберите имя либо очереди звонков, либо автосекретаря, который уже создан.</span><span class="sxs-lookup"><span data-stu-id="b7815-259">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="b7815-260">Изменение идентификатора звонящего пользователя для исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="b7815-260">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="b7815-261">Вы можете защитить удостоверение пользователя, изменив его идентификатор вызывающего абонента для исходящих звонков в очередь звонков, автосекретарь или любой другой номер службы, а затем создав политику с помощью командлета **New-кскаллинглинеидентити** .</span><span class="sxs-lookup"><span data-stu-id="b7815-261">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="b7815-262">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="b7815-262">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="b7815-263">Затем примените политику к пользователю, воспользовавшись командлетом **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="b7815-263">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="b7815-264">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="b7815-264">To do this, run:</span></span>
 
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="b7815-265">Дополнительные сведения о том, как вносить изменения в параметры идентификатора вызывающего абонента в Организации, можно получить в статье Использование [идентификатора вызывающего абонента в вашей организации](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="b7815-265">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="b7815-266">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="b7815-266">Call queue cmdlets</span></span>

<span data-ttu-id="b7815-267">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7815-267">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="b7815-268">Далее перечислены командлеты, необходимые для управления очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="b7815-268">Here are the cmdlets that you need to manage a call queue.</span></span>
 
- [<span data-ttu-id="b7815-269">New-Кскаллкуеуе</span><span class="sxs-lookup"><span data-stu-id="b7815-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b7815-270">Set-Кскаллкуеуе</span><span class="sxs-lookup"><span data-stu-id="b7815-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b7815-271">Get-Кскаллкуеуе</span><span class="sxs-lookup"><span data-stu-id="b7815-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b7815-272">Remove-Кскаллкуеуе</span><span class="sxs-lookup"><span data-stu-id="b7815-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="b7815-273">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7815-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="b7815-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="b7815-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b7815-275">С помощью Windows PowerShell вы можете управлять набором Office 365 и Microsoft Teams с помощью одной точки администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="b7815-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b7815-276">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="b7815-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b7815-277">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b7815-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="b7815-278">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="b7815-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="b7815-279">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft Teams, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7815-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b7815-280">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b7815-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b7815-281">Управление Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7815-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="b7815-282">Настройка компьютера для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7815-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="b7815-283">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b7815-283">Related topics</span></span>

[<span data-ttu-id="b7815-284">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="b7815-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b7815-285">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="b7815-285">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="b7815-286">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="b7815-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b7815-287">New-Ксонлинеаппликатионинстанце</span><span class="sxs-lookup"><span data-stu-id="b7815-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
