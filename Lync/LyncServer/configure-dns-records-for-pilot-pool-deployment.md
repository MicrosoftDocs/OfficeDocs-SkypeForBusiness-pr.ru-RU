---
title: Настройка DNS-записей для развертывания пилотного пула
description: Настройка DNS-записей для развертывания пилотного пула.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e41e163432ba910f6d083cc508e8ad8c9f2006d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548495"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Настройка DNS-записей для развертывания пилотного пула

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

Перед развертыванием пилотного пула Lync Server 2013 необходимо обновить записи узла DNS для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.

**Настройка записей A узла DNS**

1.  На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.

2.  В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.

3.  Выберите команду **Создать узел (A или AAAA)**.

4.  Нажмите кнопку **имя**, введите имя узла для пула Lync Server 2013 (имя домена предполагается в зоне, в которой определена запись, и его не нужно вводить как часть записи A).

5.  Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.

6.  Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.

7.  По завершении нажмите кнопку **Готово**.

</div>

<span> </span>

</div>

</div>

</div>

