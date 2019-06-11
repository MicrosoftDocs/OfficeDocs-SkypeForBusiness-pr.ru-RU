---
title: 'Lync Server 2013: конфигурация IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Конфигурация IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-17_

Для успешного выполнения этой процедуры необходимо войти на сервер с минимальным уровнем прав локального администратора и пользователя домена.

Перед настройкой и установкой сервера переднего плана для Lync Server 2013, Standard Edition или первого сервера переднего плана в пуле вы устанавливаете и настраиваете роль сервера и веб-службы для служб IIS.

<div class=" ">


> [!IMPORTANT]  
> Если в вашей организации требуется найти IIS и все веб-службы на диске, отличном от системного, вы можете изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне настройки при первоначальной установке Lync Server 2013 Средства администрирования. Перед установкой IIS необходимо установить средства администрирования. Если вы установили файлы установки по этому пути, включая Окскоре. msi, остальные файлы Lync Server 2013 будут развернуты и на этом диске. Дтаилс можно найти в разделе <A href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</A>. Сведения о том, как переместить ИНЕТПУБ, развернутый диспетчером Windows Server Manager при установке IIS <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>, можно найти в разделе.



</div>

В приведенной ниже таблице указаны необходимые службы ролей IIS 7,5.

### <a name="iis-75-role-services"></a>Службы ролей IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Заголовок роли</th>
<th>Служба ролей</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Стандартные компоненты HTTP установлены</p></td>
<td><p>Статическое содержимое</p></td>
</tr>
<tr class="even">
<td><p>Стандартные компоненты HTTP установлены</p></td>
<td><p>Документ по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>Стандартные компоненты HTTP установлены</p></td>
<td><p>Ошибки HTTP</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.NET</p>
<p>Для Windows Server 2012 также требуется ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширения ISAPI (Internet Server API)</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Исправность и диагностика</p></td>
<td><p>Ведение журнала HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Исправность и диагностика</p></td>
<td><p>Средства ведения журнала</p></td>
</tr>
<tr class="even">
<td><p>Исправность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Анонимная проверка подлинности (установлен и включен по умолчанию)</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности сопоставления сертификатов клиентов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Фильтрация запросов</p></td>
</tr>
<tr class="odd">
<td><p>Производительность</p></td>
<td><p>Сжатие статического содержимого</p>
<p>Сжатие динамического содержимого</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Консоль управления IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
</tbody>
</table>


В операционной системе Windows Server 2008 R2 с пакетом обновления 1 (SP1) можно использовать Windows PowerShell 2,0. Сначала нужно импортировать модуль ServerManager, а затем установить роль сервера IIS 7,5 и службы ролей.

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> Анонимная проверка подлинности устанавливается по умолчанию с ролью сервера IIS. Вы можете управлять анонимной проверкой подлинности после установки IIS. Дополнительные сведения можно найти в <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>разделе "включить анонимную проверку подлинности (IIS 7)".



</div>

В таблице ниже указаны обязательные службы ролей IIS 8,0 и IIS 8,5 для Windows Server 2012 и Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Для Windows Server 2012 и Windows Server 2012 R2 командлет Add-WindowsFeature был заменен командлетом Install-WindowsFeature. Подробности можно найти в разделе <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Службы ролей IIS 8,0 и IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Заголовок роли</th>
<th>Служба ролей</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Веб-сервер (IIS)</p></td>
<td><p>Веб-сервер</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Документ по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Просмотр каталога</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Ошибки HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Статическое содержимое</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>Перенаправление HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Ведение журнала HTTP</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Монитор запросов</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Фильтрация запросов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Обычная проверка подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности с сопоставлением сертификатов клиентов</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширения ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Включения на стороне сервера</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Консоль управления IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Совместимость метабазы IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
<tr class="odd">
<td><p>Возможности .NET 3,5 Framework</p></td>
<td><p>.NET 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Возможности .NET 4,5 Framework</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Возможности .NET 4,5 Framework</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Возможности .NET 4,5 Framework</p></td>
<td><p>Активация HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Возможности .NET 4,5 Framework</p></td>
<td><p>Общий доступ к портам TCP</p></td>
</tr>
<tr class="even">
<td><p>Фоновая интеллектуальная служба передачи</p></td>
<td><p>Серверные расширения IIS</p></td>
</tr>
<tr class="odd">
<td><p>Службы рукописного ввода</p></td>
<td><p>Службы рукописного ввода</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Пользовательские интерфейсы и инфраструктура</p></td>
<td><p>Графические средства управления и инфраструктура</p></td>
</tr>
<tr class="even">
<td><p>Пользовательские интерфейсы и инфраструктура</p></td>
<td><p>Работа с рабочим столом</p></td>
</tr>
<tr class="odd">
<td><p>Пользовательские интерфейсы и инфраструктура</p></td>
<td><p>Графическая консоль сервера</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Служба активации процессов Windows</p></td>
<td><p>Модель процесса</p></td>
</tr>
<tr class="even">
<td><p>Служба активации процессов Windows</p></td>
<td><p>API конфигурации</p></td>
</tr>
</tbody>
</table>


В Windows Server 2012 и Windows Server 2012 R2 для установки требований к службам IIS можно использовать Windows PowerShell 3,0. С помощью модуля ServerManager в Windows PowerShell 3,0 введите:

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Новая возможность в Windows Server 2012 — это параметр – source, который определяет, где можно найти исходный носитель Windows Server 2012. Этот носитель можно задать в качестве DVD-дисковода (например, Д:\саурцес\сксс) или сетевого общего доступа, в который были скопированы файлы мультимедиа (например, \\fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>См. также


[Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

