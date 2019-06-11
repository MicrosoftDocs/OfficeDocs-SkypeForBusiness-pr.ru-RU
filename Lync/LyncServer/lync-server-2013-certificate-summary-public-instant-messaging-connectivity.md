---
title: 'Lync Server 2013: сведения о сертификате-общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="ea135-102">Сведения о сертификате: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea135-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea135-103">_**Тема последнего изменения:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="ea135-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="ea135-104">Чтобы настроить сертификаты для связи с помощью общедоступной службы обмена мгновенными сообщениями, необходимо сначала обратить внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется уникальная Конфигурация сертификата.</span><span class="sxs-lookup"><span data-stu-id="ea135-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="ea135-105">В дополнение к стандартному расширенному использованию серверного ключа (EKU) для Skype Online требуется, чтобы сертификат или сертификаты (в случае пограничного пула) также содержали клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="ea135-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="ea135-106">Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ea135-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ea135-107">Сведения о сертификате: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ea135-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea135-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="ea135-108">Component</span></span></th>
<th><span data-ttu-id="ea135-109">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="ea135-109">Subject name</span></span></th>
<th><span data-ttu-id="ea135-110">Замещающий имена субъектов (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="ea135-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="ea135-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ea135-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea135-112">Внешний край и доступ</span><span class="sxs-lookup"><span data-stu-id="ea135-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="ea135-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea135-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ea135-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea135-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="ea135-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea135-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="ea135-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ea135-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ea135-117">Сертификат должен находиться в общедоступном центре сертификации, а также в том случае, если вы разворачиваете общедоступную службу обмена мгновенными сообщениями с AOL, и у вас должен быть серверный EKU</span><span class="sxs-lookup"><span data-stu-id="ea135-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="ea135-118">Сертификат назначается внешним интерфейсам пограничного сервера для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ea135-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea135-119">доступа</span><span class="sxs-lookup"><span data-stu-id="ea135-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="ea135-120">веб-конференций</span><span class="sxs-lookup"><span data-stu-id="ea135-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="ea135-121">передачи аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ea135-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="ea135-122">Обратите внимание, что сети SAN автоматически добавляются к сертификату на основе определений в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="ea135-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="ea135-123">Вы добавляете записи SAN по мере необходимости для дополнительных доменов SIP и других элементов, которые необходимо поддерживать.</span><span class="sxs-lookup"><span data-stu-id="ea135-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="ea135-124">Имя субъекта реплицируется в сети SAN и должно быть представлено для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="ea135-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea135-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ea135-125">See Also</span></span>


[<span data-ttu-id="ea135-126">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea135-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

