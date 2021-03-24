---
title: Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: Сводка. Интеграция Skype для бизнеса Server и Outlook Web App.
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109695"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="f0141-103">Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="f0141-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="f0141-104">**Сводка:** Интеграция Skype для бизнеса Server и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="f0141-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="f0141-105">Клиенты, использующие локальное развертывание Skype для бизнеса Server, могут настраивать Microsoft Outlook Web App в Microsoft Exchange Online в гибридном режиме развертывания.</span><span class="sxs-lookup"><span data-stu-id="f0141-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="f0141-106">Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="f0141-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="f0141-107">Чтобы включить эту интеграцию, необходимо настроить edge Server в локальном развертывании Skype для бизнеса, завершив следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f0141-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="f0141-108">настройте общее адресное пространство SIP;</span><span class="sxs-lookup"><span data-stu-id="f0141-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="f0141-109">Настройка поставщика хостинга на edge Server</span><span class="sxs-lookup"><span data-stu-id="f0141-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="f0141-110">Проверка репликации обновленного центра управления</span><span class="sxs-lookup"><span data-stu-id="f0141-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="f0141-111">Настройка общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="f0141-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="f0141-112">Чтобы интегрировать локальное пространство Skype для бизнеса Server с Exchange Online, необходимо настроить общее пространство адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="f0141-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="f0141-113">Одно и то же пространство адресов домена SIP поддерживается как Skype для бизнеса Server, так и службой Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f0141-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="f0141-114">С помощью оболочки управления Skype для бизнес-серверов настройте edge Server для федерации, используя команды **set-CSAccessEdgeConfiguration,** используя параметры, отображаемые в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f0141-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="f0141-115">Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="f0141-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="f0141-116">Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в сценарии общего пространства адресов SIP в Skype для бизнеса Server и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f0141-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="f0141-117">Сведения об использовании оболочки управления Skype для бизнес-серверов см. в [материале Skype for Business Server Management Shell.](../../manage/management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="f0141-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="f0141-118">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="f0141-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="f0141-119">Используя оболочку управления Skype для бизнес-серверов, настройте поставщика хостинга на edge Server, заняв команды **New-CsHostingProvider,** используя параметры в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f0141-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="f0141-120">Если вы используете Microsoft 365 или Office 365 под управлением 21Vianet в Китае, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для службы, выполняемой 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="f0141-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="f0141-121">Если вы используете Microsoft 365 или Office 365 GCC High, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="f0141-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="f0141-122">Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="f0141-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="f0141-123">Значения с пробелами должны заключаться в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f0141-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="f0141-124">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="f0141-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="f0141-125">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="f0141-125">This must be set to True.</span></span>

- <span data-ttu-id="f0141-126">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="f0141-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="f0141-127">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="f0141-127">This must be set to True.</span></span>

- <span data-ttu-id="f0141-128">**HostsOCSUsers** указывает, используется ли поставщик хостинга для размещения office Communications Server или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f0141-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="f0141-129">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="f0141-129">This must be set to False.</span></span>

- <span data-ttu-id="f0141-130">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="f0141-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="f0141-131">Для Exchange Online полное доменное имя — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f0141-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="f0141-132">**IsLocal указывает,** содержится ли прокси-сервер, используемый поставщиком хостинга, в топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f0141-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="f0141-133">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="f0141-133">This must be set to False.</span></span>

- <span data-ttu-id="f0141-134">**VerificationLevel** Указывает уровень проверки, разрешенный для сообщений, отосланных в и от принимающего поставщика.</span><span class="sxs-lookup"><span data-stu-id="f0141-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="f0141-135">Укажите **UseSourceVerification**, что основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="f0141-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="f0141-136">Если этот уровень не указан, сообщение будет отклонено как непроверяемое.</span><span class="sxs-lookup"><span data-stu-id="f0141-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="f0141-137">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="f0141-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="f0141-138">Изменения, внесенные с помощью cmdlets в предыдущих разделах, автоматически применяются к edge Server и, как правило, для репликации требуется менее минуты.</span><span class="sxs-lookup"><span data-stu-id="f0141-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="f0141-139">Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к вашему edge Server с помощью следующих cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f0141-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="f0141-140">Чтобы проверить обновления репликации на внутреннем сервере в развертывании Skype для бизнеса Server, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f0141-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="f0141-141">Проверьте, отображается ли значение UpToDate TRUE для всех реплик.</span><span class="sxs-lookup"><span data-stu-id="f0141-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="f0141-142">Чтобы подтвердить, что изменения были применены, на edge Server запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f0141-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="f0141-143">Дважды проверьте, соответствует ли показанная информация изменениям, совершенным на предыдущих действиях.</span><span class="sxs-lookup"><span data-stu-id="f0141-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0141-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f0141-144">See also</span></span>

[<span data-ttu-id="f0141-145">Предоставление голосовой почты пользователей Skype для бизнеса Server в ХОЗ Exchange</span><span class="sxs-lookup"><span data-stu-id="f0141-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[<span data-ttu-id="f0141-146">Интеграция единой системы обмена сообщениями Exchange в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f0141-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)