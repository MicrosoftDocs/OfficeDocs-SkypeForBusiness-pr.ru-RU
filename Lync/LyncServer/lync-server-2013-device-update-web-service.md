---
title: 'Lync Server 2013: веб-служба обновления устройств'
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
ms.openlocfilehash: 8c2c9f7068943deabb90e5a87d95f35fecfbc30c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="25651-102">Веб-служба обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25651-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25651-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="25651-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="25651-104">Lync Server включает веб-службу обновления устройств, которая автоматически устанавливается как часть роли веб-служб.</span><span class="sxs-lookup"><span data-stu-id="25651-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="25651-105">Эта служба позволяет загрузить обновления из Microsoft, проверить их, а затем развернуть их на IP-телефоны в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="25651-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="25651-106">Кроме того, с помощью веб-службы обновления устройств можно выполнить откат устройств к предыдущим версиям программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="25651-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="25651-107">В этом разделе приводятся сведения о том, как управлять веб-службой обновления устройств и развернутыми обновлениями с помощью журналов обновлений для устройств, правил (Lync Phone Edition использует *правила* для связи обновлений микропрограмм) и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="25651-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="25651-108">Подробные сведения о процессе и возможностях веб-службы обновления устройств можно найти в разделе [обновление устройств](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) в библиотеке TechNet 2010 для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25651-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="25651-109">(Обратите внимание, что веб-служба обновления устройства, как и все компоненты Lync Phone Edition, работает аналогично с Lync Server 2013, как это происходит в Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="25651-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25651-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="25651-110">In This Section</span></span>

  - [<span data-ttu-id="25651-111">Журналы и файлы обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25651-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="25651-112">Правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25651-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="25651-113">Параметры конфигурации обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25651-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="25651-114">Просмотр обновлений программного обеспечения для устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25651-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25651-115">См. также</span><span class="sxs-lookup"><span data-stu-id="25651-115">See Also</span></span>


<span data-ttu-id="25651-116">[Инструменты и службы для управления устройствами и устранения неполадок](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="25651-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

