---
title: Авторизация подключения к пограничному серверу Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 6181f3d42facaf49b84b7c07776dc8717e88b271
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499766"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Авторизация подключения к пограничному серверу Office Communications Server 2007 R2

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Для каждого сервера переднего плана Lync Server 2013 или сервера Standard Edition в пилотном пуле необходимо обновить список внутренних серверов, которым разрешено подключаться к пограничному серверу Office Communications Server 2007 R2. Без этих обновлений внешние аудио и видеоконференции для пользователей, присоединяющихся к конференц-связи с помощью унаследованного пограничного сервера, не будут работать.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Авторизация подключения к пограничному серверу Office Communications Server 2007 R2

1.  На пограничном сервере Office Communications Server 2007 R2 **в группе Администрирование** откройте оснастку " **Управление компьютером** ".

2.  В дереве консоли разверните узел **Службы и приложения**.

3.  Щелкните правой кнопкой мыши **Office Communications Server 2007 R2**и выберите пункт **свойства**.

4.  Откройте вкладку **Внутренние**.

5.  В разделе **Добавить сервер** щелкните **Добавить**.

6.  В диалоговом окне **Добавление сервера Office Communications Server** введите соответствующие сведения:
    
      - Укажите полное доменное имя (FQDN) каждого сервера переднего плана Lync Server 2013 или сервера Standard Edition и пула Lync Server 2013.
    
      - Укажите полное доменное имя для Lync Server 2013 Director, если вы настроили статический маршрут в пуле, указывающий компьютер следующего прыжка по полному доменному имени.

7.  После добавления записи для каждого сервера Lync Server 2013, сервера переднего плана, сервера Standard Edition, пула и директора, нажмите кнопку **Применить** , а затем нажмите кнопку **ОК** , чтобы закрыть страницу свойств.

</div>

</div>

<span> </span>

</div>

</div>

</div>

