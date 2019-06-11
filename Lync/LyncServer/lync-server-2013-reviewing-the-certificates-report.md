---
title: 'Lync Server 2013: проверка отчета о сертификатах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="4d8ce-102">Просмотр отчета о сертификатах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d8ce-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d8ce-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d8ce-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d8ce-104">Отчет о сертификатах включает все сертификаты, необходимые для рекомендуемого развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="4d8ce-105">Инструмент "планирование" используется для ввода имен субъектов и альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="4d8ce-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="4d8ce-107">Certificate information also contains information about where the certificate can typically be issued from.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="4d8ce-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="4d8ce-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="4d8ce-110">![Отчет администратора о сертификатах] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Отчет администратора о сертификатах")</span><span class="sxs-lookup"><span data-stu-id="4d8ce-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="4d8ce-111">Тщательно рассмотрите и осознайте использование и назначение каждого сертификата в развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="4d8ce-112">Если возникает вопрос о том, для чего именно нужен определенный сертификат, определите взаимодействие серверов и служб.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="4d8ce-113">Сертификаты в Lync Server 2013 используются в двух основных целях:</span><span class="sxs-lookup"><span data-stu-id="4d8ce-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="4d8ce-p103">Протокол MTLS — каждый из взаимодействующих компьютеров предоставляет сертификат, подтверждающий его удостоверение другому компьютеру. Это называется проверкой подлинности сервера. Взаимодействие не начинается до тех пор, пока каждый из компьютеров не будет доверять удостоверению другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-p103">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer. This is known as server authentication. Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="4d8ce-117">Шифрование — шифрование (по протоколам SSL и TLS) имеет критически важное значение для обеспечения безопасности связи, конфиденциальности, а также создания системы доверенного взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="4d8ce-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d8ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4d8ce-118">See Also</span></span>


[<span data-ttu-id="4d8ce-119">Просмотр отчетов администратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d8ce-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

