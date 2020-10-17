---
title: 'Lync Server 2013: определение правил преобразования'
description: 'Lync Server 2013: определение правил преобразования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c59225c8dc74d7d97bf3536c7b7073bc977925
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568395"
---
# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="6e932-103">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e932-103">Defining translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e932-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6e932-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6e932-105">Lync Server 2013 Enterprise Voice маршрутизирует вызовы, основанные на телефонных номерах, нормализованном в формате E. 164.</span><span class="sxs-lookup"><span data-stu-id="6e932-105">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="6e932-106">Это означает, что все набранные строки должны быть нормализованы до формата E. 164 для выполнения обратного просмотра номера (RNL), чтобы их можно было преобразовать в соответствующие URI SIP.</span><span class="sxs-lookup"><span data-stu-id="6e932-106">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="6e932-107">Lync Server 2013 предоставляет возможность управлять вызываемым ИДЕНТИФИКАТОРом и представлением идентификатора звонящего.</span><span class="sxs-lookup"><span data-stu-id="6e932-107">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="6e932-108">В данном разделе указывается, как обрабатывать вызываемый идентификатор и идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="6e932-108">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e932-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="6e932-109">In This Section</span></span>

  - [<span data-ttu-id="6e932-110">Презентация идентификации звонящего в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e932-110">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="6e932-111">Презентация с именем ID в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e932-111">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e932-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6e932-112">See Also</span></span>


[<span data-ttu-id="6e932-113">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e932-113">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

