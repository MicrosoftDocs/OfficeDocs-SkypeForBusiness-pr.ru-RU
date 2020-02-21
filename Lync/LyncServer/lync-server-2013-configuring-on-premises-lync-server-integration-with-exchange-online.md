---
title: Настройка локальной интеграции Lync Server с Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4900beab738f9aa792919cceec015bb0c3ad0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="e6e03-102">Настройка локальной интеграции Lync Server 2013 с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6e03-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6e03-103">_**Последнее изменение темы:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="e6e03-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="e6e03-104">Клиенты, использующие локальные развертывания Lync Server 2013, могут настраивать взаимодействие с Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="e6e03-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="e6e03-105">Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="e6e03-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="e6e03-106">Чтобы включить эту интеграцию, необходимо настроить пограничный сервер в локальном развертывании Lync Server, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6e03-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="e6e03-107">настройте общее адресное пространство SIP;</span><span class="sxs-lookup"><span data-stu-id="e6e03-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="e6e03-108">Настройка поставщика услуг хостинга на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="e6e03-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="e6e03-109">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="e6e03-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="e6e03-110">Если Lync Server 2013 интегрируется с Exchange Online, пользователь, который пытается войти в систему обмена мгновенными сообщениями из OWA, считается удаленным или внешним пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6e03-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="e6e03-111">В этом сценарии пользователю должна быть назначена политика внешнего доступа, в которой выбран следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="e6e03-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="e6e03-112">**Разрешить взаимодействие с удаленными пользователями**</span><span class="sxs-lookup"><span data-stu-id="e6e03-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="e6e03-113">Включите этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за преправителями, например, пользователи, которые находятся в командировке, могли подключаться к Lync Server через Интернет.</span><span class="sxs-lookup"><span data-stu-id="e6e03-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="e6e03-114">Дополнительные сведения см в разделе [Manage External Access Policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e6e03-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="e6e03-115">Настройка общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="e6e03-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="e6e03-116">Для интеграции локального сервера Lync Server 2013 с Exchange Online необходимо настроить общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="e6e03-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="e6e03-117">Одно и то же адресное пространство домена SIP поддерживается как в Lync Server, так и в службе Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6e03-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="e6e03-118">С помощью командной консоли Lync Server настройте пограничный сервер для Федерации, выполнив командлет **Set – CSAccessEdgeConfiguration** , используя параметры, показанные в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e6e03-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="e6e03-119">**AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="e6e03-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="e6e03-120">Это свойство также определяет, могут ли внутренние пользователи связываться с пользователями в общем адресном пространстве SIP с Lync Server и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6e03-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="e6e03-121">Сведения о том, как использовать командную консоль Lync Server, можно найти в статье [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e6e03-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="e6e03-122">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="e6e03-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="e6e03-123">Используйте командную консоль Lync Server для настройки поставщика услуг хостинга на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e6e03-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="e6e03-124">Для этого выполните командлет **New – CsHostingProvider** , используя параметры, приведенные в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e6e03-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="e6e03-125">Если вы используете Office 365 под управлением 21Vianet в Китае, замените значение параметра <STRONG>ProxyFqdn</STRONG> в этом примере ("exap.UM.Outlook.com") на полное доменное имя службы, обслуживаемой 21vianet: "exap.UM.Partner.Outlook.CN".</span><span class="sxs-lookup"><span data-stu-id="e6e03-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="e6e03-126">Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="e6e03-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="e6e03-127">Значения, содержащие пробелы, должны заключаться в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e6e03-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="e6e03-128">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e6e03-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="e6e03-129">Должно быть задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="e6e03-130">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="e6e03-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="e6e03-131">Должно быть задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="e6e03-132">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6e03-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="e6e03-133">Должно быть задано значение **false**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="e6e03-134">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e6e03-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="e6e03-135">Для Exchange Online полное доменное имя — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e6e03-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="e6e03-136">Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6e03-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="e6e03-137">Должно быть задано значение **false**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="e6e03-138">**Верификатионлевел** указывает уровень проверки, разрешенный для сообщений, отправляемых и получаемых поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e6e03-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="e6e03-139">Укажите **усесаурцеверификатион**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="e6e03-140">Этот вариант зависит от уровня проверки, включенного в сообщения, отправленные от поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="e6e03-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="e6e03-141">Если этот уровень не указан, сообщение будет отклонено как Непроверяемое.</span><span class="sxs-lookup"><span data-stu-id="e6e03-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="e6e03-142">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="e6e03-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="e6e03-143">Изменения, внесенные с помощью командлетов, описанных в предыдущих разделах, автоматически применяются к пограничному серверу, и для репликации обычно требуется менее одной минуты.</span><span class="sxs-lookup"><span data-stu-id="e6e03-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="e6e03-144">Вы можете проверить состояние репликации и применить изменения к пограничному серверу с помощью следующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="e6e03-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="e6e03-145">Чтобы проверить наличие обновлений репликации на внутреннем сервере в развертывании Lync Server, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e6e03-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="e6e03-146">Чтобы убедиться, что изменения применены, выполните следующий командлет на пограничном сервере:</span><span class="sxs-lookup"><span data-stu-id="e6e03-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6e03-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e6e03-147">See Also</span></span>


[<span data-ttu-id="e6e03-148">Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="e6e03-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="e6e03-149">Интеграция единой системы обмена сообщениями Exchange в среде Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6e03-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

