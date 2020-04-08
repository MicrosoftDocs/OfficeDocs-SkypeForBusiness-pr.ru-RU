---
title: Управление учетными записями ресурсов в Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Сведения об управлении учетными записями ресурсов в Microsoft Teams
ms.openlocfilehash: 5d1558f027226845842923140f9f9e64c5f4eae1
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190879"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="2f93f-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f93f-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="2f93f-104">Учетная запись ресурса также известна как *отключенный объект пользователя* в Azure AD, и его можно использовать для общего представления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="2f93f-105">В Exchange она может использоваться для представления конференц-залов, например, для предоставления им номера телефона.</span><span class="sxs-lookup"><span data-stu-id="2f93f-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="2f93f-106">Учетная запись ресурса может быть размещена в Microsoft 365 или локально с помощью Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2f93f-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="2f93f-107">В Microsoft Teams или Skype для бизнеса Online каждая очередь звонков или автосекретарь телефонной системы должна иметь хотя бы одну связанную учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="2f93f-108">Требуется ли для учетной записи ресурса назначенный телефонный номер, будет зависеть от предполагаемого использования соответствующей очереди звонков или автосекретаря, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="2f93f-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="2f93f-109">Кроме того, перед назначением номера телефона для учетной записи ресурса вы можете обратиться к статьям очереди звонков и с помощью автосекретарей, связанных в нижней части этой статьи.</span><span class="sxs-lookup"><span data-stu-id="2f93f-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![Пример учетных записей ресурсов и лицензий пользователей](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="2f93f-111">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2f93f-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="2f93f-112">Учетные записи ресурсов, размещенные в Skype для бизнеса Server 2019, приведены в разделе [Настройка учетных записей ресурсов](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="2f93f-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="2f93f-113">Обзор</span><span class="sxs-lookup"><span data-stu-id="2f93f-113">Overview</span></span>

