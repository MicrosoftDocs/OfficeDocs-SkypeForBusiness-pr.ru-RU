---
title: 'Lync Server 2013: Удаление конфигурации архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acca3c362a5e0a2a8a6198d156c24be47884d70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525446"
---
# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Удаление конфигурации архивации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете удалить конфигурацию сайта или пула. Однако, нельзя удалить глобальную конфигурацию. Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию. Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>Удаление конфигурации сайта или пула для архивации

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.

4.  В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).

5.  Щелкните **Commit** (Сохранить).

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации архивации с помощью командлетов Windows PowerShell

Параметры конфигурации архивации можно удалить с помощью Windows PowerShell и командлета **Remove – CsArchivingConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации архивации

  - Следующая команда удаляет параметры конфигурации архивации, применяемые к сайту Redmond.
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации архивации, применяемых на уровне сайта

  - Эта команда удаляет все параметры конфигурации архивации, применяемые на уровне службы.
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>Удаление параметров конфигурации архивации на основе указанного значения свойства

  - Эта команда удаляет все параметры конфигурации архивации, в которых отключена служба архивации Exchange.
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Принцип работы архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

