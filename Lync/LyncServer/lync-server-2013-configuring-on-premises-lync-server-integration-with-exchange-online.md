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
ms.openlocfilehash: a652fea6c54592526047e8d8b35a0bddd0ef1995
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="860d7-102">Настройка локальной интеграции Lync Server 2013 с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="860d7-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860d7-103">_**Тема последнего изменения:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="860d7-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="860d7-104">Клиенты, использующие локальные развертывания Lync Server 2013, могут настраивать взаимодействие с приложением Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридной развертки.</span><span class="sxs-lookup"><span data-stu-id="860d7-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="860d7-105">Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="860d7-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="860d7-106">Чтобы включить эту интеграцию, необходимо настроить граничный сервер в локальной среде развертывания Lync Server, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="860d7-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="860d7-107">настройте общее адресное пространство SIP;</span><span class="sxs-lookup"><span data-stu-id="860d7-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="860d7-108">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="860d7-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="860d7-109">Проверка репликации обновленного центрального хранилища в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="860d7-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="860d7-110">Если Lync Server 2013 интегрирован с Exchange Online, пользователь, который пытается войти в мгновенном сообщении из OWA, считается удаленным или внешним пользователем.</span><span class="sxs-lookup"><span data-stu-id="860d7-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="860d7-111">В этом случае пользователю должна быть назначена политика внешней доступа, для которой выбраны указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="860d7-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="860d7-112">**Включение связи с удаленными пользователями**</span><span class="sxs-lookup"><span data-stu-id="860d7-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="860d7-113">Включите этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за пределами межсетевого экрана (например, подключены к сети и пользователи, которые находятся в дороге), смогли подключиться к серверу Lync через Интернет.</span><span class="sxs-lookup"><span data-stu-id="860d7-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="860d7-114">Дополнительные сведения можно найти [в разделе Управление политикой внешнего доступа в Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="860d7-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="860d7-115">Настройка общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="860d7-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="860d7-116">Для интеграции локального сервера Lync Server 2013 с Exchange Online необходимо настроить общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="860d7-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="860d7-117">Одно и то же адресное пространство домена SIP поддерживается как в Lync Server, так и в службе Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="860d7-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="860d7-118">С помощью командной консоли Lync Server настройте сервер граничного сервера для Федерации, запустив командлет **Set-ксакцесседжеконфигуратион** , используя параметры, показанные в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="860d7-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="860d7-119">**AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="860d7-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="860d7-120">Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в общем пространстве адресного пространства SIP с Lync Server и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="860d7-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="860d7-121">Подробнее об использовании командной консоли Lync Server можно узнать в разделе [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="860d7-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="860d7-122">Настройка поставщика услуг размещения на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="860d7-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="860d7-123">Для настройки поставщика услуг размещения на пограничном сервере используйте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="860d7-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="860d7-124">Для этого выполните командлет **New-кшостингпровидер** с помощью параметров, описанных в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="860d7-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="860d7-125">При использовании Office 365 под управлением 21Vianet в Китае замените значение для параметра <STRONG>ProxyFqdn</STRONG> (например, exap.um.outlook.com) на полное доменное имя для службы под управлением 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="860d7-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="860d7-126">Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="860d7-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="860d7-127">Значения, содержащие пробелы, должны быть заключены в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="860d7-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="860d7-128">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="860d7-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="860d7-129">Должно быть задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="860d7-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="860d7-130">Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="860d7-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="860d7-131">Должно быть задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="860d7-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="860d7-132">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="860d7-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="860d7-133">Для него должно быть задано **значение false**.</span><span class="sxs-lookup"><span data-stu-id="860d7-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="860d7-134">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="860d7-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="860d7-135">Полное доменное имя Exchange Online: exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="860d7-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="860d7-136">"WebProxy **" показывает,** является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="860d7-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="860d7-137">Для него должно быть задано **значение false**.</span><span class="sxs-lookup"><span data-stu-id="860d7-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="860d7-138">**Верификатионлевел** указывает уровень проверки, разрешенный для сообщений, отправляемых и получаемых поставщиком услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="860d7-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="860d7-139">Укажите **усесаурцеверификатион**.</span><span class="sxs-lookup"><span data-stu-id="860d7-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="860d7-140">Этот параметр основывается на уровне проверки, который включен в сообщения, отправляемые поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="860d7-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="860d7-141">Если этот уровень не указан, сообщение будет отвергнуто как Непроверяемое.</span><span class="sxs-lookup"><span data-stu-id="860d7-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="860d7-142">Проверка репликации обновленного центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="860d7-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="860d7-143">Изменения, внесенные с помощью командлетов в предыдущих разделах, автоматически применяются к пограничного сервера, и для их репликации обычно требуется менее одной минуты.</span><span class="sxs-lookup"><span data-stu-id="860d7-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="860d7-144">Вы можете проверить состояние репликации и применить изменения на пограничном сервере с помощью следующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="860d7-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="860d7-145">Чтобы проверить наличие обновлений репликации на внутреннем сервере в развертывании Lync Server, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="860d7-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="860d7-146">Чтобы убедиться в том, что изменения применены, выполните на пограничном сервере следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="860d7-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="860d7-147">См. также</span><span class="sxs-lookup"><span data-stu-id="860d7-147">See Also</span></span>


[<span data-ttu-id="860d7-148">Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="860d7-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="860d7-149">Интеграция с размещенной единой системой обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="860d7-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

