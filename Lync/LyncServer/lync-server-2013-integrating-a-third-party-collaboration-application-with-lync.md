---
title: Интеграция стороннего приложения для совместной работы с Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b95f79202cbf96568b98dcb802e97bf4ca2d32
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Интеграция стороннего приложения для совместной работы с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Вы можете интегрировать Lync 2013 с любым сторонним приложением для совместной работы, добавив сведения о приложении в реестр. Вы можете использовать Lync 2013 для начала сеансов конференций данных, размещенных на внутреннем сервере, в Интернете или в обоих случаях. Сеанс совместной работы или конференц-связи можно запустить из списка контактов или из существующего сеанса обмена мгновенными сообщениями, голосовых и видеофайлов. Lync 2013 действует только в качестве транспортного средства для запуска приложения. Любые существующие беседы Lync 2013 остаются активными после начала сеанса совместной работы через Интернет.

В следующих разделах описано, как интегрировать Lync 2013 с приложениями для совместной работы на основе Интернета и сервера.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Интеграция приложения для совместной работы через Интернет с помощью Lync 2013

Как правило, для интеграции стороннего приложения для совместной работы используются следующие этапы:

1.  Сведения о приложении добавляются в реестр.

2.  Организатор входит в Lync 2013 и выбирает контакты для совместного использования данных и совместной работы. Возможно также, что Организатор уже находится в беседе и решает добавить Конференц-связь с данными.

3.  Lync 2013 считывает реестр, запускает приложение для совместной работы, а затем отправляет настраиваемое сообщение SIP (Аппинвите) выбранным участникам.

4.  Участники приняли приглашение, и приложение для совместной работы запущено на компьютере каждого пользователя. Lync 2013 использует реестр для определения приложения для совместной работы, а затем запускает приложение, используя параметры, включенные в сообщение Аппинвите.

В приведенной ниже таблице описаны записи реестра, необходимые для интеграции приложения для совместной работы в Интернете с Lync 2013. Эти записи размещаются в реестре в следующем расположении:

  - Программное\_обеспечение\\\\для локального\\компьютера\\hKey\\\_Microsoft\\Office\\15,0\\Lync сессионманажер параметры приложений

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Записи реестра для приложения для совместной работы через Интернет

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя</p></td>
<td><p>REG_SZ</p></td>
<td><p>Меню "имя приложения" для Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>смалликон</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь к 16-пиксельному значку x 16 пикселей, BMP или PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Путь</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь участника для запуска приложения для совместной работы в Интернете.</p></td>
</tr>
<tr class="even">
<td><p>оригинаторпас</p></td>
<td><p>REG_SZ</p></td>
<td><p>Путь организатора для веб-приложения совместной работы. Этот путь может содержать один или несколько настраиваемых параметров, определенных в подразделе "Параметры". Например<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>сессионтипе</p></td>
<td><p>@</p></td>
<td><p>0 = локальный сеанс. Приложение будет запущено на локальном компьютере.</p>
<p>1 = два сеанса (по умолчанию). Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю. Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</p>
<p>2 = многокомпонентный сеанс. Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, запрашивая их, чтобы запустить указанное приложение на своем компьютере.</p></td>
</tr>
<tr class="even">
<td><p>ексенсиблемену</p></td>
<td><p>REG_SZ</p></td>
<td><p>Список меню, в котором будет отображаться эта команда, отделенных точкой с запятой. Возможные значения</p>
<ul>
<li><p>маинвиндовактионс</p></li>
<li><p>маинвиндовригхткликк</p></li>
<li><p>конверсатионвиндовактионс</p></li>
<li><p>конверсатионвиндовбуттон</p></li>
<li><p>конверсатионвиндовригхткликк</p></li>
</ul>
<p>Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</p></td>
</tr>
</tbody>
</table>


В приведенной ниже таблице описаны элементы реестра для параметров. Эти записи будут находиться на странице\_hKey\_текущего\\пользователя\\,\\сессионманажер\\\\параметры\\приложений\\\\Microsoft Office 15,0 Lync.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Записи реестра для приложения для совместной работы через Интернет

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Параметр1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Используется в размеченом формате<code>%Parm1%</code>() для добавления значений, связанных с пользователем, в раздел реестра оригинаторпас.</p></td>
</tr>
<tr class="even">
<td><p>Параметр2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Просмотрите раздел Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Просмотрите раздел Param1.</p></td>
</tr>
</tbody>
</table>


В следующем примере параметры реестра интегрируют клиент Адатум для совместной работы с помощью Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Интеграция серверного приложения для совместной работы с помощью Lync 2013

Параметры, необходимые для запуска приложения для совместной работы на основе сервера в Lync 2013, аналогичны тем, которые описаны в предыдущем разделе, интеграция приложения для совместной работы в Интернете с Lync 2013. Однако Оригинаторпас не требуется, а некоторые значения изменяются. Записи в реестре размещаются в следующем расположении:

  - Программное\_обеспечение\\\\для локального\\компьютера\\hKey\\\_Microsoft\\Office\\15,0\\Lync сессионманажер параметры приложений

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Записи реестра для приложения для совместной работы на базе сервера

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Тип</th>
<th>Данные</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя</p></td>
<td><p>REG_SZ</p></td>
<td><p>Имя приложения в том виде, в каком оно отображается в меню.</p></td>
</tr>
<tr class="even">
<td><p>аппликатионтипе</p></td>
<td><p>@</p></td>
<td><p>Значение = 1. Задает тип приложения "протокол". Другие возможные значения в этом случае не применяются. Если он отсутствует, Аппликатионтипе имеет значение 0 (исполняемый объект).</p></td>
</tr>
<tr class="odd">
<td><p>Путь</p></td>
<td><p>REG_SZ</p></td>
<td><p>Протокол, используемый для запуска приложения для совместной работы. Для Live Meeting 2007 для параметра путь задано значение Path <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>сессионтипе</p></td>
<td><p>@</p></td>
<td><p>0 = локальный сеанс. Приложение будет запущено на локальном компьютере.</p>
<p>1 = два сеанса (по умолчанию). Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю. Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</p>
<p>2 = многокомпонентный сеанс. Lync 2013 запускает приложение локально, а затем отправляет пользователям системные уведомления о том, чтобы запустить указанное приложение на компьютере.</p></td>
</tr>
<tr class="odd">
<td><p>мкутипе</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA (данные) — тип сервера.</p></td>
</tr>
<tr class="even">
<td><p>екстенсиблемену</p></td>
<td><p>REG_SZ</p></td>
<td><p>Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой. Возможные значения</p>
<ul>
<li><p>маинвиндовактионс</p></li>
<li><p>маинвиндовригхткликк</p></li>
<li><p>конверсатионвиндовактионс</p></li>
<li><p>конверсатионвиндовбуттон</p></li>
<li><p>конверсатионвиндовригхткликк</p></li>
</ul>
<p>Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</p></td>
</tr>
</tbody>
</table>


В следующем примере показано, как добавить команды для запуска клиента совместной работы Адатум в Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

