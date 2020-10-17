---
title: Настройка службы автообнаружения для мобильной работы с гибридными развертываниями
description: Настройка службы автообнаружения для мобильной работы с гибридными развертываниями.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66f0045ec1fce65b8e21b6a6f4494b96c93912
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562465"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="78092-103">Настройка службы автообнаружения в Lync Server 2013 для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="78092-103">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78092-104">_**Последнее изменение темы:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="78092-104">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="78092-105">Гибридные развертывания — это конфигурации, в которых используются как облачная служба Microsoft Lync Online, так и локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="78092-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="78092-106">В такой конфигурации служба автообнаружения должна иметь возможность определять действительное расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="78092-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="78092-107">Это означает, что служба автообнаружения помогает найти учетную запись пользователя и сервера, на котором размещается учетная запись пользователя, независимо от того, находится ли он в локальном развертывании или в развертывании Lync Online.</span><span class="sxs-lookup"><span data-stu-id="78092-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="78092-108">Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка обнаружения пользователя будет выполняться следующим образом, в процессе, известном как *обнаруживаемость*.</span><span class="sxs-lookup"><span data-stu-id="78092-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="78092-109">Пользователь предпринимает попытку подключения к локальному развертыванию **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="78092-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="78092-110">Сведения о такой попытке отправляются на lyncdiscover.contoso.com — DNS-имя, сопоставленное со службой автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="78092-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="78092-111">Служба автообнаружения относится к предполагаемому пулу регистратора в contoso.com локальное развертывание и получает информацию о фактическом основном сервере пользователя, размещенном в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="78092-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="78092-112">После этого служба автообнаружения отправляет пользователю ссылку на Интернет-службу автообнаружения **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="78092-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="78092-113">Пользователь предпринимает попытку подключения к Интернет-службе автообнаружения lync.com и может обнаружить учетную запись и почтовый сервер пользователя.</span><span class="sxs-lookup"><span data-stu-id="78092-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="78092-p103">Чтобы предоставить мобильным клиентам возможность обнаружения развертывания, в котором размещен домашний сервер пользователя, необходимо настроить службу автообнаружения с новым унифицированным указателем ресурсов (URL-адресом). Выполните следующие действия для настройки службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="78092-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="78092-116">Настройка службы автообнаружения для гибридного развертывания</span><span class="sxs-lookup"><span data-stu-id="78092-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="78092-117">Для получения значения атрибута ProxyFQDN используется Get-CsHostingProvider.</span><span class="sxs-lookup"><span data-stu-id="78092-117">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="78092-118">В командной консоли Lync Server введите</span><span class="sxs-lookup"><span data-stu-id="78092-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="78092-119">Где \[ Identity \] заменяется доменным именем общего адресного пространства SIP.</span><span class="sxs-lookup"><span data-stu-id="78092-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78092-120">См. также</span><span class="sxs-lookup"><span data-stu-id="78092-120">See Also</span></span>


<span data-ttu-id="78092-121">[Get — CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="78092-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="78092-122">[Set — CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="78092-122">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

