---
title: Администрирование серверов после миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Administering servers after migration
ms:assetid: 7b08f048-c951-4050-b77c-0fff351620e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205023(v=OCS.15)
ms:contentKeyID: 48184582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc74d02f0d99319d2014262ff9a607d723aaa274
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-servers-after-migration"></a><span data-ttu-id="b9988-102">Администрирование серверов после миграции</span><span class="sxs-lookup"><span data-stu-id="b9988-102">Administering servers after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9988-103">_**Тема последнего изменения:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="b9988-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="b9988-104">Как правило, необходимо использовать средство администрирования, соответствующее серверной версии, которой вы хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="b9988-104">In general, you must use the administrative tool that corresponds to the server version that you want to manage.</span></span> <span data-ttu-id="b9988-105">Установка средств администрирования Lync Server 2010 и Lync Server 2013 на одном и том же компьютере невозможна.</span><span class="sxs-lookup"><span data-stu-id="b9988-105">You cannot install the Lync Server 2010 and the Lync Server 2013 administrative tools on the same computer.</span></span> <span data-ttu-id="b9988-106">Кроме того, панель управления Lync Server 2013 не устанавливается на каждый сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="b9988-106">Also, the Lync Server 2013 Control Panel is not installed automatically on each server.</span></span> <span data-ttu-id="b9988-107">Чтобы установить панель управления Lync Server 2013, следуйте инструкциям, приведенным в разделе [Установка средств администрирования Lync server 2013](lync-server-2013-install-lync-server-administrative-tools.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b9988-107">To install the Lync Server 2013 Control Panel, follow the procedure inside the topic [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Deployment documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9988-108">После развертывания пилотного пула Lync Server 2013 вы не сможете использовать сервер Lync Server 2010 Topology Builder или панель управления Lync Server 2010 для управления ресурсами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9988-108">After a Lync Server 2013 pilot pool is deployed, you cannot use Lync Server 2010 Topology Builder or Lync Server 2010 Control Panel to manage any Lync Server 2013 resources.</span></span> <span data-ttu-id="b9988-109">Вы должны использовать инструменты Lync Server 2013 для управления ресурсами Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b9988-109">You must use Lync Server 2013 tools to manage Lync Server 2013 and Lync Server 2010 resources.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

