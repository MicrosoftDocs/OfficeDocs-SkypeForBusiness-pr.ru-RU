---
title: Настройка учетной записи ресурса в Skype для бизнеса Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Настройте учетную запись ресурса для Skype для бизнеса Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160732"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="b6c22-103">Настройка учетных записей ресурсов</span><span class="sxs-lookup"><span data-stu-id="b6c22-103">Configure resource accounts</span></span>

<span data-ttu-id="b6c22-104">Гибридные реализации Skype для бизнеса Server 2019 используют только облачные службы, предоставляемые телефонной системой для единой системы обмена сообщениями, и не интегрируются с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6c22-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="b6c22-105">В Skype для бизнеса Server 2019 теперь вы можете использовать очереди облачных вызовов и автосекретарей, описанные в [статье возможности телефонной системы в Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span><span class="sxs-lookup"><span data-stu-id="b6c22-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="b6c22-106">Чтобы использовать эти службы телефонных систем с Skype для бизнеса Server 2019, вам потребуется создать учетные записи ресурсов, которые действуют как конечные точки приложений и могут назначать номера телефонов, а затем использовать центр администрирования Online Teams для настройки очереди звонков или автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6c22-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="b6c22-107">Эта учетная запись ресурса может быть размещена в сети (в разделе [Управление учетными записями ресурсов в Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) для создания учетных записей ресурсов, размещенных в Интернете) или локально, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b6c22-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="b6c22-108">Как правило, у вас будет несколько узлов службы телефонной системы, каждая из которых сопоставляется с учетными записями ресурсов, которые могут быть размещены в Интернете или в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b6c22-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="b6c22-109">Если вы используете существующий автосекретарь единой системы обмена сообщениями Exchange и система очередей звонков, перед переключением на Exchange Server 2019 или Exchange Online необходимо вручную записать сведения, как описано ниже, а затем внедрить совершенно новую систему с помощью центра администрирования Teams .</span><span class="sxs-lookup"><span data-stu-id="b6c22-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="b6c22-110">Обзор</span><span class="sxs-lookup"><span data-stu-id="b6c22-110">Overview</span></span>

<span data-ttu-id="b6c22-111">Если службе телефонной системы потребуется номер службы, могут выполняться различные зависимости в следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="b6c22-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="b6c22-112">Получение номера службы</span><span class="sxs-lookup"><span data-stu-id="b6c22-112">Obtain a service number</span></span>
2. <span data-ttu-id="b6c22-113">Приобретение лицензии на телефонную систему</span><span class="sxs-lookup"><span data-stu-id="b6c22-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="b6c22-114">Создайте учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-114">Create the resource account.</span></span> <span data-ttu-id="b6c22-115">Для автосекретаря или очереди вызовов требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="b6c22-116">Ожидание синхронизации Active Directory между интерактивным и локальным режимом</span><span class="sxs-lookup"><span data-stu-id="b6c22-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="b6c22-117">Назначьте лицензии на телефонную систему учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="b6c22-118">Назначьте номер службы учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="b6c22-119">Создание службы телефонной системы (очередь звонков или автосекретарь)</span><span class="sxs-lookup"><span data-stu-id="b6c22-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="b6c22-120">Сопоставление учетной записи ресурса со службой: (New-КсаппликатионинстанцеассоЦиатион)</span><span class="sxs-lookup"><span data-stu-id="b6c22-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="b6c22-121">Если автосекретарь или очередь вызовов вложены в автосекретарь верхнего уровня, соответствующей учетной записи ресурса необходим только номер телефона, если требуется несколько точек входа в структуру автосекретарей и очередей звонков.</span><span class="sxs-lookup"><span data-stu-id="b6c22-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="b6c22-122">Для перенаправления вызовов пользователям в вашей организации, размещенной в сети, у них должна быть лицензия на **телефонную систему** и включена поддержка корпоративной голосовой связи или планы звонков по Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6c22-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b6c22-123">В разделе [Назначение лицензий Microsoft Teams](/MicrosoftTeams/assign-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="b6c22-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="b6c22-124">Чтобы включить их для корпоративной голосовой связи, вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c22-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b6c22-125">Например, выполните следующие действия:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b6c22-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="b6c22-126">Если создаваемая служба телефонной системы является вложенной и не требует номера телефона, процесс будет следующим:</span><span class="sxs-lookup"><span data-stu-id="b6c22-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="b6c22-127">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="b6c22-127">Create the resource account</span></span>  
2. <span data-ttu-id="b6c22-128">Ожидание синхронизации Active Directory между интерактивным и локальным режимом</span><span class="sxs-lookup"><span data-stu-id="b6c22-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="b6c22-129">Создание службы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="b6c22-129">Create a Phone System service</span></span>
4. <span data-ttu-id="b6c22-130">Сопоставление учетной записи ресурса с службой телефонной системы</span><span class="sxs-lookup"><span data-stu-id="b6c22-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="b6c22-131">Создание учетной записи ресурса с номером телефона</span><span class="sxs-lookup"><span data-stu-id="b6c22-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="b6c22-132">Для создания учетной записи ресурса, использующей номер телефона, необходимо выполнить следующие задачи в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="b6c22-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b6c22-133">Порт или получите платный или бесплатный номер службы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="b6c22-134">Номер не может быть назначен никаким другим службам голосовой связи или учетным записям ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b6c22-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="b6c22-135">Перед назначением номера телефона учетной записи ресурса необходимо получить или перенести имеющиеся номера бесплатных или бесплатных служб.</span><span class="sxs-lookup"><span data-stu-id="b6c22-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b6c22-136">После получения платных номеров телефонов или бесплатных номеров службы они будут отображаться в**голосовых** > **номерах** >  **центра администрирования Microsoft Teams**, а указанный **тип номера** будет указан как **Service — бесплатный**.</span><span class="sxs-lookup"><span data-stu-id="b6c22-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b6c22-137">Чтобы получить номера служб, ознакомьтесь со статьей [Получение номеров служб](/MicrosoftTeams/getting-service-phone-numbers) или перенесите существующий номер службы в раздел [Передача номеров телефонов в Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="b6c22-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="b6c22-138">Если вы выходяте за пределами США, вы не сможете использовать центр администрирования Microsoft Teams для получения номеров служб.</span><span class="sxs-lookup"><span data-stu-id="b6c22-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="b6c22-139">Перейдите к разделу [Управление номерами телефонов в Организации](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) , чтобы узнать, как сделать это из за пределами США.</span><span class="sxs-lookup"><span data-stu-id="b6c22-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="b6c22-140">Приобретение лицензии на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="b6c22-140">Buy a Phone System license.</span></span> <span data-ttu-id="b6c22-141">См. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="b6c22-141">See:</span></span>  
   - [<span data-ttu-id="b6c22-142">Office 365 корпоративный E1 и E3</span><span class="sxs-lookup"><span data-stu-id="b6c22-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="b6c22-143">Office 365 корпоративный E5</span><span class="sxs-lookup"><span data-stu-id="b6c22-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="b6c22-144">Программное обеспечение Office 365 Enterprise с корпоративным предприятием</span><span class="sxs-lookup"><span data-stu-id="b6c22-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="b6c22-145">Создайте локальную учетную запись ресурса, выполнив `New-CsHybridApplicationEndpoint` командлет для каждой службы телефонной системы и присвойте каждой из них имя, SIP адрес и т. д.</span><span class="sxs-lookup"><span data-stu-id="b6c22-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="b6c22-146">Для получения дополнительных сведений о данной команде, ознакомьтесь со статьей [New – кшибридаппликатионендпоинт](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="b6c22-147">Необязательно После создания учетных записей ресурсов можно подождать, пока служба AD будет синхронизироваться между Интернетом и локальным, либо выполнить синхронизацию и перейти к настройке служб телефонной системы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b6c22-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="b6c22-148">Чтобы принудительно выполнить синхронизацию, выполните следующую команду на компьютере, на котором выполняется AAD Connect (если это еще не сделано, для запуска команды `import-module adsync` требуется загрузка):</span><span class="sxs-lookup"><span data-stu-id="b6c22-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="b6c22-149">Для получения дополнительных сведений о данной команде, ознакомьтесь со статьей [Start – адсинксинкцикле](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="b6c22-150">Назначьте лицензии на телефонную систему учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="b6c22-151">В разделе [Назначение лицензий Microsoft Teams](/MicrosoftTeams/assign-teams-licenses) и [Назначение лицензий одному пользователю](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="b6c22-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="b6c22-152">Если вы назначаете номер телефона для учетной записи ресурса, вы можете использовать лицензию на виртуальную машину с свободной стоимостью для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b6c22-153">Это обеспечивает возможности телефонной системы для телефонных номеров на уровне Организации, а также позволяет создавать автосекретарь и возможности очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b6c22-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="b6c22-154">Назначьте номер службы учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6c22-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="b6c22-155">Используйте `Set-CsHybridApplicationEndpoint` команду, чтобы назначить учетной записи ресурса номер телефона (с параметром-LineURI).</span><span class="sxs-lookup"><span data-stu-id="b6c22-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="b6c22-156">Для получения дополнительных сведений о команде [Set – кшибридаппликатионендпоинт](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="b6c22-157">Чтобы назначить прямую маршрутизацию или номер гибридной учетной записи ресурса, используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="b6c22-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="b6c22-158">Учетной записи ресурса потребуется назначенный телефонный номер, если он будет назначен автосекретарею верхнего уровня или очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="b6c22-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="b6c22-159">Номера телефонов пользователей (абонентов) нельзя назначить учетной записи ресурса, можно использовать только сервисный платный или бесплатный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="b6c22-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="b6c22-160">Создайте службу телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-160">Create the Phone system service.</span></span> <span data-ttu-id="b6c22-161">Выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="b6c22-161">See one of the following:</span></span>

   - [<span data-ttu-id="b6c22-162">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b6c22-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="b6c22-163">Создание очереди облачных звонков</span><span class="sxs-lookup"><span data-stu-id="b6c22-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="b6c22-164">Свяжите учетную запись ресурса с выбранной ранее службой телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="b6c22-165">Пример реализации для малого бизнеса в [малом бизнесе — Настройка автосекретаря](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) и [примера для малого бизнеса Настройка очереди звонков](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="b6c22-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="b6c22-166">Создание учетной записи ресурса без номера телефона</span><span class="sxs-lookup"><span data-stu-id="b6c22-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="b6c22-167">В этом разделе описывается создание учетной записи ресурса, расположенной локально.</span><span class="sxs-lookup"><span data-stu-id="b6c22-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="b6c22-168">Создание учетной записи ресурса, размещенной в Интернете, обсуждается в разделе [Управление учетными записями ресурсов в Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span><span class="sxs-lookup"><span data-stu-id="b6c22-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="b6c22-169">Эти действия необходимы, если вы создаете новую систему службы телефонной системы или переопределяете структуру, изначально созданную в единой системе обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6c22-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="b6c22-170">Войдите на сервер переднего плана Skype для бизнеса и выполните следующие командлеты PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b6c22-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="b6c22-171">Создайте локальную учетную запись ресурса, выполнив `New-CsHybridApplicationEndpoint` командлет для каждой службы телефонной системы и присвойте каждой из них имя, SIP адрес и т. д.</span><span class="sxs-lookup"><span data-stu-id="b6c22-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="b6c22-172">Для получения дополнительных сведений о данной команде, ознакомьтесь со статьей [New – кшибридаппликатионендпоинт](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="b6c22-173">Необязательно После создания учетных записей ресурсов можно подождать, пока служба AD будет синхронизироваться между Интернетом и локальным, либо выполнить синхронизацию и перейти к настройке служб телефонной системы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b6c22-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="b6c22-174">Чтобы принудительно выполнить синхронизацию, выполните следующую команду на компьютере, на котором выполняется AAD Connect (если это еще не сделано, для запуска команды `import-module adsync` требуется загрузка):</span><span class="sxs-lookup"><span data-stu-id="b6c22-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="b6c22-175">Для получения дополнительных сведений о данной команде, ознакомьтесь со статьей [Start – адсинксинкцикле](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="b6c22-176">Создайте службу телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-176">Create the Phone system service.</span></span> <span data-ttu-id="b6c22-177">Выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="b6c22-177">See one of the following:</span></span>
   - [<span data-ttu-id="b6c22-178">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b6c22-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="b6c22-179">Создание очереди облачных звонков</span><span class="sxs-lookup"><span data-stu-id="b6c22-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="b6c22-180">Свяжите учетную запись ресурса и службу телефонной системы, выбранную ранее.</span><span class="sxs-lookup"><span data-stu-id="b6c22-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="b6c22-181">Пример реализации для малого бизнеса в [малом бизнесе — Настройка автосекретаря](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) и [примера для малого бизнеса Настройка очереди звонков](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="b6c22-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="b6c22-182">Тестирование реализации</span><span class="sxs-lookup"><span data-stu-id="b6c22-182">Test the implementation</span></span>

<span data-ttu-id="b6c22-183">Лучший способ проверить реализацию — позвонить на номер, настроенный для службы телефонной системы, и подключиться к одному из агентов или меню.</span><span class="sxs-lookup"><span data-stu-id="b6c22-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="b6c22-184">Вы также можете быстро помещать тестовый вызов с помощью **кнопки тест** в области действий центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="b6c22-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="b6c22-185">Если вы хотите внести изменения в службу телефонной системы, выберите ее и затем в области действий нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6c22-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="b6c22-186">Перемещение автосекретаря единой системы обмена сообщениями Exchange или очереди звонков в телефонную систему</span><span class="sxs-lookup"><span data-stu-id="b6c22-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="b6c22-187">Для переноса из единой системы обмена сообщениями Exchange в телефонную систему потребуется повторное создание структуры очереди вызовов и автосекретаря, непосредственно переключаясь из одной в другую.</span><span class="sxs-lookup"><span data-stu-id="b6c22-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="b6c22-188">Повторное внедрение набора очередей вызовов и автосекретарей:</span><span class="sxs-lookup"><span data-stu-id="b6c22-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="b6c22-189">Получите список всех автосекретарей единой системы обмена сообщениями Exchange и очередей звонков, выполнив следующую команду в системе Exchange 2013 или 2016, войдя в систему от имени администратора:</span><span class="sxs-lookup"><span data-stu-id="b6c22-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="b6c22-190">Для каждого списка очередей вызовов единой системы обмена сообщениями Exchange или автосекретаря запомните его место в структуре, параметрах и получение копий связанных звуков или текстовых файлов в речь (GUID в выходных данных — это имя папки, в которой хранятся файлы).</span><span class="sxs-lookup"><span data-stu-id="b6c22-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="b6c22-191">Эти сведения можно получить, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b6c22-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="b6c22-192">Чтобы узнать больше об этой команде, ознакомьтесь со [статьей Get – UMAutoAttendant используется](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="b6c22-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="b6c22-193">Полный список параметров, которые может потребоваться захватить, находится на сайте [UMAutoAttendant используется](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , но наиболее важные параметры для их пометки:</span><span class="sxs-lookup"><span data-stu-id="b6c22-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="b6c22-194">Рабочие часы</span><span class="sxs-lookup"><span data-stu-id="b6c22-194">Business hours</span></span>
    - <span data-ttu-id="b6c22-195">Нерабочие часы</span><span class="sxs-lookup"><span data-stu-id="b6c22-195">Non-business hours</span></span>
    - <span data-ttu-id="b6c22-196">Язык</span><span class="sxs-lookup"><span data-stu-id="b6c22-196">Language</span></span>
    - <span data-ttu-id="b6c22-197">Расписание праздников.</span><span class="sxs-lookup"><span data-stu-id="b6c22-197">Holiday schedule</span></span>

3. <span data-ttu-id="b6c22-198">Создайте новые локальные конечные точки, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="b6c22-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="b6c22-199">Назначьте автосекретарь верхнего уровня временному номеру для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="b6c22-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="b6c22-200">Настройте службу телефонной системы, которая использует конечные точки, как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="b6c22-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="b6c22-201">Вы можете использовать упражнения, приведенные в учебном руководстве с названием " [малый бизнес" — Настройка автосекретаря](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) для создания логической карты иерархий в старой системе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6c22-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="b6c22-202">Проверьте службу телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="b6c22-203">Повторно назначьте номер телефона, связанный с очередью вызовов единой системы обмена сообщениями или автосекретарем, соответствующей службе телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="b6c22-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="b6c22-204">На этом шаге, если вы уже выполнили миграцию голосовой почты единой системы обмена сообщениями, вы должны находиться в положении для перехода на Exchange Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b6c22-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c22-205">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c22-205">See Also</span></span>

[<span data-ttu-id="b6c22-206">Создание очереди облачных звонков</span><span class="sxs-lookup"><span data-stu-id="b6c22-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="b6c22-207">Что такое автосекретаря для облака?</span><span class="sxs-lookup"><span data-stu-id="b6c22-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="b6c22-208">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b6c22-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="b6c22-209">Планирование автосекретарей в облаке</span><span class="sxs-lookup"><span data-stu-id="b6c22-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="b6c22-210">Планирование очередей облачных вызовов</span><span class="sxs-lookup"><span data-stu-id="b6c22-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="b6c22-211">Планирование облачной службы голосовой почты для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="b6c22-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="b6c22-212">New — Кшибридаппликатионендпоинт</span><span class="sxs-lookup"><span data-stu-id="b6c22-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="b6c22-213">New — Ксонлинеаппликатионинстанце</span><span class="sxs-lookup"><span data-stu-id="b6c22-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="b6c22-214">[Управление учетными записями ресурсов в Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(для создания учетных записей ресурсов, размещенных в Интернете\)</span><span class="sxs-lookup"><span data-stu-id="b6c22-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
