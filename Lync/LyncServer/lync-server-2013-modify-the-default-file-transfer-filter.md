---
title: 'Lync Server 2013: изменение фильтра передачи файлов по умолчанию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3e0da5402ea93ce33e844a2f8b32d545d4811a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Изменение фильтра передачи файлов по умолчанию в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Lync Server 2013 предоставляет глобальный фильтр передачи файлов, который блокирует определенные типы файлов во время выполнения следующих действий с файлами в развертывании Lync Server 2013:

  - Запросы на передачу файлов во время бесед с обменом мгновенными сообщениями

  - Отправки и загрузки файлов во время использования функции выдачи в клиенте Office Live Meeting 2007

  - Воспроизведение мультимедиа во время конференций

В зависимости от типов файлов, которые необходимо заблокировать или разрешить, можно использовать панель управления Lync Server для изменения глобального фильтра. Подробные сведения о фильтрации передачи файлов приведены [в разделе Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Изменение фильтра передачи файлов по умолчанию

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр файлов**.

4.  На странице **File Filter** (Фильтр файлов) дважды щелкните фильтр **Global** (Глобальный).

5.  В окне **Edit File Filter** (Изменение фильтра файлов) установите флажок **Enable file filter** (Включить фильтр файлов).

6.  В раскрывающемся списке **Передача файлов** выберите пункт **Блокировать все** или **Block specific file types** (Блокировать определенные типы файлов).

7.  При выборе варианта **Блокировать все** перейдите к действию 9.

8.  При выборе варианта **Блокировать определенные типы файлов** выполните следующие действия.
    
    1.  Щелкните **Выбрать**, чтобы изменить список блокируемых расширений файлов по умолчанию.
    
    2.  В окне **Select File Type** (Выбор типа файла) выберите типы файлов, которые требуется блокировать или разрешить, добавив или удалив их расширения из категорий в разделе **File type extensions** (Расширения типов файлов).
    
    3.  Если расширения типов файлов, которые необходимо заблокировать, не отображаются, введите расширение в текстовое поле **Add file type extensions to the list** (Добавить расширения типов файлов в список), а затем нажмите кнопку **Добавить**.
    
    4.  Нажмите кнопку **ОК**.

9.  Щелкните **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Изменение фильтра URL-адресов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

