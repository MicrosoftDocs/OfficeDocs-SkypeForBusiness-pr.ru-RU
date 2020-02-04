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
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

Помимо изменения глобального фильтра передачи файлов, вы можете настроить пользовательские фильтры передачи файлов для определенных сайтов в среде Lync Server 2013. Сведения о фильтрации передаваемых файлов приведены [в разделе Настройка фильтрации передачи файлов и URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Создание фильтра передачи файлов для определенного сайта

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **сообщение и сведения о присутствии** , а затем щелкните **Фильтр файлов**.

4.  На странице " **Фильтр файлов** " нажмите кнопку " **создать**".

5.  В диалоговом окне **выберите сайт** выберите сайт, для которого вы хотите создать фильтр передачи файлов, и нажмите кнопку **ОК**.

6.  В диалоговом окне **Новый фильтр файлов**установите флажок **включить фильтр файлов** .

7.  В раскрывающемся списке **Передача файлов** выберите команду **Блокировать все** или **блокировать определенные типы файлов**.

8.  Если вы щелкните **Блокировать все**, перейдите к шагу 10.

9.  Если вы **Выблокировали определенные типы файлов**, выполните указанные ниже действия.
    
    1.  Нажмите кнопку **выбрать** , чтобы изменить список расширений типов файлов, которые вы хотите заблокировать по умолчанию.
    
    2.  В диалоговом окне **Выбор типа файлов** выберите типы файлов, которые вы хотите заблокировать или разрешить, добавив или удалив их расширения из категорий в разделе **расширения типов файлов**.
    
    3.  Если вы не видите расширение для типа файла, который вы хотите заблокировать, введите его в текстовое поле в разделе **Добавление расширений типов файлов в список**и нажмите кнопку **Добавить**.
    
    4.  Нажмите кнопку **ОК**.

10. Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка фильтрации файлов и URL-адресов для обмена мгновенными сообщениями (IM) в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Создание фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Изменение фильтра передачи файлов по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Изменение фильтра URL-адреса по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

