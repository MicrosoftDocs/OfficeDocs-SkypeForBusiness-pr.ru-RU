---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о решениях по маршрутиации голоса.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620734"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="0c0c9-103">Устройство с ветвью (SBA) для прямой маршрутки — общедоступный предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="0c0c9-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="0c0c9-104">Это общедоступный предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-104">This is a public preview release.</span></span>

<span data-ttu-id="0c0c9-105">В редких случаях сайт клиента, использующий прямую маршрутику для подключения к телефонной системе Майкрософт, может привести к с отключению интернета.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="0c0c9-106">Предположим, что сайт клиента ,называемый ветвью, временно не может подключиться к Облаку Майкрософт с помощью прямой маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="0c0c9-107">Однако интрасеть внутри ветви по-прежнему работает полностью, и пользователи могут подключаться к контроллеру границы сеанса (SBC), который обеспечивает подключение по ННР.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="0c0c9-108">В этой статье описано, как с помощью устройства SBA (Скайп с возможностью сбоя) продолжать звонить и принимать звонки по телефонной сети общего пользования (МСК) с помощью телефонной сети Майкрософт (SBA).</span><span class="sxs-lookup"><span data-stu-id="0c0c9-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c0c9-109">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="0c0c9-109">Prerequisites</span></span>

<span data-ttu-id="0c0c9-110">Распространяемый код SBA предоставляется корпорацией Майкрософт поставщикам SBC, которые затем внедрят код в свои программы или распространят его отдельно, чтобы SBA запускался на отдельном VM-оборудовании.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="0c0c9-111">Чтобы получить последнюю версию встроенного ПО "Пограничный контроллер сеанса" с внедренным устройством Ветвной линии Скайп, обратитесь к поставщику SBC.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="0c0c9-112">Кроме того, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-112">In addition, the following is required:</span></span>

- <span data-ttu-id="0c0c9-113">Чтобы клиент Microsoft Teams на сайте филиала мог использовать потоки мультимедиа непосредственно с SBC, необходимо настроить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="0c0c9-114">В SBA VM OS должен быть включен TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="0c0c9-115">Поддерживаемые клиенты Teams</span><span class="sxs-lookup"><span data-stu-id="0c0c9-115">Supported Teams clients</span></span>

<span data-ttu-id="0c0c9-116">Функция SBA поддерживается в следующих клиентах Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="0c0c9-117">Microsoft Teams для рабочего стола Windows</span><span class="sxs-lookup"><span data-stu-id="0c0c9-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="0c0c9-118">Классические версии Microsoft Teams для macOS</span><span class="sxs-lookup"><span data-stu-id="0c0c9-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="0c0c9-119">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="0c0c9-119">How it works</span></span>

<span data-ttu-id="0c0c9-120">Во время сбоя в Интернете клиент Teams должен автоматически переключиться на SBA, и постоянные звонки должны продолжаться без прерываний.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="0c0c9-121">От пользователя не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-121">No action is required from the user.</span></span> <span data-ttu-id="0c0c9-122">Как только клиент Teams обнаружит, что Интернет подключен, и все исходяющие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим службам Teams.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="0c0c9-123">SBA загрузит собранные записи о звонках в облако, и история зовов обновится, и эта информация будет доступна для проверки администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="0c0c9-124">Если клиент Microsoft Teams работает в автономном режиме, доступны следующие функции, связанные со звонками:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="0c0c9-125">Звонки через ДНР через местные службы SBA и SBC с мультимедиа, которые проходят через SBC.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="0c0c9-126">Получение звонков по ДНР через местные службы SBA или SBC с мультимедиа, которые проходят через SBC.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="0c0c9-127">Удержание и возобновление звонков по ННР.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="0c0c9-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0c0c9-128">Configuration</span></span>

