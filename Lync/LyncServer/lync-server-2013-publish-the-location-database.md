---
title: 'Lync Server 2013: публикация базы данных расположений'
description: 'Lync Server 2013: публикация базы данных расположений.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26892429c7bf5fd9cbfebd0d7ac62482767a541e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565445"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a>Публикация базы данных местоположений из Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.

Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующего командлета:

  - **Publish — CsLisConfiguration**

Если вы используете шлюзы Emergency Location Identification Number (ELIN), необходимо также загрузить номера ELIN в базу данных Automatic Location Identification (ALI) сети PSTN. Оператор PSTN может потребовать использования определенного формата для записей ELIN. Обратитесь к оператору PSTN для получения более подробных сведений. Вы можете экспортировать записи из базы данных службы сведений о расположении и отформатировать их по мере необходимости.

<div>

## <a name="to-publish-the-location-database"></a>Публикация базы данных местоположений

  - Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

  - Чтобы опубликовать базу данных местоположений, выполните следующий командлет.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

