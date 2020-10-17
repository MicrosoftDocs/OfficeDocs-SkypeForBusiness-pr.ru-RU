---
title: Создание нового фильтра URL-адресов для обработки гиперссылок в текстовых беседах
description: Создание нового фильтра URL-адресов для обработки гиперссылок в беседах с использованием мгновенных сообщений.
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
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554665"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

В дополнение к изменению глобального фильтра URL-адресов можно настроить фильтры настраиваемых URL-адресов для отдельных сайтов в развертывании Lync Server 2013. Сведения об фильтрации URL-адресов приведены [в статье Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Создание нового фильтра URL-адресов

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр URL-адресов**.

4.  На странице **Фильтр URL-адресов** нажмите кнопку **Создать**.

5.  В диалоговом окне **Выбор сайта** щелкните сайт, для которого требуется создать фильтр URL-адресов, а затем нажмите кнопку **ОК**.

6.  В диалоговом окне **Создание фильтра URL-адресов** установите флажок **Включить фильтр URL-адресов**, чтобы включить фильтрацию URL-адресов для сайта.

7.  Чтобы заблокировать все активные URL-адреса, которые содержат файл с расширением, заданном в разделе **Расширения типов файлов для блокировки** в окне **Редактирование фильтра файлов**, установите флажок **Блокировать URL-адреса с расширением файлов**.

8.  В раскрывающемся списке **Префикс гиперссылки** выберите вариант, который соответствует тому, как требуется обрабатывать URL-адреса в беседах с обменом мгновенными сообщениями.
    
    Флажок **Разрешить сообщение** позволяет отправку пользователю предупреждающего сообщения, когда отправляются разрешенные для отправки гиперссылки.

9.  Щелкните **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Изменение фильтра передачи файлов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Изменение фильтра URL-адресов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