<span data-ttu-id="0c0c9-129">Чтобы функция SBA работала, клиент Teams должен знать, какие SBAs доступны на каждом сайте филиала и какие SBAs назначены пользователям на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="0c0c9-130">Конфигурация может выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="0c0c9-131">Создайте SBAs.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-131">Create the SBAs.</span></span>
2. <span data-ttu-id="0c0c9-132">Создайте политику ветвей ветвей Teams.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="0c0c9-133">Назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="0c0c9-134">Зарегистрируйте приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="0c0c9-135">Вся настройка делается с помощью powerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="0c0c9-136">(Центр администрирования Teams пока не поддерживает функцию SBA direct Routing.)</span><span class="sxs-lookup"><span data-stu-id="0c0c9-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="0c0c9-137">(Сведения о настройке SBC со ссылками на документацию поставщиков SBC см. в настройках граничного контроллера сеанса в конце этой статьи.)</span><span class="sxs-lookup"><span data-stu-id="0c0c9-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="0c0c9-138">Создание SBAs</span><span class="sxs-lookup"><span data-stu-id="0c0c9-138">Create the SBAs</span></span>

<span data-ttu-id="0c0c9-139">Для создания SBAs используется New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="0c0c9-140">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="0c0c9-141">Параметр</span><span class="sxs-lookup"><span data-stu-id="0c0c9-141">Parameter</span></span>| <span data-ttu-id="0c0c9-142">Описание</span><span class="sxs-lookup"><span data-stu-id="0c0c9-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="0c0c9-143">Identity</span><span class="sxs-lookup"><span data-stu-id="0c0c9-143">Identity</span></span>  | <span data-ttu-id="0c0c9-144">Удостоверение SBA</span><span class="sxs-lookup"><span data-stu-id="0c0c9-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="0c0c9-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="0c0c9-145">Fqdn</span></span> | <span data-ttu-id="0c0c9-146">The FQDN of the SBA</span><span class="sxs-lookup"><span data-stu-id="0c0c9-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="0c0c9-147">Сайт</span><span class="sxs-lookup"><span data-stu-id="0c0c9-147">Site</span></span> | <span data-ttu-id="0c0c9-148">TenantNetworkSite, на котором находится SBA</span><span class="sxs-lookup"><span data-stu-id="0c0c9-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="0c0c9-149">Описание</span><span class="sxs-lookup"><span data-stu-id="0c0c9-149">Description</span></span> | <span data-ttu-id="0c0c9-150">Текст с бесплатным форматированием</span><span class="sxs-lookup"><span data-stu-id="0c0c9-150">Free format text</span></span> |
|||

<span data-ttu-id="0c0c9-151">Например:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="0c0c9-152">Создание политики ветвей ветвей Teams</span><span class="sxs-lookup"><span data-stu-id="0c0c9-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="0c0c9-153">Для создания политики используется New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="0c0c9-154">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="0c0c9-155">Обратите внимание, что политика может содержать одно или несколько SBAs.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="0c0c9-156">Параметр</span><span class="sxs-lookup"><span data-stu-id="0c0c9-156">Parameter</span></span>| <span data-ttu-id="0c0c9-157">Описание</span><span class="sxs-lookup"><span data-stu-id="0c0c9-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="0c0c9-158">Identity</span><span class="sxs-lookup"><span data-stu-id="0c0c9-158">Identity</span></span> | <span data-ttu-id="0c0c9-159">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="0c0c9-159">The identity of the policy</span></span> |
| <span data-ttu-id="0c0c9-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="0c0c9-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="0c0c9-161">FQDN SBA на сайте</span><span class="sxs-lookup"><span data-stu-id="0c0c9-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="0c0c9-162">Например:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="0c0c9-163">Вы можете добавлять и удалять SBAs из политики с помощью Set-CsTeamsSurvivableBranchAppliancePolicy-управления.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="0c0c9-164">Например:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="0c0c9-165">Назначение политики пользователю</span><span class="sxs-lookup"><span data-stu-id="0c0c9-165">Assign a policy to a user</span></span>

<span data-ttu-id="0c0c9-166">Чтобы назначить политику отдельным пользователям, используйте Grant-CsTeamsSurvivableBranchAppliancePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="0c0c9-167">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="0c0c9-168">Параметр</span><span class="sxs-lookup"><span data-stu-id="0c0c9-168">Parameter</span></span>| <span data-ttu-id="0c0c9-169">Описание</span><span class="sxs-lookup"><span data-stu-id="0c0c9-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="0c0c9-170">Identity</span><span class="sxs-lookup"><span data-stu-id="0c0c9-170">Identity</span></span> | <span data-ttu-id="0c0c9-171">Удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="0c0c9-171">The identity of the user</span></span> |
| <span data-ttu-id="0c0c9-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="0c0c9-172">PolicyName</span></span> | <span data-ttu-id="0c0c9-173">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="0c0c9-173">The identity of the policy</span></span> |
||

