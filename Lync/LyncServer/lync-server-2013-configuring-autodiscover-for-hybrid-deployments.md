---
title: 'Lync Server 2013: Настройка автообнаружения для гибридных развертываний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="a28f1-102">Настройка службы автообнаружения в Lync Server 2013 для гибридных развертываний</span><span class="sxs-lookup"><span data-stu-id="a28f1-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a28f1-103">_**Последнее изменение темы:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="a28f1-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="a28f1-104">Гибридные развертывания — это конфигурации, в которых используются как облачная служба Microsoft Lync Online, так и локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="a28f1-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="a28f1-105">В такой конфигурации служба автообнаружения должна иметь возможность определять действительное расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="a28f1-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="a28f1-106">Это означает, что служба автообнаружения помогает найти учетную запись пользователя и сервера, на котором размещается учетная запись пользователя, независимо от того, находится ли он в локальном развертывании или в развертывании Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a28f1-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="a28f1-107">Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка обнаружения пользователя будет выполняться следующим образом, в процессе, известном как *обнаруживаемость*.</span><span class="sxs-lookup"><span data-stu-id="a28f1-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="a28f1-108">Пользователь предпринимает попытку подключения к локальному развертыванию **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="a28f1-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="a28f1-109">Сведения о такой попытке отправляются на lyncdiscover.contoso.com — DNS-имя, сопоставленное со службой автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a28f1-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="a28f1-110">Служба автообнаружения относится к предполагаемому пулу регистратора в contoso.com локальное развертывание и получает информацию о фактическом основном сервере пользователя, размещенном в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a28f1-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="a28f1-111">После этого служба автообнаружения отправляет пользователю ссылку на Интернет-службу автообнаружения **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="a28f1-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="a28f1-112">Пользователь предпринимает попытку подключения к Интернет-службе автообнаружения lync.com и может обнаружить учетную запись и почтовый сервер пользователя.</span><span class="sxs-lookup"><span data-stu-id="a28f1-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="a28f1-113">Чтобы разрешить клиентам обнаруживать развертывание, в котором находится домашний сервер пользователей, необходимо настроить службу автообнаружения с помощью нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="a28f1-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="a28f1-114">Выполните следующие действия для настройки службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a28f1-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="a28f1-115">Настройка службы автообнаружения для гибридного развертывания</span><span class="sxs-lookup"><span data-stu-id="a28f1-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="a28f1-116">В разделе, [требования к службе автообнаружения для Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), вы можете использовать Get – CsHostingProvider для получения значения атрибута ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="a28f1-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="a28f1-117">В командной консоли Lync Server введите</span><span class="sxs-lookup"><span data-stu-id="a28f1-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="a28f1-118">Где \[Identity\] заменяется доменным именем общего адресного пространства SIP.</span><span class="sxs-lookup"><span data-stu-id="a28f1-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a28f1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a28f1-119">See Also</span></span>


[<span data-ttu-id="a28f1-120">Get — CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a28f1-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="a28f1-121">Set — CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a28f1-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

