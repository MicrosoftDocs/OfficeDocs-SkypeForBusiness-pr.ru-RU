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
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о перенаправке голоса.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196493"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="d57cb-103">Устройство ветвной ветви (SBA) для прямой маршрутинга</span><span class="sxs-lookup"><span data-stu-id="d57cb-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="d57cb-104">В редких случаях сайт клиента с прямой маршрутией для подключения к телефонной системе Майкрософт может привести к простою в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d57cb-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="d57cb-105">Предположим, что сайт клиента ,называемый ветвью, временно не может подключиться к Облаку Майкрософт с помощью прямой маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="d57cb-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="d57cb-106">Однако интрасеть в филиале по-прежнему работает полностью, и пользователи могут подключиться к контроллеру границы сеанса (SBC), который обеспечивает подключение по ННР.</span><span class="sxs-lookup"><span data-stu-id="d57cb-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="d57cb-107">В этой статье описано, как с помощью устройства SBA (Скайп с возможностью сбоя) продолжать звонить и принимать звонки по телефонной сети общего пользования (МСК) с помощью телефонной сети Майкрософт (SBA).</span><span class="sxs-lookup"><span data-stu-id="d57cb-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d57cb-108">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="d57cb-108">Prerequisites</span></span>

<span data-ttu-id="d57cb-109">Распространяемый код SBA предоставляется корпорацией Майкрософт поставщикам SBC, которые затем внедрят код в свои программы или распространят его отдельно, чтобы SBA запускался на отдельном VM-оборудовании.</span><span class="sxs-lookup"><span data-stu-id="d57cb-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="d57cb-110">Чтобы получить последнюю версию встроенного ПО "Пограничный контроллер сеанса" с внедренным устройством Ветвной линии Скайп, обратитесь к поставщику SBC.</span><span class="sxs-lookup"><span data-stu-id="d57cb-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="d57cb-111">Кроме того, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="d57cb-111">In addition, the following is required:</span></span>

- <span data-ttu-id="d57cb-112">Чтобы клиент Microsoft Teams на сайте филиала мог использовать потоки мультимедиа непосредственно с SBC, необходимо настроить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d57cb-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="d57cb-113">В SBA VM OS должен быть включен TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="d57cb-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="d57cb-114">Поддерживаемые клиенты Teams</span><span class="sxs-lookup"><span data-stu-id="d57cb-114">Supported Teams clients</span></span>

<span data-ttu-id="d57cb-115">Функция SBA поддерживается в следующих клиентах Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="d57cb-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="d57cb-116">Microsoft Teams для рабочего стола Windows</span><span class="sxs-lookup"><span data-stu-id="d57cb-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="d57cb-117">Классические версии Microsoft Teams для macOS</span><span class="sxs-lookup"><span data-stu-id="d57cb-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="d57cb-118">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="d57cb-118">How it works</span></span>

<span data-ttu-id="d57cb-119">Во время сбоя в Интернете клиент Teams должен автоматически переключиться на SBA, и постоянные звонки продолжатся без прерываний.</span><span class="sxs-lookup"><span data-stu-id="d57cb-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="d57cb-120">От пользователя не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d57cb-120">No action is required from the user.</span></span> <span data-ttu-id="d57cb-121">Как только клиент Teams обнаружит, что Интернет подключен, и все исходяющие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим службам Teams.</span><span class="sxs-lookup"><span data-stu-id="d57cb-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="d57cb-122">SBA загрузит собранные записи о звонках в облако, и история зовов обновится, и эта информация будет доступна для проверки администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="d57cb-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="d57cb-123">Если клиент Microsoft Teams работает в автономном режиме, доступны следующие функции, связанные со звонками:</span><span class="sxs-lookup"><span data-stu-id="d57cb-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="d57cb-124">Звонки по ННР через местные службы SBA и SBC с мультимедиа, которые проходят через SBC.</span><span class="sxs-lookup"><span data-stu-id="d57cb-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="d57cb-125">Получение звонков по ДНР через местные службы SBA или SBC с мультимедиа, которые проходят через SBC.</span><span class="sxs-lookup"><span data-stu-id="d57cb-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="d57cb-126">Удержание и возобновление звонков по ННР.</span><span class="sxs-lookup"><span data-stu-id="d57cb-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="d57cb-127">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d57cb-127">Configuration</span></span>

