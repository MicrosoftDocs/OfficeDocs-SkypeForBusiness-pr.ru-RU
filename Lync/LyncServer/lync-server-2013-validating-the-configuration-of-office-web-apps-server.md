---
title: 'Lync Server 2013: Проверка конфигурации сервера Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Проверка конфигурации сервера Office Web Apps в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-22_

После добавления сервера Office Web Apps в топологию и после публикации этой топологии вы должны увидеть два новых события журнала событий в журнале событий Lync Server. First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:

**Сервер веб-конференций обнаружил сервер Office Web Apps Server, содержимое PowerPoint включено.**

Кроме того, должно отображаться другое событие LS Data MCU (идентификатор события — 41032), которое отправляют URL-адреса сервера Office Web Apps. Это событие может иметь, например, следующий вид:

**Обнаружение Office Web Apps Server (WAC) сервера веб-конференций выполнено успешно.**

**Страница внутренней выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Страница внутреннего участника на сервере Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Страница внешнего выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Страница внутреннего участника на сервере Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Если вы видите событие LS Data MCU с кодом события 41033, это означает, что не удалось обнаружить сервер Office Web Apps. В этом случае Microsoft Lync Server 2013 попытается выполнить столько раз, сколько нужно, чтобы найти только что настроенный сервер Office Web Apps. Если процесс обнаружения завершается сбоем, необходимо удалить сервер Office Web Apps из документа топологии, опубликовать обновленную топологию и попробовать добавить сервер Office Web Apps обратно в топологию после устранения проблем с подключением.

Если сервер Office Web Apps правильно настроен и обнаружен в процессе обнаружения, вы можете проверить правильность работы сервера Office Web Apps с помощью демонстрации презентации PowerPoint между парой клиентов Microsoft Lync 2013. Если пользователь A может загрузить и отобразить презентацию PowerPoint, а затем пользователь B может присоединиться к собранию и просмотреть эту презентацию, будет ли работать сервер Office Web Apps.

Даже если сервер Office Web Apps настроен правильно, может быть получено сообщение об ошибке "некоторые функции общего доступа недоступны из-за проблем с подключением к серверу" при попытке предоставить общий доступ к презентации PowerPoint. Если появится сообщение об ошибке, необходимо перезапустить сервер переднего плана (или серверы), связанный с новым сервером Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

