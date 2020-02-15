---
title: 'Lync Server 2013: вызываемая презентация ID'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bddaba994d5e0907200902deb8c818cca4199c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="b5935-102">Презентация с именем ID в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5935-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5935-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b5935-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b5935-104">При использовании Lync Server 2010 телефонный номер вызываемого абонента (то есть номер телефона) можно перевести из формата E. 164 в местный формат набора номера, который требуется магистральным одноранговым узлом (то есть, связанным шлюзом, УАТС или магистральной магистралью SIP).</span><span class="sxs-lookup"><span data-stu-id="b5935-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="b5935-105">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="b5935-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b5935-106">Возможность связывания одного или нескольких правил преобразования с конфигурацией магистрали корпоративной голосовой связи предназначена для использования в качестве <EM>альтернативы</EM> настройке правил преобразования на одноранговом одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="b5935-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="b5935-107">Не связывайте правила преобразования с конфигурацией магистрали корпоративной голосовой связи, если вы настроили правила преобразования на одноранговом одноранговом узле, так как эти два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="b5935-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="b5935-108">Вы можете использовать один из следующих методов для создания или изменения правила преобразования:</span><span class="sxs-lookup"><span data-stu-id="b5935-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="b5935-109">Используйте средство **создания правила преобразования** , чтобы указать значения для начальных цифр, длины, цифр для удаления и цифр для добавления, а затем позвольте панели управления Lync Server создать соответствующий шаблон и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="b5935-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="b5935-110">Запишите регулярные выражения вручную, чтобы определить шаблон сопоставления и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="b5935-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5935-111">Сведения о том, как писать регулярные выражения, можно найти в <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="b5935-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b5935-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="b5935-112">In This Section</span></span>

  - [<span data-ttu-id="b5935-113">Создание или изменение правила преобразования с помощью средства "Построение правила преобразования" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5935-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="b5935-114">Создание или изменение правила трансляции вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5935-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5935-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b5935-115">See Also</span></span>


[<span data-ttu-id="b5935-116">Презентация идентификации звонящего в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5935-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

