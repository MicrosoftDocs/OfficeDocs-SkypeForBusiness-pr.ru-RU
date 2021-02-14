---
title: Управление учетными записями ресурсов в Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: В этой статье вы узнаете, как создавать, изменять учетные записи ресурсов и управлять ими в Microsoft Teams.
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031025"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="5c3ee-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5c3ee-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="5c3ee-104">Учетная запись ресурса — это отключенный объект пользователя в Azure AD, который может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="5c3ee-105">Например, учетная запись ресурса может использоваться в Exchange для представления конференц-залов и доступа к номеру телефона и календарю.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="5c3ee-106">Учетную запись ресурса можно использовать в Microsoft 365 или локально с помощью Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="5c3ee-107">В Microsoft Teams для каждого автоотчета или очереди вызовов необходима учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="5c3ee-108">Для учетных записей ресурсов также могут быть назначены телефонные номера служб.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="5c3ee-109">Таким образом вы назначаете номера телефонов автоотводам и очередям звонков, чтобы звонив из-за пределов Teams могли связаться с автостраницой или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="5c3ee-110">В этой статье описывается, как создавать учетные записи ресурсов и создавать их для использования с автоотетарями и очередями вызовов.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="5c3ee-111">Прежде чем приступить к процедурам, которые вы сделали в этой статье, убедитесь, что вы сделали следующее:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="5c3ee-112">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="5c3ee-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="5c3ee-113">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="5c3ee-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="5c3ee-114">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="5c3ee-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="5c3ee-115">Для работы с автозаказами и очередями вызовов для каждой учетной записи ресурса требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="5c3ee-116">Вы можете использовать бесплатную телефонную *систему Microsoft 365 — лицензию виртуального* пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="5c3ee-117">Чтобы получить эти лицензии, см. [лицензию виртуального пользователя.](teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="5c3ee-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="5c3ee-118">Далее в этой статье мы покрываем, как назначить лицензию учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="5c3ee-119">Чтобы получить лицензию виртуального пользователя, в Центре администрирования Microsoft 365 перейдите к подпискам на надстройку "Приобретение служб вы выставлений счета" и прокрутите список до конца (в этом случае вы увидите "Телефонная система — лицензия виртуального  >    >   пользователя"). </span><span class="sxs-lookup"><span data-stu-id="5c3ee-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="5c3ee-120">Выберите **"Купить сейчас".**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-120">Select **Buy now**.</span></span> <span data-ttu-id="5c3ee-121">Это нулевые затраты, но для получения лицензии вам все равно необходимо следовать этим шагам.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="5c3ee-122">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="5c3ee-122">Obtain service numbers</span></span>

