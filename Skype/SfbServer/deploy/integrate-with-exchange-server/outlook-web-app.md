---
title: Настройка интеграции между локальной Скайп для Business Server 2015 и Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Сводка: Интеграция Скайп для Business Server и Outlook Web App.'
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a><span data-ttu-id="ad1bd-103">Настройка интеграции между локальной Скайп для Business Server 2015 и Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ad1bd-103">Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App</span></span>
 
<span data-ttu-id="ad1bd-104">**Сводка:** Интеграция Скайп для Business Server и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>
  
<span data-ttu-id="ad1bd-105">Пользователи, которые с помощью локального Скайп для развертываний Business Server 2015 можно настроить взаимодействие с Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-105">Customers who are using on-premises Skype for Business Server 2015 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ad1bd-106">Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ad1bd-107">Для включения этой интеграции, необходимо настроить пограничный сервер в вашей локальной Скайп для развертывания Business Server, выполнив следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ad1bd-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span> 
  
- <span data-ttu-id="ad1bd-108">настройте общее адресное пространство SIP;</span><span class="sxs-lookup"><span data-stu-id="ad1bd-108">Configure a shared SIP address space</span></span>
    
- <span data-ttu-id="ad1bd-109">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="ad1bd-109">Configure a hosting provider on the Edge Server</span></span>
    
- <span data-ttu-id="ad1bd-110">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="ad1bd-110">Verify replication of the updated Central Management store</span></span>
    
## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ad1bd-111">Настройка общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="ad1bd-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ad1bd-112">Для интеграции локальной Скайп для 2015 Business Server с Exchange Online, необходимо настроить общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-112">To integrate on-premises Skype for Business Server 2015 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ad1bd-113">Одном адресном пространстве SIP домена поддерживается Скайп для Business Server и службы Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>
  
<span data-ttu-id="ad1bd-114">Использование Скайп для консоли Business Server, Настройка пограничного сервера для федерации, выполнив командлет **Set-CSAccessEdgeConfiguration** с использованием параметров, показанных в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ad1bd-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="ad1bd-115">Параметр **AllowFederatedUsers** указывает, разрешены ли внутренних пользователей для взаимодействия с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ad1bd-116">Кроме того, это свойство определяет ли внутренние пользователи могут общаться с пользователями в общей сценария пространства адресов SIP с помощью Скайп для Business Server и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>
    
<span data-ttu-id="ad1bd-117">Для получения дополнительных сведений об использовании Скайп для консоли Business Server см [Скайп оболочки управления 2015 Business Server](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ad1bd-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server 2015 Management Shell](../../manage/management-shell.md).</span></span>
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ad1bd-118">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="ad1bd-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ad1bd-119">С помощью Скайп для консоли Business Server настройте поставщика услуг размещения на пограничном сервере, выполнив командлет **New-CsHostingProvider** , с помощью параметров в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ad1bd-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="ad1bd-120">При использовании Office 365 под управлением 21Vianet в Китае замените значение для параметра **ProxyFqdn** (например, exap.um.outlook.com) на полное доменное имя для службы под управлением 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ad1bd-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the **ProxyFqdn** parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>
  
- <span data-ttu-id="ad1bd-121">**Identity** определяет строковое значение уникального идентификатора для поставщика услуг размещения, которую вы создаете (например, «Exchange Online»).</span><span class="sxs-lookup"><span data-stu-id="ad1bd-121">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ad1bd-122">Значения с пробелами должны заключаться в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-122">Values that contain spaces must be in double quotes.</span></span>
    
- <span data-ttu-id="ad1bd-123">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-123">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ad1bd-124">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-124">This must be set to True.</span></span>
    
- <span data-ttu-id="ad1bd-125">**Параметр EnabledSharedAddressSpace** указывает, будет ли использоваться поставщика услуг размещения в общие сценарии пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-125">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ad1bd-126">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-126">This must be set to True.</span></span>
    
- <span data-ttu-id="ad1bd-127">**HostsOCSUsers** указывает, используется ли поставщик услуг размещения для размещения для сервера Office Communications Server или Скайп.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-127">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="ad1bd-128">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-128">This must be set to False.</span></span>
    
- <span data-ttu-id="ad1bd-129">**ProxyFQDN** указывает полное доменное имя (FQDN) для прокси-сервер, используемый поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-129">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ad1bd-130">Полное доменное имя Exchange Online: exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-130">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>
    
- <span data-ttu-id="ad1bd-131">**IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком услуг размещения в вашей Скайп для топологии Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-131">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ad1bd-132">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-132">This must be set to False.</span></span>
    
- <span data-ttu-id="ad1bd-133">**VerificationLevel** Указывает уровень проверки, разрешенных для сообщений, отправленных в и из размещенного в узле поставщика.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-133">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ad1bd-134">Укажите **UseSourceVerification**, основанную на уровень проверки, включенные в сообщениях, отправляемых с поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-134">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="ad1bd-135">Если этот уровень не указан, будет отклонено, как непроверяемый.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-135">If this level is not specified, the message will be rejected as being unverifiable.</span></span>
    
## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ad1bd-136">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="ad1bd-136">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ad1bd-137">Изменения, внесенные с помощью командлетов в предыдущих разделах автоматически применяются на пограничный сервер и обычно занять менее минуты для репликации.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-137">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="ad1bd-138">Можно проверить состояние репликации и затем убедиться, что были ли применены изменения на пограничный сервер с помощью следующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="ad1bd-138">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>
  
<span data-ttu-id="ad1bd-139">Проверка обновлений репликации, на внутреннем вашей Скайп для развертывания Business Server, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ad1bd-139">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>
  
```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="ad1bd-140">Чтобы убедиться в том, что были ли применены изменения, на пограничном сервере, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ad1bd-140">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="ad1bd-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ad1bd-141">See also</span></span>

#### 

[<span data-ttu-id="ad1bd-142">Предоставление Скайп для Business Server 2015 пользователям голосовой почты на hosted Exchange единой системы обмена СООБЩЕНИЯМИ</span><span class="sxs-lookup"><span data-stu-id="ad1bd-142">Providing Skype for Business Server 2015 users voice mail on hosted Exchange UM</span></span>](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[<span data-ttu-id="ad1bd-143">Размещенной интеграции единой системы обмена сообщениями Exchange, в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ad1bd-143">Hosted Exchange Unified Messaging integration in Skype for Business Server 2015</span></span>](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

