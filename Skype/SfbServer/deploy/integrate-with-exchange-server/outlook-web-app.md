---
title: Настройка интеграции между локальным Skype для бизнеса Server и Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Аннотация: интеграция Skype для бизнеса Server и Outlook Web App.'
ms.openlocfilehash: b7c279dc41515d9613d8c000ab9e81164a1ccaa6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244213"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="ff716-103">Настройка интеграции между локальным Skype для бизнеса Server и Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ff716-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="ff716-104">**Сводка:** Интегрируйте Skype для бизнеса Server и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ff716-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="ff716-105">Пользователи локальных развертываний Skype для бизнеса Server могут настраивать взаимодействие с приложением Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридной развертки.</span><span class="sxs-lookup"><span data-stu-id="ff716-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ff716-106">Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ff716-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ff716-107">Чтобы включить эту интеграцию, необходимо настроить граничный сервер в локальной среде развертывания Skype для бизнеса Server, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ff716-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="ff716-108">настройте общее адресное пространство SIP;</span><span class="sxs-lookup"><span data-stu-id="ff716-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="ff716-109">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="ff716-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="ff716-110">Проверка репликации обновленного центрального хранилища в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="ff716-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ff716-111">Настройка общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="ff716-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ff716-112">Для интеграции локального сервера Skype для бизнеса с Exchange Online необходимо настроить общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="ff716-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ff716-113">Одно и то же адресное пространство домена SIP поддерживается как в Skype для бизнеса Server, так и в службе Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ff716-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="ff716-114">Используя командную консоль управления Skype для бизнеса Server, настройте граничный сервер для Федерации, запустив командлет **Set-ксакцесседжеконфигуратион** , используя параметры, показанные в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ff716-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="ff716-115">Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="ff716-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ff716-116">Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в рамках сценария общего адресного пространства SIP в Skype для бизнеса Server и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ff716-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="ff716-117">Подробнее об использовании командной консоли Skype для бизнеса Server можно найти в [командной консоли управления Skype для бизнеса Server](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ff716-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ff716-118">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="ff716-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ff716-119">С помощью командной консоли Skype для бизнеса Server настройте поставщик услуг размещения на пограничном сервере, выполнив командлет **New-кшостингпровидер** , используя параметры в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ff716-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="ff716-120">При использовании Office 365 под управлением 21Vianet в Китае замените значение для параметра ProxyFqdn (например, exap.um.outlook.com) на полное доменное имя для службы под управлением 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ff716-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="ff716-121">Если вы используете Office 365 GCC High, замените значение параметра Проксифкдн в этом примере ("exap.um.outlook.com") с полным доменным именем для GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="ff716-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="ff716-122">Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="ff716-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ff716-123">Значения с пробелами должны заключаться в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ff716-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="ff716-124">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ff716-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ff716-125">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="ff716-125">This must be set to True.</span></span>

- <span data-ttu-id="ff716-126">Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="ff716-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ff716-127">Должен иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="ff716-127">This must be set to True.</span></span>

- <span data-ttu-id="ff716-128">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ff716-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="ff716-129">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="ff716-129">This must be set to False.</span></span>

- <span data-ttu-id="ff716-130">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ff716-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ff716-131">Полное доменное имя Exchange Online: exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ff716-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="ff716-132">\*\*\*\* "WebProxy" показывает, является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ff716-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ff716-133">Должен иметь значение False.</span><span class="sxs-lookup"><span data-stu-id="ff716-133">This must be set to False.</span></span>

- <span data-ttu-id="ff716-134">**Верификатионлевел** Указывает уровень проверки, разрешенный для сообщений, отправляемых поставщику услуг хостинга и от него.</span><span class="sxs-lookup"><span data-stu-id="ff716-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ff716-135">Укажите параметр **UseSourceVerification**, который основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="ff716-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="ff716-136">Если этот уровень не указан, сообщение будет отвергнуто как Непроверяемое.</span><span class="sxs-lookup"><span data-stu-id="ff716-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ff716-137">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="ff716-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ff716-138">Изменения, внесенные с помощью командлетов, описанных в предыдущих разделах, автоматически применяются к пограничного сервера, и для их репликации обычно требуется менее одной минуты.</span><span class="sxs-lookup"><span data-stu-id="ff716-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="ff716-139">Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к пограничного сервера с помощью следующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="ff716-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ff716-140">Чтобы проверить наличие обновлений репликации на сервере во внутренней среде развертывания Skype для бизнеса Server, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ff716-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="ff716-141">Убедитесь, что значение Уптодате для всех реплик отображается верно.</span><span class="sxs-lookup"><span data-stu-id="ff716-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="ff716-142">Чтобы убедиться, что изменения применены, на пограничном сервере выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ff716-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="ff716-143">Дважды убедитесь, что отображаемая информация соответствует изменениям, зафиксированным в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="ff716-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff716-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ff716-144">See also</span></span>

[<span data-ttu-id="ff716-145">Предоставление пользователям Skype для бизнеса сервера голосовой почты в размещенной UM-среде обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="ff716-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="ff716-146">Интеграция единой системы обмена сообщениями Exchange в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ff716-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