<span data-ttu-id="2f93f-114">Если в вашей организации уже используется по крайней мере одна лицензия на телефонную систему, вы можете назначить номер телефона в очередь звонков телефонной системы. процесс:</span><span class="sxs-lookup"><span data-stu-id="2f93f-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="2f93f-115">Получить номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="2f93f-115">Obtain a service number.</span></span>
2. <span data-ttu-id="2f93f-116">Получите бесплатную [лицензию на виртуальную](teams-add-on-licensing/virtual-user.md) или платную телефонную систему для использования с учетной записью ресурса или лицензией на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="2f93f-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="2f93f-117">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-117">Create the resource account.</span></span> <span data-ttu-id="2f93f-118">Для связи между автосекретарем и очередью звонков требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="2f93f-119">Назначьте телефонную систему или лицензию виртуальных пользователей для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="2f93f-120">Назначьте номер телефона для учетной записи ресурса, на которую вы только что назначили лицензии.</span><span class="sxs-lookup"><span data-stu-id="2f93f-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="2f93f-121">Создание очереди звонков телефонной системы или автосекретаря</span><span class="sxs-lookup"><span data-stu-id="2f93f-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="2f93f-122">Свяжите учетную запись ресурса с очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="2f93f-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="2f93f-123">Если автосекретарь или очередь звонков вложены в автосекретарь верхнего уровня, соответствующая учетная запись ресурса должна иметь только номер телефона, если вы хотите добавить несколько точек ввода в структуру автосекретарей и очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="2f93f-124">Для переадресации звонков между абонентами в вашей организации, которые подключены к сети, у них должна быть лицензия на **телефонную систему** и включена поддержка корпоративной голосовой связи или планы звонков по Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f93f-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="2f93f-125">Ознакомьтесь с разделами [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="2f93f-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="2f93f-126">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f93f-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="2f93f-127">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="2f93f-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="2f93f-128">Чтобы избежать проблем с учетной записью ресурса, выполните указанные ниже действия в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="2f93f-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="2f93f-129">Если очередь звонков телефонной системы или автосекретарь, которые вы создаете, будут вложены и вам не понадобится номер телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="2f93f-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="2f93f-130">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="2f93f-130">Create the resource account</span></span>
2. <span data-ttu-id="2f93f-131">Создание очереди звонков телефонной системы или автосекретаря</span><span class="sxs-lookup"><span data-stu-id="2f93f-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="2f93f-132">Связывание учетной записи ресурса с очередью звонков телефонной системы или автосекретарем</span><span class="sxs-lookup"><span data-stu-id="2f93f-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="2f93f-133">Создание учетной записи ресурса с использованием номера телефона</span><span class="sxs-lookup"><span data-stu-id="2f93f-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="2f93f-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="2f93f-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f93f-135">Телефонный номер не назначается для автосекретаря или очереди звонков, а не для учетной записи ресурса, связанной с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="2f93f-136">Для автосекретаря или очереди звонков на верхний уровень требуется связать номер телефона с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="2f93f-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="2f93f-137">Для создания учетной записи ресурса, использующей номер телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="2f93f-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="2f93f-138">Получайте или получайте платный или бесплатный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="2f93f-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="2f93f-139">Номер не может быть назначен другим услугам голосовой почты или учетным записям ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="2f93f-140">Перед тем как назначить номер телефона учетной записи ресурса, вам нужно получить или перенести на него номера бесплатных или платных услуг.</span><span class="sxs-lookup"><span data-stu-id="2f93f-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="2f93f-141">После получения платных и > **бесплатных телефонных номеров** > в **центре администрирования Microsoft Teams**они отображаются в виде**номеров телефонов**, а **тип номера** будет указан в **списке бесплатный.**</span><span class="sxs-lookup"><span data-stu-id="2f93f-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="2f93f-142">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md) или перенесите существующий номер Услуги в разделе [Перенос номеров телефонов в Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2f93f-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="2f93f-143">Если вы назначаете номер телефона для учетной записи ресурса, вы можете использовать лицензию на виртуальную систему, доступную для бесплатной подсистемы оплаты.</span><span class="sxs-lookup"><span data-stu-id="2f93f-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="2f93f-144">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне Организации, а также позволяет создавать автосекретаря и возможности очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="2f93f-145">Получите лицензию виртуальных пользователей для телефонной системы или обычную лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="2f93f-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="2f93f-146">Чтобы получить лицензию на виртуальную пользователей, начиная с центра администрирования Microsoft 365, перейдите в раздел**подписки на надстройки** **служб** >  **выставления счетов** > и прокрутите список до конца, вы увидите лицензию "телефонная система — виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="2f93f-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="2f93f-147">Нажмите кнопку **Купить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="2f93f-147">Select **Buy now**.</span></span> <span data-ttu-id="2f93f-148">У тебя нулевая стоимость, но для получения лицензии вам по-прежнему нужно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2f93f-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="2f93f-149">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-149">Create a new resource account.</span></span> <span data-ttu-id="2f93f-150">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f93f-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="2f93f-151">Назначьте для учетной записи ресурсов телефонную [лицензию на виртуальную систему пользователя](teams-add-on-licensing/virtual-user.md) или лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="2f93f-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="2f93f-152">В разделе [Назначение лицензий Microsoft Teams](assign-teams-licenses.md) и [Назначение лицензий одному пользователю](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="2f93f-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="2f93f-153">Назначьте номер Услуги учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="2f93f-154">Ознакомьтесь [с Разназначением и отменой назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="2f93f-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="2f93f-155">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="2f93f-156">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="2f93f-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="2f93f-157">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="2f93f-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="2f93f-158">Свяжите учетную запись ресурса с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="2f93f-159">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="2f93f-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="2f93f-160">При создании автосекретаря с учетной записью ресурса лицензии применяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="2f93f-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="2f93f-161">Создание учетной записи ресурса без номера телефона</span><span class="sxs-lookup"><span data-stu-id="2f93f-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="2f93f-162">Для вложенного автосекретаря или очереди звонков потребуется учетная запись ресурса, но во многих случаях для соответствующей учетной записи ресурса номер телефона не требуется, а лицензирование требуется для поддержки телефонного номера.</span><span class="sxs-lookup"><span data-stu-id="2f93f-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="2f93f-163">Для создания учетной записи ресурса, не требующей номера телефона, необходимо выполнить следующие действия в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="2f93f-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="2f93f-164">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-164">Create a new resource account.</span></span> <span data-ttu-id="2f93f-165">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="2f93f-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="2f93f-166">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="2f93f-167">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="2f93f-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="2f93f-168">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="2f93f-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="2f93f-169">Назначение учетной записи ресурса очереди звонков или автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="2f93f-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="2f93f-170">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="2f93f-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="2f93f-171">Создание учетной записи ресурса в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f93f-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="2f93f-172">После того как вы приобрели лицензию на телефонную систему, с помощью центра администрирования Microsoft Teams перейдите в раздел > **учетные записи ресурсов**" **Параметры организации**".</span><span class="sxs-lookup"><span data-stu-id="2f93f-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Снимок экрана: страница "учетные записи ресурсов"](media/r-a-master.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/teamscallout1.png)

<span data-ttu-id="2f93f-175">Чтобы создать новую учетную запись ресурса, нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2f93f-175">To create a new resource account click **+ Add**.</span></span> <span data-ttu-id="2f93f-176">Во всплывающем окне введите **Отображаемое имя**, имя **пользователя** (доменное имя должно быть автоматически) и **тип учетной записи ресурса** для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-176">In the pop-up, fill out the **Display name**, **Username** (the domain name should populate automatically), and **Resource account type**  for the resource account.</span></span> <span data-ttu-id="2f93f-177">Тип учетной записи ресурса может быть **автосекретарем** или **очередью звонков** в зависимости от приложения, которое вы хотите связать с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-177">Resource account type can be either **Auto attendant** or **Call queue** depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="2f93f-178">Когда все будет готово, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2f93f-178">When you are ready,  click **Save**.</span></span>

![Снимок экрана: параметры новой учетной записи ресурса](media/res-acct.png)

<span data-ttu-id="2f93f-180">Затем примените лицензию к учетной записи ресурса в центре администрирования Office 365, как описано в разделе [Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="2f93f-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="2f93f-181">Изменение учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="2f93f-181">Edit resource account</span></span> 

<span data-ttu-id="2f93f-182">![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/teamscallout2.png) вы можете изменить **Отображаемое имя** учетной записи ресурса и тип **учетной записи ресурса** с помощью команды **изменить** .</span><span class="sxs-lookup"><span data-stu-id="2f93f-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="2f93f-183">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="2f93f-183">Click **Save** when you are done.</span></span>

![Снимок экрана: параметр "изменить учетную запись ресурса"](media/r-a-edit.png)

<span data-ttu-id="2f93f-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="2f93f-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="2f93f-186">Назначение и отмена назначения номеров телефонов и служб</span><span class="sxs-lookup"><span data-stu-id="2f93f-186">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="2f93f-187">![Значок с номером 3, указывающий на выноску на предыдущем снимке экрана](media/teamscallout3.png) после создания учетной записи ресурса и назначения лицензии, вы можете выбрать команду **назначить или отменить назначение** для присвоения номера услуги учетной записи ресурса, задать тип номера телефона или назначить учетной записи ресурса конкретный автоматический секретарь или уже существующую очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="2f93f-188">Назначение прямого номера маршрутизации может выполняться только с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="2f93f-189">Если вы еще не создали очередь звонков или автосекретарь, вы будете присоединиться к учетной записи ресурса, оставив это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="2f93f-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="2f93f-190">Вы можете создать связь с учетной записью ресурса при ее создании.</span><span class="sxs-lookup"><span data-stu-id="2f93f-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="2f93f-191">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="2f93f-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="2f93f-192">Параметры для **типа номера телефона** :</span><span class="sxs-lookup"><span data-stu-id="2f93f-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="2f93f-193">Нет</span><span class="sxs-lookup"><span data-stu-id="2f93f-193">None</span></span>
- <span data-ttu-id="2f93f-194">В Интернете</span><span class="sxs-lookup"><span data-stu-id="2f93f-194">Online</span></span>
- <span data-ttu-id="2f93f-195">Бесплатный</span><span class="sxs-lookup"><span data-stu-id="2f93f-195">Toll-free</span></span>
- <span data-ttu-id="2f93f-196">Локальная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="2f93f-196">On-premises</span></span>

![Снимок экрана: параметры назначения и отмены](media/r-a-assign.png)

<span data-ttu-id="2f93f-198">Чтобы назначить учетной записи ресурсов прямой маршрут или гибридный номер, необходимо ознакомиться с разделом ниже.</span><span class="sxs-lookup"><span data-stu-id="2f93f-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f93f-199">Если у вашей учетной записи ресурса нет действующей лицензии, внутренняя проверка вызовет сбой при попытке назначить номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f93f-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="2f93f-200">Вы не сможете назначить номер или связать учетную запись ресурса с очередью звонков или автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="2f93f-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f93f-201">Телефонный номер не назначается для автосекретаря или очереди звонков, а не для учетной записи ресурса, связанной с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="2f93f-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="2f93f-202">Изменение существующей учетной записи ресурса для использования лицензии виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="2f93f-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="2f93f-203">Если вы решили переключить лицензии на существующую учетную запись ресурса из лицензии на телефонную систему в лицензию виртуального пользователя, вам потребуется приобрести бесплатную лицензию на виртуальные пользователи, а затем выполнить связанные действия в центре администрирования Microsoft 365, чтобы [переместить пользователей в другую подписку](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="2f93f-203">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="2f93f-204">Всегда удаляйте полную лицензию на телефонную систему и назначьте лицензию на виртуальную пользователей в том же действии лицензирования.</span><span class="sxs-lookup"><span data-stu-id="2f93f-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="2f93f-205">Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="2f93f-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="2f93f-206">В этом случае мы рекомендуем создать новую учетную запись ресурса для лицензии виртуального пользователя и удалить неработающие учетные записи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2f93f-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="2f93f-207">Создание учетной записи ресурса в PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f93f-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="2f93f-208">В зависимости от того, где находится ваша учетная запись в сети или в Skype для бизнеса Server 2019, вам потребуется подключиться к соответствующему приглашению PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="2f93f-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="2f93f-209">Ниже приведены примеры командлетов PowerShell, демонстрирующие создание учетной записи ресурсов, размещенной в Интернете с помощью [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f93f-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="2f93f-210">Для учетных записей ресурсов, размещенных в Skype для бизнеса Server 2019, которые можно использовать с очередями облачных вызовов и облачными автосекретарями, ознакомьтесь со статьей [планирование очередей облачных вызовов](/SkypeforBusiness/hybrid/plan-call-queue) и [планирование автосекретарей облака](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="2f93f-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="2f93f-211">Гибридные реализации (номера, расположенные в прямом маршруте) настраиваются с помощью командлета [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) на локальном сервере 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f93f-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="2f93f-212">При создании экземпляров приложения необходимо использовать идентификатор приложения:</span><span class="sxs-lookup"><span data-stu-id="2f93f-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="2f93f-213">**Автоматический секретарь:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="2f93f-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="2f93f-214">**Очередь звонков:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="2f93f-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="2f93f-215">Если вы хотите, чтобы очередь звонков или автосекретарь были доступны для поиска пользователям Skype для бизнеса Server 2019, необходимо создать учетные записи ресурсов в Skype для Business Server 2019, так как учетные записи Интернет-ресурсов не синхронизируются с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f93f-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="2f93f-216">Когда DNS SRV-записи для sipfederationtls разрешаются в Skype для бизнеса Server 2019, учетные записи ресурсов **должны** быть созданы в Skype для бизнеса Server 2019 с помощью оболочки управления SfB и синхронизированы с веб-службой Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f93f-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="2f93f-217">Чтобы создать учетную запись ресурса Online для использования с автосекретарем, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2f93f-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="2f93f-218">Вы не сможете использовать учетную запись ресурса, пока вы не примените к ней лицензию.</span><span class="sxs-lookup"><span data-stu-id="2f93f-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="2f93f-219">Инструкции по применению лицензии к учетной записи в центре администрирования Office 365 можно найти [в разделе Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , а также [Назначение лицензий Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="2f93f-219">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="2f93f-220">Необязательно После того как правильная лицензия будет применена к учетной записи ресурсов, вы можете назначить номер телефона для учетной записи ресурсов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2f93f-220">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="2f93f-221">Не все учетные записи ресурсов требуют номера телефона.</span><span class="sxs-lookup"><span data-stu-id="2f93f-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="2f93f-222">Если вы не применяли лицензию для учетной записи ресурса, назначение номера телефона завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="2f93f-222">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="2f93f-223">Для получения дополнительных сведений об этой команде ознакомьтесь с командой [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2f93f-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2f93f-224">С помощью центра администрирования Microsoft Teams проще всего настроить номер телефона в Интернете, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="2f93f-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="2f93f-225">Чтобы назначить номер телефона для прямой маршрутизации учетной записи ресурса (в Microsoft Teams или Skype для бизнеса Server 2019), используйте следующий командлет для Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2f93f-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="2f93f-226">Управление параметрами учетной записи ресурсов в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f93f-226">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="2f93f-227">Чтобы настроить учетные записи ресурсов в центре администрирования Microsoft Teams, перейдите в раздел > **учетные записи ресурсов**в **масштабах Организации**, выберите учетную запись ресурса, параметры которой нужно изменить, а затем нажмите кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="2f93f-227">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="2f93f-228">в окне **изменение учетной записи ресурса** вы сможете изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2f93f-228">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="2f93f-229">**Отображаемое имя** учетной записи</span><span class="sxs-lookup"><span data-stu-id="2f93f-229">**Display name** for the account</span></span>
- <span data-ttu-id="2f93f-230">Очередь звонков или автосекретарей, использующая учетную запись</span><span class="sxs-lookup"><span data-stu-id="2f93f-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="2f93f-231">Номер телефона, назначенный учетной записи</span><span class="sxs-lookup"><span data-stu-id="2f93f-231">Phone number assigned to the account</span></span>

<span data-ttu-id="2f93f-232">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2f93f-232">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="2f93f-233">Удаление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="2f93f-233">Delete a resource account</span></span>

<span data-ttu-id="2f93f-234">Убедитесь, что у вас есть связь с номером телефона для учетной записи ресурса перед ее удалением, чтобы не зависнуть номер службы в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="2f93f-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="2f93f-235">Это можно сделать, используя следующие unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="2f93f-235">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="2f93f-236">После этого вы можете удалить учетную запись ресурса на портале администрирования Office 365 на вкладке Пользователи.</span><span class="sxs-lookup"><span data-stu-id="2f93f-236">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="2f93f-237">Чтобы отключить прямую маршрутизацию на номер телефона от учетной записи ресурса, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2f93f-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="2f93f-238">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="2f93f-238">Troubleshooting</span></span>

<span data-ttu-id="2f93f-239">На случай, если вы не видите номер телефона, назначенный учетной записи ресурса в центре администрирования Teams, и вы не можете назначить этот номер, пожалуйста, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="2f93f-239">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="2f93f-240">Если атрибут "Отдел" отображает конечную точку приложения Skype для бизнеса, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2f93f-240">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="2f93f-241">После запуска cmldet обновите веб-страницу центра администрирования Teams, и вы сможете правильно назначить номер.</span><span class="sxs-lookup"><span data-stu-id="2f93f-241">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="2f93f-242">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2f93f-242">Related Information</span></span>

<span data-ttu-id="2f93f-243">Для внедрения, гибридных с помощью Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2f93f-243">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="2f93f-244">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="2f93f-244">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="2f93f-245">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="2f93f-245">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="2f93f-246">Настройка локальной учетной записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="2f93f-246">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="2f93f-247">Для реализаций в Teams или Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="2f93f-247">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="2f93f-248">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="2f93f-248">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="2f93f-249">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="2f93f-249">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="2f93f-250">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="2f93f-250">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="2f93f-251">Создание облачной очереди звонков</span><span class="sxs-lookup"><span data-stu-id="2f93f-251">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="2f93f-252">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="2f93f-252">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="2f93f-253">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="2f93f-253">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="2f93f-254">Телефонная система — лицензия виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="2f93f-254">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
