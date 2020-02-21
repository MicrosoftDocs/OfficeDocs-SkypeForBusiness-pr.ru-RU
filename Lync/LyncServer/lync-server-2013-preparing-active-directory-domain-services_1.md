---
title: 'Lync Server 2013: Подготовка доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c5d83acbe32d33a235e7c2918663340a3ac7ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Подготовка доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-19_

В Lync Server 2013 вы можете использовать мастер развертывания Lync Server для подготовки доменных служб Active Directory или напрямую использовать командлеты командной консоли Lync Server. Кроме того, можно использовать программу командной строки ldifde.exe непосредственно в контроллерах доменов, как описывается ниже в данной статье.

Мастер развертывания Lync Server поможет вам выполнить все задачи по подготовке Active Directory. Мастер развертывания выполняет командлеты командной консоли Lync Server. Это средство полезно для сред с одним доменом и топологией одного леса или другой аналогичной топологией.

<div>


> [!IMPORTANT]  
> Вы можете развернуть Lync Server в лесу или домене, где контроллеры домена выполняют 32-разрядные версии некоторых операционных систем (Дополнительные сведения см. в статье <A href="lync-server-2013-active-directory-infrastructure-requirements.md">требования к инфраструктуре Active Directory для Lync Server 2013</A>). Однако мастер развертывания Lync Server невозможно использовать для запуска схемы, леса и подготовки доменов в этих средах, так как мастер развертывания и вспомогательные файлы имеют только 64 бит. Вместо этого можно использовать Ldifde. exe и связанные LDF файлы на контроллере домена 32, чтобы подготовить схему, лес и домен. Ознакомьтесь с разделом "использование командлетов и LDIFDE. exe" Далее в этом разделе.



</div>

Командлеты командной консоли Lync Server можно использовать для удаленного запуска задач или более сложных сред.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Необходимые условия для подготовки Active Directory

Необходимо выполнить подготовительные действия Active Directory на компьютере под управлением Windows Server 2012, Windows Server 2012 R2 или Windows Server 2008 R2 с пакетом обновления 1 (64-разр). Для подготовки Active Directory требуется командная консоль Lync Server и OCSCore.

Для выполнения задач подготовки Active Directory необходимы следующие компоненты.

  - Основные компоненты Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Если вы планируете использовать командную консоль Lync Server для подготовки Active Directory, необходимо сначала запустить мастер развертывания Lync Server, чтобы установить основные компоненты.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Для Windows Server 2012 и Windows Server 2012 R2 вы устанавливаете и активизируете .NET Framework 4,5 с помощью диспетчера серверов. Подробнее: "Microsoft .NET Framework 4,5" в <A href="lync-server-2013-additional-software-requirements.md">дополнительных требованиях к программному обеспечению для Lync Server 2013</A>. Для Windows Server&nbsp;2008&nbsp;R2 Скачайте и установите <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> на веб-сайте Майкрософт.

    
    </div>

  - Средства удаленного администрирования сервера (RSAT).
    
    <div>
    

    > [!NOTE]  
    > Некоторые средства RSAT необходимы, когда действия по подготовке Active Directory выполняются не в контроллере домена, а на рядовом сервере. Установите оснастки AD DS и средства командной строки и модуль Active Directory для Windows PowerShell из узла AD DS and AD LDS Tools в диспетчере серверов.

    
    </div>

  - Распространяемый комплект Microsoft Visual C++ 11.
    
    <div>
    

    > [!NOTE]  
    > Программа установки предложит установить этот необходимый компонент, если он не был установлен ранее. Пакет вам поставляется, и не придется приобретать его отдельно.

    
    </div>

  - Windows PowerShell 3,0 (64-бит)
    
    Для Windows Server 2012 и Windows Server 2012 R2 необходимо включить Windows PowerShell 3,0 в установку Lync Server 2013. Для Windows Server 2008 R2 необходимо установить или обновить Windows PowerShell 3,0. Дополнительные сведения см в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Права и роли администратора

В следующей таблице приведены административные права и роли, которые необходимы для каждой задачи подготовки Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Права пользователя, необходимые для подготовки Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedure</th>
<th>Права или роли</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Подготовка схемы</p></td>
<td><p>Членство в группе администраторов схемы для корневого домена леса и права администратора для хозяина схемы</p></td>
</tr>
<tr class="even">
<td><p>Подготовка леса</p></td>
<td><p>Членство в группе администраторов предприятия для леса</p></td>
</tr>
<tr class="odd">
<td><p>Подготовка домена</p></td>
<td><p>Членство в группе администраторов предприятия или в группе администраторов домена для конкретного домена</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Командлеты подготовки Active Directory

В следующей таблице сравниваются командлеты командной консоли Lync Server, которые используются для подготовки AD DS к командам командами LcsCmd, используемым для подготовки AD DS в Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Командлеты в сравнении с командами LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Командлеты</th>
<th>Командами LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install — CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get — CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable — CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable — CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get — CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable — CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable — CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get — CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Блокирование требований Active Directory

Если в вашей организации отключено наследование разрешений, или должны быть отключены разрешения авторизованного пользователя, то во время подготовки домена необходимо выполнить дополнительные действия. Дополнительные сведения см [в статье Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Разрешения настраиваемых контейнеров

Если в вашей организации вместо трех встроенных контейнеров ("Пользователи", "Компьютеры" и "Контроллеры доменов") используются настраиваемые контейнеры, то необходимо предоставить группе авторизованных пользователей доступ на чтение в этих настраиваемых контейнерах. Доступ на чтение в этих контейнерах необходим для подготовки домена. Дополнительные сведения см. в статье [Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Использование командлетов и Ldifde.exe

Этап **подготовки схемы** в мастере развертывания Lync Server и командлет **Install – CsAdServerSchema** расширяет схему Active Directory на контроллерах домена под управлением 64 разрядной операционной системы. Если требуется распространить схему Active Directory на контроллер домена с 32-разрядной операционной системой, можно выполнить командлет **Install-CsAdServerSchema** удаленно с рядового сервера (это рекомендуемый подход). Однако если требуется выполнить подготовку схемы непосредственно в контроллере домена, можно использовать программу Ldifde.exe для импорта файлов схемы. Программа Ldifde.exe поставляется с большинством версий операционной системы Windows.

Если импорт файлов схемы выполняется с помощью программы Ldifde.exe, то необходимо импортировать все файлы, независимо от того, выполняется ли миграция от предыдущей версии или чистая установка. Эти файлы необходимо импортировать в следующем порядке:

1.  Екстерналсчема. ldf

2.  Серверсчема. ldf

3.  Бакккомпатсчема. ldf

4.  Версионсчема. ldf

<div>


> [!NOTE]  
> Эти четыре LDF-файла расположены в каталоге \Support\Schema установочного носителя или загрузки.



</div>

Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Например:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Параметр b следует использовать только в том случае, если вы вошли как другой пользователь. Подробные сведения о необходимых правах пользователя см. в разделе "Права и роли администратора" выше в этой статье.



</div>

Чтобы с помощью программы Ldifde.exe импортировать эти четыре файла схемы в контроллер домена, который не является хозяином схемы, используйте следующий формат:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Подробнее об использовании ldifde можно узнать в статье базы знаний Майкрософт 237677 "использование средства LDIFDE для импорта и экспорта объектов каталога в Active Directory" по адресу [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).

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

