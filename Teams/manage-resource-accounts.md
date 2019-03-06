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
description: Управление учетными записями ресурсов в группах Майкрософт
ms.openlocfilehash: 22574b2045f162353c3b1154590f3cf903721cf8
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408261"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="87e01-103">Управление учетными записями ресурсов в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="87e01-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="87e01-104">Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом.</span><span class="sxs-lookup"><span data-stu-id="87e01-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="87e01-105">В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона.</span><span class="sxs-lookup"><span data-stu-id="87e01-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="87e01-106">Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.</span><span class="sxs-lookup"><span data-stu-id="87e01-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="87e01-107">В группами Майкрософт или Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="87e01-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="87e01-108">Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="87e01-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="87e01-109">Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="87e01-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="87e01-110">Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="87e01-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="87e01-111">Необходимые условия для назначения номера телефона для учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="87e01-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="87e01-112">Для начала работы необходимо помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="87e01-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="87e01-113">Ваша организация должна иметь (как минимум) лицензию типа "Корпоративный E3 с**телефонной системой"** или лицензию "Корпоративный E5".</span><span class="sxs-lookup"><span data-stu-id="87e01-113">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="87e01-114">Число пользовательских лицензий **Телефонной системой** , для которых влияет на число номеров службы, которые доступны для использования для учетных записей ресурсов, назначенных для вызова очередей или автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="87e01-114">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for resource accounts assigned to call queues or auto attendants.</span></span> <span data-ttu-id="87e01-115">Число учетных записей ресурсов, которые могут возникнуть, зависит от числа лицензий **Телефонной системой** и **Звук конференц-связи** , назначенные в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="87e01-115">The number of resource accounts you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="87e01-116">Дополнительные сведения о лицензировании см. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="87e01-116">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="87e01-117">Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365.</span><span class="sxs-lookup"><span data-stu-id="87e01-117">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="87e01-118">В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="87e01-118">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="87e01-119">Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87e01-119">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="87e01-120">Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="87e01-120">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="87e01-121">Чтобы узнать больше о вызове планы Office 365, обратитесь к разделу [Вызов планы для Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="87e01-121">To learn more about Office 365 Calling Plans, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>
- <span data-ttu-id="87e01-122">Можно назначить только международную и бесплатных служба телефонных номеров, для которого в **Центр администрирования группами Майкрософт** или передан от другого поставщика услуг в учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="87e01-122">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="87e01-123">Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.</span><span class="sxs-lookup"><span data-stu-id="87e01-123">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="87e01-124">Номера телефонов пользователей (подписчика) не могут назначаться учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="87e01-124">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="87e01-125">Можно использовать только службы международную и бесплатных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="87e01-125">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="87e01-126">Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или перенос существующих международную или бесплатная служба номеров.</span><span class="sxs-lookup"><span data-stu-id="87e01-126">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="87e01-127">После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**.</span><span class="sxs-lookup"><span data-stu-id="87e01-127">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="87e01-128">Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) или существующий номер службы и передача, см [передачи телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="87e01-128">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="87e01-129">Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы.</span><span class="sxs-lookup"><span data-stu-id="87e01-129">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="87e01-130">Перейдите на [Управление телефонные номера для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.</span><span class="sxs-lookup"><span data-stu-id="87e01-130">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="87e01-131">Создание учетной записи ресурса в Powershell</span><span class="sxs-lookup"><span data-stu-id="87e01-131">Create a resource account in Powershell</span></span>

 <span data-ttu-id="87e01-132">Вам нужно создать учетную запись ресурса, выполнив командлет соответствующие Powershell при необходимости (для одного или нескольких учетных записей ресурсов) и присвойте имя каждой из них и т. д.</span><span class="sxs-lookup"><span data-stu-id="87e01-132">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="87e01-133">В данный момент не вариант при создании учетной записи ресурса в центре администрирования группами Майкрософт, но можно изменить номера телефонов и измените вызова очередь или auto attendant назначения для учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="87e01-133">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="87e01-134">В зависимости от того, ли номер телефона расположен через Интернет или локально необходимо подключиться к строке соответствующие Powershell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="87e01-134">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="87e01-135">Для создания учетной записи ресурса, размещенный на локальном реализации гибридных (номера телефонов, размещенных на прямой маршрутизации, OPCH и системы CCE) будет использовать [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="87e01-135">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="87e01-136">Интернет-версия только для реализации, использующие [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) иметь учетную запись ресурса, который расположен в Интернете.</span><span class="sxs-lookup"><span data-stu-id="87e01-136">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="87e01-137">Ниже приведен пример создания учетной записи ресурса online среды:</span><span class="sxs-lookup"><span data-stu-id="87e01-137">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

<span data-ttu-id="87e01-138">В разделе [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="87e01-138">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="87e01-139">Можно легко установить номер телефона, с помощью центра администрирования группами Майкрософт, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="87e01-139">It's easiest to set the phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="87e01-140">Вы также можете использовать `Set-CsOnlineApplicationInstance` команду для назначения номер телефона, чтобы учетная запись ресурса после его первоначального создания как показано:</span><span class="sxs-lookup"><span data-stu-id="87e01-140">You can also use the `Set-CsOnlineApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

<span data-ttu-id="87e01-141">В разделе [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.</span><span class="sxs-lookup"><span data-stu-id="87e01-141">See [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="87e01-142">Управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="87e01-142">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="87e01-143">Для управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт, перейдите к **Параметры масштабе организации**  > **учетные записи ресурса**, выберите учетную запись ресурса, чтобы изменить параметры для и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="87e01-143">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="87e01-144">в окне **Изменение учетной записи ресурсов** вы сможете изменить:</span><span class="sxs-lookup"><span data-stu-id="87e01-144">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="87e01-145">**Отображаемое имя** для учетной записи</span><span class="sxs-lookup"><span data-stu-id="87e01-145">**Display name** for the account</span></span>
- <span data-ttu-id="87e01-146">Звонок очередь или автосекретаря, который использует учетную запись</span><span class="sxs-lookup"><span data-stu-id="87e01-146">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="87e01-147">Номер телефона, назначенная учетной записи</span><span class="sxs-lookup"><span data-stu-id="87e01-147">Phone number assigned to the account</span></span>

<span data-ttu-id="87e01-148">По завершении щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87e01-148">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="87e01-149">Связанные сведения</span><span class="sxs-lookup"><span data-stu-id="87e01-149">Related Information</span></span>

<span data-ttu-id="87e01-150">Для реализации, которые являются гибридное развертывание с Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="87e01-150">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="87e01-151">Планирование облачных автосекретаря</span><span class="sxs-lookup"><span data-stu-id="87e01-151">Plan Cloud auto attendant</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="87e01-152">Настройка автосекретарей облако</span><span class="sxs-lookup"><span data-stu-id="87e01-152">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="87e01-153">Для реализации в группы или Скайп для бизнеса в Интернет:</span><span class="sxs-lookup"><span data-stu-id="87e01-153">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="87e01-154">Что такое автосекретари телефонной системы?</span><span class="sxs-lookup"><span data-stu-id="87e01-154">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="87e01-155">Настройка автосекретаря телефонной системы</span><span class="sxs-lookup"><span data-stu-id="87e01-155">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="87e01-156">Пример для малого бизнеса — Настройка автосекретарю.</span><span class="sxs-lookup"><span data-stu-id="87e01-156">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="87e01-157">Создание очереди звонков в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="87e01-157">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="87e01-158">Новый CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="87e01-158">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="87e01-159">Новый CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="87e01-159">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
