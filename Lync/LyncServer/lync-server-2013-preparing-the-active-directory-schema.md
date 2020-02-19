---
title: 'Lync Server 2013: подготовка схемы Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d92527ce109e68c932a9875020aab647bb6a723b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Подготовка схемы Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-27_

Прежде чем приступить к подготовке доменных служб Active Directory, можно открыть файлы схемы в текстовом редакторе, например в блокноте Windows, или просмотреть все расширения схемы доменных служб Active Directory, которые будут изменены для Lync Server 2013, в текстовом редакторе, например в блокноте Windows, или на странице " [расширения схемы Active Directory, классы и атрибуты, используемые в Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) . Lync Server использует четыре файла схемы:

  - Екстерналсчема. ldf, который используется для взаимодействия с Microsoft Exchange Server

  - Серверсчема. ldf, который является основным файлом схемы Lync Server 2013

  - BackCompatSchema.ldf, который используется для взаимодействия с какими-либо компонентами из предыдущих версий

  - VersionSchema.ldf, который используется для получения информации о версии подготовленной схемы

Все файлы .ldf устанавливаются в ходе подготовки схемы независимо от того, выполняется ли перенос с предыдущей версии или чистая установка. Эти файлы схемы устанавливаются в последовательности, показанной в предыдущем списке, и находятся в папке \\схемы\\поддержки на установочном носителе.

Расширения схемы Lync Server реплицируются по всем доменам, что влияет на сетевой трафик. Выполняйте подготовку схемы в то время, когда уровень использования сети является низким.

<div>


> [!NOTE]  
> Если вам нужно добавить поддержку Microsoft® Office Communicator Mobile 2007 R2 для Java и Microsoft® Office Communicator Mobile для Nokia 1,0 для мобильных клиентов в развертывание Lync Server 2013, необходимо подготовить схему Active Directory для Microsoft Office. Communications Server 2007 R2 во время установки Lync Server 2013. Необходимое программное обеспечение и документация см <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.



</div>

<div>

## <a name="adsi-edit"></a>Редактор ADSI

Редактор интерфейсов службы Active Directory (Active Directory Service Interfaces Editor — ADSI) — это средство администрирования AD DS, которое можно использовать для проверки подготовки схемы и репликации.

Редактор ADSI устанавливается по умолчанию при установке роли AD DS, чтобы сделать сервер контроллером домена. Для Windows Server 2008 и Windows Server 2008 R2 в состав средств удаленного администрирования сервера (RSAT. msc) включено средство редактирования ADSI (adsiedit. msc). Можно также установить RSAT на рядовые серверы или автономные серверы. Пакет RSAT копируется на эти серверы по умолчанию при установке Windows, но их установка по умолчанию не выполняется. Можно установить отдельные средства с помощью диспетчера серверов. Редактор ADSI входит в **средства администрирования ролей**, **средства доменных служб Active Directory** и **средства контроллера домена Active Directory**.

При использовании Windows Server 2003 редактор ADSI входит в состав средств поддержки. Средства поддержки доступны на компакт-диске Windows Server 2003 в папке " \\средства\\поддержки", или их можно загрузить с помощью средства поддержки Windows Server 2003 с пакетом обновления 2 32-разрядные [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770)версии. Инструкции по установке средств поддержки с компакт-диска продукта доступны в разделе "Установка средств поддержки Windows" [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771). Регистрация Adsiedit.dll выполняется автоматически при установке средств поддержки. Однако, если вы скопировали файлы на компьютер, необходимо выполнить команду **regsvr32** для регистрации файла adsiedit.dll, прежде чем вы сможете запустить это средство.

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Выполнение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

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

