---
title: 'Lync Server 2013: Проверка связи с клиентом Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518666"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="4a988-102">Проверка связи с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a988-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a988-103">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="4a988-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="4a988-104">Чтобы разрешить пользователям Lync в Организации общаться с пользователями Microsoft Lync Online 2010, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a988-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="4a988-105">Соблюсти все обязательные условия.</span><span class="sxs-lookup"><span data-stu-id="4a988-105">Met all prerequisites.</span></span> <span data-ttu-id="4a988-106">К ним относятся развертывание внутренних и пограничных серверов, включение поддержки федерации для организации и настройка пользовательских учетных записей.</span><span class="sxs-lookup"><span data-stu-id="4a988-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="4a988-107">Сведения о том, [как включить федерацию с клиентом Lync Online в Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md), можно найти в статье необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="4a988-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="4a988-108">Настроить поддержку доступа к домену во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4a988-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="4a988-109">Сюда входит создание записи поставщика узла и Настройка развертывания для предоставления доступа из домена клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4a988-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="4a988-110">Дополнительную информацию можно узнать [в статье Настройка поддержки федерации для домена Lync Online в Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="4a988-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="4a988-111">Настроить пользовательские учетные записи для поддержки федерации.</span><span class="sxs-lookup"><span data-stu-id="4a988-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="4a988-112">Дополнительную информацию можно узнать в статье [Настройка доступа пользователей для Федерации с клиентом Lync Online в Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="4a988-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="4a988-113">После выполнения всех этих действий администратор Lync Online 2010 завершает всю конфигурацию своих веб-служб для поддержки Федерации с вашей организацией, а также для проверки связи путем тестирования связи между внутренним пользователем в Организации и пользователем клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4a988-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="4a988-114">В случае неудачного подключения используйте средство ведения журнала с пограничного сервера для записи файлов журнала и трассировки, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="4a988-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="4a988-115">Сведения об использовании средства ведения журнала приведены в статье [Open the администрирование Lync Server 2013 Tools](lync-server-2013-open-lync-server-administrative-tools.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4a988-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="4a988-116">Для получения дополнительных сведений о средстве ведения журнала обратитесь к документации по средству ведения журнала Lync Server 2010 в библиотеке TechNet по адресу [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="4a988-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

