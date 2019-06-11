---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a27dbab3e954c96a07739f8a214ae7d1ec87ace
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="49e78-102">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="49e78-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e78-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="49e78-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="49e78-104">В смешанной среде, если вы создаете новый доверенный сервер приложений, необходимо задать пул следующего прыжка в качестве пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49e78-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="49e78-105">В смешанной среде в раскрывающемся списке отображаются стандартный пул Lync Server 2010 и пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49e78-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="49e78-106">Выбор устаревшего пула не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="49e78-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="49e78-107">**Выбор пункта Lync Server 2013 в качестве следующего прыжка при создании надежного сервера приложений**</span><span class="sxs-lookup"><span data-stu-id="49e78-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="49e78-108">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="49e78-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="49e78-109">В левой области щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="49e78-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="49e78-110">Введите **полное доменное имя пула** для доверенного пула приложений и укажите, будет ли он одним или несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="49e78-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="49e78-111">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="49e78-111">Click **Next**.</span></span>

5.  <span data-ttu-id="49e78-112">На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49e78-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="49e78-113">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="49e78-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="49e78-114">Выберите верхний узел **Lync Server** , а затем в меню **действия** выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="49e78-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="49e78-115">Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="49e78-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

