---
title: 'Lync Server 2013: сводка по сертификатам — общедоступная служба обмена мгновенными сообщениями'
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
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512786"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b2d34-102">Сводка по сертификатам: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2d34-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2d34-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b2d34-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b2d34-104">Чтобы настроить сертификаты для подключения к общедоступным службам обмена мгновенными сообщениями, необходимо сначала обратить внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется уникальная конфигурация сертификата.</span><span class="sxs-lookup"><span data-stu-id="b2d34-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="b2d34-105">В дополнение к обычному расширенному использованию ключей сервера (EKU) для America Online необходимо, чтобы сертификаты или сертификаты (в случае пограничного пула) также содержали клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="b2d34-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="b2d34-106">Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b2d34-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b2d34-107">Сводка по сертификату– подключение к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b2d34-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2d34-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="b2d34-108">Component</span></span></th>
<th><span data-ttu-id="b2d34-109">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="b2d34-109">Subject name</span></span></th>
<th><span data-ttu-id="b2d34-110">Альтернативные имена субъекта (SAN)/порядок</span><span class="sxs-lookup"><span data-stu-id="b2d34-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="b2d34-111">Comments</span><span class="sxs-lookup"><span data-stu-id="b2d34-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2d34-112">Внешний/пограничный доступ</span><span class="sxs-lookup"><span data-stu-id="b2d34-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="b2d34-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2d34-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b2d34-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2d34-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="b2d34-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2d34-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="b2d34-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b2d34-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="b2d34-117">Сертификат должен относиться к общедоступному центру сертификации и иметь EKU для сервера и клиента, если необходимо развернуть общедоступную службу обмена мгновенными сообщениями с AOL.</span><span class="sxs-lookup"><span data-stu-id="b2d34-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="b2d34-118">Сертификат назначается интерфейсам внешних пограничных серверов для:</span><span class="sxs-lookup"><span data-stu-id="b2d34-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2d34-119">Пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="b2d34-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="b2d34-120">Служба пограничного сервера веб-конференций</span><span class="sxs-lookup"><span data-stu-id="b2d34-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="b2d34-121">Пограничная служба аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="b2d34-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="b2d34-p103">Обратите внимание, что альтернативные имена субъекта автоматически добавляются в сертификат на основе определений в построителе топологий. Записи альтернативных имен необходимы для дополнительных доменов SIP и прочих записей, которые должны поддерживаться. Имя субъекта копируется в одно из альтернативных имен, что необходимо для правильного выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="b2d34-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2d34-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d34-125">See Also</span></span>


[<span data-ttu-id="b2d34-126">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2d34-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

