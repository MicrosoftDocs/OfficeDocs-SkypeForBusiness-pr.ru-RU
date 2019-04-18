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
ms.openlocfilehash: e8d3da4938a5040972b3c4853434808ca7457c90
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914596"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c0640-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0640-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c0640-104">Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="c0640-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="c0640-105">В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона.</span><span class="sxs-lookup"><span data-stu-id="c0640-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="c0640-106">Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.</span><span class="sxs-lookup"><span data-stu-id="c0640-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="c0640-107">В группами Майкрософт или Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c0640-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="c0640-108">Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="c0640-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="c0640-109">Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="c0640-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="c0640-110">Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="c0640-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="c0640-111">Необходимые условия для назначения номера телефона для учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="c0640-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="c0640-112">Для начала работы необходимо помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="c0640-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c0640-113">Auto-attendant или звонок очереди необходимо иметь учетную запись связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c0640-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c0640-114">Сведения о учетные записи ресурса в разделе [Управление учетными записями ресурсов в группах](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="c0640-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c0640-115">Если вы планируете нумерации прямой маршрутизации, необходимо получить и назначение лицензий на следующие учетные записи ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки\).</span><span class="sxs-lookup"><span data-stu-id="c0640-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="c0640-116">Вместо этого при назначении номера службы Майкрософт, необходимо получить и назначьте следующие лицензии свою учетную запись ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки и вызов планирование\).</span><span class="sxs-lookup"><span data-stu-id="c0640-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="c0640-117">Необходимо лицензировать учетных записей с номером телефона, назначенные им.</span><span class="sxs-lookup"><span data-stu-id="c0640-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="c0640-118">В вложенных auto attendant или звонков в очереди не нужно лицензировать rest автосекретари или вызвать очередей, если у них нет номера телефона, связанные с ними</span><span class="sxs-lookup"><span data-stu-id="c0640-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="c0640-119">Прямое номеров службы маршрутизации для принимаемые автосекретарем и очереди вызовов поддерживается для групп Майкрософт пользователей и агенты только в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c0640-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only at the moment.</span></span>

