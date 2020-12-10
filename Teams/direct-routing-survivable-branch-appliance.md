---
title: Прямая маршрутизация SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Ознакомьтесь с дополнительными сведениями о прямой маршрутизации, такими как конфигурация, требования к развертыванию, необходимые основные решения для развертывания и рекомендации по маршрутизации голосовой связи.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611793"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="417d0-103">Бесперебойно работающее устройство филиала (SBA) для прямой маршрутизации — общедоступная Предварительная версия</span><span class="sxs-lookup"><span data-stu-id="417d0-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="417d0-104">Это общедоступная Предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="417d0-104">This is a public preview release.</span></span>

<span data-ttu-id="417d0-105">Иногда сайт клиента, использующий прямую маршрутизацию для подключения к телефонной системе Microsoft, может столкнуться со сбоями в Интернете.</span><span class="sxs-lookup"><span data-stu-id="417d0-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="417d0-106">Предполагается, что сайт клиента (филиал) временно не может подключаться к облаку Microsoft с помощью прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="417d0-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="417d0-107">Тем не менее, интрасеть внутри ветви по-прежнему работает полностью, и пользователи могут подключаться к контроллеру границ сеанса (SBC), обеспечивающему подключение по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="417d0-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="417d0-108">В этой статье описано, как использовать бесперебойно работающее устройство филиала (SBA), чтобы система Microsoft Phone System продолжала совершать и принимать вызовы по коммутируемой телефонной сети (PSTN) в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="417d0-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="417d0-109">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="417d0-109">Prerequisites</span></span>

<span data-ttu-id="417d0-110">SBA является распространяемым кодом, предоставленным корпорацией Майкрософт поставщикам SBC, которые затем внедряют код в микропрограмму своего SBCs.</span><span class="sxs-lookup"><span data-stu-id="417d0-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="417d0-111">Чтобы получить последнюю версию встроенного микрокода контроллера границы сеанса с помощью встроенного устройства с бесперебойной подразделением, обратитесь к поставщику SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="417d0-112">Кроме того, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="417d0-112">In addition, the following is required:</span></span>

- <span data-ttu-id="417d0-113">Необходимо настроить SBC для обхода мультимедиа, чтобы убедиться в том, что в клиенте Microsoft Teams на сайте филиала мультимедиа можно переносить непосредственно с помощью SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="417d0-114">В ОС SBA VM должна быть включена поддержка TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="417d0-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="417d0-115">Поддерживаемые клиенты Teams</span><span class="sxs-lookup"><span data-stu-id="417d0-115">Supported Teams clients</span></span>

<span data-ttu-id="417d0-116">Функция SBA поддерживается следующими клиентами Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="417d0-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="417d0-117">Классическое приложение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="417d0-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="417d0-118">Microsoft Teams macOS Desktop</span><span class="sxs-lookup"><span data-stu-id="417d0-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="417d0-119">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="417d0-119">How it works</span></span>

<span data-ttu-id="417d0-120">Во время отключения в Интернете клиент Teams должен автоматически переключаться на SBA, а текущие звонки должны продолжаться без перерывов.</span><span class="sxs-lookup"><span data-stu-id="417d0-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="417d0-121">Пользователю не требуется предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="417d0-121">No action is required from the user.</span></span> <span data-ttu-id="417d0-122">После того как клиент Teams обнаружит, что Интернет и все исходящие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим службам Teams.</span><span class="sxs-lookup"><span data-stu-id="417d0-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="417d0-123">SBA отправит собранные записи данных о звонке в облако и журнал звонков будут обновлены таким образом, чтобы эта информация была доступна для проверки администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="417d0-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="417d0-124">Если клиент Microsoft Teams работает в автономном режиме, доступны следующие функции, связанные с вызовом:</span><span class="sxs-lookup"><span data-stu-id="417d0-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="417d0-125">Совершение КОММУТИРУЕМых звонков через местные SBA/SBC с мультимедиа, передаваемым через SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="417d0-126">Получение звонков по коммутируемой телефонной связи через местные SBA/SBC с мультимедиа, передаваемым через SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="417d0-127">Удержание и возобновление звонков по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="417d0-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="417d0-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="417d0-128">Configuration</span></span>

<span data-ttu-id="417d0-129">Чтобы функция SBA работала, клиенту Teams нужно знать, какие SBAs доступны в каждом сайте филиала, и какие SBAs назначены пользователям на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="417d0-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="417d0-130">Ниже указаны этапы настройки.</span><span class="sxs-lookup"><span data-stu-id="417d0-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="417d0-131">Создайте SBAs.</span><span class="sxs-lookup"><span data-stu-id="417d0-131">Create the SBAs.</span></span>
2. <span data-ttu-id="417d0-132">Создание политики бесперебойной работы филиалов Teams.</span><span class="sxs-lookup"><span data-stu-id="417d0-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="417d0-133">Назначение политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="417d0-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="417d0-134">Зарегистрируйте приложение для SBA с помощью Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="417d0-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="417d0-135">Все настройки осуществляется с помощью командлетов PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="417d0-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="417d0-136">(Центр администрирования Teams пока не поддерживает функцию прямой маршрутизации SBA.)</span><span class="sxs-lookup"><span data-stu-id="417d0-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="417d0-137">(Дополнительные сведения о настройке SBC и ссылки на документацию поставщика SBC см. в разделе Конфигурация контроллера границ сеанса в конце этой статьи.)</span><span class="sxs-lookup"><span data-stu-id="417d0-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="417d0-138">Создание SBAs</span><span class="sxs-lookup"><span data-stu-id="417d0-138">Create the SBAs</span></span>

