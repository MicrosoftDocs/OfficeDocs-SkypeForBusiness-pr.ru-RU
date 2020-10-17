---
title: Сброс контроля допуска звонков
description: Сброс контроля допуска звонков.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551245"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="4a85a-103">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="4a85a-103">Reset call admission control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a85a-104">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="4a85a-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="4a85a-105">Если в пуле переднего плана Lync Server 2010 размещается контроль допуска звонков (CAC), необходимо переместить размещение CAC в пул Lync Server 2013, прежде чем можно будет удалить интерфейсный пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4a85a-105">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="4a85a-106">Чтобы сбросить контроль допуска звонков</span><span class="sxs-lookup"><span data-stu-id="4a85a-106">To reset CAC</span></span>

1.  <span data-ttu-id="4a85a-107">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="4a85a-107">Open Topology Builder.</span></span>

2.  <span data-ttu-id="4a85a-108">Щелкните правой кнопкой мыши узел сайта, затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4a85a-108">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4a85a-109">Убедитесь, что в разделе **Параметры контроля допуска звонков** выбран параметр **Включить контроль допуска звонков**.</span><span class="sxs-lookup"><span data-stu-id="4a85a-109">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="4a85a-110">В разделе **пул переднего плана для запуска контроля допуска звонков (CAC)** выберите пул Lync Server 2013, который будет обслуживать CAC, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4a85a-110">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="4a85a-111">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="4a85a-111">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

