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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Узнайте о управления учетными записями ресурсов в группах Майкрософт
ms.openlocfilehash: 345b3b8698f0c387f90b37cc1212c320a2d3d85d
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013647"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="e93c6-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e93c6-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="e93c6-104">Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="e93c6-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="e93c6-105">В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e93c6-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="e93c6-106">Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.</span><span class="sxs-lookup"><span data-stu-id="e93c6-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="e93c6-107">В группами Майкрософт или Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e93c6-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="e93c6-108">Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="e93c6-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="e93c6-109">Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="e93c6-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="e93c6-110">Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="e93c6-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="e93c6-111">Необходимые условия для назначения номера телефона для учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="e93c6-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="e93c6-112">Для начала работы необходимо помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="e93c6-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="e93c6-113">Auto-attendant или звонок очереди необходимо иметь учетную запись связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e93c6-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="e93c6-114">Сведения о учетные записи ресурса в разделе [Управление учетными записями ресурсов в группах](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="e93c6-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="e93c6-115">Если вы планируете нумерации прямой маршрутизации, необходимо получить и назначение лицензий на следующие учетные записи ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки\).</span><span class="sxs-lookup"><span data-stu-id="e93c6-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="e93c6-116">Вместо этого при назначении номера службы Майкрософт, необходимо получить и назначьте следующие лицензии свою учетную запись ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки и вызов планирование\).</span><span class="sxs-lookup"><span data-stu-id="e93c6-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="e93c6-117">Корпорация Майкрософт работает на соответствующей модели лицензирования для приложений, таких как автосекретари облако и очереди вызовов, для теперь необходимо использовать модель лицензирования пользователя.</span><span class="sxs-lookup"><span data-stu-id="e93c6-117">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e93c6-118">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="e93c6-118">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="e93c6-119">В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e93c6-119">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="e93c6-120">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e93c6-120">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e93c6-121">Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e93c6-121">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="e93c6-122">Номер прямого гибридной маршрутизации можно назначить учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="e93c6-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="e93c6-123">Для получения дополнительных сведений см. [Планирование прямой маршрутизации](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="e93c6-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="e93c6-124">Для Microsoft Тарифные планы могут быть назначены только международную и бесплатных служба телефонных номеров, для которого в **Центр администрирования группами Майкрософт** или передан от другого поставщика услуг в учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="e93c6-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="e93c6-125">Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.</span><span class="sxs-lookup"><span data-stu-id="e93c6-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="e93c6-126">Номера телефонов пользователей (подписчика) не могут назначаться учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="e93c6-126">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="e93c6-127">Можно использовать только службы международную и бесплатных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="e93c6-127">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="e93c6-128">Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или перенос существующих международную или бесплатная служба номеров.</span><span class="sxs-lookup"><span data-stu-id="e93c6-128">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="e93c6-129">После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="e93c6-129">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="e93c6-130">Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) или необходимо перенести существующий номер службы, в статье [передачи телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e93c6-130">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e93c6-131">Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы.</span><span class="sxs-lookup"><span data-stu-id="e93c6-131">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="e93c6-132">Перейдите на [Управление телефонные номера для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.</span><span class="sxs-lookup"><span data-stu-id="e93c6-132">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="e93c6-133">Создание учетной записи ресурса в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e93c6-133">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="e93c6-134">Чтобы создать учетную запись ресурса в центре администрирования группами Майкрософт, перейдите к **масштабе организации параметры** > **учетные записи ресурса**, нажмите кнопку **+ Добавить**и заполните отображаемое имя, имя пользователя, а затем выберите имя домена и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e93c6-134">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, click **+ Add**, and fill out the display name, user name, then select the domain name and click **Save**.</span></span>

<span data-ttu-id="e93c6-135">Чтобы применить лицензия учетную запись ресурса, перейдите на вкладку Центр администрирования O365 пользователей.</span><span class="sxs-lookup"><span data-stu-id="e93c6-135">To apply a license to the resource account, navigate to the O365 Admin Center users tab.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="e93c6-136">Создание учетной записи ресурса в Powershell</span><span class="sxs-lookup"><span data-stu-id="e93c6-136">Create a resource account in Powershell</span></span>

 <span data-ttu-id="e93c6-137">Вам нужно создать учетную запись ресурса, выполнив командлет соответствующие Powershell при необходимости (для одного или нескольких учетных записей ресурсов) и присвойте имя каждой из них и т. д.</span><span class="sxs-lookup"><span data-stu-id="e93c6-137">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="e93c6-138">В данный момент не вариант при создании учетной записи ресурса в центре администрирования группами Майкрософт, но можно изменить номера телефонов и измените вызова очередь или auto attendant назначения для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="e93c6-138">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="e93c6-139">В зависимости от того, ли номер телефона расположен через Интернет или локально необходимо подключиться к строке соответствующие Powershell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e93c6-139">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="e93c6-140">Для создания учетной записи ресурса, размещенный на локальном реализации гибридных (номера телефонов, размещенных на прямой маршрутизации, OPCH и системы CCE) будет использовать [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e93c6-140">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="e93c6-141">Интернет-версия только для реализации, использующие [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) иметь учетную запись ресурса, который расположен в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e93c6-141">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="e93c6-142">Ниже приведен пример создания учетной записи ресурса online среды:</span><span class="sxs-lookup"><span data-stu-id="e93c6-142">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="e93c6-143">В разделе [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="e93c6-143">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="e93c6-144">Можно легко указывается, что online телефона с помощью центра администрирования группами Майкрософт, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="e93c6-144">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="e93c6-145">Вы также можете использовать `Set-CsOnlineVoiceApplicationInstance` команду для назначения номер телефона, чтобы учетная запись ресурса после его первоначального создания как показано:</span><span class="sxs-lookup"><span data-stu-id="e93c6-145">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

<span data-ttu-id="e93c6-146">Если лицензия не применяются при создании учетной записи ресурса назначения номера телефона завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e93c6-146">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="e93c6-147">В разделе [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="e93c6-147">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="e93c6-148">Управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e93c6-148">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="e93c6-149">Для управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт, перейдите к **Параметры масштабе организации**  > **учетные записи ресурса**, выберите учетную запись ресурса, чтобы изменить параметры для и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="e93c6-149">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="e93c6-150">в окне **Изменение учетной записи ресурсов** вы сможете изменить:</span><span class="sxs-lookup"><span data-stu-id="e93c6-150">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="e93c6-151">**Отображаемое имя** для учетной записи</span><span class="sxs-lookup"><span data-stu-id="e93c6-151">**Display name** for the account</span></span>
- <span data-ttu-id="e93c6-152">Звонок очередь или автосекретаря, который использует учетную запись</span><span class="sxs-lookup"><span data-stu-id="e93c6-152">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="e93c6-153">Номер телефона, назначенная учетной записи</span><span class="sxs-lookup"><span data-stu-id="e93c6-153">Phone number assigned to the account</span></span>

<span data-ttu-id="e93c6-154">По завершении щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e93c6-154">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="e93c6-155">Связанные сведения</span><span class="sxs-lookup"><span data-stu-id="e93c6-155">Related Information</span></span>

<span data-ttu-id="e93c6-156">Для реализации, которые являются гибридное развертывание с Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="e93c6-156">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="e93c6-157">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="e93c6-157">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="e93c6-158">Настройка автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="e93c6-158">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="e93c6-159">Для реализации в группы или Скайп для бизнеса в Интернет:</span><span class="sxs-lookup"><span data-stu-id="e93c6-159">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="e93c6-160">Что такое автосекретари телефонной системы?</span><span class="sxs-lookup"><span data-stu-id="e93c6-160">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="e93c6-161">Настройка автосекретаря телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e93c6-161">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="e93c6-162">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="e93c6-162">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="e93c6-163">Создание очереди звонков в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="e93c6-163">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="e93c6-164">Новый CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="e93c6-164">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="e93c6-165">Новый CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="e93c6-165">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
