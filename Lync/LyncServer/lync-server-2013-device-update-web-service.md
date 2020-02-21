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
ms.openlocfilehash: 509428b4cd0646e0993d6127bcee8a1f2182c11f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="3b1da-102">Веб-служба обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1da-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b1da-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3b1da-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3b1da-104">Lync Server включает веб-службу обновления устройств, которая автоматически устанавливается в составе роли веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3b1da-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="3b1da-105">Эта служба позволяет скачивать обновления от Майкрософт, тестировать их, а затем развертывать обновления на IP-телефонах в Организации.</span><span class="sxs-lookup"><span data-stu-id="3b1da-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="3b1da-106">Вы также можете использовать веб-службу обновления устройств для отката устройств к предыдущим версиям программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="3b1da-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="3b1da-107">В этом разделе приводятся сведения об управлении веб-службой обновления устройств и развертыванием обновлений с помощью журналов обновления устройств, правил (Lync Phone Edition использует *правила* для связи обновлений микропрограммного обеспечения с аппаратными устройствами) и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3b1da-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="3b1da-108">Подробные сведения о процессе и возможностях веб-службы обновления устройств приведены в статье [обновление устройств](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) в библиотеке TechNet для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b1da-108">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="3b1da-109">(Обратите внимание, что веб-служба обновления устройств, как и все компоненты Lync Phone Edition, работает аналогично с Lync Server 2013, как и в случае с Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="3b1da-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b1da-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="3b1da-110">In This Section</span></span>

  - [<span data-ttu-id="3b1da-111">Журналы и файлы обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1da-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="3b1da-112">Правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1da-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="3b1da-113">Параметры конфигурации обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1da-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="3b1da-114">Просмотр обновлений программного обеспечения для устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b1da-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b1da-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3b1da-115">See Also</span></span>


<span data-ttu-id="3b1da-116">[Средства и службы для управления устройствами и устранения неполадок](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3b1da-116">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