<span data-ttu-id="5c3ee-123">Номера служб необязательны для автоотетаря и очередей вызовов, но для того чтобы вызывающие могли связаться с автостраницой и конфигурацией очереди вызовов, требуется хотя бы один номер службы.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="5c3ee-124">Для работы с автостраницой или очередью вызовов, с помощью номера службы необходимо иметь учетную запись ресурса со связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="5c3ee-125">Для учетных записей ресурсов можно использовать как платные, так и бесплатные номера служб.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="5c3ee-126">Вы можете запросить новые номера или номера для переноса у другого оператора связи.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="5c3ee-127">Чтобы получить новые номера служб, [см. получение номеров телефонов службы.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="5c3ee-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="5c3ee-128">Чтобы перенести номер от другого оператора, см. перенос [номеров телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5c3ee-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="5c3ee-129">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="5c3ee-129">Create a resource account</span></span>

<span data-ttu-id="5c3ee-130">Учетную запись ресурса можно создать в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-130">You can create a resource account in the Teams admin center.</span></span>

![Снимок экрана: добавление учетной записи ресурса в пользовательский интерфейс](media/resource-account-add.png)

1. <span data-ttu-id="5c3ee-132">В Центре администрирования Teams раз щелкните **"Параметры** организации", а затем выберите "Учетные записи **ресурсов".**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="5c3ee-133">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-133">Click **Add**.</span></span>

3. <span data-ttu-id="5c3ee-134">В области **"Добавление учетной** записи ресурса" введите **отображаемого** имени, имени **пользователя** и типа **учетной записи ресурса.**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="5c3ee-135">В зависимости от того, как вы собираетесь использовать эту учетную запись **ресурса,** типом учетной записи ресурса может быть автоотчет или очередь вызовов. </span><span class="sxs-lookup"><span data-stu-id="5c3ee-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="5c3ee-136">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-136">Click **Save**.</span></span>

![Снимок экрана: список учетных записей ресурсов](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="5c3ee-138">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="5c3ee-138">Assign a license</span></span>

<span data-ttu-id="5c3ee-139">Для каждой учетной записи ресурса необходимо назначить лицензию на телефонную систему *Microsoft 365 — лицензию виртуального* пользователя или *телефонную систему.*</span><span class="sxs-lookup"><span data-stu-id="5c3ee-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Снимок экрана: пользовательский интерфейс назначения лицензий в Центре администрирования Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="5c3ee-141">В Центре администрирования Microsoft 365 выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="5c3ee-142">На **вкладке "Лицензии и** приложения" в **области "Лицензии"** выберите **"Телефонная система Microsoft 365 — виртуальный пользователь".**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="5c3ee-143">Нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="5c3ee-144">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="5c3ee-144">Assign a service number</span></span>

<span data-ttu-id="5c3ee-145">Если вы планируете использовать учетную запись ресурса с автоотетарем или очередью вызовов, которая требует номер службы, назначьте номер учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Снимок экрана: пользовательский интерфейс назначения номера службы](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="5c3ee-147">В Центре администрирования Teams  на странице "Учетные записи ресурсов" выберите учетную запись ресурса, для которой вы хотите назначить номер службы, а затем нажмите кнопку "Назначить/отозначить". </span><span class="sxs-lookup"><span data-stu-id="5c3ee-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="5c3ee-148">В **dropdown (Тип номера телефона)** выберите нужный тип номера.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="5c3ee-149">В поле **"Назначенное номер телефона"** найдите нужный номер и нажмите кнопку "Добавить". </span><span class="sxs-lookup"><span data-stu-id="5c3ee-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="5c3ee-150">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-150">Click **Save**.</span></span>


<span data-ttu-id="5c3ee-151">Чтобы назначить учетной записи ресурса прямое маршрутное или гибридное число, используйте PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="5c3ee-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5c3ee-152">Next steps</span></span>

<span data-ttu-id="5c3ee-153">После завершения настройки учетной записи ресурса и назначения номера службы при необходимости вы можете использовать учетную запись ресурса с автоотетарем или очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="5c3ee-154">См. следующие ссылки:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-154">See the following references:</span></span>

 - [<span data-ttu-id="5c3ee-155">Автозаметарь в облаке</span><span class="sxs-lookup"><span data-stu-id="5c3ee-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="5c3ee-156">Очередь облачных вызовов</span><span class="sxs-lookup"><span data-stu-id="5c3ee-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="5c3ee-157">Отображаемого имени  учетной записи и типа учетной записи ресурса можно изменить **с** помощью **параметра "Изменить".**</span><span class="sxs-lookup"><span data-stu-id="5c3ee-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="5c3ee-158">Когда **все будет готово,** нажмите кнопку "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="5c3ee-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="5c3ee-159">Изменение существующей учетной записи ресурса для использования лицензии виртуального пользователя</span><span class="sxs-lookup"><span data-stu-id="5c3ee-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="5c3ee-160">Если вы решите переключить лицензии существующей  учетной записи ресурсов с лицензии телефонной системы на лицензию виртуального пользователя, вам потребуется получить бесплатную лицензию виртуального пользователя, а затем в Центре администрирования Microsoft 365 выполните действия по переходу пользователей на другую подписку. [](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="5c3ee-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="5c3ee-161">Всегда удалять полную лицензию на телефонную систему и назначать лицензию виртуальному пользователю в одном действии с лицензией.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="5c3ee-162">Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может перестать работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="5c3ee-163">В этом случае мы рекомендуем создать новую учетную запись ресурса для лицензии виртуального пользователя и удалить неотвеяжаемую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="5c3ee-164">Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5c3ee-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="5c3ee-165">Если учетные записи ресурсов, которые используются в Skype для бизнеса Server 2019, [](/SkypeforBusiness/hybrid/plan-call-queue) которые могут использоваться с очередями облачных звонков и автозавершить, см. статью "Планирование очередей звонков в облаке" или "Планирование автозавершника в облаке". [](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="5c3ee-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="5c3ee-166">Гибридные реализации (номера, которые находятся на прямой маршрутизации) настраиваются с помощью cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) на локальном сервере Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="5c3ee-167">При создании экземпляров приложения вам нужны такие ИД:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="5c3ee-168">**автосекретарь:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="5c3ee-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="5c3ee-169">**Очередь** вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="5c3ee-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="5c3ee-170">Если вы хотите, чтобы пользователи Skype для бизнеса Server 2019 могли использовать для поиска очередь звонков или автозаверверх, создайте учетные записи ресурсов в Skype для бизнеса Server 2019, так как учетные записи ресурсов в Сети не синхронизируются с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="5c3ee-171">Когда записи SRV DNS для sipfederationtls разрешались в Skype для  бизнеса Server 2019, то в Skype для бизнеса Server 2019 необходимо создать учетные записи ресурсов с помощью оболочки управления SfB и синхронизироваться с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="5c3ee-172">Для реализации, гибридной со Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="5c3ee-173">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="5c3ee-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="5c3ee-174">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="5c3ee-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="5c3ee-175">Настройка учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="5c3ee-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="5c3ee-176">Удаление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="5c3ee-176">Delete a resource account</span></span>

<span data-ttu-id="5c3ee-177">Перед удалением номера телефона из учетной записи ресурса убедитесь, что он не удаляется, чтобы номер службы не зависал в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="5c3ee-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="5c3ee-178">После этого вы можете удалить учетную запись ресурса в Центре администрирования Microsoft 365 на вкладке "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="5c3ee-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="5c3ee-179">Чтобы отсоединять прямой маршрутный номер телефона из учетной записи ресурса, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5c3ee-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
