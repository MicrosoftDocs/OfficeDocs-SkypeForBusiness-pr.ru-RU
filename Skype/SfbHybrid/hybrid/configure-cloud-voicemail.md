---
title: Настройка службы голосовой почты Cloud для локального пользователя
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по внедрению облачной голосовой почты для пользователей, уехав в Skype для бизнеса Server.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118988"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="6f38e-103">Настройка службы голосовой почты Cloud для локального пользователя</span><span class="sxs-lookup"><span data-stu-id="6f38e-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="6f38e-104">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="6f38e-104">Overview</span></span> 
<span data-ttu-id="6f38e-105">В этой статье описывается настройка службы голосовой почты Microsoft Cloud для локального пользователя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6f38e-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="6f38e-106">В этой статье предполагается, что Skype для бизнеса Server уже развернут в поддерживаемой топологии и что вы выполнили необходимые условия для настройки гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="6f38e-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="6f38e-107">Дополнительные сведения о преимуществах, соображениях планирования и требованиях к реализации облачной голосовой почты см. в [сервисе Голосовой почты Plan Cloud.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="6f38e-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="6f38e-108">Настройка облачной голосовой почты включает следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6f38e-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="6f38e-109">Убедитесь, что вы выполнили необходимые условия, описанные в [службе голосовой почты Plan Cloud.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="6f38e-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="6f38e-110">Убедитесь, что вы настроили гибридное подключение, как описано в [plan hybrid connectivity](plan-hybrid-connectivity.md) и [Configure hybrid connectivity.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="6f38e-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="6f38e-111">[Настройка облачной голосовой почты в качестве поставщика хостинга на переднем сервере,](#configure-cloud-voicemail-as-the-hosting-provider) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="6f38e-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="6f38e-112">[Настройка политики голосовой почты, как](#configure-a-hosted-voicemail-policy) описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="6f38e-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="6f38e-113">[Назначение политики голосовой почты,](#assign-a-hosted-voicemail-policy) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="6f38e-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="6f38e-114">[Включить пользователя для облачной голосовой почты,](#enable-a-user-for-cloud-voicemail) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="6f38e-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="6f38e-115">Настройка облачной голосовой почты в качестве поставщика хостинга</span><span class="sxs-lookup"><span data-stu-id="6f38e-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="6f38e-116">Вы настраивает облачную голосовую почту в качестве поставщика хостинга на переднем сервере с помощью New-CsHostingProvider с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="6f38e-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="6f38e-117">**Identity** указывает уникальный идентификатор строковых значений для создающегося поставщика хостинга; например, облачная голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="6f38e-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="6f38e-118">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="6f38e-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="6f38e-119">Этот параметр должен быть задан true.</span><span class="sxs-lookup"><span data-stu-id="6f38e-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="6f38e-120">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="6f38e-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="6f38e-121">Этот параметр должен быть задан true.</span><span class="sxs-lookup"><span data-stu-id="6f38e-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="6f38e-122">**HostsOCSUsers** указывает, используется ли поставщик хостинга для размещения учетных записей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f38e-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="6f38e-123">Этот параметр должен быть задан false.</span><span class="sxs-lookup"><span data-stu-id="6f38e-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="6f38e-124">**ProxyFQDN** указывает полное доменное имя (FQDN) для прокси-сервера, используемого поставщиком хостинга; например, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f38e-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="6f38e-125">Чтобы получить эту информацию, обратитесь к своему поставщику услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="6f38e-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="6f38e-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="6f38e-126">This value cannot be modified.</span></span> <span data-ttu-id="6f38e-127">Если поставщик хостинга меняет прокси-сервер, необходимо удалить и повторно создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="6f38e-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="6f38e-128">**IsLocal указывает,** содержится ли прокси-сервер, используемый поставщиком хостинга, в топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f38e-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="6f38e-129">Этот параметр должен быть задан false.</span><span class="sxs-lookup"><span data-stu-id="6f38e-129">This parameter must be set to False.</span></span>

<span data-ttu-id="6f38e-130">Например, в оболочке Skype для управления бизнесом следующий кодлет настраивает облачную голосовую почту в качестве поставщика хостинга:</span><span class="sxs-lookup"><span data-stu-id="6f38e-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="6f38e-131">Настройка политики голосовой почты с хост-почтой</span><span class="sxs-lookup"><span data-stu-id="6f38e-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="6f38e-132">Чтобы обеспечить маршрутизации голосовой почты для организации в службу облачной голосовой почты, необходимо настроить политику голосовой почты для организации.</span><span class="sxs-lookup"><span data-stu-id="6f38e-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="6f38e-133">Во многих случаях требуется только одна политика голосовой почты, и вы можете изменить глобальную политику для удовлетворения всех ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="6f38e-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="6f38e-134">Если в организации требуется несколько политик голосовой почты, можно добавить политики с помощью нового cmdlet cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="6f38e-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="6f38e-135">Чтобы изменить глобальную политику, запустите следующую команду в оболочке управления Skype для бизнеса Server после обновления вашей Организации и TenantID:</span><span class="sxs-lookup"><span data-stu-id="6f38e-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="6f38e-136">**Назначение** указывает полностью квалифицированное доменное имя (FQDN) службы голосовой почты облачной почты.</span><span class="sxs-lookup"><span data-stu-id="6f38e-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="6f38e-137">Это значение должно быть заданной **для exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="6f38e-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="6f38e-138">**Организация** — это домен по умолчанию, назначенный вашему клиенту.</span><span class="sxs-lookup"><span data-stu-id="6f38e-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="6f38e-139">Эту информацию можно получить, office.com администратора клиента, щелкните приложение Центр администрирования,  перейдите к установке слева и щелкните **Домены**.</span><span class="sxs-lookup"><span data-stu-id="6f38e-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="6f38e-140">Например: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6f38e-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="6f38e-141">Имя организации также является доменным именем по умолчанию в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f38e-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="6f38e-142">Чтобы убедиться, что политика голосовой почты с хост-почтой создана успешно, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6f38e-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="6f38e-143">Назначение политики голосовой почты с хост-почтой</span><span class="sxs-lookup"><span data-stu-id="6f38e-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="6f38e-144">По умолчанию политика голосовой почты глобального хостинга назначена всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="6f38e-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="6f38e-145">Если используется другая политика, прежде чем включить пользователей для принимающей голосовой почты, сначала необходимо предоставить пользователям желаемую политику голосовой почты с помощью cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6f38e-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="6f38e-146">Например, следующая команда назначает пользователю политику голосовой почты, не относящаяся к глобальной сети:</span><span class="sxs-lookup"><span data-stu-id="6f38e-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="6f38e-147">Включить пользователя для облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="6f38e-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="6f38e-148">Чтобы включить перенастройку голосовой почты пользователя в облачную голосовую почту, используйте комлет [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) с параметром HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="6f38e-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="6f38e-149">Например, следующая команда включает учетную запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="6f38e-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="6f38e-150">В этом кодлете проверяется, применяется ли к этому пользователю политика голосовой почты облачной голосовой почты на глобальном уровне, на сайте или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f38e-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="6f38e-151">Если политика не применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="6f38e-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="6f38e-152">В следующем примере отключает учетную запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="6f38e-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="6f38e-153">В этом кодлете проверяется, что к этому пользователю не применяется политика голосовой почты на глобальном уровне, на сайте или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f38e-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="6f38e-154">Если политика применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="6f38e-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="6f38e-155">Пользователям должна быть включена корпоративная голосовая почта для использования службы голосовой почты Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6f38e-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>