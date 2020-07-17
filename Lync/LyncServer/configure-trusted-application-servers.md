---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="24fda-102">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="24fda-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24fda-103">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="24fda-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="24fda-104">Если вы создаете новый доверенный сервер приложений, в смешанной среде необходимо установить пул следующего прыжка в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24fda-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="24fda-105">В смешанной среде в раскрывающемся списке отображаются устаревший пул Lync Server 2010 и пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24fda-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="24fda-106">Предыдущую версию пула выбрать нельзя.</span><span class="sxs-lookup"><span data-stu-id="24fda-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="24fda-107">**Выбор Lync Server 2013 в качестве следующего перехода при создании доверенного сервера приложений**</span><span class="sxs-lookup"><span data-stu-id="24fda-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="24fda-108">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="24fda-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="24fda-109">В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений**, затем щелкните **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="24fda-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="24fda-110">Введите **Полное доменное имя пула** для пула доверенных приложений и укажите, будет ли это пул с одним или несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="24fda-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="24fda-111">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="24fda-111">Click **Next**.</span></span>

5.  <span data-ttu-id="24fda-112">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24fda-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="24fda-113">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="24fda-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="24fda-114">Выберите верхний узел **Lync Server** в меню **Действие** выберите действие **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="24fda-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="24fda-115">Убедитесь в том, что **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="24fda-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

