---
title: Авторизовать подключение к Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Авторизовать подключение к Office Communications Server 2007 R2 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Для каждого сервера переднего плана и сервера Standard Edition для Lync Server 2013 в пилотном пуле необходимо обновить список внутренних серверов, которым разрешено подключаться к серверу Office Communications Server 2007 R2 Edge. Без этих обновлений не работают внешние аудио-и визуальные конференции для пользователей, присоединяющихся с помощью устаревшего пограничного сервера.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Чтобы авторизовать подключение к Office Communications Server 2007 R2 Edge Server

1.  На пограничном сервере Office Communications Server 2007 R2 в группе **средства администрирования** откройте оснастку **Управление компьютером** .

2.  В дереве консоли разверните узел **службы и приложения**.

3.  Щелкните правой кнопкой мыши **Office Communications Server 2007 R2**и выберите пункт **свойства**.

4.  Откройте вкладку **внутренний** .

5.  В разделе **Добавить сервер**нажмите кнопку **Добавить**.

6.  В диалоговом окне **Добавление сервера Office Communications Server** введите нужные сведения.
    
      - Укажите полное доменное имя (FQDN) каждого сервера Lync Server 2013, а также сервера Standard Edition и пула Lync Server 2013.
    
      - Укажите полное доменное имя режиссера Lync Server 2013, если вы настроили статический маршрут для пула, указывающий на следующий компьютер по полному доменному имени.

7.  После добавления записи для каждого сервера Lync Server 2013, сервера переднего плана, сервера Standard Edition, пула и режиссера нажмите кнопку **Применить** , а затем нажмите кнопку **ОК** , чтобы закрыть страницу свойств.

</div>

</div>

<span> </span>

</div>

</div>

</div>

