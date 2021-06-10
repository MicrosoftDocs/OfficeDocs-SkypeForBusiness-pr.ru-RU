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
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094249"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="9fca1-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fca1-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="9fca1-104">Учетная запись ресурса — это объект отключенного пользователя в Azure AD, который может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="9fca1-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="9fca1-105">Например, учетную запись ресурса можно использовать в Exchange для представления конференц-залов и доступа к номеру телефона и календарю.</span><span class="sxs-lookup"><span data-stu-id="9fca1-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="9fca1-106">Учетную запись ресурса можно использовать в Microsoft 365 локально или Skype для бизнеса Server 2019 г.</span><span class="sxs-lookup"><span data-stu-id="9fca1-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="9fca1-107">В Microsoft Teams требуется учетная запись ресурса для каждого автоотчета или очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="9fca1-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="9fca1-108">Для учетных записей ресурсов также могут быть назначены телефонные номера служб.</span><span class="sxs-lookup"><span data-stu-id="9fca1-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="9fca1-109">Таким образом вы назначаете номера телефонов автоотводчикам и очередям звонков, чтобы Teams могли связаться с автозаводом или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="9fca1-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="9fca1-110">В этой статье описывается, как создавать учетные записи ресурсов и создавать их для использования с автосчетами и очередями вызовов.</span><span class="sxs-lookup"><span data-stu-id="9fca1-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="9fca1-111">Прежде чем приступить к процедурам в этой статье, убедитесь, что вы сделали следующее:</span><span class="sxs-lookup"><span data-stu-id="9fca1-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="9fca1-112">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="9fca1-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="9fca1-113">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="9fca1-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="9fca1-114">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="9fca1-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="9fca1-115">Для работы с автозаказами и очередями вызовов для каждой учетной записи ресурса требуется лицензия.</span><span class="sxs-lookup"><span data-stu-id="9fca1-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="9fca1-116">Вы можете использовать бесплатную *лицензию Microsoft 365 телефонная система — виртуальный* пользователь.</span><span class="sxs-lookup"><span data-stu-id="9fca1-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="9fca1-117">Чтобы получить эти лицензии, см. [лицензию виртуального пользователя.](teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="9fca1-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="9fca1-118">Далее в этой статье мы покрываем, как назначить лицензию учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="9fca1-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="9fca1-119">Чтобы получить лицензию виртуального пользователя, в Центре администрирования Microsoft 365 перейдите к подпискам на надстройки "Приобретение услуг вы выставлением счета" и прокрутите список до конца — вы увидите телефонная система — лицензия виртуального  >    >   пользователя. </span><span class="sxs-lookup"><span data-stu-id="9fca1-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="9fca1-120">Выберите **Купить .**</span><span class="sxs-lookup"><span data-stu-id="9fca1-120">Select **Buy now**.</span></span> <span data-ttu-id="9fca1-121">Это нулевые затраты, но для получения лицензии все равно необходимо сделать это.</span><span class="sxs-lookup"><span data-stu-id="9fca1-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="9fca1-122">Получение номеров служб</span><span class="sxs-lookup"><span data-stu-id="9fca1-122">Obtain service numbers</span></span>

