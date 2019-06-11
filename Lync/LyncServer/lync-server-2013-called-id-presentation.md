---
title: 'Lync Server 2013: вызываемый идентификационный номер презентации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="12750-102">Презентация с именем "идентификатор" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12750-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12750-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="12750-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="12750-104">При использовании Lync Server 2010 номер телефона вызываемого абонента (т. е. номер телефона) можно перевести из формата E. 164 в локальный формат набора номера, который требуется магистральным одноранговым узлом (то есть шлюзом, частным обменом филиалов или телефонной магистральной панелью SIP).</span><span class="sxs-lookup"><span data-stu-id="12750-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="12750-105">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="12750-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12750-106">Возможность связывать одно или несколько правил трансляции с конфигурацией магистрали корпоративной голосовой связи предназначена для использования в качестве альтернативы настройке <EM></EM> правил перевода на магистральном одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="12750-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="12750-107">Не применяйте правила перевода с конфигурацией корпоративной магистрали, если вы настроили правила трансляции для однорангового канала, так как эти правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="12750-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="12750-108">Чтобы создать или изменить правило трансляции, можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="12750-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="12750-109">С помощью инструмента " **Создание правил перевода** " можно указать значения для начальных цифр, длину, цифр для удаления и цифр, которые нужно добавить, а затем позволить панели управления Lync Server создать соответствующий шаблон сопоставления и правило перевода.</span><span class="sxs-lookup"><span data-stu-id="12750-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="12750-110">Напишите регулярные выражения вручную, чтобы задать шаблон сопоставления и правило трансляции.</span><span class="sxs-lookup"><span data-stu-id="12750-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12750-111">Сведения о том, как создавать регулярные выражения, приведены в <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="12750-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12750-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="12750-112">In This Section</span></span>

  - [<span data-ttu-id="12750-113">Создание или изменение правила трансляции с помощью инструмента "Создание правил перевода" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12750-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="12750-114">Создание и изменение правила трансляции вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12750-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12750-115">См. также</span><span class="sxs-lookup"><span data-stu-id="12750-115">See Also</span></span>


[<span data-ttu-id="12750-116">Презентация идентификации вызывающего абонента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12750-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

