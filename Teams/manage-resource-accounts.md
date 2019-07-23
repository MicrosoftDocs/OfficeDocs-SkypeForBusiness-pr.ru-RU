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
ms.openlocfilehash: 1dd3fd8c7a9300b9c887cbc0c3cd3611b378d0c9
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821064"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="d45b7-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d45b7-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="d45b7-104">Учетная запись ресурса также известна как *отключенный объект пользователя* в Azure Active Directory, и его можно использовать для общего представления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-104">A resource account is also known as a *disabled user object* in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="d45b7-105">В Exchange она может использоваться для представления конференц-залов, например, для предоставления им номера телефона.</span><span class="sxs-lookup"><span data-stu-id="d45b7-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="d45b7-106">Учетная запись ресурса может быть размещена в Microsoft 365 или локально с помощью Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d45b7-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="d45b7-107">В Microsoft Teams или Skype для бизнеса Online для каждой очереди звонков телефонной системы или автосекретаря требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="d45b7-108">Требуется ли для учетной записи ресурса назначенный телефонный номер, будет зависеть от того, какое назначение использует соответствующая очередь звонков или автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="d45b7-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="d45b7-109">Перед назначением номера телефона для учетной записи ресурса ознакомьтесь со статьями очереди звонков и автосекретарей, связанных в нижней части этой статьи.</span><span class="sxs-lookup"><span data-stu-id="d45b7-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="d45b7-110">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d45b7-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="d45b7-111">Учетные записи ресурсов, размещенные в Skype для бизнеса Server 2019, приведены в разделе [Настройка учетных записей ресурсов](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="d45b7-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="d45b7-112">Обзор</span><span class="sxs-lookup"><span data-stu-id="d45b7-112">Overview</span></span>

<span data-ttu-id="d45b7-113">Предполагается, что ваша организация использует по крайней мере одну лицензию на телефонную систему, чтобы назначить службе телефонной системы номер телефона, вам нужно будет решить различные зависимости в следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="d45b7-113">Assuming that your organization is using at least one Phone System License, to assigning a Phone System service a phone number, you will need to address the various dependencies in the following sequence:</span></span>

1. <span data-ttu-id="d45b7-114">Получить номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="d45b7-114">Obtain a service number.</span></span>
2. <span data-ttu-id="d45b7-115">Получите [лицензию виртуального пользователя](teams-add-on-licensing/virtual-user.md) телефонной системы или обычную лицензию на телефонную систему для использования с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-115">Obtain a Phone System [Virtual user license](teams-add-on-licensing/virtual-user.md) or a regular Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="d45b7-116">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-116">Create the resource account.</span></span> <span data-ttu-id="d45b7-117">Для связи между автосекретарем и очередью звонков требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="d45b7-118">Назначьте телефонную систему или лицензию виртуального пользователя телефонной системы для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-118">Assign the Phone System or a Phone System Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="d45b7-119">Назначьте номер телефона для учетной записи ресурса, на которую вы только что назначили лицензии.</span><span class="sxs-lookup"><span data-stu-id="d45b7-119">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="d45b7-120">Создайте службу телефонной системы (очередь звонков или автосекретарь).</span><span class="sxs-lookup"><span data-stu-id="d45b7-120">Create a Phone System service (a call queue or auto attendant).</span></span>
7. <span data-ttu-id="d45b7-121">Свяжите учетную запись ресурса со службой.</span><span class="sxs-lookup"><span data-stu-id="d45b7-121">Link the resource account with a service.</span></span>

<span data-ttu-id="d45b7-122">Если автосекретарь или очередь звонков вложены в автосекретарь верхнего уровня, соответствующая учетная запись ресурса должна иметь только номер телефона, если вы хотите добавить несколько точек ввода в структуру автосекретарей и очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="d45b7-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="d45b7-123">Для переадресации звонков между абонентами в вашей организации, которые подключены к сети, у них должна быть лицензия на **телефонную систему** и включена поддержка корпоративной голосовой связи или планы звонков по Office 365.</span><span class="sxs-lookup"><span data-stu-id="d45b7-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="d45b7-124">Ознакомьтесь с разделами [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d45b7-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="d45b7-125">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d45b7-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d45b7-126">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d45b7-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="d45b7-127">Чтобы избежать проблем с учетной записью ресурса, выполните указанные ниже действия в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="d45b7-127">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="d45b7-128">Если служба телефонной системы, которую вы создаете, является вложенной и вам не понадобится номер телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="d45b7-128">If the Phone System service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="d45b7-129">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d45b7-129">Create the resource account</span></span>  
2. <span data-ttu-id="d45b7-130">Создание службы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="d45b7-130">Create a Phone System service</span></span>
3. <span data-ttu-id="d45b7-131">Связывание учетной записи ресурса с службой телефонной системы</span><span class="sxs-lookup"><span data-stu-id="d45b7-131">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="d45b7-132">Создание учетной записи ресурса с использованием номера телефона</span><span class="sxs-lookup"><span data-stu-id="d45b7-132">Create a resource account with a phone number</span></span>

<span data-ttu-id="d45b7-133">Для создания учетной записи ресурса, использующей номер телефона, необходимо выполнить указанные ниже действия в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="d45b7-133">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="d45b7-134">Получайте или получайте платный или бесплатный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="d45b7-134">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="d45b7-135">Номер не может быть назначен другим услугам голосовой почты или учетным записям ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-135">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="d45b7-136">Перед тем как назначить номер телефона учетной записи ресурса, вам нужно будет получить или перенести на него номера бесплатных или платных услуг.</span><span class="sxs-lookup"><span data-stu-id="d45b7-136">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d45b7-137">После получения платных и бесплатных телефонных номеров в >  **центре администрирования Microsoft Teams**они будут отображаться в номерах**голосовых** > **телефонов**, а также в списке **тип номера** будет указан как **услуга бесплатно**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-137">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="d45b7-138">Чтобы получить номера услуг, ознакомьтесь со статьей [получение телефонных номеров служб](getting-service-phone-numbers.md) или перенесите существующий номер Услуги в разделе [Перенос номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d45b7-138">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="d45b7-139">Если вы назначаете номер телефона для учетной записи ресурса, вы можете использовать лицензию на виртуальную систему, доступную для бесплатной подсистемы оплаты.</span><span class="sxs-lookup"><span data-stu-id="d45b7-139">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="d45b7-140">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне Организации, а также позволяет создавать автосекретаря и возможности очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="d45b7-140">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="d45b7-141">Получите лицензию виртуальных пользователей для телефонной системы или обычную лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="d45b7-141">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="d45b7-142">Чтобы получить виртуальную лицензию, в центре администрирования Microsoft 365 перейдите в раздел**подписки** на надстройки**служб** >  **выставления счетов** > и прокрутите список до конца, и вы увидите лицензию "телефонная система — виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="d45b7-142">To get the virtual license, from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="d45b7-143">Нажмите кнопку **Купить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-143">Select **Buy now**.</span></span> <span data-ttu-id="d45b7-144">У тебя нулевая стоимость, но для получения лицензии вам по-прежнему нужно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d45b7-144">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="d45b7-145">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-145">Create a new resource account.</span></span> <span data-ttu-id="d45b7-146">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="d45b7-146">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="d45b7-147">Назначьте для учетной записи ресурсов лицензию на виртуальную или телефонную систему [пользователя](teams-add-on-licensing/virtual-user.md) .</span><span class="sxs-lookup"><span data-stu-id="d45b7-147">Assign  [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="d45b7-148">В разделе [Назначение лицензий Microsoft Teams](assign-teams-licenses.md) и [Назначение лицензий одному пользователю](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="d45b7-148">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="d45b7-149">Назначьте номер Услуги учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-149">Assign the service number to the resource account.</span></span> <span data-ttu-id="d45b7-150">Ознакомьтесь с разназначением и отменой [назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="d45b7-150">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="d45b7-151">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-151">Set up one of the following:</span></span>
   - [<span data-ttu-id="d45b7-152">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="d45b7-152">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d45b7-153">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="d45b7-153">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="d45b7-154">Свяжите учетную запись ресурса с автосекретарем или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="d45b7-154">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="d45b7-155">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="d45b7-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="d45b7-156">Создание учетной записи ресурса без номера телефона</span><span class="sxs-lookup"><span data-stu-id="d45b7-156">Create a resource account without a phone number</span></span>

<span data-ttu-id="d45b7-157">Для создания учетной записи ресурса, не требующей номера телефона, необходимо выполнить следующие действия в указанном ниже порядке.</span><span class="sxs-lookup"><span data-stu-id="d45b7-157">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="d45b7-158">Создайте новую учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-158">Create a new resource account.</span></span> <span data-ttu-id="d45b7-159">Дополнительные сведения о создании учетной [записи ресурса в центре администрирования Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) или [создании учетной записи ресурса в PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="d45b7-159">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="d45b7-160">Настройте один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-160">Set up one of the following:</span></span>
   - [<span data-ttu-id="d45b7-161">Автоматический секретарь облачной функции</span><span class="sxs-lookup"><span data-stu-id="d45b7-161">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="d45b7-162">Очередь облачных звонков</span><span class="sxs-lookup"><span data-stu-id="d45b7-162">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="d45b7-163">Назначьте службе учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-163">Assign the resource account to the service.</span></span> <span data-ttu-id="d45b7-164">Просмотр [назначения и отмены назначения номеров телефонов и служб](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="d45b7-164">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="d45b7-165">Создание учетной записи ресурса в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d45b7-165">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="d45b7-166">После того как вы приобрели лицензию на телефонную систему, с помощью центра администрирования Microsoft Teams перейдите в раздел > **учетные записи ресурсов**" **Параметры организации**".</span><span class="sxs-lookup"><span data-stu-id="d45b7-166">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Снимок экрана со страницей "учетные записи ресурсов"](media/r-a-master.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="d45b7-169">Чтобы создать новую учетную запись ресурса, нажмите кнопку **+ создать учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-169">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="d45b7-170">Во всплывающем окне введите отображаемое имя и имя пользователя для учетной записи ресурса (доменное имя должно быть автоматически заполнено) и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-170">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Снимок экрана с новыми параметрами учетной записи ресурса](media/res-acct.png)

<span data-ttu-id="d45b7-172">Затем примените лицензию к учетной записи ресурса в центре администрирования Office 365, как описано в разделе [Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d45b7-172">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="d45b7-173">Изменение имени учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d45b7-173">Edit resource account name</span></span>

<span data-ttu-id="d45b7-174">![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png) вы можете изменить отображаемое имя учетной записи ресурса с помощью команды " **изменить** ".</span><span class="sxs-lookup"><span data-stu-id="d45b7-174">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="d45b7-175">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="d45b7-175">Click **Save** when you are done.</span></span>
<span data-ttu-id="d45b7-176">![Снимок экрана с параметром изменения учетной записи ресурса](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="d45b7-176">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="d45b7-177">Назначение и отмена назначения номеров телефонов и служб</span><span class="sxs-lookup"><span data-stu-id="d45b7-177">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="d45b7-178">![Значок с номером 3, указывающий на выноску на предыдущем снимке экрана](media/sfbcallout3.png) после создания учетной записи ресурса и назначения лицензии, вы можете выбрать команду **назначить или отменить назначение** для присвоения номера услуги учетной записи ресурса или назначить ресурс. Учетная запись для автосекретаря или уже существующей очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="d45b7-178">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="d45b7-179">Назначение прямого номера маршрутизации может выполняться только с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-179">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="d45b7-180">Если вы хотите создать очередь звонков или автосекретарь, вы можете связать ее с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="d45b7-180">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="d45b7-181">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="d45b7-181">Click **Save** when you are done.</span></span>

<span data-ttu-id="d45b7-182">Чтобы назначить учетной записи ресурсов прямой маршрут или гибридный номер, необходимо ознакомиться с разделом ниже.</span><span class="sxs-lookup"><span data-stu-id="d45b7-182">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d45b7-183">Если у вашей учетной записи ресурса нет лицензии на виртуальную пользователей или телефонную систему, при попытке назначить номер телефона для учетной записи ресурса внутренняя проверка вызовет сбой.</span><span class="sxs-lookup"><span data-stu-id="d45b7-183">If your resource account doesn't have a Virtual User or Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="d45b7-184">Вы не сможете назначить номер или связать учетную запись ресурса со службой.</span><span class="sxs-lookup"><span data-stu-id="d45b7-184">You won't be able to assign the number or associate the resource account with a service.</span></span>

![Снимок экрана с параметрами "назначить/отменить назначение"](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="d45b7-186">Изменение существующей учетной записи ресурса для использования лицензии виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="d45b7-186">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="d45b7-187">Если вы решили переключить лицензии на существующую учетную запись ресурса из лицензии на телефонную систему в лицензию виртуального пользователя, вам потребуется акуире бесплатную лицензию на виртуальные пользователи, а затем выполнить связанные действия в центре администрирования Microsoft 365, чтобы [переместить пользователей на другую подписку](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="d45b7-187">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to  aquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="d45b7-188">Всегда удаляйте полную лицензию на телефонную систему и назначьте лицензию на виртуальную пользователей в том же действии лицензирования.</span><span class="sxs-lookup"><span data-stu-id="d45b7-188">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="d45b7-189">Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="d45b7-189">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="d45b7-190">В этом случае мы рекомендуем создать новую учетную запись ресурса для лицензии виртуального пользователя и удалить неработающие учетные записи ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d45b7-190">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="d45b7-191">Создание учетной записи ресурса в PowerShell</span><span class="sxs-lookup"><span data-stu-id="d45b7-191">Create a resource account in Powershell</span></span>

<span data-ttu-id="d45b7-192">В зависимости от того, с какой учетной записью ресурс находится в сети или локально, вам потребуется подключиться к соответствующему приглашению PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d45b7-192">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="d45b7-193">В следующих примерах командлетов PowerShell предполагается, что учетная запись ресурса подключена к сети с помощью [New-ксонлинеаппликатионинстанце](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) для создания учетной записи ресурсов, которая размещена в сети.</span><span class="sxs-lookup"><span data-stu-id="d45b7-193">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="d45b7-194">Для учетных записей ресурсов, размещенных локально в Skype для бизнеса Server 2019, которые можно использовать с очередями облачных вызовов и облачными автосекретарями, ознакомьтесь с раздел [Настройка очередей облачных вызовов](/skypeforbusiness/hybrid/configure-call-queue.md) или Настройка автосекретаря [облака](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="d45b7-194">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="d45b7-195">Гибридные реализации (номера, расположенные в прямом маршруте) будут использовать [New-кшибридаппликатионендпоинт](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d45b7-195">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="d45b7-196">При создании экземпляров приложения необходимо использовать идентификатор приложения:</span><span class="sxs-lookup"><span data-stu-id="d45b7-196">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="d45b7-197">**Автоматический секретарь:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="d45b7-197">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="d45b7-198">**Очередь звонков:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="d45b7-198">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="d45b7-199">Если вы хотите, чтобы очередь звонков или автосекретарь были доступны для поиска локальными пользователями, следует создать учетные записи ресурсов локально, так как учетные записи ресурсов в сети не синхронизируются с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d45b7-199">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="d45b7-200">Чтобы создать учетную запись ресурса в Интернете для автосекретаря, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d45b7-200">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="d45b7-201">Вы не сможете использовать учетную запись ресурса, пока вы не примените к ней лицензию.</span><span class="sxs-lookup"><span data-stu-id="d45b7-201">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="d45b7-202">Инструкции по применению лицензии к учетной записи в центре администрирования Office 365 можно найти [в разделе Назначение лицензий пользователям в microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , а также [Назначение лицензий Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="d45b7-202">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="d45b7-203">Необязательно После того как правильная лицензия будет применена к учетной записи ресурсов, вы можете указать номер телефона для учетной записи ресурса, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d45b7-203">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="d45b7-204">Не все учетные записи ресурсов требуют номера телефона.</span><span class="sxs-lookup"><span data-stu-id="d45b7-204">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="d45b7-205">Если вы не применяли лицензию для учетной записи ресурса, назначение номера телефона завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="d45b7-205">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="d45b7-206">Для получения дополнительных сведений об этой команде ознакомьтесь с командой [Set-ксонлиневоицеаппликатионинстанце](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d45b7-206">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="d45b7-207">С помощью центра администрирования Microsoft Teams проще всего настроить номер телефона в Интернете, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="d45b7-207">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="d45b7-208">Чтобы назначить для учетной записи ресурсов прямой маршрут или гибридный номер, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d45b7-208">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="d45b7-209">Управление параметрами учетной записи ресурсов в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d45b7-209">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="d45b7-210">Чтобы настроить учетные записи ресурсов в центре администрирования Microsoft Teams, перейдите в раздел**учетные записи ресурсов**в **масштабах**  > Организации, выберите учетную запись ресурса, параметры которой нужно изменить, а затем нажмите кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="d45b7-210">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="d45b7-211">в окне **изменение учетной записи ресурса** вы сможете изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d45b7-211">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="d45b7-212">**Отображаемое имя** учетной записи</span><span class="sxs-lookup"><span data-stu-id="d45b7-212">**Display name** for the account</span></span>
- <span data-ttu-id="d45b7-213">Очередь звонков или автосекретарей, использующая учетную запись</span><span class="sxs-lookup"><span data-stu-id="d45b7-213">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="d45b7-214">Номер телефона, назначенный учетной записи</span><span class="sxs-lookup"><span data-stu-id="d45b7-214">Phone number assigned to the account</span></span>

<span data-ttu-id="d45b7-215">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-215">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="d45b7-216">Удаление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d45b7-216">Delete a resource account</span></span>

<span data-ttu-id="d45b7-217">Убедитесь, что у вас есть связь с номером телефона для учетной записи ресурса перед ее удалением, чтобы не зависнуть номер службы в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="d45b7-217">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="d45b7-218">Это можно сделать, используя следующие unifiedgroup:</span><span class="sxs-lookup"><span data-stu-id="d45b7-218">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="d45b7-219">После этого вы можете удалить учетную запись ресурса на портале администрирования Office 365 на вкладке Пользователи.</span><span class="sxs-lookup"><span data-stu-id="d45b7-219">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d45b7-220">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d45b7-220">Troubleshooting</span></span>

<span data-ttu-id="d45b7-221">На случай, если вы не видите номер телефона, назначенный учетной записи ресурса в центре администрирования Teams, и вы не можете назначить этот номер, пожалуйста, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="d45b7-221">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="d45b7-222">Если атрибут "Отдел" отображает конечную точку приложения Skype для бизнеса, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d45b7-222">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="d45b7-223">После запуска кмлдет обновите веб-страницу центра администрирования Teams, и вы сможете правильно назначить номер.</span><span class="sxs-lookup"><span data-stu-id="d45b7-223">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="d45b7-224">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d45b7-224">Related Information</span></span>

<span data-ttu-id="d45b7-225">Для внедрения, гибридных с помощью Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d45b7-225">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="d45b7-226">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="d45b7-226">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="d45b7-227">Планирование очередей звонков в облаке</span><span class="sxs-lookup"><span data-stu-id="d45b7-227">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="d45b7-228">Настройка локальных учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="d45b7-228">Configure onprem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="d45b7-229">Для реализаций в Teams или Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="d45b7-229">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="d45b7-230">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="d45b7-230">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="d45b7-231">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="d45b7-231">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="d45b7-232">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="d45b7-232">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="d45b7-233">Создание облачной очереди звонков</span><span class="sxs-lookup"><span data-stu-id="d45b7-233">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="d45b7-234">New-Кшибридаппликатионендпоинт</span><span class="sxs-lookup"><span data-stu-id="d45b7-234">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="d45b7-235">New-Ксонлинеаппликатионинстанце</span><span class="sxs-lookup"><span data-stu-id="d45b7-235">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="d45b7-236">Лицензия виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="d45b7-236">Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
