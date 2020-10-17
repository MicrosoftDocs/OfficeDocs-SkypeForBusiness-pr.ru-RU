---
title: Удаление авторизованной записи узла
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bad444821c352991c1befd184d91920dcd5d147
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500106"
---
# <a name="remove-an-authorized-host-entry"></a>Удаление авторизованной записи узла

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

В этом разделе описывается, как удалить устаревшую авторизованную запись узла (которая называется *записью доверенного приложения* в Lync Server 2013). При переносе удаленного управления звонками в развертывание Lync Server 2013 необходимо удалить существующие авторизованные записи узла для всех шлюзов SIP/CSTA в развертывании Office Communications Server 2007 R2. Чтобы удалить существующие авторизованные записи узла, необходимо использовать средства администрирования, входящие в состав Office Communications Server 2007 R2.

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a>Удаление авторизованной записи узла в развертывании Office Communications Server 2007 R2

1.  Откройте консоль администрирования Office Communications Server 2007 R2.

2.  Разверните дерево и щелкните правой кнопкой мыши пул, в котором был создан авторизованный узел.

3.  Щелкните  **Свойства**, затем **Свойства интерфейсного сервера**.

4.  Перейдите на вкладку **Авторизация узла**.

5.  Выберите сервер, затем нажмите кнопку **Удалить**.

6.  В окне **Свойства** нажмите кнопку **ОК**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

