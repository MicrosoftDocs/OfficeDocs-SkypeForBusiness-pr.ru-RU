---
title: 'Lync Server 2013: использование командлетов для отмены подготовки леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="e625c-102">Использование командлетов для отмены подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e625c-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e625c-103">_**Тема последнего изменения:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="e625c-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="e625c-104">Используйте командлет **Disable-ксадфорест** для реверсирования этапа подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="e625c-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e625c-105">Если запустить командлет <STRONG>Disable-ксадфорест</STRONG> в среде, где также уже развернута Предыдущая версия Lync Server, будут также удалены глобальные параметры для предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="e625c-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="e625c-106">Использование командлетов для обратной подготовки леса</span><span class="sxs-lookup"><span data-stu-id="e625c-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="e625c-107">Войдите в систему на компьютере, который входит в состав домена, в качестве члена группы администраторов домена в корневом домене леса.</span><span class="sxs-lookup"><span data-stu-id="e625c-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="e625c-108">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e625c-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e625c-109">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e625c-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="e625c-110">Например:</span><span class="sxs-lookup"><span data-stu-id="e625c-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="e625c-111">Параметр Force указывает, требуется ли принудительное выполнение задачи.</span><span class="sxs-lookup"><span data-stu-id="e625c-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="e625c-112">Если этот параметр не указан, команда не будет выполняться, если даже один домен в лесу все еще подготовлен для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e625c-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="e625c-113">Если указан параметр Force, действие будет продолжено независимо от состояния других доменов в лесу.</span><span class="sxs-lookup"><span data-stu-id="e625c-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="e625c-114">Если параметр Граупдомаин не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="e625c-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e625c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e625c-115">See Also</span></span>


[<span data-ttu-id="e625c-116">Проведение подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e625c-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="e625c-117">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e625c-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