> [!NOTE] 
> <span data-ttu-id="c0640-120">Корпорация Майкрософт работает на соответствующей модели лицензирования для приложений, таких как автосекретари облако и очереди вызовов, для теперь необходимо использовать модель лицензирования пользователя.</span><span class="sxs-lookup"><span data-stu-id="c0640-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c0640-121">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0640-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c0640-122">В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c0640-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c0640-123">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0640-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c0640-124">Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c0640-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="c0640-125">Номер прямого гибридной маршрутизации можно назначить учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="c0640-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="c0640-126">Для получения дополнительных сведений см. [Планирование прямой маршрутизации](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="c0640-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="c0640-127">Для Microsoft Тарифные планы могут быть назначены только международную и номера телефонов бесплатных службы, в **Центр администрирования группами Майкрософт** или перенесен из другого поставщика услуг для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="c0640-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="c0640-128">Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.</span><span class="sxs-lookup"><span data-stu-id="c0640-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="c0640-129">Номера телефонов пользователей (подписчика) не могут назначаться учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="c0640-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="c0640-130">Можно использовать только службы международную и бесплатных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="c0640-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="c0640-131">Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или порт существующего счета или бесплатная служба номеров.</span><span class="sxs-lookup"><span data-stu-id="c0640-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c0640-132">После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="c0640-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c0640-133">Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) или необходимо перенести существующий номер службы, в статье [передачи телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c0640-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0640-134">Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы.</span><span class="sxs-lookup"><span data-stu-id="c0640-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c0640-135">Перейдите на [Управление телефонные номера для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.</span><span class="sxs-lookup"><span data-stu-id="c0640-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="c0640-136">Создание учетной записи ресурса в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c0640-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="c0640-137">Чтобы создать учетную запись ресурса в центре администрирования группами Майкрософт, перейдите к **масштабе организации параметры** > **учетные записи ресурса**, нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c0640-137">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="c0640-138">Во всплывающем введите отображаемое имя и имя пользователя для учетной записи ресурса (имя домена должно отобразиться автоматически) нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c0640-138">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Учетная запись ресурса](media/res-acct.png)

<span data-ttu-id="c0640-140">Необходимо также для применения лицензии учетная запись ресурса, как описано в [Назначение лицензий для пользователей в Office 365 для бизнеса](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="c0640-140">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="c0640-141">После создания учетной записи ресурса и назначены лицензии, вы щелкаете **Назначить или снять** назначение номер телефона для учетной записи ресурса, а также назначить учетную запись ресурса в очередь auto attendant или звонок.</span><span class="sxs-lookup"><span data-stu-id="c0640-141">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="c0640-142">Создание учетной записи ресурса в Powershell</span><span class="sxs-lookup"><span data-stu-id="c0640-142">Create a resource account in Powershell</span></span>

<span data-ttu-id="c0640-143">Для Microsoft Тарифные планы могут быть назначены только международную и номера телефонов бесплатных службы, в **Центр администрирования группами Майкрософт** или перенесен из другого поставщика услуг для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="c0640-143">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="c0640-144">Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.</span><span class="sxs-lookup"><span data-stu-id="c0640-144">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="c0640-145">В зависимости от того, ли номер телефона расположен через Интернет или локально необходимо подключиться к строке соответствующие Powershell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c0640-145">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>


- <span data-ttu-id="c0640-146">(Номера, размещенных на прямой маршрутизации) реализации гибридных будет использоваться для создания учетной записи ресурса, размещенный на локальном [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c0640-146">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="c0640-147">Интернет-версия только для реализации, использующие [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) иметь учетную запись ресурса, который расположен в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c0640-147">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="c0640-148">Ниже приведен пример создания учетной записи ресурса с автосекретарем ApplicationID сети Интернет.</span><span class="sxs-lookup"><span data-stu-id="c0640-148">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="c0640-149">Задания в очереди вызовов можно использовать следующие ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span><span class="sxs-lookup"><span data-stu-id="c0640-149">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="c0640-150">В разделе [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="c0640-150">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="c0640-151">Можно легко указывается, что online телефона с помощью центра администрирования группами Майкрософт, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c0640-151">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="c0640-152">Вы также можете использовать `Set-CsOnlineVoiceApplicationInstance` команду для назначения номер телефона, чтобы учетная запись ресурса после его первоначального создания как показано:</span><span class="sxs-lookup"><span data-stu-id="c0640-152">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="c0640-153">Если лицензия не применяются при создании учетной записи ресурса назначения номера телефона завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c0640-153">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="c0640-154">В разделе [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="c0640-154">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="c0640-155">Управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c0640-155">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="c0640-156">Для управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт, перейдите к **Параметры масштабе организации**  > **учетные записи ресурса**, выберите учетную запись ресурса, чтобы изменить параметры для и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="c0640-156">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="c0640-157">в окне **Изменение учетной записи ресурсов** вы сможете изменить:</span><span class="sxs-lookup"><span data-stu-id="c0640-157">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="c0640-158">**Отображаемое имя** для учетной записи</span><span class="sxs-lookup"><span data-stu-id="c0640-158">**Display name** for the account</span></span>
- <span data-ttu-id="c0640-159">Звонок очередь или автосекретаря, который использует учетную запись</span><span class="sxs-lookup"><span data-stu-id="c0640-159">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="c0640-160">Номер телефона, назначенная учетной записи</span><span class="sxs-lookup"><span data-stu-id="c0640-160">Phone number assigned to the account</span></span>

<span data-ttu-id="c0640-161">По завершении щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c0640-161">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="c0640-162">Связанные сведения</span><span class="sxs-lookup"><span data-stu-id="c0640-162">Related Information</span></span>

<span data-ttu-id="c0640-163">Для реализации, которые являются гибридное развертывание с Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="c0640-163">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="c0640-164">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="c0640-164">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="c0640-165">Настройка автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="c0640-165">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="c0640-166">Для реализации в группы или Скайп для бизнеса в Интернет:</span><span class="sxs-lookup"><span data-stu-id="c0640-166">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="c0640-167">Что такое автосекретари облако?</span><span class="sxs-lookup"><span data-stu-id="c0640-167">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="c0640-168">Настроить автосекретарь облако</span><span class="sxs-lookup"><span data-stu-id="c0640-168">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="c0640-169">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="c0640-169">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="c0640-170">Создание очереди вызовов облако</span><span class="sxs-lookup"><span data-stu-id="c0640-170">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="c0640-171">Новый CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="c0640-171">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="c0640-172">Новый CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c0640-172">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
