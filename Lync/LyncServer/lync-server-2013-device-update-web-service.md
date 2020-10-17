---
title: 'Lync Server 2013: веб-служба обновления устройств'
description: 'Lync Server 2013: веб-служба обновления устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565955"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="10ef4-103">Веб-служба обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10ef4-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10ef4-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="10ef4-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="10ef4-105">Lync Server включает веб-службу обновления устройств, которая автоматически устанавливается в составе роли веб-служб.</span><span class="sxs-lookup"><span data-stu-id="10ef4-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="10ef4-106">Эта служба позволяет скачивать обновления от Майкрософт, тестировать их, а затем развертывать обновления на IP-телефонах в Организации.</span><span class="sxs-lookup"><span data-stu-id="10ef4-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="10ef4-107">Вы также можете использовать веб-службу обновления устройств для отката устройств к предыдущим версиям программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="10ef4-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="10ef4-108">В этом разделе приводятся сведения об управлении веб-службой обновления устройств и развертыванием обновлений с помощью журналов обновления устройств, правил (Lync Phone Edition использует *правила* для связи обновлений микропрограммного обеспечения с аппаратными устройствами) и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="10ef4-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="10ef4-109">Подробные сведения о процессе и возможностях веб-службы обновления устройств приведены в статье [обновление устройств](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) в библиотеке TechNet для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="10ef4-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="10ef4-110">(Обратите внимание, что веб-служба обновления устройств, как и все компоненты Lync Phone Edition, работает аналогично с Lync Server 2013, как и в случае с Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="10ef4-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="10ef4-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="10ef4-111">In This Section</span></span>

  - [<span data-ttu-id="10ef4-112">Журналы и файлы обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10ef4-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="10ef4-113">Правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10ef4-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="10ef4-114">Параметры конфигурации обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10ef4-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="10ef4-115">Просмотр обновлений программного обеспечения для устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10ef4-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10ef4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="10ef4-116">See Also</span></span>


<span data-ttu-id="10ef4-117">[Средства и службы для управления устройствами и устранения неполадок](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="10ef4-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