<span data-ttu-id="d57cb-128">Чтобы функция SBA работала, клиент Teams должен знать, какие SBAs доступны на каждом сайте филиала и какие SBAs назначены пользователям этого сайта.</span><span class="sxs-lookup"><span data-stu-id="d57cb-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="d57cb-129">Настройка может выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d57cb-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="d57cb-130">Создайте SBAs.</span><span class="sxs-lookup"><span data-stu-id="d57cb-130">Create the SBAs.</span></span>
2. <span data-ttu-id="d57cb-131">Создайте политику ветвей ветвей Teams.</span><span class="sxs-lookup"><span data-stu-id="d57cb-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="d57cb-132">Назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="d57cb-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="d57cb-133">Зарегистрируйте приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d57cb-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="d57cb-134">Вся настройка делается с помощью powerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d57cb-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="d57cb-135">(Центр администрирования Teams пока не поддерживает функцию SBA direct Routing.)</span><span class="sxs-lookup"><span data-stu-id="d57cb-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="d57cb-136">(Сведения о настройке SBC со ссылками на документацию поставщиков SBC см. в настройках граничного контроллера сеанса в конце этой статьи.)</span><span class="sxs-lookup"><span data-stu-id="d57cb-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="d57cb-137">Создание SBAs</span><span class="sxs-lookup"><span data-stu-id="d57cb-137">Create the SBAs</span></span>

<span data-ttu-id="d57cb-138">Для создания SBAs используется New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="d57cb-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="d57cb-139">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d57cb-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="d57cb-140">Параметр</span><span class="sxs-lookup"><span data-stu-id="d57cb-140">Parameter</span></span>| <span data-ttu-id="d57cb-141">Описание</span><span class="sxs-lookup"><span data-stu-id="d57cb-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d57cb-142">Identity</span><span class="sxs-lookup"><span data-stu-id="d57cb-142">Identity</span></span>  | <span data-ttu-id="d57cb-143">Удостоверение SBA</span><span class="sxs-lookup"><span data-stu-id="d57cb-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="d57cb-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="d57cb-144">Fqdn</span></span> | <span data-ttu-id="d57cb-145">The FQDN of the SBA</span><span class="sxs-lookup"><span data-stu-id="d57cb-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="d57cb-146">Сайт</span><span class="sxs-lookup"><span data-stu-id="d57cb-146">Site</span></span> | <span data-ttu-id="d57cb-147">TenantNetworkSite, на котором находится SBA</span><span class="sxs-lookup"><span data-stu-id="d57cb-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="d57cb-148">Описание</span><span class="sxs-lookup"><span data-stu-id="d57cb-148">Description</span></span> | <span data-ttu-id="d57cb-149">Свободное форматирование текста</span><span class="sxs-lookup"><span data-stu-id="d57cb-149">Free format text</span></span> |
|||

<span data-ttu-id="d57cb-150">Например:</span><span class="sxs-lookup"><span data-stu-id="d57cb-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="d57cb-151">Создание политики ветвей ветвей Teams</span><span class="sxs-lookup"><span data-stu-id="d57cb-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="d57cb-152">Для создания политики используется New-CsTeamsSurvivableBranchAppliancePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="d57cb-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d57cb-153">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d57cb-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="d57cb-154">Обратите внимание, что политика может содержать одно или несколько SBAs.</span><span class="sxs-lookup"><span data-stu-id="d57cb-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="d57cb-155">Параметр</span><span class="sxs-lookup"><span data-stu-id="d57cb-155">Parameter</span></span>| <span data-ttu-id="d57cb-156">Описание</span><span class="sxs-lookup"><span data-stu-id="d57cb-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d57cb-157">Identity</span><span class="sxs-lookup"><span data-stu-id="d57cb-157">Identity</span></span> | <span data-ttu-id="d57cb-158">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="d57cb-158">The identity of the policy</span></span> |
| <span data-ttu-id="d57cb-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="d57cb-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="d57cb-160">FQDN SBA на сайте</span><span class="sxs-lookup"><span data-stu-id="d57cb-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="d57cb-161">Например:</span><span class="sxs-lookup"><span data-stu-id="d57cb-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="d57cb-162">Вы можете добавлять и удалять SBAs из политики с помощью Set-CsTeamsSurvivableBranchAppliancePolicy-управления.</span><span class="sxs-lookup"><span data-stu-id="d57cb-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d57cb-163">Например:</span><span class="sxs-lookup"><span data-stu-id="d57cb-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="d57cb-164">Назначение политики пользователю</span><span class="sxs-lookup"><span data-stu-id="d57cb-164">Assign a policy to a user</span></span>

<span data-ttu-id="d57cb-165">Чтобы назначить политику отдельным пользователям, используйте Grant-CsTeamsSurvivableBranchAppliancePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="d57cb-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d57cb-166">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d57cb-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="d57cb-167">Параметр</span><span class="sxs-lookup"><span data-stu-id="d57cb-167">Parameter</span></span>| <span data-ttu-id="d57cb-168">Описание</span><span class="sxs-lookup"><span data-stu-id="d57cb-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d57cb-169">Identity</span><span class="sxs-lookup"><span data-stu-id="d57cb-169">Identity</span></span> | <span data-ttu-id="d57cb-170">Удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="d57cb-170">The identity of the user</span></span> |
| <span data-ttu-id="d57cb-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="d57cb-171">PolicyName</span></span> | <span data-ttu-id="d57cb-172">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="d57cb-172">The identity of the policy</span></span> |
||

