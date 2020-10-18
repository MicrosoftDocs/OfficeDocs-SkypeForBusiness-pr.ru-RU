---
title: 'Lync Server 2013: Просмотр отчета о сертификатах'
description: 'Lync Server 2013: Просмотр отчета о сертификатах.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2133e2f70c78217788d84251c2035a9115bc3283
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578465"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="3c2a0-103">Просмотр отчета о сертификатах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c2a0-103">Reviewing the Certificates Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c2a0-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3c2a0-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3c2a0-105">Отчет по сертификатам содержит все сертификаты, которые необходимы в рекомендуемом развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-105">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="3c2a0-106">Учетные записи средства планирования для имен субъектов и альтернативных имен субъектов, которые были введены.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-106">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="3c2a0-107">Текст по умолчанию, который остается нередактируемым, может представлять потенциальную задачу для группы, отвечающей за запрос и выдачу сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-107">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="3c2a0-108">Сведения о сертификате также содержат сведения о том, где может быть обычно выдан сертификат.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-108">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="3c2a0-109">Если в инфраструктуре отсутствует внутренняя инфраструктура открытых ключей (PKI), все сертификаты можно запросить через общедоступный поставщик сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-109">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="3c2a0-110">Использование расширенных ключей (EKU) и назначение полей в отчете очень полезно для понимания назначения и местоположения каждого сертификата.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-110">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="3c2a0-111">![Отчет администратора сертификатов](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Отчет администратора сертификатов")</span><span class="sxs-lookup"><span data-stu-id="3c2a0-111">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="3c2a0-112">Внимательно проанализируйте и обязательно изучите использование и назначение каждого сертификата в развертывании.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-112">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="3c2a0-113">При возникновении вопросов о том, что делает сертификат, определите, какой сервер или служба говорят.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-113">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="3c2a0-114">Сертификаты в Lync Server 2013 используются в двух основных целях:</span><span class="sxs-lookup"><span data-stu-id="3c2a0-114">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="3c2a0-115">Transport Layer Security (MTLS) — компьютеры, участвующие в обмене данными, представляют собой сертификат, подтверждающий их подлинность другому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-115">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="3c2a0-116">Это называется проверкой подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-116">This is known as server authentication.</span></span> <span data-ttu-id="3c2a0-117">Связь не может быть выполнена до тех пор, пока не будут считаться удостоверениями других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-117">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="3c2a0-118">Шифрование шифрования (Secure Sockets Layer, SSL, TLS и TLS) — это важный способ обеспечения безопасности связи, обеспечения конфиденциальности и создания доверенной системы связи и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="3c2a0-118">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3c2a0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3c2a0-119">See Also</span></span>


[<span data-ttu-id="3c2a0-120">Просмотр отчетов администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c2a0-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

