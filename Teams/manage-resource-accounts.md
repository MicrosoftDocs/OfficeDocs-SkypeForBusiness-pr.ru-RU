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
ms.openlocfilehash: ad435a812191cc8f7b9061ac5fba2bbe626b908e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886063"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="82ffd-103">Управление учетными записями ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82ffd-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="82ffd-104">Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="82ffd-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="82ffd-105">В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона.</span><span class="sxs-lookup"><span data-stu-id="82ffd-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="82ffd-106">Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.</span><span class="sxs-lookup"><span data-stu-id="82ffd-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="82ffd-107">В группами Майкрософт или Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="82ffd-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="82ffd-108">Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="82ffd-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="82ffd-109">Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="82ffd-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="82ffd-110">Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="82ffd-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="82ffd-111">Необходимые условия для назначения номера телефона для учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="82ffd-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="82ffd-112">Для начала работы необходимо помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="82ffd-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="82ffd-113">Необходимо назначить учетную запись ресурса, который будет связан с auto attendant или звонок очереди лицензию телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="82ffd-113">You need to assign a Phone System license to a resource account that will be associated with your auto attendant or call queue.</span></span> <span data-ttu-id="82ffd-114">Дополнительные сведения о лицензировании см. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="82ffd-114">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    

    > [!NOTE]
    > <span data-ttu-id="82ffd-115">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="82ffd-115">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="82ffd-116">В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="82ffd-116">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="82ffd-117">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82ffd-117">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="82ffd-118">Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="82ffd-118">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="82ffd-119">Номер прямого гибридной маршрутизации можно назначить учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="82ffd-119">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="82ffd-120">Для получения дополнительных сведений см. [Планирование прямой маршрутизации](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="82ffd-120">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="82ffd-121">Для Microsoft Тарифные планы могут быть назначены только международную и бесплатных служба телефонных номеров, для которого в **Центр администрирования группами Майкрософт** или передан от другого поставщика услуг в учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="82ffd-121">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="82ffd-122">Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.</span><span class="sxs-lookup"><span data-stu-id="82ffd-122">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="82ffd-123">Номера телефонов пользователей (подписчика) не могут назначаться учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="82ffd-123">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="82ffd-124">Можно использовать только службы международную и бесплатных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="82ffd-124">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="82ffd-125">Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или перенос существующих международную или бесплатная служба номеров.</span><span class="sxs-lookup"><span data-stu-id="82ffd-125">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="82ffd-126">После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="82ffd-126">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="82ffd-127">Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) или необходимо перенести существующий номер службы, в статье [передачи телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="82ffd-127">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="82ffd-128">Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы.</span><span class="sxs-lookup"><span data-stu-id="82ffd-128">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="82ffd-129">Перейдите на [Управление телефонные номера для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.</span><span class="sxs-lookup"><span data-stu-id="82ffd-129">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="82ffd-130">Создание учетной записи ресурса в Powershell</span><span class="sxs-lookup"><span data-stu-id="82ffd-130">Create a resource account in Powershell</span></span>

 <span data-ttu-id="82ffd-131">Вам нужно создать учетную запись ресурса, выполнив командлет соответствующие Powershell при необходимости (для одного или нескольких учетных записей ресурсов) и присвойте имя каждой из них и т. д.</span><span class="sxs-lookup"><span data-stu-id="82ffd-131">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="82ffd-132">В данный момент не вариант при создании учетной записи ресурса в центре администрирования группами Майкрософт, но можно изменить номера телефонов и измените вызова очередь или auto attendant назначения для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="82ffd-132">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="82ffd-133">В зависимости от того, ли номер телефона расположен через Интернет или локально необходимо подключиться к строке соответствующие Powershell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="82ffd-133">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="82ffd-134">Для создания учетной записи ресурса, размещенный на локальном реализации гибридных (номера телефонов, размещенных на прямой маршрутизации, OPCH и системы CCE) будет использовать [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="82ffd-134">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="82ffd-135">Интернет-версия только для реализации, использующие [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) иметь учетную запись ресурса, который расположен в Интернете.</span><span class="sxs-lookup"><span data-stu-id="82ffd-135">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="82ffd-136">Ниже приведен пример создания учетной записи ресурса online среды:</span><span class="sxs-lookup"><span data-stu-id="82ffd-136">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="82ffd-137">В разделе [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="82ffd-137">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="82ffd-138">Можно легко указывается, что online телефона с помощью центра администрирования группами Майкрософт, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="82ffd-138">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="82ffd-139">Вы также можете использовать `Set-CsOnlineVoiceApplicationInstance` команду для назначения номер телефона, чтобы учетная запись ресурса после его первоначального создания как показано:</span><span class="sxs-lookup"><span data-stu-id="82ffd-139">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

<span data-ttu-id="82ffd-140">В разделе [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="82ffd-140">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="82ffd-141">Управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="82ffd-141">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="82ffd-142">Для управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт, перейдите к **Параметры масштабе организации**  > **учетные записи ресурса**, выберите учетную запись ресурса, чтобы изменить параметры для и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="82ffd-142">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="82ffd-143">в окне **Изменение учетной записи ресурсов** вы сможете изменить:</span><span class="sxs-lookup"><span data-stu-id="82ffd-143">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="82ffd-144">**Отображаемое имя** для учетной записи</span><span class="sxs-lookup"><span data-stu-id="82ffd-144">**Display name** for the account</span></span>
- <span data-ttu-id="82ffd-145">Звонок очередь или автосекретаря, который использует учетную запись</span><span class="sxs-lookup"><span data-stu-id="82ffd-145">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="82ffd-146">Номер телефона, назначенная учетной записи</span><span class="sxs-lookup"><span data-stu-id="82ffd-146">Phone number assigned to the account</span></span>

<span data-ttu-id="82ffd-147">По завершении щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="82ffd-147">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="82ffd-148">Связанные сведения</span><span class="sxs-lookup"><span data-stu-id="82ffd-148">Related Information</span></span>

<span data-ttu-id="82ffd-149">Для реализации, которые являются гибридное развертывание с Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="82ffd-149">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="82ffd-150">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="82ffd-150">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="82ffd-151">Настройка автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="82ffd-151">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="82ffd-152">Для реализации в группы или Скайп для бизнеса в Интернет:</span><span class="sxs-lookup"><span data-stu-id="82ffd-152">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="82ffd-153">Что такое автосекретари телефонной системы?</span><span class="sxs-lookup"><span data-stu-id="82ffd-153">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="82ffd-154">Настройка автосекретаря телефонной системы</span><span class="sxs-lookup"><span data-stu-id="82ffd-154">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="82ffd-155">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="82ffd-155">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="82ffd-156">Создание очереди звонков в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="82ffd-156">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="82ffd-157">Новый CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="82ffd-157">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="82ffd-158">Новый CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="82ffd-158">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
