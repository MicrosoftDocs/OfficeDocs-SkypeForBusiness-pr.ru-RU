---
title: 'Lync Server 2013: подготовка доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Подготовка доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-19_

В Lync Server 2013 можно использовать мастер развертывания Lync Server для подготовки доменных служб Active Directory, а также использовать командлеты командной консоли Lync Server напрямую. Кроме того, вы можете использовать средство командной строки ldifde. exe непосредственно на контроллерах домена, как описано далее в этой статье.

Мастер развертывания Lync Server поможет вам пройти все задачи подготовки Active Directory. Мастер развертывания выполнит командлеты командной консоли Lync Server. Этот инструмент полезен для сред с одним доменом и топологией с одним лесом или с другой аналогичной топологией.

<div>


> [!IMPORTANT]  
> Вы можете развернуть Lync Server в лесу или домене, где контроллеры домена выполняют 32-разрядные версии некоторых операционных систем (Дополнительные сведения можно найти в разделе <A href="lync-server-2013-active-directory-infrastructure-requirements.md">требования к инфраструктуре службы каталогов Active Directory для Lync Server 2013</A>). Однако вы не можете использовать мастер развертывания Lync Server для подготовки схемы, леса и домена в этих средах, так как мастер развертывания и вспомогательные файлы предназначены только для 64. Вместо этого вы можете подготовить схему, лес и домен с помощью LDIFDE. exe и связанных с ними LDF-файлов на контроллере домена 32-bit. Ознакомьтесь с разделом "использование командлетов и LDIFDE. exe" Далее в этом разделе.



</div>

Вы можете использовать командлеты командной консоли Lync Server для удаленного запуска задач или для более сложных сред.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Необходимые условия для подготовки службы каталогов Active Directory

Вы должны выполнить подготовительные шаги Active Directory на компьютере под управлением Windows Server 2012, Windows Server 2012 R2 или Windows Server 2008 R2 с пакетом обновления 1 (64-разр.). Для подготовки Active Directory требуется командная консоль Lync Server Management Shell и Окскоре.

