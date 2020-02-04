---
title: 'Lync Server 2013: Пометка приложения на языке обработки Microsoft SIP (МСПЛ) как критическое или некритическое'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Пометка приложения на языке обработки Microsoft SIP (МСПЛ) как критическое или некритическое в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Серверные приложения Microsoft SIP Language (МСПЛ) — это приложения только сценария, использующие язык сценариев МСПЛ вместо Microsoft Lync 2010 API. Некоторые серверные приложения МСПЛ задаются как критические. Если сценарий является критическим, во время запуска системы необходимо запустить сценарий, чтобы Lync Server 2013 начал работу. Если при запуске Lync Server происходит сбой сценария, сервер не завершает работу, но перестает передавать трафик сценариям и записывает ошибки в журнал событий.

С помощью панели управления Lync Server можно помечать серверные приложения на языке обработки Microsoft SIP (МСПЛ) как критические или не помечать их.

Этот параметр поддерживают не все сценарии. Например, сценарий Дефаултраутинг помечается как критический, и этот параметр невозможно изменить для Дефаултраутинг.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Пометка или снятие пометки приложения сервера МСПЛ как критического

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **топология** и щелкните **серверное приложение**.

4.  На странице **серверное приложение** щелкните заголовок столбца, чтобы отсортировать приложения, если необходимо, а затем выберите серверное приложение, которое вы хотите изменить.

5.  Нажмите кнопку **действие**.

6.  Выберите команду **помечать как критические** или **снимите флажок как критический** (то есть, если сценарий поддерживает этот параметр).

</div>

<div>

## <a name="see-also"></a>См. также


[Включение и отключение серверного приложения Microsoft SIP Languageing (МСПЛ) в Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Управление топологией Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

