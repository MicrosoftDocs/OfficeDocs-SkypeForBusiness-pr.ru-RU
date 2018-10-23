---
title: Настройка службы голосовой почты в облаке
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по реализации голосовой почты на основе облака для пользователей, размещенных на Скайп для Business Server.
ms.openlocfilehash: 80f154a7fa8e34b7912ebf5762e5d0390e21fd22
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696186"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="0367c-103">Настройка службы голосовой почты в облаке</span><span class="sxs-lookup"><span data-stu-id="0367c-103">Configure Cloud Voicemail service</span></span>

## <a name="overview"></a><span data-ttu-id="0367c-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="0367c-104">Overview</span></span> 
<span data-ttu-id="0367c-105">В этой статье описывается настройка службы Microsoft Cloud голосовой почты для вашей Скайп для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0367c-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="0367c-106">В этой статье предполагается, что вы уже Скайп Business Server, развернутые в поддерживаемые топологии и что удовлетворены необходимые условия для настройки гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="0367c-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="0367c-107">Дополнительные сведения о преимуществах рекомендации по планированию и требования к внедрению голосовой почты в облаке, см [Планирование голосовой почты облачной службы](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="0367c-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="0367c-108">Настройка голосовой почты в облаке состоит из следующих задач:</span><span class="sxs-lookup"><span data-stu-id="0367c-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="0367c-109">Убедитесь, что удовлетворены необходимого программного обеспечения, как описано в [Планирование голосовой почты облачной службы](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="0367c-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="0367c-110">Убедитесь, что настройки гибридного подключения, как описано в [план гибридного подключения](plan-hybrid-connectivity.md) и [Настройка гибридного подключения](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="0367c-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="0367c-111">[Настройка голосовой почты облачных как поставщика услуг размещения на пограничном сервере](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0367c-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="0367c-112">[Настройка политики размещенной голосовой почты](#configure-a-hosted-voicemail-policy) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0367c-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="0367c-113">[Назначение политики размещенной голосовой почты](#assign-a-hosted-voicemail-policy) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0367c-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="0367c-114">[Включение пользователей для голосовой почты в облаке](#enable-a-user-for-cloud-voicemail) , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0367c-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="0367c-115">Настройка голосовой почты в облаке в качестве поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="0367c-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="0367c-116">Настройка голосовой почты в облаке как поставщика услуг размещения на пограничном сервере с помощью командлета New-CsHostingProvider со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="0367c-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="0367c-117">**Identity** определяет строковое значение уникального идентификатора для поставщика услуг размещения, которую вы создаете; Например облако голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0367c-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="0367c-118">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="0367c-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="0367c-119">Этот параметр должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="0367c-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="0367c-120">**Параметр EnabledSharedAddressSpace** указывает, будет ли использоваться поставщика услуг размещения в общие сценарии пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="0367c-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="0367c-121">Этот параметр должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="0367c-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="0367c-122">**HostsOCSUsers** указывает, используется ли поставщик услуг размещения для размещения Скайп для учетных записей Business Server.</span><span class="sxs-lookup"><span data-stu-id="0367c-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="0367c-123">Этот параметр должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="0367c-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="0367c-124">**ProxyFQDN** указывает полное доменное имя (FQDN) для прокси-сервер, используемый поставщиком услуг размещения; Например proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0367c-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="0367c-125">Связаться с поставщиком услуг размещения для эти сведения.</span><span class="sxs-lookup"><span data-stu-id="0367c-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="0367c-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0367c-126">This value cannot be modified.</span></span> <span data-ttu-id="0367c-127">Если поставщик услуг размещения изменяется ее прокси-сервер, необходимо удалить и повторно создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0367c-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="0367c-128">**IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком услуг размещения в вашей Скайп для топологии Business Server.</span><span class="sxs-lookup"><span data-stu-id="0367c-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="0367c-129">Этот параметр должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="0367c-129">This parameter must be set to False.</span></span>

<span data-ttu-id="0367c-130">Например в Скайп оболочки управления бизнес-процессов, следующий командлет настраивает голосовой почты в облаке как поставщика услуг размещения:</span><span class="sxs-lookup"><span data-stu-id="0367c-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="0367c-131">Настройка политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="0367c-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="0367c-132">Чтобы убедиться, что голосовой почты для вашей организации перенаправляется в службе голосовой почты в облаке, необходимо настроить политику размещенной голосовой почты для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0367c-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="0367c-133">Во многих случаях политика только один размещенной голосовой почты является обязательным и можно изменить глобальную политику в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="0367c-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="0367c-134">Если в организации требуется несколько политик размещенной голосовой почты, можно добавить политики с помощью командлета новые cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="0367c-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="0367c-135">Чтобы изменить глобальную политику, выполните следующую команду в Скайп для Business Server консоли после обновления вашей организации и TenantID:</span><span class="sxs-lookup"><span data-stu-id="0367c-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="0367c-136">**Назначение** указывает полное доменное имя (FQDN) размещенной голосовой почты облачной службы.</span><span class="sxs-lookup"><span data-stu-id="0367c-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="0367c-137">Это значение должно иметь значение **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="0367c-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="0367c-138">**Организация** — это домен по умолчанию, назначенный для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="0367c-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="0367c-139">Эти сведения можно получить, если администратор клиента вход на сайте office.com, щелкните на приложение центра администрирования, перейдите в раздел **Установка** слева и щелкните элемент **домены**.</span><span class="sxs-lookup"><span data-stu-id="0367c-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="0367c-140">Например: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0367c-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="0367c-141">Название организации также является именем домена по умолчанию в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0367c-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="0367c-142">**TenantID** используется для идентификации вашего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="0367c-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="0367c-143">Дополнительные сведения можно [Найти код клиента Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="0367c-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="0367c-144">Чтобы гарантировать, что политика размещенной голосовой почты был создан успешно, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0367c-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="0367c-145">Назначение политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="0367c-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="0367c-146">По умолчанию, размещенных Global всем пользователям назначается политика голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0367c-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="0367c-147">Если вы используете различные политики, перед включением пользователей для размещенной голосовой почты, необходимо сначала предоставить пользователям политика желаемую размещенной голосовой почты с помощью командлета [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0367c-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="0367c-148">Например следующая команда назначает политику глобальной размещенной голосовой почты для пользователя:</span><span class="sxs-lookup"><span data-stu-id="0367c-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="0367c-149">Включить пользователя в облаке голосовой почты</span><span class="sxs-lookup"><span data-stu-id="0367c-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="0367c-150">Чтобы включить вызовы пользователя голосовой почты для маршрутизации голосовой почты в облаке, используйте командлет [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) с параметром HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="0367c-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="0367c-151">Например следующая команда включает учетную запись пользователя для голосовой почты в облаке.</span><span class="sxs-lookup"><span data-stu-id="0367c-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="0367c-152">Командлет проверяет, что политика голосовой почты в облаке — в глобальной, сайта или на уровне пользователя, назначенного для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0367c-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="0367c-153">Если политика не применяется, командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0367c-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="0367c-154">Следующий пример отключает учетную запись пользователя для голосовой почты в облаке:</span><span class="sxs-lookup"><span data-stu-id="0367c-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="0367c-155">Командлет, проверяет, не политика размещенной голосовой почты — в глобальной, сайта или на уровне пользователя, назначенного для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0367c-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="0367c-156">Если применить политику, командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0367c-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="0367c-157">Пользователи должны быть включен для использования службы Microsoft Cloud голосовой почты корпоративной voice.</span><span class="sxs-lookup"><span data-stu-id="0367c-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>