<span data-ttu-id="9fca1-123">Номера служб необязательны для автозаверх и очередей вызовов, но для того чтобы вызывающие могли связаться с автослужбой и конфигурацией очереди вызовов, требуется по крайней мере один номер службы.</span><span class="sxs-lookup"><span data-stu-id="9fca1-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="9fca1-124">Если вы хотите связаться с автоотчетом или очередью вызовов напрямую по номеру службы, у вас должна быть учетная запись ресурса со связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="9fca1-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="9fca1-125">В учетных записях ресурсов могут быть как платные, так и бесплатные номера служб.</span><span class="sxs-lookup"><span data-stu-id="9fca1-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="9fca1-126">Вы можете запросить новые номера или номера переноса у другого оператора связи.</span><span class="sxs-lookup"><span data-stu-id="9fca1-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="9fca1-127">Чтобы получить новые номера служб, см. [получение номеров телефонов службы.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="9fca1-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="9fca1-128">Чтобы перенести номер от другого оператора связи, см. перенос [номеров телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9fca1-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="9fca1-129">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="9fca1-129">Create a resource account</span></span>

<span data-ttu-id="9fca1-130">Вы можете создать учетную запись ресурса в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="9fca1-130">You can create a resource account in the Teams admin center.</span></span>

![Снимок экрана: добавление пользовательского интерфейса учетной записи ресурса](media/resource-account-add.png)

1. <span data-ttu-id="9fca1-132">В центре Teams разметка **параметров** для всей организации и нажмите кнопку **Учетные записи ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="9fca1-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="9fca1-133">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9fca1-133">Click **Add**.</span></span>

3. <span data-ttu-id="9fca1-134">В области **Добавление учетной записи** ресурса введите **отображаемого** имени , **имя пользователя** и тип **учетной записи ресурса.**</span><span class="sxs-lookup"><span data-stu-id="9fca1-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="9fca1-135">Тип учетной записи  ресурса может быть автоотчетом или очередью вызовов **в** зависимости от того, как вы собираетесь использовать эту учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="9fca1-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="9fca1-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9fca1-136">Click **Save**.</span></span>

![Снимок экрана: список учетных записей ресурсов](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="9fca1-138">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="9fca1-138">Assign a license</span></span>

<span data-ttu-id="9fca1-139">Для каждой учетной записи ресурса необходимо назначить лицензию *Microsoft 365 телефонная система виртуальный* пользователь или телефонная система *лицензию.*</span><span class="sxs-lookup"><span data-stu-id="9fca1-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Снимок экрана: пользовательский интерфейс назначения лицензий в центре Microsoft 365 администрирования](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="9fca1-141">В центре Microsoft 365 выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="9fca1-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="9fca1-142">На **вкладке Лицензии и приложения** в области **Лицензии** выберите Microsoft 365 телефонная система **— виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="9fca1-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="9fca1-143">Нажмите **кнопку Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="9fca1-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="9fca1-144">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="9fca1-144">Assign a service number</span></span>

<span data-ttu-id="9fca1-145">Если вы планируете использовать учетную запись ресурса с автослужавщиком или очередью вызовов, которая требует номер службы, назначьте номер учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="9fca1-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Снимок экрана: пользовательский интерфейс назначения номера службы](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="9fca1-147">В Центре Teams администрирования на  странице Учетные записи ресурсов выберите учетную запись ресурса, для которой нужно назначить номер службы, и нажмите кнопку **Назначить/отозначить**.</span><span class="sxs-lookup"><span data-stu-id="9fca1-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="9fca1-148">В **Телефон числовом типе** выберите нужный тип.</span><span class="sxs-lookup"><span data-stu-id="9fca1-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="9fca1-149">В **поле Назначен номер телефона** найдите нужный номер и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="9fca1-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="9fca1-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9fca1-150">Click **Save**.</span></span>


<span data-ttu-id="9fca1-151">Чтобы назначить учетной записи ресурса прямую маршрутику или гибридный номер, необходимо использовать PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9fca1-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="9fca1-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9fca1-152">Next steps</span></span>

<span data-ttu-id="9fca1-153">После завершения настройки учетной записи ресурса и назначения номера службы при необходимости вы можете использовать учетную запись ресурса с автослужавщиком или очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="9fca1-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="9fca1-154">См. следующие ссылки:</span><span class="sxs-lookup"><span data-stu-id="9fca1-154">See the following references:</span></span>

 - [<span data-ttu-id="9fca1-155">Облачный автозаводщик</span><span class="sxs-lookup"><span data-stu-id="9fca1-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="9fca1-156">Очередь облачных вызовов</span><span class="sxs-lookup"><span data-stu-id="9fca1-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="9fca1-157">Изменить отображаемую  и тип учетной записи ресурса можно **с** помощью **параметра Изменить.**</span><span class="sxs-lookup"><span data-stu-id="9fca1-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="9fca1-158">Когда **все будет готово,** нажмите кнопку Сохранить.</span><span class="sxs-lookup"><span data-stu-id="9fca1-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="9fca1-159">Изменение существующей учетной записи ресурса на использование лицензии виртуального пользователя</span><span class="sxs-lookup"><span data-stu-id="9fca1-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="9fca1-160">Если вы решите переключить лицензии существующей учетной записи ресурсов с лицензии **телефонная система** на лицензию виртуального пользователя, вам потребуется получить бесплатную лицензию виртуального пользователя, а затем в Центре администрирования Microsoft 365 выполните действия, чтобы переместить пользователей в другую подписку. [](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="9fca1-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="9fca1-161">Всегда удаляем полную телефонная система лицензию и назначаем лицензию виртуального пользователя в одном действии с лицензией.</span><span class="sxs-lookup"><span data-stu-id="9fca1-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="9fca1-162">Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может перестать работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="9fca1-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="9fca1-163">В этом случае мы рекомендуем создать новую учетную запись ресурса для лицензии виртуального пользователя и удалить неотвеяжаемую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="9fca1-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="9fca1-164">Skype Для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="9fca1-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="9fca1-165">Если учетные записи ресурсов, Skype на сервере Skype 2019, которые можно использовать с [](/SkypeforBusiness/hybrid/plan-call-queue) очередями облачных вызовов и автозавершниками, см. статью Планирование очередей вызовов в облаке или Планирование автозавершников в облаке. [](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="9fca1-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="9fca1-166">Гибридные реализации (числа, которые находятся на основе прямой маршрутизации) настраиваются с помощью нового [csHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) на локальном сервере Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9fca1-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="9fca1-167">При создании экземпляров приложений вам нужны такие ИД:</span><span class="sxs-lookup"><span data-stu-id="9fca1-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="9fca1-168">**Автоотчет:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="9fca1-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="9fca1-169">**Очередь вызовов:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="9fca1-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="9fca1-170">Если вы хотите, чтобы пользователи Skype for Business Server 2019 могли искать в очереди вызовов или автоотводе, создайте учетные записи ресурсов на сервере Skype для бизнеса Server 2019, так как учетные записи ресурсов в Интернете не синхронизируются с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9fca1-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="9fca1-171">Когда записи SRV DNS для sipfederationtls разрешались в Skype для бизнеса Server 2019 г., то учетные записи ресурсов необходимо создавать на сервере Skype Для бизнеса Server 2019 с помощью оболочки управления SfB и синхронизировать с Azure AD. </span><span class="sxs-lookup"><span data-stu-id="9fca1-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="9fca1-172">Для реализации, гибридной с Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="9fca1-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="9fca1-173">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="9fca1-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="9fca1-174">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="9fca1-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="9fca1-175">Настройка настраиваемых учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="9fca1-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="9fca1-176">Удаление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="9fca1-176">Delete a resource account</span></span>

<span data-ttu-id="9fca1-177">Перед удалением убедитесь, что номер телефона не удален из учетной записи ресурса, чтобы номер службы не зависал в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="9fca1-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="9fca1-178">После этого вы можете удалить учетную запись ресурса в центре администрирования Microsoft 365 на вкладке Пользователи.</span><span class="sxs-lookup"><span data-stu-id="9fca1-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="9fca1-179">Чтобы отсоединять прямой маршрутный номер телефона от учетной записи ресурса, используйте следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9fca1-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```