---
title: 'Lync Server 2013: Просмотр отчета о сертификатах'
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
ms.openlocfilehash: 9c751de439ef84e718ed1d21e43c11be89cc28fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="d198f-102">Просмотр отчета о сертификатах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d198f-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d198f-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d198f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d198f-104">Отчет по сертификатам содержит все сертификаты, которые необходимы в рекомендуемом развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d198f-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="d198f-105">Учетные записи средства планирования для имен субъектов и альтернативных имен субъектов, которые были введены.</span><span class="sxs-lookup"><span data-stu-id="d198f-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="d198f-106">Текст по умолчанию, который остается нередактируемым, может представлять потенциальную задачу для группы, отвечающей за запрос и выдачу сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d198f-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="d198f-107">Сведения о сертификате также содержат сведения о том, где может быть обычно выдан сертификат.</span><span class="sxs-lookup"><span data-stu-id="d198f-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="d198f-108">Если в инфраструктуре отсутствует внутренняя инфраструктура открытых ключей (PKI), все сертификаты можно запросить через общедоступный поставщик сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d198f-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="d198f-109">Использование расширенных ключей (EKU) и назначение полей в отчете очень полезно для понимания назначения и местоположения каждого сертификата.</span><span class="sxs-lookup"><span data-stu-id="d198f-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="d198f-110">![Отчет администратора сертификатов](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Отчет администратора сертификатов")</span><span class="sxs-lookup"><span data-stu-id="d198f-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="d198f-111">Внимательно проанализируйте и обязательно изучите использование и назначение каждого сертификата в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d198f-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="d198f-112">При возникновении вопросов о том, что делает сертификат, определите, какой сервер или служба говорят.</span><span class="sxs-lookup"><span data-stu-id="d198f-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="d198f-113">Сертификаты в Lync Server 2013 используются в двух основных целях:</span><span class="sxs-lookup"><span data-stu-id="d198f-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="d198f-114">Transport Layer Security (MTLS) — компьютеры, участвующие в обмене данными, представляют собой сертификат, подтверждающий их подлинность другому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d198f-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="d198f-115">Это называется проверкой подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="d198f-115">This is known as server authentication.</span></span> <span data-ttu-id="d198f-116">Связь не может быть выполнена до тех пор, пока не будут считаться удостоверениями других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d198f-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="d198f-117">Шифрование шифрования (Secure Sockets Layer, SSL, TLS и TLS) — это важный способ обеспечения безопасности связи, обеспечения конфиденциальности и создания доверенной системы связи и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="d198f-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d198f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d198f-118">See Also</span></span>


[<span data-ttu-id="d198f-119">Просмотр отчетов администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d198f-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

