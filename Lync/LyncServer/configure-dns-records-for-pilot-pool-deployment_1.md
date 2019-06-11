---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0425d8adf0e09f3a0d081b1708d7e67e3f53a24
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Настройка DNS-записей для развертывания пилотного пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Перед развертыванием пула проектов Lync Server 2013 Pilot необходимо обновить записи узла DNS для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или домен, как минимум, с учетной записью члена группы администраторов домена или пользователя, который является членом группы Днсадминс.

**Настройка записей узла DNS**

1.  На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.

2.  В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.

3.  Выберите команду **создать узел (A или AAAA)**.

4.  Щелкните **Name (имя**), введите имя узла для пула (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).

5.  Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.

6.  Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.

7.  Когда все будет готово, нажмите кнопку **Готово**.

</div>

<span> </span>

</div>

</div>

</div>

