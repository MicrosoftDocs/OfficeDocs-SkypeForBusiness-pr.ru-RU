---
title: 'Lync Server 2013: создание нового фильтра передачи файлов для определенного сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a374cb234567c5aeb44ce6071f6e67559c5159ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

В дополнение к изменению глобального фильтра передачи файлов можно настроить пользовательские фильтры передачи файлов для определенных сайтов в развертывании Lync Server 2013. Подробные сведения о фильтрации передачи файлов приведены [в разделе Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Создание фильтра передачи файлов для определенного сайта

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр файлов**.

4.  На странице **Фильтр файлов** нажмите кнопку **Создать**.

5.  В диалоговом окне **Выбор сайта** щелкните сайт, для которого требуется создать фильтр передачи файлов, а затем нажмите кнопку **ОК**.

6.  В окне **Создание фильтра файлов** установите флажок **Включить фильтр файлов**.

7.  В раскрывающемся списке **Передача файлов** выберите пункт **Блокировать все** или **Блокировать определенные типы файлов**.

8.  При выборе варианта **Block All** (Блокировать все) перейдите к действию 10.

9.  При выборе варианта **Блокировать определенные типы файлов** выполните следующие действия.
    
    1.  Щелкните **Выбрать**, чтобы изменить список блокируемых расширений файлов по умолчанию.
    
    2.  В диалоговом окне **Выбор типа файла** выберите типы файлов, которые требуется блокировать или разрешить, добавив или удалив их расширения из категорий в разделе **Расширения типов файлов**.
    
    3.  Если расширения типов файлов, которые необходимо заблокировать, не отображаются, введите расширение в текстовое поле **Добавить расширения типов файлов в список**, а затем нажмите кнопку **Добавить**.
    
    4.  Нажмите кнопку **ОК**.

10. Щелкните **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Изменение фильтра передачи файлов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Изменение фильтра URL-адресов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

