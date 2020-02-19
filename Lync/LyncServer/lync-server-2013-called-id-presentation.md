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
ms.openlocfilehash: 8b4ad6f728f01f0cf9ef1aac6ed57ad22c7ff345
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Презентация с именем ID в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

При использовании Lync Server 2010 телефонный номер вызываемого абонента (то есть номер телефона) можно перевести из формата E. 164 в местный формат набора номера, который требуется магистральным одноранговым узлом (то есть, связанным шлюзом, УАТС или магистральной магистралью SIP). Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.

<div>


> [!IMPORTANT]  
> Возможность связывания одного или нескольких правил преобразования с конфигурацией магистрали корпоративной голосовой связи предназначена для использования в качестве <EM>альтернативы</EM> настройке правил преобразования на одноранговом одноранговом узле. Не связывайте правила преобразования с конфигурацией магистрали корпоративной голосовой связи, если вы настроили правила преобразования на одноранговом одноранговом узле, так как эти два правила могут конфликтовать.



</div>

Вы можете использовать один из следующих методов для создания или изменения правила преобразования:

  - Используйте средство **создания правила преобразования** , чтобы указать значения для начальных цифр, длины, цифр для удаления и цифр для добавления, а затем позвольте панели управления Lync Server создать соответствующий шаблон и правило преобразования.

  - Запишите регулярные выражения вручную, чтобы определить шаблон сопоставления и правило преобразования.

<div>


> [!NOTE]  
> Сведения о том, как писать регулярные выражения, можно найти в <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>разделе "регулярные выражения .NET Framework".



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание или изменение правила преобразования с помощью средства "Построение правила преобразования" в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Создание или изменение правила трансляции вручную в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Презентация идентификации звонящего в Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

