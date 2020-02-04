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
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Настройка хранилища личных контактов на клиентских компьютерах для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

При интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 рекомендуется настроить хранилище персональных контактов на любом клиентском компьютере, работающем под управлением Microsoft Lync 2010. В частности, вы должны настроить Lync для использования Exchange в качестве личного хранилища контактов и, в то же время, убедиться, что пользователи не могут переопределять это решение. Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.

Обратите внимание, что это не требуется на компьютерах с Lync 2013.

Чтобы настроить данное значение на одном компьютере, выполните следующие действия:

1.  На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **Выполнить**.

2.  В диалоговом окне **Выполнить** введите regedit, а затем нажмите ВВОД.

3.  В редакторе реестра разверните узел **hKey\_локального\_компьютера**, разверните раздел **программы**, **а затем разверните**раздел **Microsoft**, а затем — **Communicator**.

4.  Щелкните элемент **Communicator** правой кнопкой мыши, наведите указатель на пункт **Создать** и выберите пункт **Параметр DWORD (32-разрядный)**.

5.  После создания параметра введите **PersonalContactStoreOverride** и нажмите клавишу ВВОД, чтобы переименовать параметр.

6.  Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.

Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики. Подробные сведения можно найти в документации по групповой политике [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).

</div>

<span> </span>

</div>

</div>

</div>

