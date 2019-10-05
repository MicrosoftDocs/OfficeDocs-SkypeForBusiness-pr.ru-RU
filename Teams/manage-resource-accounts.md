---
title: Управление учетными записями ресурсов в Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Сведения об управлении учетными записями ресурсов в Microsoft Teams
ms.openlocfilehash: 022163de7c3674fa0123927bad09a389514cc107
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401852"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="96080-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96080-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="96080-104">Учетная запись ресурса также известна как *отключенный объект пользователя* в Azure AD, и его можно использовать для общего представления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="96080-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="96080-105">В Exchange она может использоваться для представления конференц-залов, например, для предоставления им номера телефона.</span><span class="sxs-lookup"><span data-stu-id="96080-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="96080-106">Учетная запись ресурса может быть размещена в Microsoft 365 или в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="96080-106">A resource account can be homed in Microsoft 365 or on Skype for Business Server 2019.</span></span>

<span data-ttu-id="96080-107">В Microsoft Teams или Skype для бизнеса Online каждая очередь звонков или автосекретарь телефонной системы должна иметь хотя бы одну связанную учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="96080-108">Требуется ли для учетной записи ресурса назначенный телефонный номер, будет зависеть от предполагаемого использования соответствующей очереди звонков или автосекретаря, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="96080-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="96080-109">Кроме того, перед назначением номера телефона для учетной записи ресурса вы можете обратиться к статьям очереди звонков и с помощью автосекретарей, связанных в нижней части этой статьи.</span><span class="sxs-lookup"><span data-stu-id="96080-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96080-110">Телефонный номер не назначается для автосекретаря или очереди звонков, а не для учетной записи ресурса, связанной с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-110">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

