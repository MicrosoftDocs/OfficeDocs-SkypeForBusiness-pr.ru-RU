---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f22f26ae48835dee6028e5b41b79dd116d610a25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529816"
---
# <a name="reset-call-admission-control"></a>Сброс контроля допуска звонков

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-11_

Если в пуле переднего плана Lync Server 2010 размещается контроль допуска звонков (CAC), необходимо переместить размещение CAC в пул Lync Server 2013, прежде чем можно будет удалить интерфейсный пул Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Чтобы сбросить контроль допуска звонков

1.  Откройте построитель топологий.

2.  Щелкните правой кнопкой мыши узел сайта, затем выберите **Изменить свойства**.

3.  Убедитесь, что в разделе **Параметры контроля допуска звонков** выбран параметр **Включить контроль допуска звонков**.

4.  В разделе **пул переднего плана для запуска контроля допуска звонков (CAC)** выберите пул Lync Server 2013, который будет обслуживать CAC, а затем нажмите кнопку **ОК**.

5.  Опубликуйте топологию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

