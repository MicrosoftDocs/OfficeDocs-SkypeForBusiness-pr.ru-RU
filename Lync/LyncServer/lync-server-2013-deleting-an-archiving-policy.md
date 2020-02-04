---
title: 'Lync Server 2013: Удаление политики архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Удаление политики архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете удалить политику пользователей или политику сайта. Невозможно удалить глобальную политику. Если вы попытаетесь удалить глобальную политику, Lync Server 2013 автоматически восстанавливает значения по умолчанию для этой политики.

<div>


> [!NOTE]  
> Если вы включили интеграцию Microsoft Exchange для развертывания, политики Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте. Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Удаление политики пользователя или сайта для архивации

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.

4.  В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.

5.  Нажмите **Исполнить**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик архивации с помощью командлетов Windows PowerShell

Политики архивации можно удалить с помощью Windows PowerShell и командлета **Remove-ксарчивингполици** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Удаление указанной политики архивации

  - Например, **Remove-ксарчивингполици** удаляет политику с сайтом удостоверений: Redmond. Обратите внимание на то, что при удалении политики сайта Политика сайта автоматически управляется пользователями, которые раньше настроили политикой для архивации. Следующая команда удаляет архивирование, примененное к сайту Redmond.
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Удаление всех политик архивации, примененных к области "на пользователя"

  - Эта команда удаляет все политики архивации, примененные к области "на пользователя".
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Удаление всех политик архивации, исключающих внутреннее архивирование

  - Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>См. также


[Управление архивированием внутренней и внешней связи в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