![Пример учетных записей ресурсов и лицензий пользователей](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="96080-112">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="96080-112">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="96080-113">Учетные записи ресурсов, размещенные в Skype для бизнеса Server 2019, приведены в разделе [Настройка учетных записей ресурсов](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="96080-113">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="96080-114">Обзор</span><span class="sxs-lookup"><span data-stu-id="96080-114">Overview</span></span>

<span data-ttu-id="96080-115">Если в вашей организации уже используется по крайней мере одна лицензия на телефонную систему, вы можете назначить номер телефона в очередь звонков телефонной системы. процесс:</span><span class="sxs-lookup"><span data-stu-id="96080-115">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="96080-116">Получить номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="96080-116">Obtain a service number.</span></span>
2. <span data-ttu-id="96080-117">Получите бесплатную [лицензию на виртуальную](teams-add-on-licensing/virtual-user.md) или платную телефонную систему для использования с учетной записью ресурса или лицензией на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="96080-117">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="96080-118">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-118">Create the resource account.</span></span> <span data-ttu-id="96080-119">Для связи между автосекретарем и очередью звонков требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-119">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="96080-120">Назначьте телефонную систему или лицензию виртуальных пользователей для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-120">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="96080-121">Назначьте номер телефона для учетной записи ресурса, на которую вы только что назначили лицензии.</span><span class="sxs-lookup"><span data-stu-id="96080-121">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="96080-122">Создание очереди звонков телефонной системы или автосекретаря</span><span class="sxs-lookup"><span data-stu-id="96080-122">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="96080-123">Свяжите учетную запись ресурса с очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="96080-123">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="96080-124">Если автосекретарь или очередь звонков вложены в автосекретарь верхнего уровня, соответствующая учетная запись ресурса должна иметь только номер телефона, если вы хотите добавить несколько точек ввода в структуру автосекретарей и очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-124">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="96080-125">Для переадресации звонков между абонентами в вашей организации, которые подключены к сети, у них должна быть лицензия на **телефонную систему** и включена поддержка корпоративной голосовой связи или планы звонков по Office 365.</span><span class="sxs-lookup"><span data-stu-id="96080-125">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="96080-126">Ознакомьтесь с разделами [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="96080-126">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="96080-127">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96080-127">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="96080-128">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="96080-128">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="96080-129">Чтобы избежать проблем с учетной записью ресурса, выполните указанные ниже действия в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="96080-129">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="96080-130">Если очередь звонков телефонной системы или автосекретарь, которые вы создаете, будут вложены и вам не понадобится номер телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="96080-130">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="96080-131">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="96080-131">Create the resource account</span></span>
2. <span data-ttu-id="96080-132">Создание очереди звонков телефонной системы или автосекретаря</span><span class="sxs-lookup"><span data-stu-id="96080-132">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="96080-133">Связывание учетной записи ресурса с очередью звонков телефонной системы или автосекретарем</span><span class="sxs-lookup"><span data-stu-id="96080-133">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="96080-134">Создание учетной записи ресурса с использованием номера телефона</span><span class="sxs-lookup"><span data-stu-id="96080-134">Create a resource account with a phone number</span></span>

<span data-ttu-id="96080-135"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="96080-135"></span></span>

> [!IMPORTANT]
> <span data-ttu-id="96080-136">Телефонный номер не назначается для автосекретаря или очереди звонков, а не для учетной записи ресурса, связанной с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-136">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="96080-137">Для автосекретаря или очереди звонков на верхний уровень требуется связать номер телефона с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="96080-137">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="96080-138">Для создания учетной записи ресурса, использующей номер телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="96080-138">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="96080-139">Получайте или получайте платный или бесплатный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="96080-139">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="96080-140">Номер не может быть назначен другим услугам голосовой почты или учетным записям ресурсов.</span><span class="sxs-lookup"><span data-stu-id="96080-140">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="96080-141">Перед тем как назначить номер телефона учетной записи ресурса, вам нужно получить или перенести на него номера бесплатных или платных услуг.</span><span class="sxs-lookup"><span data-stu-id="96080-141">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="96080-142">После получения платных и > **бесплатных телефонных номеров** > в **центре администрирования Microsoft Teams**они отображаются в виде**номеров телефонов**, а **тип номера** будет указан в **списке бесплатный.**</span><span class="sxs-lookup"><span data-stu-id="96080-142">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="96080-143">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md) или перенесите существующий номер Услуги в разделе [Перенос номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="96080-143">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="96080-144">Если вы назначаете номер телефона для учетной записи ресурса, вы можете использовать лицензию на виртуальную систему, доступную для бесплатной подсистемы оплаты.</span><span class="sxs-lookup"><span data-stu-id="96080-144">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="96080-145">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне Организации, а также позволяет создавать автосекретаря и возможности очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-145">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="96080-146">Получите лицензию виртуальных пользователей для телефонной системы или обычную лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="96080-146">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="96080-147">Чтобы получить лицензию на виртуальную пользователей, начиная с центра администрирования Microsoft 365, перейдите в раздел**подписки на надстройки** **служб** >  **выставления счетов** > и прокрутите список до конца, вы увидите лицензию "телефонная система — виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="96080-147">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="96080-148">Нажмите кнопку **Купить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="96080-148">Select **Buy now**.</span></span> <span data-ttu-id="96080-149">У тебя нулевая стоимость, но для получения лицензии вам по-прежнему нужно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="96080-149">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="96080-150">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-150">Create a new resource account.</span></span> <span data-ttu-id="96080-151">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="96080-151">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="96080-152">Назначьте для учетной записи ресурсов телефонную [лицензию на виртуальную систему пользователя](teams-add-on-licensing/virtual-user.md) или лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="96080-152">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="96080-153">В разделе [Назначение лицензий Microsoft Teams](assign-teams-licenses.md) и [Назначение лицензий одному пользователю](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="96080-153">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="96080-154">Назначьте номер Услуги учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="96080-155">Ознакомьтесь [с Разназначением и отменой назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="96080-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="96080-156">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="96080-156">Set up one of the following:</span></span>
   - [<span data-ttu-id="96080-157">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="96080-157">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="96080-158">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="96080-158">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="96080-159">Свяжите учетную запись ресурса с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-159">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="96080-160">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="96080-160">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="96080-161">При создании автосекретаря с учетной записью ресурса лицензии применяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="96080-161">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="96080-162">Создание учетной записи ресурса без номера телефона</span><span class="sxs-lookup"><span data-stu-id="96080-162">Create a resource account without a phone number</span></span>

<span data-ttu-id="96080-163">Для вложенного автосекретаря или очереди звонков потребуется учетная запись ресурса, но во многих случаях для соответствующей учетной записи ресурса номер телефона не требуется, а лицензирование требуется для поддержки телефонного номера.</span><span class="sxs-lookup"><span data-stu-id="96080-163">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="96080-164">Для создания учетной записи ресурса, не требующей номера телефона, необходимо выполнить следующие действия в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="96080-164">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="96080-165">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-165">Create a new resource account.</span></span> <span data-ttu-id="96080-166">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="96080-166">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="96080-167">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="96080-167">Set up one of the following:</span></span>
   - [<span data-ttu-id="96080-168">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="96080-168">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="96080-169">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="96080-169">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="96080-170">Назначение учетной записи ресурса очереди звонков или автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="96080-170">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="96080-171">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="96080-171">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="96080-172">Создание учетной записи ресурса в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96080-172">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="96080-173">После того как вы приобрели лицензию на телефонную систему, с помощью центра администрирования Microsoft Teams перейдите в раздел > **учетные записи ресурсов**" **Параметры организации**".</span><span class="sxs-lookup"><span data-stu-id="96080-173">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Снимок экрана: страница "учетные записи ресурсов"](media/r-a-master.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="96080-176">Чтобы создать новую учетную запись ресурса, нажмите кнопку **+ создать учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="96080-176">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="96080-177">Во всплывающем окне введите отображаемое имя и имя пользователя для учетной записи ресурса (доменное имя должно быть автоматически заполнено) и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96080-177">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Снимок экрана: параметры новой учетной записи ресурса](media/res-acct.png)

<span data-ttu-id="96080-179">Затем примените лицензию к учетной записи ресурса в центре администрирования Office 365, как описано в разделе [Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="96080-179">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="96080-180">Изменение имени учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="96080-180">Edit resource account name</span></span>

<span data-ttu-id="96080-181">![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png) вы можете изменить отображаемое имя учетной записи ресурса с помощью команды " **изменить** ".</span><span class="sxs-lookup"><span data-stu-id="96080-181">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="96080-182">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="96080-182">Click **Save** when you are done.</span></span>
<span data-ttu-id="96080-183">![Снимок экрана: параметр "изменить учетную запись ресурса"](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="96080-183">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

<a name="phonenumber"></a>
### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="96080-184">Назначение и отмена назначения номеров телефонов и служб</span><span class="sxs-lookup"><span data-stu-id="96080-184">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="96080-185">![Значок с номером 3, указывающий на выноску на предыдущем снимке экрана](media/sfbcallout3.png) после создания учетной записи ресурса и назначения лицензии, вы можете выбрать команду **назначить или отменить назначение** для присвоения номера услуги учетной записи ресурса или назначить ресурс. Учетная запись для автосекретаря или уже существующей очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="96080-185">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="96080-186">Назначение прямого номера маршрутизации может выполняться только с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="96080-186">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="96080-187">Если вы хотите создать очередь звонков или автосекретарь, вы можете связать ее с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-187">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="96080-188">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="96080-188">Click **Save** when you are done.</span></span>

<span data-ttu-id="96080-189">Чтобы назначить учетной записи ресурсов прямой маршрут или гибридный номер, необходимо ознакомиться с разделом ниже.</span><span class="sxs-lookup"><span data-stu-id="96080-189">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96080-190">Если у вашей учетной записи ресурса нет действующей лицензии, внутренняя проверка вызовет сбой при попытке назначить номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="96080-190">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="96080-191">Вы не сможете назначить номер или связать учетную запись ресурса с очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="96080-191">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

![Снимок экрана: параметры назначения и отмены](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="96080-193">Изменение существующей учетной записи ресурса для использования лицензии виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="96080-193">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="96080-194">Если вы решили переключить лицензии на существующую учетную запись ресурса из лицензии на телефонную систему в лицензию виртуального пользователя, вам потребуется приобрести бесплатную лицензию на виртуальные пользователи, а затем выполнить связанные действия в центре администрирования Microsoft 365, чтобы [переместить пользователей на другую подписку](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="96080-194">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="96080-195">Всегда удаляйте полную лицензию на телефонную систему и назначьте лицензию на виртуальную пользователей в том же действии лицензирования.</span><span class="sxs-lookup"><span data-stu-id="96080-195">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="96080-196">Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="96080-196">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="96080-197">В этом случае мы рекомендуем создать новую учетную запись ресурса для лицензии виртуального пользователя и удалить неработающие учетные записи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="96080-197">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="96080-198">Создание учетной записи ресурса в PowerShell</span><span class="sxs-lookup"><span data-stu-id="96080-198">Create a resource account in Powershell</span></span>

<span data-ttu-id="96080-199">В зависимости от того, где находится ваша учетная запись в сети или в Skype для бизнеса Server 2019, вам потребуется подключиться к соответствующему приглашению PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="96080-199">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="96080-200">Ниже приведены примеры командлетов PowerShell, демонстрирующие создание учетной записи ресурсов, размещенной в Интернете с помощью [New-ксонлинеаппликатионинстанце](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="96080-200">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="96080-201">Для учетных записей ресурсов, размещенных в Skype для бизнеса Server 2019, которые можно использовать с очередями облачных вызовов и облачными автосекретарями, ознакомьтесь с раздел [Настройка очередей](/skypeforbusiness/hybrid/configure-call-queue.md) облачных вызовов или [Настройка автосекретарей в облаке](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="96080-201">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="96080-202">Гибридные реализации (номера, расположенные в прямом маршруте) будут использовать [New-кшибридаппликатионендпоинт](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="96080-202">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="96080-203">При создании экземпляров приложения необходимо использовать идентификатор приложения:</span><span class="sxs-lookup"><span data-stu-id="96080-203">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="96080-204">**Автоматический секретарь:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="96080-204">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="96080-205">**Очередь звонков:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="96080-205">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="96080-206">Если вы хотите, чтобы очередь звонков или автосекретарь были доступны для поиска пользователям Skype для бизнеса Server 2019, необходимо создать учетные записи ресурсов в Skype для Business Server 2019, так как учетные записи Интернет-ресурсов не синхронизируются с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96080-206">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="96080-207">Когда DNS SRV-записи для сипфедератионтлс разрешаются в Skype для бизнеса Server 2019, учетные записи ресурсов **должны** быть созданы в Skype для бизнеса Server 2019 с помощью оболочки управления SfB и синхронизированы с веб-службой Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96080-207">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="96080-208">Чтобы создать учетную запись ресурса Online для использования с автосекретарем, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="96080-208">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="96080-209">Вы не сможете использовать учетную запись ресурса, пока вы не примените к ней лицензию.</span><span class="sxs-lookup"><span data-stu-id="96080-209">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="96080-210">Инструкции по применению лицензии к учетной записи в центре администрирования Office 365 можно найти [в разделе Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , а также [Назначение лицензий Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="96080-210">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="96080-211">Необязательно После того как правильная лицензия будет применена к учетной записи ресурсов, вы можете назначить номер телефона для учетной записи ресурсов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="96080-211">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="96080-212">Не все учетные записи ресурсов требуют номера телефона.</span><span class="sxs-lookup"><span data-stu-id="96080-212">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="96080-213">Если вы не применяли лицензию для учетной записи ресурса, назначение номера телефона завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="96080-213">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="96080-214">Для получения дополнительных сведений об этой команде ознакомьтесь с командой [Set-ксонлиневоицеаппликатионинстанце](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="96080-214">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96080-215">С помощью центра администрирования Microsoft Teams проще всего настроить номер телефона в Интернете, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="96080-215">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="96080-216">Чтобы назначить номер телефона для прямой маршрутизации учетной записи ресурса (в Microsoft Teams или Skype для бизнеса Server 2019), используйте следующий командлет для Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="96080-216">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="96080-217">Управление параметрами учетной записи ресурсов в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96080-217">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="96080-218">Чтобы настроить учетные записи ресурсов в центре администрирования Microsoft Teams, перейдите в раздел > **учетные записи ресурсов**в **масштабах Организации**, выберите учетную запись ресурса, параметры которой нужно изменить, а затем нажмите кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="96080-218">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="96080-219">в окне **изменение учетной записи ресурса** вы сможете изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="96080-219">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="96080-220">**Отображаемое имя** учетной записи</span><span class="sxs-lookup"><span data-stu-id="96080-220">**Display name** for the account</span></span>
- <span data-ttu-id="96080-221">Очередь звонков или автосекретарей, использующая учетную запись</span><span class="sxs-lookup"><span data-stu-id="96080-221">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="96080-222">Номер телефона, назначенный учетной записи</span><span class="sxs-lookup"><span data-stu-id="96080-222">Phone number assigned to the account</span></span>

<span data-ttu-id="96080-223">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96080-223">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="96080-224">Удаление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="96080-224">Delete a resource account</span></span>

<span data-ttu-id="96080-225">Убедитесь, что у вас есть связь с номером телефона для учетной записи ресурса перед ее удалением, чтобы не зависнуть номер службы в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="96080-225">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="96080-226">Это можно сделать, используя следующие unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="96080-226">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="96080-227">После этого вы можете удалить учетную запись ресурса на портале администрирования Office 365 на вкладке Пользователи.</span><span class="sxs-lookup"><span data-stu-id="96080-227">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="96080-228">Чтобы отключить прямую маршрутизацию на номер телефона от учетной записи ресурса, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="96080-228">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="96080-229">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="96080-229">Troubleshooting</span></span>

<span data-ttu-id="96080-230">На случай, если вы не видите номер телефона, назначенный учетной записи ресурса в центре администрирования Teams, и вы не можете назначить этот номер, пожалуйста, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="96080-230">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="96080-231">Если атрибут "Отдел" отображает конечную точку приложения Skype для бизнеса, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="96080-231">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="96080-232">После запуска кмлдет обновите веб-страницу центра администрирования Teams, и вы сможете правильно назначить номер.</span><span class="sxs-lookup"><span data-stu-id="96080-232">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="96080-233">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="96080-233">Related Information</span></span>

<span data-ttu-id="96080-234">Для внедрения, гибридных с помощью Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="96080-234">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="96080-235">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="96080-235">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="96080-236">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="96080-236">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="96080-237">Настройка локальной учетной записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="96080-237">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="96080-238">Для реализаций в Teams или Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="96080-238">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="96080-239">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="96080-239">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="96080-240">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="96080-240">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="96080-241">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="96080-241">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="96080-242">Создание облачной очереди звонков</span><span class="sxs-lookup"><span data-stu-id="96080-242">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="96080-243">New-Кшибридаппликатионендпоинт</span><span class="sxs-lookup"><span data-stu-id="96080-243">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="96080-244">New-Ксонлинеаппликатионинстанце</span><span class="sxs-lookup"><span data-stu-id="96080-244">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="96080-245">Телефонная система — лицензия виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="96080-245">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
