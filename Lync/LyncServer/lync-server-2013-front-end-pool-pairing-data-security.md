---
title: 'Lync Server 2013: связывание данных, связанных с пулом переднего плана'
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
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500726"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="00d17-102">Безопасность данных связывания пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d17-102">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d17-103">_**Последнее изменение темы:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="00d17-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="00d17-104">Служба резервного копирования — это механизм репликации данных, появившийся в Lync Server 2013, который передает данные пользователей и содержимое конференций между двумя связанными интерфейсными пулами непрерывно в два центра обработки данных для целей аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="00d17-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="00d17-105">Данные пользователей содержат SIP URI, а также списки контактов и настройки пользователей.</span><span class="sxs-lookup"><span data-stu-id="00d17-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="00d17-106">Содержимое конференции включает в себя отправку Microsoft PowerPoint 2010, а также доски, используемые в конференциях.</span><span class="sxs-lookup"><span data-stu-id="00d17-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="00d17-107">Данные пользователей и контент конференций из исходного пула экспортируются из локального хранилища, пакуются, переносятся в целевой пул, где они распаковываются и импортируются в локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="00d17-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="00d17-108">Служба резервного копирования предполагает, что канал связи между двумя центрами обработки данных находится в пределах корпоративной сети, защищенной от Интернета.</span><span class="sxs-lookup"><span data-stu-id="00d17-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="00d17-109">Он не шифрует передаваемые данные между двумя центрами обработки данных и не использует безопасный протокол, такой как HTTPS.</span><span class="sxs-lookup"><span data-stu-id="00d17-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="00d17-110">Поэтому атака с посредником из внутреннего персонала в пределах корпоративной сети возможна.</span><span class="sxs-lookup"><span data-stu-id="00d17-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="00d17-111">Оценка рисков безопасности</span><span class="sxs-lookup"><span data-stu-id="00d17-111">Evaluating Security Risks</span></span>

<span data-ttu-id="00d17-112">Любой предприятие, которое развертывает Lync Server 2013 в нескольких центрах обработки данных и использует функцию аварийного восстановления, должно обеспечивать защиту трафика центра обработки данных в корпоративной интрасети.</span><span class="sxs-lookup"><span data-stu-id="00d17-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="00d17-113">Предприятия, которые хотят предотвратить внутренние атаки, должны защитить каналы связи между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="00d17-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="00d17-p103">Защита центров обработки данных предприятия в пределах корпоративной интрасети является стандартом. Существует множество других типов корпоративных конфиденциальных данных, передаваемых между этими центрами обработки данных. ИТ-инфраструктура предприятия подвергается большому риску если каналы связи между центрами обработки данных не защищены.</span><span class="sxs-lookup"><span data-stu-id="00d17-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="00d17-p104">Хотя риск атаки с посредником внутри корпоративной сети существует, он относительно небольшой по сравнению с предоставлением доступа к трафику из Интернета. В частности, пользовательские данные, предоставляемые службой резервного копирования (такие как SIP URI), как правило, доступны всем сотрудникам компании с помощью других средств, таких как глобальная адресная книга Exchange или других  программных каталогов. Следовательно, необходимо сосредоточить усилия на защите глобальной сети между двумя центрами обработки данных, когда два центра обработки данных используются для копирования данных между две спаренными пулами.</span><span class="sxs-lookup"><span data-stu-id="00d17-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="00d17-120">Снижение рисков безопасности</span><span class="sxs-lookup"><span data-stu-id="00d17-120">Mitigating Security Risks</span></span>

<span data-ttu-id="00d17-121">Существует множество способов улучшить безопасность трафика службы резервного копирования: от ограничения доступа к центрам обработки данных до защиты трафика глобальной сети между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="00d17-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="00d17-122">В большинстве случаев предприятия, развертывающие Lync Server 2013, могут уже иметь необходимую инфраструктуру безопасности.</span><span class="sxs-lookup"><span data-stu-id="00d17-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="00d17-123">Корпорация Майкрософт представляет предприятиям, которым требуется помощь, решение, являющееся примером создания безопасной ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="00d17-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="00d17-124">Однако это не означает, что это единственное решение, а также не подразумевает, что это предпочтительное решение для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00d17-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="00d17-125">Корпоративным клиентам рекомендуется выбрать решение, которое лучше всего соответствует их потребностям, на основе их ИТ-инфраструктуры безопасности.Пример решения Майкрософт использует IPSec и групповую политику для изоляции серверов и доменов.</span><span class="sxs-lookup"><span data-stu-id="00d17-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="00d17-126">Дополнительные сведения см [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) .</span><span class="sxs-lookup"><span data-stu-id="00d17-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="00d17-127">При наличии вопросов пишите по адресу secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="00d17-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="00d17-128">Другим возможным решением является использование IPSec только для защиты данных, отправляемых самой службой резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="00d17-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="00d17-129">При выборе этого метода необходимо настроить правила IPSec для протокола SMB для следующих серверов, где пул A и пул B являются двумя связанными интерфейсными пулами.</span><span class="sxs-lookup"><span data-stu-id="00d17-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="00d17-130">Служба SMB (TCP/445) от каждого сервера переднего плана в пуле A до хранилища файлов, используемого пулом B.</span><span class="sxs-lookup"><span data-stu-id="00d17-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="00d17-131">Служба SMB (TCP/445) от каждого сервера переднего плана в пуле B до хранилища файлов, используемого пулом A.</span><span class="sxs-lookup"><span data-stu-id="00d17-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="00d17-132">Протокол IPsec не предназначен для замены безопасности на уровне приложения, например SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="00d17-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="00d17-133">Одним из преимуществ использования IPsec является то, что он обеспечивает безопасность сетевого трафика для существующих приложений без необходимости их изменения.</span><span class="sxs-lookup"><span data-stu-id="00d17-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="00d17-134">Предприятия, которые хотят защитить транспортировку между двумя центрами обработки данных, должны обратиться к соответствующим поставщикам сетевых устройств о способах настройки безопасных подключений к глобальной сети с помощью оборудования поставщика.</span><span class="sxs-lookup"><span data-stu-id="00d17-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

