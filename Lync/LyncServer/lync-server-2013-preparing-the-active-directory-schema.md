---
title: 'Lync Server 2013: подготовка схемы Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Подготовка схемы Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-27_

Прежде чем приступить к подготовке доменных служб Active Directory, вы можете открыть файлы схемы в текстовом редакторе, например в блокноте, или просмотреть [расширения, классы и атрибуты схемы Active Directory, которые используются в Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) для проверки всех активных Расширения схемы доменных служб Active Directory, которые будут изменены для Lync Server 2013. Lync Server использует четыре файла схемы:

  - Екстерналсчема. ldf, который используется для взаимодействия с сервером Microsoft Exchange Server

  - Серверсчема. ldf, являющийся основным файлом схемы Lync Server 2013

  - Бакккомпатсчема. ldf, который используется для взаимодействия с любыми компонентами предыдущих выпусков

  - Версионсчема. ldf, который используется для получения сведений о версии подготовленной схемы

Все LDF-файлы устанавливаются во время подготовки схемы, независимо от того, выполняется ли миграция из предыдущего выпуска или выполняется чистая установка. Эти файлы схемы устанавливаются в последовательности, указанной в предыдущем списке, и находятся в папке схемы \\поддержки\\на установочном носителе.

Расширения схемы Lync Server реплицируются по всем доменам, что влияет на сетевой трафик. Выполняйте подготовку схемы по истечении уровня использования сети.

<div>


> [!NOTE]  
> Если вам нужно добавить поддержку Microsoft® Office Communicator Mobile 2007 R2 для Java и Microsoft® Office Communicator Mobile для мобильных клиентов для Nokia 1,0 на сайте Lync Server 2013, необходимо подготовить схему Active Directory для Microsoft Office. Communications Server 2007 R2 во время установки Lync Server 2013. Необходимое программное обеспечение и документацию можно <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>найти в разделе.



</div>

<div>

## <a name="adsi-edit"></a>Редактирование ADSI

Редактор интерфейсов служб Active Directory (Редактирование ADSI) — это средство администрирования доменных служб, которое можно использовать для проверки подготовки и репликации схемы.

Редактирование ADSI устанавливается по умолчанию при установке роли AD DS, чтобы сделать сервер контроллером домена. В Windows Server 2008 и Windows Server 2008 R2 средство редактирования ADSI (adsiedit. msc) входит в состав средств удаленного администрирования сервера (RSAT). Вы также можете установить RSAT на рядовые серверы домена или отдельные серверы. Пакет RSAT копируется на эти серверы по умолчанию при установке Windows, но не устанавливается по умолчанию. Отдельные инструменты устанавливаются с помощью диспетчера сервера. Редактирование ADSI входит в раздел **средства администрирования ролей**, **средства доменных служб Active Directory**, **средства контроллера домена Active Directory**.

В Windows Server 2003 Редактирование ADSI входит в состав средств поддержки. Средства поддержки доступны на компакт-диске Windows Server 2003 в папке " \\средства\\поддержки", а также в разделе "Windows Server 2003 с пакетом обновления 2 32-разрядная версия для поддержки [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)". Инструкции по установке средств поддержки с компакт-диска продукта можно найти в разделе "Установка средств поддержки Windows" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)на сайте. Файл adsiedit. dll автоматически регистрируется при установке средств поддержки. Тем не менее, если вы скопировали файлы на свой компьютер, необходимо выполнить команду **regsvr32** для регистрации файла adsiedit. dll, прежде чем можно будет запустить средство.

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Проведение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Проверка репликации схемы в Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