<span data-ttu-id="417d0-139">Чтобы создать SBAs, вы будете использовать командлет New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="417d0-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="417d0-140">Этот командлет имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="417d0-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="417d0-141">Параметр</span><span class="sxs-lookup"><span data-stu-id="417d0-141">Parameter</span></span>| <span data-ttu-id="417d0-142">Описание</span><span class="sxs-lookup"><span data-stu-id="417d0-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="417d0-143">Identity</span><span class="sxs-lookup"><span data-stu-id="417d0-143">Identity</span></span>  | <span data-ttu-id="417d0-144">Удостоверение SBA</span><span class="sxs-lookup"><span data-stu-id="417d0-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="417d0-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="417d0-145">Fqdn</span></span> | <span data-ttu-id="417d0-146">Полное доменное имя SBA</span><span class="sxs-lookup"><span data-stu-id="417d0-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="417d0-147">Сайт</span><span class="sxs-lookup"><span data-stu-id="417d0-147">Site</span></span> | <span data-ttu-id="417d0-148">TenantNetworkSite, где находится SBA</span><span class="sxs-lookup"><span data-stu-id="417d0-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="417d0-149">Описание</span><span class="sxs-lookup"><span data-stu-id="417d0-149">Description</span></span> | <span data-ttu-id="417d0-150">Бесплатный формат текста</span><span class="sxs-lookup"><span data-stu-id="417d0-150">Free format text</span></span> |
|||

<span data-ttu-id="417d0-151">Например:</span><span class="sxs-lookup"><span data-stu-id="417d0-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="417d0-152">Создание политики бесперебойной работы филиалов Teams</span><span class="sxs-lookup"><span data-stu-id="417d0-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="417d0-153">Чтобы создать политику, используйте командлет New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="417d0-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="417d0-154">Этот командлет имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="417d0-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="417d0-155">Обратите внимание, что политика может содержать один или несколько SBAs.</span><span class="sxs-lookup"><span data-stu-id="417d0-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="417d0-156">Параметр</span><span class="sxs-lookup"><span data-stu-id="417d0-156">Parameter</span></span>| <span data-ttu-id="417d0-157">Описание</span><span class="sxs-lookup"><span data-stu-id="417d0-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="417d0-158">Identity</span><span class="sxs-lookup"><span data-stu-id="417d0-158">Identity</span></span> | <span data-ttu-id="417d0-159">Удостоверение политики.</span><span class="sxs-lookup"><span data-stu-id="417d0-159">The identity of the policy</span></span> |
| <span data-ttu-id="417d0-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="417d0-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="417d0-161">Полное доменное имя SBA (ов) на сайте</span><span class="sxs-lookup"><span data-stu-id="417d0-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="417d0-162">Например:</span><span class="sxs-lookup"><span data-stu-id="417d0-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="417d0-163">Вы можете добавить или удалить SBAs из политики с помощью командлета Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="417d0-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="417d0-164">Например:</span><span class="sxs-lookup"><span data-stu-id="417d0-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="417d0-165">Назначение пользователю политики</span><span class="sxs-lookup"><span data-stu-id="417d0-165">Assign a policy to a user</span></span>

<span data-ttu-id="417d0-166">Чтобы назначить политику отдельным пользователям, вы будете использовать командлет Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="417d0-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="417d0-167">Этот командлет имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="417d0-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="417d0-168">Параметр</span><span class="sxs-lookup"><span data-stu-id="417d0-168">Parameter</span></span>| <span data-ttu-id="417d0-169">Описание</span><span class="sxs-lookup"><span data-stu-id="417d0-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="417d0-170">Identity</span><span class="sxs-lookup"><span data-stu-id="417d0-170">Identity</span></span> | <span data-ttu-id="417d0-171">Удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="417d0-171">The identity of the user</span></span> |
| <span data-ttu-id="417d0-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="417d0-172">PolicyName</span></span> | <span data-ttu-id="417d0-173">Удостоверение политики.</span><span class="sxs-lookup"><span data-stu-id="417d0-173">The identity of the policy</span></span> |
||