<span data-ttu-id="0c0c9-174">Например:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="0c0c9-175">Вы можете удалить политику пользователя, $Null политику, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="0c0c9-176">Регистрация приложения для SBA в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c0c9-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="0c0c9-177">Чтобы другие SBA, используемые в клиенте, могли читать необходимые данные от Microsoft 365, необходимо зарегистрировать приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="0c0c9-178">Дополнительные сведения о регистрации приложений см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="0c0c9-179">Разработка бизнес-приложений для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c0c9-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="0c0c9-180">[Зарегистрируйте приложение на платформе удостоверений Майкрософт.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="0c0c9-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="0c0c9-181">Вам нужно зарегистрировать только одно приложение для использования всеми SBAs в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="0c0c9-182">Для регистрации SBA требуются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="0c0c9-183">ИД приложения (клиента)</span><span class="sxs-lookup"><span data-stu-id="0c0c9-183">Application (client) ID</span></span> 
- <span data-ttu-id="0c0c9-184">Секрет клиента</span><span class="sxs-lookup"><span data-stu-id="0c0c9-184">Client secret</span></span> 

<span data-ttu-id="0c0c9-185">Для приложения SBA следует помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="0c0c9-186">Имя может быть любым, что вы решаете.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="0c0c9-187">Поддерживаемые типы учетных записей — только учетная запись в этом каталоге организации.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="0c0c9-188">Uri web Redirect = ( Uri веб-перенаправления). https://login.microsoftonline.com/common/oauth2/nativeclient</span><span class="sxs-lookup"><span data-stu-id="0c0c9-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="0c0c9-189">Неявный маркеры предоставления = маркеры доступа и токены ИД.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="0c0c9-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="0c0c9-191">Секрет клиента: вы можете использовать любое описание и срок действия.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="0c0c9-192">Не забудьте скопировать секрет клиента сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="0c0c9-193">На вкладке "Обзор" отображается ИД приложения (клиента).</span><span class="sxs-lookup"><span data-stu-id="0c0c9-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="0c0c9-194">Затем выполните указанные далее действия.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-194">Then follow these steps:</span></span>

1. <span data-ttu-id="0c0c9-195">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-195">Register the application.</span></span>
2. <span data-ttu-id="0c0c9-196">Установите неявные маркеры предоставления.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="0c0c9-197">За установите разрешения API.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-197">Set the API permissions.</span></span>
4. <span data-ttu-id="0c0c9-198">Создайте секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="0c0c9-199">Настройка граничного контроллера сеанса</span><span class="sxs-lookup"><span data-stu-id="0c0c9-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="0c0c9-200">Пошаговую инструкцию по настройке контроллера границы сеанса с помощью внедренного ветвного устройства см. в документации поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="0c0c9-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="0c0c9-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="0c0c9-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="0c0c9-202">Лента</span><span class="sxs-lookup"><span data-stu-id="0c0c9-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="0c0c9-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="0c0c9-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="0c0c9-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="0c0c9-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="0c0c9-205">Проблемы с отчетами</span><span class="sxs-lookup"><span data-stu-id="0c0c9-205">Reporting issues</span></span>

<span data-ttu-id="0c0c9-206">Сообщайте о проблемах в службе поддержки поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="0c0c9-207">Сообщая о проблеме, указать, что у вас установлена ветвная устройство Скайп.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0c0c9-208">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="0c0c9-208">Known issues</span></span>

- <span data-ttu-id="0c0c9-209">Применение новых устройств с ветвными устройствами с использованием ветвных устройств с подавными системами может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="0c0c9-210">Когда вы назначаете пользователю политику "Сетчивая устройство", может потребоваться некоторое время, прежде чем SBA будет показан в выходе Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="0c0c9-211">Обратный просмотр номеров для контактов Azure AD не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="0c0c9-212">SBA не поддерживает параметры переадваровки параметров.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="0c0c9-213">Экстренные вызовы на номера, настроенные для динамических экстренных вызовов (E911), не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="0c0c9-214">Результат Get-CsOnlineUser TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="0c0c9-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
