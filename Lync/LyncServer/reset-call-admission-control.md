---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="41e18-102">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="41e18-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41e18-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="41e18-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="41e18-104">Если в пуле внешних интерфейсов Lync Server 2010 (CAC) размещен элемент управления допускной передачей, необходимо переместить сервер CAC на пул Lync Server 2013, прежде чем можно будет удалить пул внешних интерфейсов Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="41e18-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="41e18-105">Чтобы сбросить параметры CAC</span><span class="sxs-lookup"><span data-stu-id="41e18-105">To reset CAC</span></span>

1.  <span data-ttu-id="41e18-106">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="41e18-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="41e18-107">Щелкните правой кнопкой мыши узел сайта и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="41e18-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="41e18-108">Убедитесь, что в разделе **параметр управления**допуском звонков установлен флажок **включить управление допуском звонков** .</span><span class="sxs-lookup"><span data-stu-id="41e18-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="41e18-109">В разделе **пул переднего плана, чтобы запустить управление допуском звонков (CAC)**, выберите пул Lync Server 2013, который будет размещаться в CAC, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41e18-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="41e18-110">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="41e18-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

