---
title: 'Lync Server 2013: Удаление конфигурации архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a67d944de9b2c35c9ea2428603b39ddabbbcb26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Удаление конфигурации архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете удалить конфигурацию сайта или конфигурацию пула. Невозможно удалить глобальную конфигурацию. При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию. Сведения о способах реализации конфигураций архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, приведены в разделе [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, развертывание Документация или операционные документы.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>Удаление конфигурации сайта или пула для архивации

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.

4.  В списке конфигураций архивирования нажмите конфигурацию сайта или пула, которую необходимо удалить, затем выберите **Изменить** и **Удалить**.

5.  Нажмите **Исполнить**.

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации архивации с помощью командлетов Windows PowerShell

Параметры конфигурации архивации можно удалить с помощью Windows PowerShell и командлета **Remove-ксарчивингконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>Удаление заданной коллекции параметров конфигурации архивации

  - Следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond.
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации архивации, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации архивации, примененные к области служб.
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>Удаление параметров конфигурации архивации на основе заданного значения свойства

  - Эта команда удаляет все параметры конфигурации архивации, в которых отключено архивирование Exchange.
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Управление архивированием внутренней и внешней связи в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

