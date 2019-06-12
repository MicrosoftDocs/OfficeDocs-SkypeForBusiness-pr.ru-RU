---
title: 'Lync Server 2013: Проверка связи с клиентом Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="d8a51-102">Проверка связи с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8a51-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8a51-103">_**Тема последнего изменения:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d8a51-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d8a51-104">Чтобы разрешить пользователям Lync в организации взаимодействовать с пользователями Microsoft Lync Online 2010, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d8a51-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="d8a51-105">Выполнены все необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="d8a51-105">Met all prerequisites.</span></span> <span data-ttu-id="d8a51-106">Сюда входит развертывание внутренних и пограничных серверов, включение поддержки федерации для Организации и Настройка учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8a51-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="d8a51-107">Дополнительные сведения можно найти [в разделе Предварительные требования для Федерации с клиентом Lync Online в Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="d8a51-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="d8a51-108">Настройка поддержки доступа к доменам во внутренней среде.</span><span class="sxs-lookup"><span data-stu-id="d8a51-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="d8a51-109">Сюда входит создание записи поставщика узла и Настройка развертывания для разрешения доступа из домена клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d8a51-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="d8a51-110">Подробности можно найти [в разделе Настройка поддержки федерации для домена Lync Online в Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d8a51-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="d8a51-111">Настройка учетных записей пользователей для поддержки Федерации.</span><span class="sxs-lookup"><span data-stu-id="d8a51-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="d8a51-112">Подробности можно найти [в разделе Настройка доступа пользователей к интеграции с клиентом Lync Online в Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="d8a51-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="d8a51-113">После выполнения всех этих действий и администратором пользователя Lync Online 2010 завершается вся настройка интернет-служб для поддержки Федерации с вашей организацией, проверка связи путем тестирования связи между внутренней пользователя в Организации и пользователя клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d8a51-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="d8a51-114">Если связь не была успешной, для устранения проблемы используйте средство ведения журналов из пограничного сервера для захвата файлов журнала и трассировки.</span><span class="sxs-lookup"><span data-stu-id="d8a51-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="d8a51-115">Подробнее об использовании средства ведения журнала можно найти в разделе [Открытие средства администрирования Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="d8a51-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="d8a51-116">Подробные сведения о средстве ведения журнала можно найти в документации по средству ведения журнала Lync Server 2010 в [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)библиотеке TechNet по адресу.</span><span class="sxs-lookup"><span data-stu-id="d8a51-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

