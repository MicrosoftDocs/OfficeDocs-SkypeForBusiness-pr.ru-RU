---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Сброс контроля допуска звонков

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-11_

Если в пуле внешних интерфейсов Lync Server 2010 (CAC) размещен элемент управления допускной передачей, необходимо переместить сервер CAC на пул Lync Server 2013, прежде чем можно будет удалить пул внешних интерфейсов Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Чтобы сбросить параметры CAC

1.  Открытие построителя топологии.

2.  Щелкните правой кнопкой мыши узел сайта и выберите команду **изменить свойства**.

3.  Убедитесь, что в разделе **параметр управления**допуском звонков установлен флажок **включить управление допуском звонков** .

4.  В разделе **пул переднего плана, чтобы запустить управление допуском звонков (CAC)**, выберите пул Lync Server 2013, который будет размещаться в CAC, и нажмите кнопку **ОК**.

5.  Опубликуйте топологию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

