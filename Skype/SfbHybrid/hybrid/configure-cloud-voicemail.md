---
title: Настройка облачной службы голосовой почты для локальных пользователей
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по внедрению голосовой почты в облаке для пользователей, размещенных в Skype для бизнеса Server.
ms.openlocfilehash: e3b18f8048f8779eac322dece88e5919b2aa7a96
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963007"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="9bd07-103">Настройка облачной службы голосовой почты для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="9bd07-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="9bd07-104">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="9bd07-104">Overview</span></span> 
<span data-ttu-id="9bd07-105">В этой статье описано, как настроить облачную службу голосовой почты Майкрософт для локальных пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9bd07-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="9bd07-106">В этой статье предполагается, что вы уже развернули Skype для бизнеса Server в поддерживаемой топологии и удовлетворены предварительные требования для настройки гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd07-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="9bd07-107">Дополнительные сведения о преимуществах, рекомендациях по планированию и требованиях для реализации облачной голосовой почты можно найти в статье [планирование облачной службы голосовой почты](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9bd07-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="9bd07-108">Настройка облачной голосовой почты состоит из следующих задач:</span><span class="sxs-lookup"><span data-stu-id="9bd07-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="9bd07-109">Убедитесь, что соблюдены предварительные требования, описанные в статье [Plan Cloud голосовой голосовой службы](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9bd07-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="9bd07-110">Убедитесь, что вы настроили гибридное подключение, как описано в статье [Plan гибридное подключение](plan-hybrid-connectivity.md) и [Настройка гибридного](configure-hybrid-connectivity.md)подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd07-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="9bd07-111">[Настройте облачную голосовую почту в качестве поставщика услуг хостинга на пограничном сервере](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9bd07-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="9bd07-112">[Настройте размещенную политику голосовой почты](#configure-a-hosted-voicemail-policy) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9bd07-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="9bd07-113">[Назначьте размещенную политику голосовой почты](#assign-a-hosted-voicemail-policy) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9bd07-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="9bd07-114">[Включите пользователя для облачной голосовой почты](#enable-a-user-for-cloud-voicemail) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9bd07-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="9bd07-115">Настройка облачной голосовой почты в качестве поставщика услуг хостинга на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="9bd07-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="9bd07-116">Вы настраиваете облачную голосовую почту как поставщик услуг хостинга на сервере переднего плана с помощью командлета New – CsHostingProvider со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="9bd07-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="9bd07-117">**Identity** указывает уникальный идентификатор строкового значения для создаваемого поставщика услуг хостинга; Например, облачная Голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="9bd07-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="9bd07-118">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="9bd07-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="9bd07-119">Для этого параметра должно быть задано значение true.</span><span class="sxs-lookup"><span data-stu-id="9bd07-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="9bd07-120">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="9bd07-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="9bd07-121">Для этого параметра должно быть задано значение true.</span><span class="sxs-lookup"><span data-stu-id="9bd07-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="9bd07-122">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9bd07-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="9bd07-123">Для этого параметра должно быть задано значение false.</span><span class="sxs-lookup"><span data-stu-id="9bd07-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="9bd07-124">**ProxyFQDN** указывает полное доменное имя (FQDN) прокси-сервера, используемого поставщиком услуг хостинга; Например, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9bd07-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="9bd07-125">Чтобы получить эту информацию, обратитесь к своему поставщику услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="9bd07-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="9bd07-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="9bd07-126">This value cannot be modified.</span></span> <span data-ttu-id="9bd07-127">Если поставщик услуг хостинга изменяет свой прокси-сервер, необходимо удалить и повторно создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="9bd07-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="9bd07-128">Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9bd07-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="9bd07-129">Для этого параметра должно быть задано значение false.</span><span class="sxs-lookup"><span data-stu-id="9bd07-129">This parameter must be set to False.</span></span>

<span data-ttu-id="9bd07-130">Например, в командной консоли Skype для бизнеса следующий командлет настраивает облачную голосовую почту в качестве поставщика услуг хранения:</span><span class="sxs-lookup"><span data-stu-id="9bd07-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="9bd07-131">Настройка политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9bd07-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="9bd07-132">Чтобы Голосовая почта Организации направлялась в облачную службу голосовой почты, необходимо настроить для организации политику размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bd07-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="9bd07-133">Во многих случаях требуется только одна политика размещенной голосовой почты, и вы можете изменить глобальную политику в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="9bd07-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="9bd07-134">Если в Организации требуется несколько политик размещенной голосовой почты, можно добавить политики с помощью командлета New – cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="9bd07-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="9bd07-135">Чтобы изменить глобальную политику, выполните следующую команду в командной консоли Skype для бизнеса Server после обновления вашей организации и TenantID:</span><span class="sxs-lookup"><span data-stu-id="9bd07-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="9bd07-136">**Destination** указывает полное доменное имя (FQDN) размещенной облачной службы голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bd07-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="9bd07-137">Это значение должно быть равно **exap.UM.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="9bd07-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="9bd07-138">**Organization** — это домен по умолчанию, назначенный вашему клиенту.</span><span class="sxs-lookup"><span data-stu-id="9bd07-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="9bd07-139">Вы можете получить эту информацию, дополнив вход администратора клиента в office.com, выберите приложение центра администрирования, перейдите к разделу **Настройка** слева и нажмите кнопку **домены**.</span><span class="sxs-lookup"><span data-stu-id="9bd07-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="9bd07-140">Пример: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="9bd07-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="9bd07-141">Имя организации также является именем домена по умолчанию в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9bd07-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="9bd07-142">**Клиент** используется для идентификации клиента в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9bd07-142">**Tenant** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="9bd07-143">Для получения дополнительных сведений обратитесь [к разделу Find Your ID клиента Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="9bd07-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="9bd07-144">Чтобы убедиться, что политика размещенной голосовой почты успешно создана, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bd07-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="9bd07-145">Назначение политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9bd07-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="9bd07-146">По умолчанию для всех пользователей назначается Глобальная политика размещения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bd07-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="9bd07-147">Если вы используете другую политику, прежде чем разрешить пользователям размещенную голосовую почту, необходимо сначала предоставить пользователям нужную политику размещенной голосовой почты с помощью командлета [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9bd07-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="9bd07-148">Например, следующая команда назначает пользователю неглобальную политику размещенной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="9bd07-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="9bd07-149">Включение поддержки облачной голосовой почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="9bd07-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="9bd07-150">Чтобы включить маршрутизацию голосовых вызовов пользователя в облачную голосовую почту, используйте командлет [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) с параметром хостедвоицемаил.</span><span class="sxs-lookup"><span data-stu-id="9bd07-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="9bd07-151">Например, следующая команда включает учетную запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="9bd07-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="9bd07-152">Командлет проверяет, применяется ли политика облачной голосовой почты (на глобальном уровне, на уровне сайта или на уровне пользователя) к этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="9bd07-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="9bd07-153">Если политика не применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="9bd07-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="9bd07-154">В следующем примере отключается учетная запись пользователя для облачной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="9bd07-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="9bd07-155">Командлет проверяет, относится ли политика размещенной голосовой почты на глобальном уровне, на уровне сайта или на уровне пользователя к этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="9bd07-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="9bd07-156">Если политика применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="9bd07-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="9bd07-157">Для использования облачной службы голосовой почты Майкрософт пользователям необходимо разрешить поддержку корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9bd07-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
