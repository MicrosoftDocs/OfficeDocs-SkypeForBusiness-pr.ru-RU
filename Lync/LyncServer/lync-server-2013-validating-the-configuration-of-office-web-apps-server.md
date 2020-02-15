---
title: 'Lync Server 2013: Проверка конфигурации сервера Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c774411fd825dd01595ef1e51ffa9c65c6eb8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Проверка конфигурации сервера Office Web Apps в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-22_

После добавления сервера Office Web Apps в топологию и после публикации этой топологии в журнале событий Lync Server должны появиться два новых события журнала событий. Сначала необходимо добавить событие MCU для данных LS (Event ID 41034); Это событие сообщит о том, что сервер Office Web Apps обнаружен:

**Сервер веб-конференций сервер Office Web Apps обнаружен, содержимое PowerPoint включено.**

Кроме того, должно отображаться другое событие LS Data MCU (идентификатор события — 41032), которое отправляют URL-адреса сервера Office Web Apps. Это событие может иметь, например, следующий вид:

**Сервер веб-конференций сервер Office Web Apps обнаружил успешность.**

**Внутренняя страница выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Страница внутреннего участника сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Внешняя страница докладчика сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Страница внутреннего участника сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Если событие LS Data MCU отображается с идентификатором события 41033, это означает, что произошел сбой обнаружения сервера Office Web Apps Server. В этом случае Microsoft Lync Server 2013 будет пытаться попытаться столько раз, сколько необходимо для обнаружения нового настроенного сервера Office Web Apps. Если происходит многократный сбой процесса обнаружения, следует удалить сервер Office Web Apps из документа топологии, опубликовать обновленную топологию, а затем снова попробовать добавить сервер Office Web Apps в топологию после устранения неполадок, связанных с подключением.

Если сервер Office Web Apps настроен правильно и распознается процессом обнаружения, можно проверить, что сервер Office Web Apps работает надлежащим образом, выполнив совместное использование презентации PowerPoint между двумя клиентами Microsoft Lync 2013. Если пользователь А может загружать и отображать презентацию PowerPoint, а пользователь Б затем может присоединяться к собранию и просматривать презентацию, сервер Office Web Apps функционирует правильно.

Даже если кажется, что сервер Office Web Apps настроен правильно, при попытке совместного использования презентации PowerPoint существует вероятность возникновения сообщения об ошибке "Некоторые функции общего доступа недоступны из-за проблем с подключением к серверу". В случае отображения этого сообщения об ошибке следует перезапустить серверы переднего плана, сопоставленные с новым сервером Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

