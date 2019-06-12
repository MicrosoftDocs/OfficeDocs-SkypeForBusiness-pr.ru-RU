---
title: 'Lync Server 2013: использование файла config. XML для выполнения задач установки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3fb6f4c77375781b6c5d767087ad61f3ec6401b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Использование файла config. XML для выполнения задач установки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:

  - задание пути для точки сетевой установки;

  - выбор устанавливаемых продуктов;

  - настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;

  - задание параметров установки, таких как имя пользователя;

  - копирование локального источника установки на компьютер пользователя без установки Office;

  - добавление и удаления языков из установки.

Мы рекомендуем использовать файл config. XML для настройки автоматической установки Lync 2013.

По умолчанию файл config. XML, хранящийся в основной папке продукта (например, \\Product. WW) направляет настройку для установки этого продукта. Например, файл config. XML из следующей папки устанавливает Lync 2013:

  - \\\\Общий\\доступ\\к\\серверу Lync15 Lync \\. WW config. XML

Элементы config. XML, наиболее часто используемые при установке Lync 2013, перечислены в таблице ниже.

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
<td><p>Configuration</p></td>
<td><p>Элемент верхнего уровня (обязательно). Имеет атрибут Product, например: Product = Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Определяет, как при установке будут обрабатываться компоненты конкретного продукта. Следующие атрибуты используются для предотвращения установки служб Business Connectivity Services, включая общие компоненты, которые мешают работе Outlook 2010:</p>
<ul>
<li><p>ID =&quot;лобимаин&quot;</p></li>
<li><p>Штат =&quot;отсутствует&quot;</p></li>
<li><p>Дочерние элементы =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p></td>
<td><p>Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Комплетионнотице =&quot;да&quot; | &quot;нет&quot;(по умолчанию)</p></li>
<li><p>Атрибута AcceptEULA =&quot;да&quot; | &quot;нет&quot;(по умолчанию)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Type =&quot;OFF&quot; | &quot;Standard&quot;(по умолчанию) | &quot;Подробный&quot;</p></li>
<li><p>Template="filename.txt" (имя файла журнала)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Setting</p></td>
<td><p>Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</p>
<ul>
<li><p>Параметр ID =&quot;Name&quot; (имя свойства установщика Windows)</p></li>
<li><p>Value =&quot;value&quot; (значение, которое нужно присвоить свойству)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</p>
<ul>
<li><p>Location="path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


В следующем примере показан файл config. XML для типичной автоматической установки Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Подробные сведения об использовании файла config. XML для выполнения задач по установке и сопровождению Office можно найти <http://go.microsoft.com/fwlink/p/?linkid=267514>по адресу.

<div>

## <a name="to-customize-the-configxml-file"></a>Изменение файла Config.xml

1.  Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".

2.  Найдите строки, содержащие элементы, которые нужно изменить.

3.  Измените запись для элемента, используя нужные значения параметров автоматической установки. Убедитесь, что вы удалите разделители комментариев, "\<\!--" и "--\>". Например, используйте следующий синтаксис:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Сохраните файл Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

