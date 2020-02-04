---
title: 'Lync Server 2013: безопасность спаренных данных пула переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="3a852-102">Безопасность спаренных данных пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a852-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a852-103">_**Тема последнего изменения:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="3a852-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="3a852-104">Служба резервного копирования — это механизм репликации данных, представленный в Lync Server 2013 и передающий данные пользователей и собраний между двумя объединенными пулами переднего плана в двух центрах обработки данных для целей аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="3a852-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="3a852-105">Пользовательские данные содержат URI SIP пользователя, а также списки контактов и параметры.</span><span class="sxs-lookup"><span data-stu-id="3a852-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="3a852-106">В контент Конференции входит Microsoft PowerPoint 2010, а также доска, используемая в конференциях.</span><span class="sxs-lookup"><span data-stu-id="3a852-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="3a852-107">Из исходного пула данные пользователя и конференции экспортируются из локального хранилища, ZIP, передаются в конечный пул, где он не ZIP и импортирован в локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="3a852-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="3a852-108">Служба резервного копирования предполагает, что канал связи между двумя центрами обработки данных находится в пределах корпоративной сети, защищенной от Интернета.</span><span class="sxs-lookup"><span data-stu-id="3a852-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="3a852-109">Она не шифрует данные, передаваемые между двумя центрами обработки данных и не инкапсулированные в безопасном протоколе, например HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3a852-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="3a852-110">Таким образом, это может привести к повременному взаимоатаке внутренних сотрудников в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="3a852-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="3a852-111">Оценка рисков безопасности</span><span class="sxs-lookup"><span data-stu-id="3a852-111">Evaluating Security Risks</span></span>

<span data-ttu-id="3a852-112">Любая организация, развертывающая сервер Lync Server 2013 в нескольких центрах обработки данных и использующая функцию аварийного восстановления, должна обеспечивать защиту трафика центра обработки данных в корпоративной интрасети.</span><span class="sxs-lookup"><span data-stu-id="3a852-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="3a852-113">Компании, которые важны для защиты от внутренних атак, должны обеспечивать безопасность коммуникационных связей между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3a852-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="3a852-114">Предположение о том, что центры обработки данных предприятия защищены от корпоративной интрасети, являются стандартными.</span><span class="sxs-lookup"><span data-stu-id="3a852-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="3a852-115">В этих центрах обработки данных есть другие типы корпоративных конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="3a852-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="3a852-116">ИТ-инфраструктура компании Дире риск, если эти ссылки на источники данных не защищены.</span><span class="sxs-lookup"><span data-stu-id="3a852-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="3a852-117">Хотя риск атаки "злоумышленник в середине" внутри корпоративной сети существует, он относительно небольшой по сравнению с предоставлением доступа к трафику из Интернета.</span><span class="sxs-lookup"><span data-stu-id="3a852-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="3a852-118">В частности, данные пользователей, предоставленные службой резервного копирования (например, URI SIP), обычно доступны всем сотрудникам Организации с помощью других средств, таких как Глобальная адресная книга, Exchange или другого программного обеспечения для каталогов.</span><span class="sxs-lookup"><span data-stu-id="3a852-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="3a852-119">Следовательно, при использовании службы резервного копирования для копирования данных между двумя объединенными пулами фокус должен быть защищен между двумя центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3a852-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="3a852-120">Снижение угроз безопасности</span><span class="sxs-lookup"><span data-stu-id="3a852-120">Mitigating Security Risks</span></span>

<span data-ttu-id="3a852-121">Существует множество способов улучшить защиту трафика службы резервного копирования, начиная от ограничения доступа к центрам обработки данных для обеспечения безопасности транспорта WAN между двумя центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3a852-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="3a852-122">В большинстве случаев компании, в которых развертывается Lync Server 2013, уже может быть нужна инфраструктура безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a852-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="3a852-123">Для предприятий, которым нужна рекомендация, корпорация Майкрософт предоставляет решение в качестве примера создания безопасной ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3a852-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="3a852-124">Однако это не означает, что это единственное решение, и не означает, что это решение является предпочтительным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a852-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="3a852-125">Корпорация Майкрософт рекомендует корпоративным клиентам выбирать решение, удовлетворяющее определенным требованиям, в зависимости от их инфраструктуры и требований безопасности. В примере решения Майкрософт используются IPSec и групповая политика для изоляции сервера и домена.</span><span class="sxs-lookup"><span data-stu-id="3a852-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="3a852-126">Подробности можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)разделе.</span><span class="sxs-lookup"><span data-stu-id="3a852-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="3a852-127">Чтобы получить ответы на вопросы и примечания, обратитесь в secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3a852-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="3a852-128">Другим возможным решением является использование IPSec, чтобы обеспечить безопасность данных, отправленных самой службой резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="3a852-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="3a852-129">При выборе этого метода требуется настроить правила IPSec для протокола SMB для следующих серверов, где пул A и пул B являются двумя связанными внешними пулами.</span><span class="sxs-lookup"><span data-stu-id="3a852-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="3a852-130">Служба SMB (TCP/445) от каждого внешнего сервера в пуле A до хранилища файлов, используемого в пуле B.</span><span class="sxs-lookup"><span data-stu-id="3a852-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="3a852-131">Служба SMB (TCP/445) от каждого внешнего сервера в пуле B до хранилища файлов, используемого в пуле A.</span><span class="sxs-lookup"><span data-stu-id="3a852-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3a852-132">Протокол IPsec не был предназначен для замены средств обеспечения безопасности на уровне приложений, таких как SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="3a852-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="3a852-133">Преимущество использования IPsec заключается в том, что этот протокол может обеспечить безопасность сетевого трафика существующих приложений без их изменения.</span><span class="sxs-lookup"><span data-stu-id="3a852-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="3a852-134">Предприятия, которые хотят просто защитить передачу данных между двумя центрами обработки данных, должны проконсультироваться с поставщиками сетевого оборудования по поводу способов настройки безопасного соединения WAN с использованием оборудования поставщика.</span><span class="sxs-lookup"><span data-stu-id="3a852-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

