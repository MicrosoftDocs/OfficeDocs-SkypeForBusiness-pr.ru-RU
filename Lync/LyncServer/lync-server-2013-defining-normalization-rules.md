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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Определение правил нормализации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-22_

В правилах нормализации Lync Server 2013 используются регулярные выражения .NET Framework для перевода телефонных номеров с набором в формат E. 164. другими словами, правила нормализации принимают номер телефона, набранный пользователем, и преобразуют его в формат, используемый приложением Lync Server для внутренних целей. Каждой абонентской группе должно быть назначено хотя бы одно правило нормализации.

Дополнительные сведения о правилах нормализации приведены [в разделе планы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) в документации по планированию.

Сведения о том, как создавать регулярные выражения, приведены в [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".

Чтобы определить или изменить правило нормализации, можно использовать один из указанных ниже способов.

  - С помощью средства **создания правил нормализации** укажите значения для начальных цифр, длину, цифр для удаления и цифр, которые нужно добавить, а затем откройте на панели управления Lync Server соответствующие шаблон сопоставления и правило перевода.

  - Напишите регулярные выражения вручную, чтобы задать шаблон сопоставления и правило трансляции.

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание и изменение правила нормализации с помощью сборки правила нормализации в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Создание или изменение правила нормализации вручную в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

