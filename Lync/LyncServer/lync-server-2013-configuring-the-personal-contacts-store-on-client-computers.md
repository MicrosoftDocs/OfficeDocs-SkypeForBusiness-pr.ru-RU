---
title: 'Lync Server 2013: Настройка хранилища личных контактов на клиентских компьютерах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6020182c0083ecadcb65c07fa71be213f9458f0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532349"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Настройка хранилища личных контактов на клиентских компьютерах для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

При интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 рекомендуется настроить хранилище личных контактов на всех клиентских компьютерах, работающих под управлением Microsoft Lync 2010. В частности, необходимо настроить Lync для использования Exchange в качестве личного хранилища контактов и, в то же время, убедиться, что пользователи не могут переопределить это решение. Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.

Обратите внимание, что это не обязательно на компьютерах с Lync 2013.

Чтобы настроить данное значение на одном компьютере, выполните следующие действия:

1.  На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **выполнить**.

2.  В диалоговом окне **Выполнить** введите regedit, затем нажмите ВВОД.

3.  В редакторе реестра разверните узел **" \_ локальный \_ компьютер**", разверните узел **программное обеспечение**, **политики**, разверните узел **Microsoft**, а затем — **Communicator**.

4.  Щелкните правой кнопкой мыши **Communicator**, наведите указатель мыши на **создать**и выберите **значение DWORD (32-бит)**.

5.  После создания нового значения введите **PersonalContactStoreOverride** и нажмите КЛАВИШу ввод, чтобы переименовать значение.

6.  Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.

Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики. Дополнительные сведения см. в документации по групповой политике [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .

</div>

<span> </span>

</div>

</div>

</div>