<span data-ttu-id="417d0-174">Например:</span><span class="sxs-lookup"><span data-stu-id="417d0-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="417d0-175">Вы можете удалить политику с пользователя, предоставив $Null политику, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="417d0-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="417d0-176">Регистрация приложения для SBA с помощью Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="417d0-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="417d0-177">Чтобы разрешить различным SBAs, используемым в вашем клиенте, чтение необходимых данных из Microsoft 365, необходимо зарегистрировать приложение для SBA с помощью Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="417d0-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="417d0-178">Дополнительные сведения о регистрации приложений можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="417d0-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="417d0-179">Разработка бизнес-приложений для Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="417d0-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="417d0-180">[Зарегистрируйте приложение на платформе Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="417d0-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="417d0-181">Только одно приложение должно быть зарегистрировано для использования всеми SBAs в клиенте.</span><span class="sxs-lookup"><span data-stu-id="417d0-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="417d0-182">Для регистрации SBA вам понадобятся следующие значения, созданные регистрацией.</span><span class="sxs-lookup"><span data-stu-id="417d0-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="417d0-183">Идентификатор приложения (клиента)</span><span class="sxs-lookup"><span data-stu-id="417d0-183">Application (client) ID</span></span> 
- <span data-ttu-id="417d0-184">Секрет клиента</span><span class="sxs-lookup"><span data-stu-id="417d0-184">Client secret</span></span> 

<span data-ttu-id="417d0-185">Если вы хотите, чтобы приложение SBA, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="417d0-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="417d0-186">Это имя может быть любым из ваших решений.</span><span class="sxs-lookup"><span data-stu-id="417d0-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="417d0-187">Поддерживаемые типы учетных записей = учетная запись только в этом организационном каталоге.</span><span class="sxs-lookup"><span data-stu-id="417d0-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="417d0-188">URI перенаправления веб-сайта = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="417d0-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="417d0-189">Неявные токены Grant = маркеры доступа и ИДЕНТИФИКАТОРы маркеров.</span><span class="sxs-lookup"><span data-stu-id="417d0-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="417d0-190">Разрешения API = клиент Skype и Teams Access — > разрешения на доступ к приложениям > application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="417d0-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="417d0-191">Секрет клиента: вы можете использовать любое описание и срок действия.</span><span class="sxs-lookup"><span data-stu-id="417d0-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="417d0-192">Не забудьте скопировать секретный ключ клиента сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="417d0-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="417d0-193">Идентификатор приложения (клиент) отображается на вкладке Обзор.</span><span class="sxs-lookup"><span data-stu-id="417d0-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="417d0-194">Затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="417d0-194">Then follow these steps:</span></span>

1. <span data-ttu-id="417d0-195">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="417d0-195">Register the application.</span></span>
2. <span data-ttu-id="417d0-196">Задайте неявные токены GRANT.</span><span class="sxs-lookup"><span data-stu-id="417d0-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="417d0-197">Настройте разрешения API.</span><span class="sxs-lookup"><span data-stu-id="417d0-197">Set the API permissions.</span></span>
4. <span data-ttu-id="417d0-198">Создайте секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="417d0-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="417d0-199">Настройка контроллера границ сеанса</span><span class="sxs-lookup"><span data-stu-id="417d0-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="417d0-200">Пошаговые инструкции по настройке контроллера границ сеанса с помощью встроенного устройства с бесперебойной подразделением можно найти в документации, предоставленной вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="417d0-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="417d0-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="417d0-202">Вариантов</span><span class="sxs-lookup"><span data-stu-id="417d0-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="417d0-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="417d0-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="417d0-204">Системы TE</span><span class="sxs-lookup"><span data-stu-id="417d0-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="417d0-205">Вопросы, связанные с отчетами</span><span class="sxs-lookup"><span data-stu-id="417d0-205">Reporting issues</span></span>

<span data-ttu-id="417d0-206">Сообщите о проблемах в организацию поддержки вашего поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="417d0-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="417d0-207">При сообщении об ошибке укажите, что вы настроили работающее устройство филиалов.</span><span class="sxs-lookup"><span data-stu-id="417d0-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="417d0-208">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="417d0-208">Known issues</span></span>

- <span data-ttu-id="417d0-209">При добавлении новых бесперебойных устройств филиалов может потребоваться некоторое время, прежде чем можно будет использовать их в бесперебойно используемых политиках устройств управления филиалами.</span><span class="sxs-lookup"><span data-stu-id="417d0-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="417d0-210">При назначении пользователю бесперебойной политики филиалов может потребоваться некоторое время, прежде чем SBA будет отображено в выходных данных Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="417d0-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="417d0-211">Обратный просмотр номера в контактах Azure AD не выполняется.</span><span class="sxs-lookup"><span data-stu-id="417d0-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="417d0-212">SBA не поддерживает параметры переадресации звонков.</span><span class="sxs-lookup"><span data-stu-id="417d0-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="417d0-213">Совершение экстренного звонка на экстренный номер, настроенный на динамическую видеосвязь (E911), не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="417d0-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="417d0-214">В выходных данных Get-CsOnlineUser показан TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="417d0-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
