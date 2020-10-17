---
title: 'Lync Server 2013: Импорт пакетов управления Lync Server 2013'
description: 'Lync Server 2013: Импорт пакетов управления Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9615e559baf2f1c8b99015f1e407230559ff770
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547785"
---
# <a name="importing-the-lync-server-2013-management-packs"></a>Импорт пакетов управления Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Вы можете расширить возможности System Center Operations Manager, устанавливая пакеты управления — программное обеспечение, которое определяет, какие элементы будут отслеживаться системой System Center Operations Manager и как эти элементы должны контролироваться и как они должны быть включены в отчет. Lync Server 2013 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:

  - Пакет управления компонентом и пользовательским пакетом (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные в журналах событий, зарегистрированные счетчиками производительности или зарегистрированные в журналах сведений о вызовах (CDR) или в базах данных качества взаимодействия (QoE). Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или обмена сообщениями в службе коротких сообщений (SMS). SMS — это технология передачи текстовых сообщений с одного мобильного устройства на другое.
    
    <div>
    

    > [!NOTE]  
    > Подробнее о настройке уведомлений Operations Manager можно узнать в статье Настройка уведомлений в библиотеке TechNet по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> .

    
    </div>

  - Пакет управления Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) служит для профилактического тестирования ключевых компонентов Lync Server, таких как вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в телефонной сети общего пользования (PSTN). Эти тесты выполняются с помощью командлетов искусственной транзакции Lync Server. Например, с помощью командлета **Test-CsIM** можно симулировать обмен мгновенными сообщениями между парой тестовых пользователей. При возникновении ошибки в этой симулированной беседе создается предупреждение.

Пакеты управления нужно импортировать. Если вы не импортируете пакеты управления, вы не можете использовать Operations Manager для мониторинга событий Lync Server или для запуска искусственных транзакций Lync Server.

Пакет управления компонентом и пользователями используется только для мониторинга Lync Server 2013. Если используется сценарий сосуществования, на котором установлены как Lync Server 2013, так и Lync Server 2010, следует по прежнему использовать пакеты управления Lync Server 2010 для компьютеров Lync Server 2010.

<div>


> [!NOTE]  
> Пакеты управления для Lync Server 2010 включают пакет управления мониторинга Lync Server 2010 и пакет управления мониторинга группового чата для Lync Server 2010.



</div>

Для импорта пакетов управления можно использовать следующие средства:

  - **System Center Operations Manager**     С помощью этого метода можно добавить мониторинг для Lync Server с помощью Operations Manager.

  - Оболочка Operations **Manager**     С помощью командной консоли Operations Manager можно импортировать и устранять неполадки, которые возникают при импорте пакетов управления с помощью консоли System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Импорт пакетов управления с помощью System Center Operations Manager

1.  Загрузите файлы Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  В System Center Operations Manager щелкните **Администрирование**.

3.  На панели **Администрирование** щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.

4.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).

5.  В диалоговом окне **Подключение к каталогу в Интернете** нажмите кнопку **Отмена** , чтобы запретить Operations Manager переходить в оперативный режим, чтобы узнать, существуют ли зависимости для пакетов управления Lync Server. Если вы используете System Center Operations Manager 2012, нажмите кнопку **нет**.

6.  В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы **Microsoft.LS.2013.Monitoring.mp** и **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, а затем нажмите кнопку **Открыть**. Чтобы выбрать в этом диалоговом окне несколько файлов, щелкните первый файл, а затем, удерживая клавишу CTRL, щелкните второй файл.

7.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**. Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и перезапустите процесс импорта и установки.

8.  В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**. Обратите внимание на то, что для выполнения процесса импорта и установки может потребоваться несколько минут.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Импорт пакетов управления с помощью командной консоли Operations Manager

В общем случае проще импортировать пакеты управления с помощью Operations Manager. Однако при возникновении ошибки и неудачном импорте консоль не всегда предоставляет соответствующие отчеты об ошибках. По сравнению с оболочкой Operations Manager предоставляются подробные сведения. Если вы используете Operations Manager и при импорте пакета управления возникли проблемы, импортируйте пакет с помощью командной консоли Operations Manager. В командной консоли Operations Manager содержатся дополнительные сведения, которые могут помочь определить причину сбоя импорта.

Если вы используете System Center Operations Manager 2007 R2, выполните следующую процедуру:

1.  В меню **Пуск**выберите пункт **все программы**, затем **System Center Operations Manager 2007 R2**и выберите команду **Shell Operations Manager**.

2.  В командной консоли Operations Manager введите в командной строке следующую команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Закройте командную консоль Operations Manager.

Если вы используете System Center Operations Manager 2012, выполните эту процедуру следующим образом:

1.  Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft System Center 2012**, **Operations Manager**, а затем — **Shell Operations Manager**.

2.  В командной консоли Operations Manager введите в командной строке следующую команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

