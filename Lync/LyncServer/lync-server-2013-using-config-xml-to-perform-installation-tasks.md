---
title: 'Lync Server 2013: использование Config.xml для выполнения задач установки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901d95797955c6f545c0d305e2c855829c92addf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535786"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Использование Config.xml для выполнения задач установки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:

  - задание пути для точки сетевой установки;

  - выбор устанавливаемых продуктов;

  - настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;

  - задание параметров установки, таких как имя пользователя;

  - копирование локального источника установки на компьютер пользователя без установки Office;

  - Добавление или удаление устанавливаемых языков.

Рекомендуется использовать файл Config.xml для настройки автоматической установки Lync 2013.

По умолчанию файл Config.xml, хранящийся в основной папке продукта (например, \\ Product. WW) направляет программу установки для установки этого продукта. Например, файл Config.xml в следующей папке устанавливает Lync 2013:

  - \\\\\\общий доступ к серверу \\ Lync15 \\ Lync. WW \\Config.xml

Элементы Config.xml, наиболее часто используемые для установки Lync 2013, перечислены в следующей таблице.

### <a name="configxml-elements"></a>Элементы Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Элемент</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Конфигурация</p></td>
<td><p>Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Определяет, как при установке будут обрабатываться компоненты конкретного продукта. Используйте следующие атрибуты для предотвращения установки служб Business Connectivity Services, в том числе общих компонентов, которые мешают работе с Outlook 2010:</p>
<ul>
<li><p>ID = &quot; лобимаин&quot;</p></li>
<li><p>State = &quot; отсутствует&quot;</p></li>
<li><p>Дети = &quot; Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Отображение</p></td>
<td><p>Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>CompletionNotice = &quot; Да &quot;  |  &quot; нет &quot; (по умолчанию)</p></li>
<li><p>AcceptEula = &quot; Да &quot;  |  &quot; нет &quot; (по умолчанию)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Ведение журнала</p></td>
<td><p>Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Тип = &quot; &quot;  |  &quot; Standard &quot; (по умолчанию) | &quot; Verbose&quot;</p></li>
<li><p>Template=”имя файла.txt” (имя файла журнала)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Параметр</p></td>
<td><p>Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Параметр ID = &quot; Name &quot; (имя свойства установщика Windows)</p></li>
<li><p>Значение = &quot; значение &quot; (значение, присваиваемое свойству)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</p>
<ul>
<li><p>Location = "путь"</p></li>
</ul></td>
</tr>
</tbody>
</table>


В следующем примере показан файл Config.xml для типичной автоматической установки Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Подробные сведения об использовании файла Config.xml для выполнения задач установки и обслуживания Office можно найти на сайте <https://go.microsoft.com/fwlink/p/?linkid=267514> .

<div>

## <a name="to-customize-the-configxml-file"></a>Изменение файла Config.xml

1.  Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".

2.  Найдите строки, содержащие элементы, которые нужно изменить.

3.  Измените запись для элемента, используя нужные значения параметров автоматической установки. Убедитесь, что вы удалили разделители комментариев, " \<\!--" and "--\> ". Например, используйте следующий синтаксис:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Сохраните файл Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

