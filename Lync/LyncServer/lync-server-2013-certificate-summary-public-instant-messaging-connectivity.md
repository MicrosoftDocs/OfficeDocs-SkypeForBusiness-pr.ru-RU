---
title: 'Lync Server 2013: сводка по сертификатам — общедоступная служба обмена мгновенными сообщениями'
description: 'Lync Server 2013: сводка по сертификатам — общедоступная служба обмена мгновенными сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf5a01bdeb03da158e221c623417a1b42cc82f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572335"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="7c519-103">Сводка по сертификатам: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c519-103">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c519-104">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="7c519-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="7c519-105">Чтобы настроить сертификаты для подключения к общедоступным службам обмена мгновенными сообщениями, необходимо сначала обратить внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется уникальная конфигурация сертификата.</span><span class="sxs-lookup"><span data-stu-id="7c519-105">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="7c519-106">В дополнение к обычному расширенному использованию ключей сервера (EKU) для America Online необходимо, чтобы сертификаты или сертификаты (в случае пограничного пула) также содержали клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="7c519-106">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="7c519-107">Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7c519-107">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7c519-108">Сводка по сертификату– подключение к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c519-108">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c519-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="7c519-109">Component</span></span></th>
<th><span data-ttu-id="7c519-110">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="7c519-110">Subject name</span></span></th>
<th><span data-ttu-id="7c519-111">Альтернативные имена субъекта (SAN)/порядок</span><span class="sxs-lookup"><span data-stu-id="7c519-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="7c519-112">Comments</span><span class="sxs-lookup"><span data-stu-id="7c519-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c519-113">Внешний/пограничный доступ</span><span class="sxs-lookup"><span data-stu-id="7c519-113">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="7c519-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c519-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7c519-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c519-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="7c519-116">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c519-116">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="7c519-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7c519-117">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7c519-118">Сертификат должен относиться к общедоступному центру сертификации и иметь EKU для сервера и клиента, если необходимо развернуть общедоступную службу обмена мгновенными сообщениями с AOL.</span><span class="sxs-lookup"><span data-stu-id="7c519-118">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="7c519-119">Сертификат назначается интерфейсам внешних пограничных серверов для:</span><span class="sxs-lookup"><span data-stu-id="7c519-119">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c519-120">Пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="7c519-120">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="7c519-121">Служба пограничного сервера веб-конференций</span><span class="sxs-lookup"><span data-stu-id="7c519-121">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="7c519-122">Пограничная служба аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="7c519-122">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="7c519-p103">Обратите внимание, что альтернативные имена субъекта автоматически добавляются в сертификат на основе определений в построителе топологий. Записи альтернативных имен необходимы для дополнительных доменов SIP и прочих записей, которые должны поддерживаться. Имя субъекта копируется в одно из альтернативных имен, что необходимо для правильного выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="7c519-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c519-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7c519-126">See Also</span></span>


[<span data-ttu-id="7c519-127">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c519-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

