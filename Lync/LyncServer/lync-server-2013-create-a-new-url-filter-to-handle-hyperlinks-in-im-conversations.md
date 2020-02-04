---
title: Создание фильтра URL-адресов для обработки гиперссылок в текстовых беседах
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Создание фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-26_

Помимо изменения глобального фильтра URL-адреса вы можете настроить пользовательские фильтры URL-адресов для отдельных сайтов в среде Lync Server 2013. Подробнее об фильтрации URL-адресов можно узнать [в разделе Настройка параметров передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Создание фильтра для нового URL-адреса

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **сообщение и сведения о присутствии**, а затем щелкните **Фильтр URL-адресов**.

4.  На странице **Фильтр URL-адресов** нажмите кнопку **создать**.

5.  В списке **выберите сайт**выберите сайт, для которого вы хотите создать фильтр URL-адресов, и нажмите кнопку **ОК**.

6.  В диалоговом окне **Новый фильтр URL-адресов** установите флажок **включить фильтр URL** -адресов, чтобы включить фильтрацию URL-адресов для сайта.

7.  Чтобы заблокировать любой активный URL-адрес, содержащий файл с расширением, указанным в разделе **расширения типа файла, который будет заблокирован** в диалоговом окне **Изменение фильтра файлов**, установите флажок **блокировать URL-адреса с использованием расширения файла** .

8.  В раскрывающемся списке " **префикс гиперссылки** " выберите параметр, соответствующий тому, как вы хотите обрабатывать URL-адреса в мгновенных сообщениях.
    
    Окно **Разрешить сообщение** позволяет отправлять пользователю предупреждение при отправке гиперссылок, которые разрешено отправлять.

9.  Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка фильтрации файлов и URL-адресов для обмена мгновенными сообщениями (IM) в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Изменение фильтра передачи файлов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Изменение фильтра URL-адреса по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

