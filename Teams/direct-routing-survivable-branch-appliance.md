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
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о перенаправке голосовой связи.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589243"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="b2d07-103">Ветвное устройство (SBA) для прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="b2d07-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="b2d07-104">Иногда на сайте клиента с использованием прямой маршрутии для подключения к Телефон (Майкрософт) система может возникнуть скайп в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b2d07-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="b2d07-105">Предположим, что сайт клиента , называемый ветвью, временно не может подключиться к Microsoft Cloud с помощью прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="b2d07-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="b2d07-106">Однако интрасеть внутри ветви по-прежнему работает полностью, и пользователи могут подключиться к контроллеру границы сеанса (SBC), который обеспечивает подключение по STN.</span><span class="sxs-lookup"><span data-stu-id="b2d07-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="b2d07-107">В этой статье описано, как с помощью устройства SBA (СР) можно продолжать звонить и принимать звонки по телефонной сети общего пользования (PSTN) в случае сбоя в системе Телефон (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="b2d07-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2d07-108">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="b2d07-108">Prerequisites</span></span>

<span data-ttu-id="b2d07-109">Код SBA предоставляется корпорацией Майкрософт поставщикам SBC, которые затем внедрили код в свое программное обеспечение или распространяли его отдельно для запуска SBA на отдельном VM-устройстве или оборудовании.</span><span class="sxs-lookup"><span data-stu-id="b2d07-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="b2d07-110">Чтобы получить последнюю версию встроенного постройного постройки "Контроллер границы сеанса" с внедренным устройством ветвной ветви "Ветвь", обратитесь к поставщику SBC.</span><span class="sxs-lookup"><span data-stu-id="b2d07-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="b2d07-111">Кроме того, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="b2d07-111">In addition, the following is required:</span></span>

- <span data-ttu-id="b2d07-112">Чтобы клиент Microsoft Teams на сайте филиала мог иметь поток мультимедиа непосредственно с SBC, необходимо настроить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b2d07-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="b2d07-113">В SBA VM OS должна быть включена TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="b2d07-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="b2d07-114">Поддерживаемые Teams клиентов</span><span class="sxs-lookup"><span data-stu-id="b2d07-114">Supported Teams clients</span></span>

<span data-ttu-id="b2d07-115">Функция SBA поддерживается в следующих клиентах Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="b2d07-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="b2d07-116">Microsoft Teams Windows рабочего стола</span><span class="sxs-lookup"><span data-stu-id="b2d07-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="b2d07-117">Microsoft Teams macOS</span><span class="sxs-lookup"><span data-stu-id="b2d07-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="b2d07-118">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="b2d07-118">How it works</span></span>

<span data-ttu-id="b2d07-119">Во время сбоя в Teams клиент должен автоматически переключиться на SBA, а постоянные звонки должны продолжаться без прерываний.</span><span class="sxs-lookup"><span data-stu-id="b2d07-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="b2d07-120">Пользователю не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="b2d07-120">No action is required from the user.</span></span> <span data-ttu-id="b2d07-121">Как только клиент Teams обнаружит подключение к Интернету и все исходяющие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим Teams службам.</span><span class="sxs-lookup"><span data-stu-id="b2d07-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="b2d07-122">SBA загрузит собранные записи данных об звонках в облако, и история зовов будет обновлена, чтобы эта информация была доступна для проверки администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="b2d07-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="b2d07-123">Если клиент Microsoft Teams в автономном режиме, доступны следующие функции, связанные со звонками:</span><span class="sxs-lookup"><span data-stu-id="b2d07-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="b2d07-124">Звонки по ННП через локальный SBA или SBC с потоком мультимедиа через SBC.</span><span class="sxs-lookup"><span data-stu-id="b2d07-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="b2d07-125">Прием звонков по ДНР через локальный SBA или SBC с потоком мультимедиа через SBC.</span><span class="sxs-lookup"><span data-stu-id="b2d07-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="b2d07-126">Удержание и возобновление звонков по ОКП.</span><span class="sxs-lookup"><span data-stu-id="b2d07-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="b2d07-127">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b2d07-127">Configuration</span></span>

<span data-ttu-id="b2d07-128">Чтобы функция SBA работала, Teams должен знать, какие SBAs доступны на каждом сайте филиала и какие они назначены пользователям на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="b2d07-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="b2d07-129">Для настройки выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b2d07-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="b2d07-130">Создайте SBAs.</span><span class="sxs-lookup"><span data-stu-id="b2d07-130">Create the SBAs.</span></span>
2. <span data-ttu-id="b2d07-131">Создайте политику Teams ветвей ветвей.</span><span class="sxs-lookup"><span data-stu-id="b2d07-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="b2d07-132">Назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="b2d07-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="b2d07-133">Зарегистрируйте приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2d07-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="b2d07-134">Вся настройка делается с Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2d07-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="b2d07-135">(Центр администрирования Teams пока не поддерживает функцию SBA прямой маршрутии.)</span><span class="sxs-lookup"><span data-stu-id="b2d07-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="b2d07-136">(Сведения о настройке SBC со ссылками на документацию поставщиков SBC см. в статье Настройка контроллера границы сеанса в конце этой статьи.)</span><span class="sxs-lookup"><span data-stu-id="b2d07-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="b2d07-137">Создание SBAs</span><span class="sxs-lookup"><span data-stu-id="b2d07-137">Create the SBAs</span></span>

<span data-ttu-id="b2d07-138">Для создания SBAs используется New-CsTeamsSurvivableBranchAppliance SBAs.</span><span class="sxs-lookup"><span data-stu-id="b2d07-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="b2d07-139">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b2d07-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="b2d07-140">Параметр</span><span class="sxs-lookup"><span data-stu-id="b2d07-140">Parameter</span></span>| <span data-ttu-id="b2d07-141">Описание</span><span class="sxs-lookup"><span data-stu-id="b2d07-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="b2d07-142">Identity</span><span class="sxs-lookup"><span data-stu-id="b2d07-142">Identity</span></span>  | <span data-ttu-id="b2d07-143">Удостоверение SBA</span><span class="sxs-lookup"><span data-stu-id="b2d07-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="b2d07-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="b2d07-144">Fqdn</span></span> | <span data-ttu-id="b2d07-145">The FQDN of the SBA</span><span class="sxs-lookup"><span data-stu-id="b2d07-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="b2d07-146">Сайт</span><span class="sxs-lookup"><span data-stu-id="b2d07-146">Site</span></span> | <span data-ttu-id="b2d07-147">TenantNetworkSite, на котором находится SBA</span><span class="sxs-lookup"><span data-stu-id="b2d07-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="b2d07-148">Описание</span><span class="sxs-lookup"><span data-stu-id="b2d07-148">Description</span></span> | <span data-ttu-id="b2d07-149">Свободный формат текста</span><span class="sxs-lookup"><span data-stu-id="b2d07-149">Free format text</span></span> |
|||

<span data-ttu-id="b2d07-150">Например:</span><span class="sxs-lookup"><span data-stu-id="b2d07-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="b2d07-151">Создание политики Teams ветвей</span><span class="sxs-lookup"><span data-stu-id="b2d07-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="b2d07-152">Чтобы создать политику, используйте New-CsTeamsSurvivableBranchAppliancePolicy политики.</span><span class="sxs-lookup"><span data-stu-id="b2d07-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="b2d07-153">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b2d07-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="b2d07-154">Обратите внимание, что политика может содержать один или несколько SBAs.</span><span class="sxs-lookup"><span data-stu-id="b2d07-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="b2d07-155">Параметр</span><span class="sxs-lookup"><span data-stu-id="b2d07-155">Parameter</span></span>| <span data-ttu-id="b2d07-156">Описание</span><span class="sxs-lookup"><span data-stu-id="b2d07-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="b2d07-157">Identity</span><span class="sxs-lookup"><span data-stu-id="b2d07-157">Identity</span></span> | <span data-ttu-id="b2d07-158">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="b2d07-158">The identity of the policy</span></span> |
| <span data-ttu-id="b2d07-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="b2d07-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="b2d07-160">FQDN SBA на сайте</span><span class="sxs-lookup"><span data-stu-id="b2d07-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="b2d07-161">Например:</span><span class="sxs-lookup"><span data-stu-id="b2d07-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="b2d07-162">Вы можете добавить или удалить SBAs из политики с помощью Set-CsTeamsSurvivableBranchAppliancePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="b2d07-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="b2d07-163">Например:</span><span class="sxs-lookup"><span data-stu-id="b2d07-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="b2d07-164">Назначение политики пользователю</span><span class="sxs-lookup"><span data-stu-id="b2d07-164">Assign a policy to a user</span></span>

<span data-ttu-id="b2d07-165">Чтобы назначить политику отдельным пользователям, используйте Grant-CsTeamsSurvivableBranchAppliancePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="b2d07-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="b2d07-166">Этот cmdlet имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b2d07-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="b2d07-167">Параметр</span><span class="sxs-lookup"><span data-stu-id="b2d07-167">Parameter</span></span>| <span data-ttu-id="b2d07-168">Описание</span><span class="sxs-lookup"><span data-stu-id="b2d07-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="b2d07-169">Identity</span><span class="sxs-lookup"><span data-stu-id="b2d07-169">Identity</span></span> | <span data-ttu-id="b2d07-170">Удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="b2d07-170">The identity of the user</span></span> |
| <span data-ttu-id="b2d07-171">Имя политики</span><span class="sxs-lookup"><span data-stu-id="b2d07-171">PolicyName</span></span> | <span data-ttu-id="b2d07-172">Удостоверение политики</span><span class="sxs-lookup"><span data-stu-id="b2d07-172">The identity of the policy</span></span> |
||

<span data-ttu-id="b2d07-173">Например:</span><span class="sxs-lookup"><span data-stu-id="b2d07-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="b2d07-174">Вы можете удалить политику пользователя, $Null политику, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b2d07-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="b2d07-175">Зарегистрируйте приложение для SBA в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2d07-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="b2d07-176">Чтобы различные SBAs, используемые в клиенте, могли читать необходимые данные из Microsoft 365, необходимо зарегистрировать приложение для SBA в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2d07-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="b2d07-177">Дополнительные сведения о регистрации приложений см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="b2d07-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="b2d07-178">Разработка бизнес-приложений для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2d07-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="b2d07-179">[Зарегистрируйте приложение в платформа удостоверений Майкрософт](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="b2d07-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="b2d07-180">Вам нужно зарегистрировать только одно приложение для использования всеми SBAs в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b2d07-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="b2d07-181">Для регистрации SBA необходимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b2d07-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="b2d07-182">ИД приложения (клиента)</span><span class="sxs-lookup"><span data-stu-id="b2d07-182">Application (client) ID</span></span> 
- <span data-ttu-id="b2d07-183">Секрет клиента</span><span class="sxs-lookup"><span data-stu-id="b2d07-183">Client secret</span></span> 

<span data-ttu-id="b2d07-184">В приложении SBA помните следующее:</span><span class="sxs-lookup"><span data-stu-id="b2d07-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="b2d07-185">Имя может быть любым, что вы решаете.</span><span class="sxs-lookup"><span data-stu-id="b2d07-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="b2d07-186">Поддерживаемые типы учетных записей = Учетная запись только в этом организационном каталоге.</span><span class="sxs-lookup"><span data-stu-id="b2d07-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="b2d07-187">Uri перенаправления в Интернете = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="b2d07-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="b2d07-188">Неявные маркеры предоставления = маркеры доступа и маркеры ИД.</span><span class="sxs-lookup"><span data-stu-id="b2d07-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="b2d07-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="b2d07-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="b2d07-190">Секрет клиента: вы можете использовать любое описание и срок действия.</span><span class="sxs-lookup"><span data-stu-id="b2d07-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="b2d07-191">Не забудьте скопировать секрет клиента сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="b2d07-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="b2d07-192">На вкладке Обзор отображается ИД приложения (клиента).</span><span class="sxs-lookup"><span data-stu-id="b2d07-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="b2d07-193">Затем выполните указанные далее действия.</span><span class="sxs-lookup"><span data-stu-id="b2d07-193">Then follow these steps:</span></span>

1. <span data-ttu-id="b2d07-194">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="b2d07-194">Register the application.</span></span>
2. <span data-ttu-id="b2d07-195">Установите неявные маркеры предоставления.</span><span class="sxs-lookup"><span data-stu-id="b2d07-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="b2d07-196">Настройка разрешений API.</span><span class="sxs-lookup"><span data-stu-id="b2d07-196">Set the API permissions.</span></span>
4. <span data-ttu-id="b2d07-197">Создайте секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="b2d07-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="b2d07-198">Настройка контроллера границы сеанса</span><span class="sxs-lookup"><span data-stu-id="b2d07-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="b2d07-199">Пошаговая инструкция по настройке геймпада границы сеанса с помощью внедренного ветвного устройства с возможностью ветвей с возможностью ветвей с возможностью ветвячих устройств см. в документации, предоставленной поставщиком SBC:</span><span class="sxs-lookup"><span data-stu-id="b2d07-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="b2d07-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="b2d07-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="b2d07-201">Ленты</span><span class="sxs-lookup"><span data-stu-id="b2d07-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="b2d07-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="b2d07-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="b2d07-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="b2d07-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="b2d07-204">Отчеты о проблемах</span><span class="sxs-lookup"><span data-stu-id="b2d07-204">Reporting issues</span></span>

<span data-ttu-id="b2d07-205">Сообщить о проблемах в организацию службы поддержки поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="b2d07-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="b2d07-206">Сообщая о проблеме, указать, что у вас установлено устройство ветвной ветви с возможностью ветвей с</span><span class="sxs-lookup"><span data-stu-id="b2d07-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b2d07-207">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="b2d07-207">Known issues</span></span>

- <span data-ttu-id="b2d07-208">После добавления новых устройств для ветвей с использованием ветвей с использованием в политиках ветвной ветви может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="b2d07-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="b2d07-209">Когда вы назначаете пользователю политику "Устройство ветвной ветвной ветви с возможностью ветвей с возможностью ветвей", может потребоваться некоторое время, прежде чем она будет показана в результатах Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="b2d07-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="b2d07-210">Обратный просмотр номеров для контактов Azure AD не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b2d07-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="b2d07-211">SBA не поддерживает параметры переад вызовов.</span><span class="sxs-lookup"><span data-stu-id="b2d07-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="b2d07-212">Звонок на экстренный номер, настроенный для динамических экстренных вызовов (E911), не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b2d07-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