<span data-ttu-id="d57cb-173">Например:</span><span class="sxs-lookup"><span data-stu-id="d57cb-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="d57cb-174">Вы можете удалить политику пользователя, $Null политику, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d57cb-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="d57cb-175">Регистрация приложения для SBA в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d57cb-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="d57cb-176">Чтобы другие SBA, используемые в клиенте, могли читать необходимые данные от Microsoft 365, необходимо зарегистрировать приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d57cb-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="d57cb-177">Дополнительные сведения о регистрации приложений см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="d57cb-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="d57cb-178">Разработка бизнес-приложений для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d57cb-178">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="d57cb-179">[Зарегистрируйте приложение на платформе удостоверений Майкрософт.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="d57cb-179">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="d57cb-180">Вам нужно зарегистрировать только одно приложение для использования всеми SBAs в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d57cb-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="d57cb-181">Для регистрации SBA требуются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d57cb-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="d57cb-182">ИД приложения (клиента)</span><span class="sxs-lookup"><span data-stu-id="d57cb-182">Application (client) ID</span></span> 
- <span data-ttu-id="d57cb-183">Секрет клиента</span><span class="sxs-lookup"><span data-stu-id="d57cb-183">Client secret</span></span> 

<span data-ttu-id="d57cb-184">Для приложения SBA следует помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="d57cb-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="d57cb-185">Имя может быть любым, что вы решаете.</span><span class="sxs-lookup"><span data-stu-id="d57cb-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="d57cb-186">Поддерживаемые типы учетных записей — только учетная запись в этом каталоге организации.</span><span class="sxs-lookup"><span data-stu-id="d57cb-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="d57cb-187">Uri web Redirect = ( Uri веб-перенаправления). https://login.microsoftonline.com/common/oauth2/nativeclient</span><span class="sxs-lookup"><span data-stu-id="d57cb-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="d57cb-188">Неявный маркеры предоставления = маркеры доступа и токены ИД.</span><span class="sxs-lookup"><span data-stu-id="d57cb-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="d57cb-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="d57cb-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="d57cb-190">Секрет клиента: вы можете использовать любое описание и срок действия.</span><span class="sxs-lookup"><span data-stu-id="d57cb-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="d57cb-191">Не забудьте скопировать секрет клиента сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="d57cb-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="d57cb-192">На вкладке "Обзор" отображается ИД приложения (клиента).</span><span class="sxs-lookup"><span data-stu-id="d57cb-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="d57cb-193">Затем выполните указанные далее действия.</span><span class="sxs-lookup"><span data-stu-id="d57cb-193">Then follow these steps:</span></span>

1. <span data-ttu-id="d57cb-194">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="d57cb-194">Register the application.</span></span>
2. <span data-ttu-id="d57cb-195">Установите неявные маркеры предоставления.</span><span class="sxs-lookup"><span data-stu-id="d57cb-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="d57cb-196">За установите разрешения API.</span><span class="sxs-lookup"><span data-stu-id="d57cb-196">Set the API permissions.</span></span>
4. <span data-ttu-id="d57cb-197">Создайте секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="d57cb-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="d57cb-198">Настройка граничного контроллера сеанса</span><span class="sxs-lookup"><span data-stu-id="d57cb-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="d57cb-199">Пошаговую инструкцию по настройке граничного геймпада сеанса с помощью внедренного ветвного устройства см. в документации вашего поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="d57cb-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="d57cb-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d57cb-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="d57cb-201">Лента</span><span class="sxs-lookup"><span data-stu-id="d57cb-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="d57cb-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="d57cb-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="d57cb-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="d57cb-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="d57cb-204">Проблемы с отчетами</span><span class="sxs-lookup"><span data-stu-id="d57cb-204">Reporting issues</span></span>

<span data-ttu-id="d57cb-205">Сообщайте о проблемах в службе поддержки поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="d57cb-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="d57cb-206">Сообщая о проблеме, указать, что у вас установлена ветвная устройство с возможностью ветвь Скайп.</span><span class="sxs-lookup"><span data-stu-id="d57cb-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d57cb-207">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="d57cb-207">Known issues</span></span>

- <span data-ttu-id="d57cb-208">Применение новых устройств с ветвными устройствами с использованием ветвных устройств с подавными системами может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="d57cb-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="d57cb-209">Когда вы назначаете пользователю политику с возможностью ветвного устройства с возможностью сбоя, может потребоваться некоторое время, прежде чем SBA будет показан в выходе Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="d57cb-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="d57cb-210">Обратный просмотр номеров для контактов Azure AD не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d57cb-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="d57cb-211">SBA не поддерживает параметры переадваровки параметров.</span><span class="sxs-lookup"><span data-stu-id="d57cb-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="d57cb-212">Экстренные вызовы на номера, настроенные для динамических экстренных вызовов (E911), не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d57cb-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="d57cb-213">Результат Get-CsOnlineUser TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="d57cb-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
