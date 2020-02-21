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

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Определение правил нормализации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-22_

В правилах нормализации Lync Server 2013 для преобразования набранных номеров в формат E. 164 используются регулярные выражения .NET Framework; другими словами, правила нормализации получают телефонный номер, набранный пользователем, и преобразовывают его в формат, используемый внешним приложением Lync Server. Каждой абонентской группе должно быть назначено одно или несколько правил нормализации.

Подробные сведения о правилах нормализации приведены [в статье Планирование и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) .

Сведения о том, как писать регулярные выражения, можно найти в [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".

Для задания или изменения регулярных выражений можно использовать следующие способы.

  - Используйте средство **создания правил нормализации** , чтобы указать значения для начальных цифр, длину, цифр для удаления и цифр для добавления, а затем позвольте панели управления Lync Server создать соответствующий шаблон и правило преобразования.

  - Запишите регулярные выражения вручную, чтобы определить шаблон сопоставления и правило преобразования.

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание или изменение правила нормализации с помощью построения правила нормализации в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

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