Для выполнения задач подготовки Active Directory требуются следующие компоненты:

  - Основные компоненты Lync Server (Окскоре. msi)
    
    <div>
    

    > [!NOTE]  
    > Если вы планируете использовать командную консоль управления Lync Server для подготовки службы каталогов Active Directory, сначала необходимо запустить мастер развертывания Lync Server для установки основных компонентов.

    
    </div>

  - Платформа Microsoft .NET Framework 4.5.
    
    <div>
    

    > [!NOTE]  
    > Для Windows Server 2012 и Windows Server 2012 R2 нужно установить и активировать платформу .NET Framework 4,5 с помощью диспетчера серверов. Дополнительные сведения можно найти в разделе "Microsoft .NET Framework 4,5" в <A href="lync-server-2013-additional-software-requirements.md">дополнительных требованиях к программному обеспечению для Lync Server 2013</A>. Для Windows Server&nbsp;2008&nbsp;R2 Скачайте и установите <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">платформу .NET Framework 4,5</A> на веб-сайте Майкрософт.

    
    </div>

  - Средства удаленного администрирования сервера (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Некоторые инструменты для RSAT нужны при запуске шагов подготовки Active Directory на рядовом сервере, а не на контроллере домена. Установите оснастки AD DS и средства командной строки и модуль Active Directory для Windows PowerShell из узла "средства AD DS и AD LDS" в диспетчере серверов.

    
    </div>

  - Распространяемый пакет Microsoft Visual C++ 11
    
    <div>
    

    > [!NOTE]  
    > Программа установки предложит установить этот компонент, если он еще не установлен на компьютере. Пакет предоставляется вам, и вы не сможете его получить отдельно.

    
    </div>

  - Windows PowerShell 3,0 (64-разр.)
    
    Для Windows Server 2012 и Windows Server 2012 R2, Windows PowerShell 3,0 следует включить в установку Lync Server 2013. Для Windows Server 2008 R2 необходимо установить или обновить приложение до Windows PowerShell 3,0. Дополнительные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Права и роли администратора

В следующей таблице показаны права администратора и роли, необходимые для каждой задачи подготовки Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Права пользователей, необходимые для подготовки службы каталогов Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Процедур</th>
<th>Права и роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Подготовка схемы</p></td>
<td><p>Группа "Администраторы схемы" для корневого домена леса и права администратора на хозяине схемы</p></td>
</tr>
<tr class="even">
<td><p>Подготовка леса</p></td>
<td><p>Член группы администраторов предприятия для леса</p></td>
</tr>
<tr class="odd">
<td><p>Подготовка домена</p></td>
<td><p>Входить в группу "Администраторы предприятия" или "Администраторы домена" для указанного домена</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Командлеты подготовки службы каталогов Active Directory

В следующей таблице сравниваются командлеты командной консоли Lync Server, используемые для подготовки AD DS к командам Лкскмд, используемым для подготовки AD DS в Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Командлеты по сравнению с Лкскмд

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Командлеты</th>
<th>Лкскмд</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Лкскмд/Forest/Актион: Счемапреп/Счематипе: Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Лкскмд/Forest/Актион: Чекксчемапрепстате</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Лкскмд/Forest/Актион: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Лкскмд/Forest/Актион: Форестунпреп</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Лкскмд/Forest/Актион: Чеккфорестпрепстате</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Лкскмд/Domain/Актион: Домаинпреп</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Лкскмд/Domain/Актион: Домаинунпреп</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Лкскмд/Domain/Актион: Чеккдомаинпрепстате</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Заблокированные требования Active Directory

Если наследование разрешений отключено или разрешения пользователей, прошедших проверку подлинности, должны быть отключены в вашей организации, необходимо выполнить дополнительные действия в процессе подготовки домена. Дополнительные сведения можно найти [в разделе Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Разрешения для настраиваемого контейнера

Если в вашей организации используются пользовательские контейнеры вместо трех встроенных контейнеров (то есть пользователей, компьютеров и контроллеров домена), необходимо предоставить доступ на чтение настраиваемым контейнерам для группы пользователей, прошедших проверку подлинности. Для подготовки домена требуется доступ на чтение к контейнерам. Дополнительные сведения можно найти в разделе [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Использование командлетов и LDIFDE. exe

Этап **подготовки схемы** в мастере развертывания Lync Server и командлет **Install-Ксадсерверсчема** расширяет схему Active Directory на контроллерах домена под управлением 64-разрядной операционной системы. Если вам нужно продлить схему Active Directory на контроллере домена под управлением 32-разрядной операционной системы, вы можете выполнить командлет **Install-ксадсерверсчема** удаленно с рядового сервера (рекомендуемый способ). Тем не менее, если требуется выполнить подготовку схемы непосредственно на контроллере домена, можно использовать средство ldifde. exe для импорта файлов схемы. Средство Ldifde. exe поставляется с большинством версий операционной системы Windows.

Если для импорта файлов схемы используется программа LDIFDE. exe, необходимо импортировать все четыре файла независимо от того, выполняется ли миграция из предыдущей версии или выполняется чистая установка. Вы должны импортировать их в следующей последовательности:

1.  Екстерналсчема. ldf

2.  Серверсчема. ldf

3.  Бакккомпатсчема. ldf

4.  Версионсчема. ldf

<div>


> [!NOTE]  
> Четыре LDF файлов находятся в каталоге \Суппорт\счема установочного носителя или файле.



</div>

Чтобы использовать Ldifde. exe для импорта четырех файлов схемы на контроллере домена, который является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Например:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Параметр b следует использовать только в том случае, если вы вошли в систему под учетной записью другого пользователя. Подробные сведения о необходимых правах пользователей можно найти в разделе "права и роли администратора", приведенном ранее в этой статье.



</div>

Чтобы использовать Ldifde. exe для импорта четырех файлов схемы на контроллере домена, который не является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Подробнее об использовании ldifde можно узнать в статье 237677 базы знаний Майкрософт "использование LDIFDE для импорта и экспорта объектов службы каталогов Active Directory" [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Подготовка схемы Active Directory в Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

