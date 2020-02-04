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
ms.openlocfilehash: e8a0d9ade3fd750f5dc89526969bad7e39ad0f35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Изменение фильтра передачи файлов по умолчанию в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Lync Server 2013 предоставляет глобальный фильтр передачи файлов, который блокирует определенные типы файлов во время выполнения следующих действий, связанных с файлами, в среде Lync Server 2013.

  - Запросы на передачу файлов в текстовых беседах (мгновенных сообщений)

  - Загрузка и загрузка файлов с помощью функции выдач в клиенте Office Live Meeting 2007

  - Воспроизведение мультимедиа во время конференций

В зависимости от типа файлов, которые вы хотите заблокировать или разрешить, вы можете изменить глобальный фильтр с помощью панели управления Lync Server. Сведения о фильтрации передаваемых файлов приведены [в разделе Настройка фильтрации передачи файлов и URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Изменение фильтра передачи файлов по умолчанию

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **сообщение и сведения о присутствии** , а затем щелкните **Фильтр файлов**.

4.  На странице " **Фильтр файлов** " дважды щелкните **глобальный** фильтр.

5.  В диалоговом окне **Изменение фильтра файлов**установите флажок **включить фильтр файлов** .

6.  В раскрывающемся списке **Пересылка файлов** выберите команду **Блокировать все** или **блокировать определенные типы файлов**.

7.  Если вы щелкните **Блокировать все**, перейдите к шагу 9.

8.  Если вы **Выблокировали определенные типы файлов**, выполните указанные ниже действия.
    
    1.  Нажмите кнопку **выбрать** , чтобы изменить список расширений типов файлов, которые вы хотите заблокировать по умолчанию.
    
    2.  В списке **выберите тип файла**выберите типы файлов, которые вы хотите заблокировать или разрешить, добавив или удалив их расширения из категорий в разделе **расширения типов файлов**.
    
    3.  Если вы не видите расширение для типа файла, который вы хотите заблокировать, введите его в текстовое поле в разделе **Добавление расширений типов файлов в список**и нажмите кнопку **Добавить**.
    
    4.  Нажмите кнопку **ОК**.

9.  Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка фильтрации файлов и URL-адресов для обмена мгновенными сообщениями (IM) в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Создание фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Изменение фильтра URL-адреса по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

