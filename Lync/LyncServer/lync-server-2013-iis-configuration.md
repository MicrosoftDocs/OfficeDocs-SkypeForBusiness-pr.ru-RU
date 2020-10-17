---
title: 'Lync Server 2013: Конфигурация IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528156"
---
# <a name="iis-configuration-in-lync-server-2013"></a>Конфигурация IIS в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-17_

Для успешного выполнения этой процедуры вам необходимо выполнить вход на сервер как минимум с учетной записью локального администратора и пользователя домена.

Перед настройкой и установкой сервера переднего плана для Lync Server 2013, Standard Edition или первого сервера переднего плана в пуле устанавливается и настраивается роль сервера и веб-службы для служб IIS.

<div class=" ">


> [!IMPORTANT]  
> Если в Организации требуется, чтобы службы IIS и все веб-службы настроились на диске, отличном от системного диска, можно изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне программы установки при первоначальной установке средств администрирования Lync Server 2013. Средства администрирования устанавливаются перед установкой служб IIS. Если вы устанавливаете файлы установки по указанному пути, в том числе OCSCore.msi, остальные файлы Lync Server 2013 будут развернуты на этом диске. Сведения о дтаилс можно найти в <A href="lync-server-2013-install-lync-server-administrative-tools.md">статье Установка средств администрирования Lync Server 2013</A>. Сведения о том, как переместить INETPUB, развернутый диспетчером Windows Server при установке IIS, можно узнать в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .



</div>

В следующей таблице перечислены требуемые службы роли IIS 7.5.

### <a name="iis-75-role-services"></a>Службы ролей IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Название роли</th>
<th>Служба роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Статическое содержимое</p></td>
</tr>
<tr class="even">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Документ по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>Общие установленные функции HTTP</p></td>
<td><p>Ошибки HTTP</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.NET</p>
<p>Для Windows Server 2012 также требуется ASP. NET 4.5.</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширения Internet Server API (ISAPI)</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Ведение журнала HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Образца</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Анонимная проверка подлинности (установлена и включена по умолчанию)</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности с сопоставлением сертификатов клиентов</p></td>
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


В операционной системе Windows Server 2008 R2 с пакетом обновления 1 (SP1) для Windows Server R2 можно использовать Windows PowerShell 2,0. Сначала нужно импортировать модуль ServerManager, а затем установить роль и службы роли IIS 7.5.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> Анонимная проверка подлинности устанавливается по умолчанию при установке роли сервера IIS. Вы можете управлять анонимной проверкой подлинности после установки служб IIS. Дополнительные сведения см. в разделе "Включение анонимной проверки подлинности (IIS 7)" <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .



</div>

В следующей таблице указаны обязательные службы ролей IIS 8,0 и IIS 8,5 для Windows Server 2012 и Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Для Windows Server 2012 и Windows Server 2012 R2 командлет Add-WindowsFeature был заменен командлетом Install-WindowsFeature. Дополнительные сведения см. в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install $ WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Службы ролей IIS 8,0 и IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Название роли</th>
<th>Служба роли</th>
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
<td><p>Просмотр каталогов</p></td>
</tr>
<tr class="even">
<td><p>Основные возможности HTTP</p></td>
<td><p>ошибки HTTP;</p></td>
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
<td><p>Проверка работоспособности и диагностика</p></td>
<td><p>Средства ведения журнала</p></td>
</tr>
<tr class="odd">
<td><p>Проверка работоспособности и диагностика</p></td>
<td><p>Монитор запросов</p></td>
</tr>
<tr class="even">
<td><p>Проверка работоспособности и диагностика</p></td>
<td><p>Образца</p></td>
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
<td><p>проверка подлинности с сопоставлением сертификата клиента.</p></td>
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
<td><p>Компоненты на стороне сервера</p></td>
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
<td><p>Функции .NET 3,5 Framework</p></td>
<td><p>.NET 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Функции .NET 4,5 Framework</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Функции .NET 4,5 Framework</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Функции .NET 4,5 Framework</p></td>
<td><p>Активация по протоколу HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Функции .NET 4,5 Framework</p></td>
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
<td><p>Возможности рабочего стола</p></td>
</tr>
<tr class="odd">
<td><p>Пользовательские интерфейсы и инфраструктура</p></td>
<td><p>Графическая консоль сервера</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3,5</p></td>
<td><p>Windows Identity Foundation 3,5</p></td>
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

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Новый элемент с Windows Server 2012 — это параметр – source, определяющий, где можно найти исходный носитель Windows Server 2012. Носитель можно определить как DVD-дисковод (например, Д:\саурцес\сксс) или в сетевую папку, в которую были скопированы файлы мультимедиа (например, \\ fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>См. также


[Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

