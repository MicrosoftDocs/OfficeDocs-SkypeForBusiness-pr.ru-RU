---
title: 'Lync Server 2013: определение правил нормализации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 712e4cec9be89894b391ba940f054bc121e4acea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="68bd0-102">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bd0-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68bd0-103">_**Последнее изменение темы:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="68bd0-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="68bd0-104">В правилах нормализации Lync Server 2013 для преобразования набранных номеров в формат E. 164 используются регулярные выражения .NET Framework; другими словами, правила нормализации получают телефонный номер, набранный пользователем, и преобразовывают его в формат, используемый внешним приложением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68bd0-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="68bd0-105">Каждой абонентской группе должно быть назначено одно или несколько правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="68bd0-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="68bd0-106">Подробные сведения о правилах нормализации приведены [в статье Планирование и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) .</span><span class="sxs-lookup"><span data-stu-id="68bd0-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="68bd0-107">Сведения о том, как писать регулярные выражения, можно найти в [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="68bd0-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="68bd0-108">Для задания или изменения регулярных выражений можно использовать следующие способы.</span><span class="sxs-lookup"><span data-stu-id="68bd0-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="68bd0-109">Используйте средство **создания правил нормализации** , чтобы указать значения для начальных цифр, длину, цифр для удаления и цифр для добавления, а затем позвольте панели управления Lync Server создать соответствующий шаблон и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="68bd0-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="68bd0-110">Запишите регулярные выражения вручную, чтобы определить шаблон сопоставления и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="68bd0-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68bd0-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="68bd0-111">In This Section</span></span>

  - [<span data-ttu-id="68bd0-112">Создание или изменение правила нормализации с помощью построения правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bd0-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="68bd0-113">Создание или изменение правила нормализации вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bd0-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68bd0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="68bd0-114">See Also</span></span>


[<span data-ttu-id="68bd0-115">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bd0-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="68bd0-116">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68bd0-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

