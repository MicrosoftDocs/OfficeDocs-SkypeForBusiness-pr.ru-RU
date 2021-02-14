---
title: Настройка облачной службы голосовой почты для пользователей локальной сети
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
description: Инструкции по внедрению облачной голосовой почты для пользователей Skype для бизнеса Server.
ms.openlocfilehash: 29faba6bf092647f0c55899f013c6b4bf146304f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552585"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="c60dd-103">Настройка облачной службы голосовой почты для пользователей локальной сети</span><span class="sxs-lookup"><span data-stu-id="c60dd-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="c60dd-104">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="c60dd-104">Overview</span></span> 
<span data-ttu-id="c60dd-105">В этой статье описывается настройка облачной службы голосовой почты Майкрософт для локального пользователя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c60dd-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="c60dd-106">В этой статье предполагается, что skype для бизнеса Server уже развернут в поддерживаемой топологии и что выполнены все необходимые условия для настройки гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="c60dd-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="c60dd-107">Дополнительные сведения о преимуществах, планировании и требованиях к внедрению облачной голосовой почты см. в этой [теме.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="c60dd-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="c60dd-108">Настройка облачной голосовой почты включает следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c60dd-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="c60dd-109">Убедитесь, что выполнены все необходимые условия, описанные в описании плана [облачной голосовой почты.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="c60dd-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="c60dd-110">Убедитесь, что вы настроили гибридное подключение, как описано в описании планирования гибридного подключения и [настройки гибридного подключения.](configure-hybrid-connectivity.md) [](plan-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="c60dd-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="c60dd-111">[Настройте облачную голосовую почту](#configure-cloud-voicemail-as-the-hosting-provider) в качестве поставщика услуг размещения на сервере переднего сервера, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c60dd-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="c60dd-112">[Настройте политику голосовой почты,](#configure-a-hosted-voicemail-policy) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c60dd-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="c60dd-113">[Назначьте политику голосовой почты,](#assign-a-hosted-voicemail-policy) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c60dd-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="c60dd-114">[Включить для пользователя облачную голосовую почту,](#enable-a-user-for-cloud-voicemail) как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c60dd-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="c60dd-115">Настройка облачной голосовой почты в качестве поставщика услуг размещения</span><span class="sxs-lookup"><span data-stu-id="c60dd-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="c60dd-116">Облачная голосовая почта настраивается в качестве поставщика услуг размещения на сервере переднего New-CsHostingProvider с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c60dd-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="c60dd-117">**Идентификатор** указывает уникальный идентификатор строковых значений для создающегося поставщика услуг размещения; например, Облачная голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="c60dd-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="c60dd-118">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="c60dd-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="c60dd-119">Для этого параметра должно быть задано true.</span><span class="sxs-lookup"><span data-stu-id="c60dd-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="c60dd-120">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="c60dd-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="c60dd-121">Для этого параметра должно быть задано true.</span><span class="sxs-lookup"><span data-stu-id="c60dd-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="c60dd-122">**HostsOCSUsers** указывает, используется ли поставщик услуг размещения для размещения учетных записей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c60dd-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="c60dd-123">Для этого параметра должно быть задано false.</span><span class="sxs-lookup"><span data-stu-id="c60dd-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="c60dd-124">**ProxyFQDN** указывает полное доменное имя прокси-сервера, используемого поставщиком услуг размещения; например, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c60dd-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="c60dd-125">Чтобы получить эту информацию, обратитесь к своему поставщику услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="c60dd-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="c60dd-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="c60dd-126">This value cannot be modified.</span></span> <span data-ttu-id="c60dd-127">Если поставщик услуг размещения изменяет свой прокси-сервер, необходимо удалить и повторно создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="c60dd-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="c60dd-128">**IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком услуг размещения, в топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c60dd-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="c60dd-129">Для этого параметра должно быть задано false.</span><span class="sxs-lookup"><span data-stu-id="c60dd-129">This parameter must be set to False.</span></span>

<span data-ttu-id="c60dd-130">Например, в оболочке управления Skype для бизнеса следующий cmdlet настраивает облачную голосовую почту в качестве поставщика услуг размещения:</span><span class="sxs-lookup"><span data-stu-id="c60dd-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="c60dd-131">Настройка политики настроенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="c60dd-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="c60dd-132">Чтобы обеспечить маршрутизации голосовой почты для организации в облачную службу голосовой почты, необходимо настроить политику маршрутизации голосовой почты для организации.</span><span class="sxs-lookup"><span data-stu-id="c60dd-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="c60dd-133">Во многих случаях требуется только одна политика голосовой почты, и вы можете изменить глобальную политику для удовлетворения всех ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="c60dd-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="c60dd-134">Если в организации требуется несколько политик голосовой почты, можно добавить политики с помощью нового cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="c60dd-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="c60dd-135">Чтобы изменить глобальную политику, после обновления organization и TenantID в командной оболочке Skype для бизнеса Server запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c60dd-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="c60dd-136">**Назначение** указывает полное доменное имя службы облачной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="c60dd-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="c60dd-137">Для этого значения необходимо установить **exap.um.outlook.com.**</span><span class="sxs-lookup"><span data-stu-id="c60dd-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="c60dd-138">**Организация** — это домен по умолчанию, присвоенный вашему арендатору.</span><span class="sxs-lookup"><span data-stu-id="c60dd-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="c60dd-139">Вы можете получить эти сведения, войдите в office.com, щелкните приложение "Центр  администрирования", выберите "Настройка" слева и щелкните **"Домены".**</span><span class="sxs-lookup"><span data-stu-id="c60dd-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="c60dd-140">Например: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c60dd-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="c60dd-141">Имя организации также является именем домена по умолчанию в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="c60dd-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="c60dd-142">Чтобы убедиться, что политика голосовой почты успешно создана, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c60dd-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="c60dd-143">Назначение политики hosted voicemail</span><span class="sxs-lookup"><span data-stu-id="c60dd-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="c60dd-144">По умолчанию всем пользователям назначена глобальная политика голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="c60dd-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="c60dd-145">Если вы используете другую политику, перед включением для пользователей услуг голосовой почты, необходимо сначала предоставить пользователям нужную политику голосовой почты с помощью с помощьюлета [Grant-CSHostedVoicemailPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c60dd-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="c60dd-146">Например, следующая команда назначает пользователю политику голосовой почты, которая не является глобальной:</span><span class="sxs-lookup"><span data-stu-id="c60dd-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="c60dd-147">Включить для пользователя облачную голосовую почту</span><span class="sxs-lookup"><span data-stu-id="c60dd-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="c60dd-148">Чтобы включить маршрутизов голосовой почты пользователя в облачную голосовую почту, используйте с параметром HostedVoiceMail параметр [Set-CsUser.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c60dd-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="c60dd-149">Например, следующая команда включает учетную запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="c60dd-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="c60dd-150">Он проверяет, применяется ли к этому пользователю политика облачной голосовой почты (на глобальном уровне, на уровне сайта или пользователя).</span><span class="sxs-lookup"><span data-stu-id="c60dd-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="c60dd-151">Если политика не применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c60dd-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="c60dd-152">В следующем примере отключает учетную запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="c60dd-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="c60dd-153">Он проверяет, не применяется ли к этому пользователю политика голосовой почты на глобальном уровне, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="c60dd-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="c60dd-154">Если политика применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c60dd-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="c60dd-155">Для использования службы облачной голосовой почты Майкрософт пользователям должна быть включена корпоративная голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="c60dd-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
