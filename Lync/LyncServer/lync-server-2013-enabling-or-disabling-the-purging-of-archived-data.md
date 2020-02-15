---
title: 'Lync Server 2013: Включение или отключение очистки архивных данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Включение или отключение очистки архивных данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы включать и отключать очистку и настраивать реализацию очистки. Это включает следующие конфигурации архивирования:

  - Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.

  - Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.

Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания. Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.

<div>


> [!NOTE]  
> Чтобы использовать архивацию для пользователей, размещенных в Lync Server 2013, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для обоих. По умолчанию архивация не включена для внутренних и внешних коммуникаций. Прежде чем включать архивацию в любых политиках, необходимо указать соответствующие конфигурации архивации для развертывания и, при необходимости, для конкретных сайтов и пулов, как описано в этом разделе. Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.<BR>Если вы решили после развертывания архивации, в которой вы хотите использовать интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013, а все пользователи размещены на серверах Exchange 2013, следует удалить конфигурацию базы данных SQL Server. из топологии. Для этого необходимо использовать построитель топологий. Дополнительные сведения приведены в статье <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных архивации в Lync Server 2013</A> в документации по операциям.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Включение или отключение очистки для архивации

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.

4.  В списке конфигураций архивации выберите название соответствующей глобальной конфигурации, конфигурации узла или пула, в меню **Правка** выберите пункт **Показать подробности** и затем сделайте следующее.
    
      - Чтобы включить очистку, установите флажок **Включить очистку данных архивации** и выполните одно из следующих действий.
        
          - Чтобы очистить все записи, щелкните **Очищать экспортированные и сохраненные данные архивации после максимального срока (дней)** и укажите число дней.
        
          - Чтобы очистить только экспортированные данные, щелкните **Очищать только экспортированные данные архивации**.
    
      - Чтобы отключить очистку, снимите флажок **Включить очистку данных архивации**.

5.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Включение или отключение очистки данных архивации с помощью командлетов Windows PowerShell

Включение и отключение автоматической очистки данных архивации может осуществляться с помощью Windows PowerShell и командлета **Set – CsArchivingConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Включение очистки всех данных архивации

  - Чтобы включить очистку всех данных архивации, установите для свойства **EnablePurging** значение True ($True). Пример:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    После выполнения этой команды каждый день Lync Server будет очищать все записи архивации старше значения, указанного для свойства **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Включение очистки только экспортированных данных архивации

  - Чтобы ограничить удаление записями, экспортированными в файл данных (с помощью командлета [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), необходимо также задать для свойства Пуржеекспортедарчивесонли значение True ($true). Пример:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    После выполнения этой команды Lync Server будет очищать только записи архивации, соответствующие двум условиям: 1), которые старше значения, указанного для свойства **KeepArchivingDataForDays** ; и 2) они были экспортированы с помощью командлета **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Отключение очистки всех данных архивации

  - Чтобы отключить автоматическую очистку записей архивации, установите для свойства **EnablePurging** значение False ($False). Пример:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Для получения дополнительных сведений, в том числе дополнительных вариантов очистки данных архивации, обратитесь к разделу "Справка" для командлета [Set – CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Принцип работы архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Настройка и назначение политик архивации в Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

