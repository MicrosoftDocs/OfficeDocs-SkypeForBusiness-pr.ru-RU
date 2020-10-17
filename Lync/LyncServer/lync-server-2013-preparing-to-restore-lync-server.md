---
title: 'Lync Server 2013: подготовка к восстановлению Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31354ee87cdf7df5efdb6c4e2accf3758829c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506836"
---
# <a name="preparing-to-restore-lync-server-2013"></a>Подготовка к восстановлению Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Прежде чем приступать к восстановлению серверов и баз данных после сбоя, необходимо определить следующее:

  - Что необходимо восстановить.

  - Оборудование, программное обеспечение, данные и инструменты, необходимые для восстановления.

<div>

## <a name="determining-what-to-restore"></a>Определение объектов для восстановления

В этом разделе описывается, как восстановить простои Lync Server, происходящие на уровне сервера, пула или центрального хранилища управления. Если центральное хранилище управления завершается с ошибкой, развертывание Lync Server продолжает работать, но вы не можете вносить какие – либо изменения в конфигурацию. В случае сбоя фонового сервера или сервера Standard Edition пул пользователей перестает работать. Если какой-либо другой сервер завершается с ошибкой, то величина сбоя зависит от роли сервера, на котором работает сервер, и от того, содержит ли сервер одну или несколько баз данных.

### <a name="what-to-restore"></a>Восстановление

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Если это не удалось</th>
<th>В этом разделе:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Сервер Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Восстановление сервера Standard Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Центральное хранилище управления</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Серверная часть Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Зеркальный сервер основного сервера Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — основной</a></p></td>
</tr>
<tr class="odd">
<td><p>Дополнительный зеркальный сервер сервера Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — зеркало</a></p></td>
</tr>
<tr class="even">
<td><p>Любой сервер Enterprise Edition, на котором работает роль сервера, например, сервер переднего плана, пограничный сервер, директор, сервер-посредник или сервер сохраняемого чата.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Весь пул Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Восстановление пула Lync Server в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Хранилище файлов Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Восстановление хранилища файлов в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Автономная база данных мониторинга или база данных архивации</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Восстановление данных мониторинга или архивации в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Автономная база данных сохраняемого чата</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Восстановление данных сохраняемого чата в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Сбор данных о оборудовании, программном обеспечении и средствах

При восстановлении сервера необходимо начать с нового или чистого компьютера. Кроме того, необходимо наличие следующего аппаратного и программного обеспечения:

  - Чистый или новый сервер с таким же полным доменным именем (FQDN), что и сервер, на котором произошел сбой.
    
    <div>
    

    > [!IMPORTANT]  
    > При установке операционной системы убедитесь, что учетная запись компьютера не удалена в доменных службах Active Directory, и убедитесь, что разрешения группы для учетной записи сохранены.

    
    </div>

  - Установка программного обеспечения для операционной системы. Чтобы установить операционную систему, воспользуйтесь процедурами и конфигурациями развертывания сервера, установленными в Организации. При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.

  - Установка программного обеспечения для SQL Server 2012 или SQL Server 2008 R2. Чтобы установить сервер баз данных, используйте соответствующую версию SQL Server, а также процедуры и конфигурации развертывания сервера базы данных, установленные вашей организацией. При восстановлении службы должны быть доступны указанные ниже процедуры и требования к конфигурации.
    
    <div>
    

    > [!NOTE]  
    > Мастер развертывания Lync Server автоматически устанавливает SQL Server 2012 Express на каждом сервере Standard Edition и на любом другом сервере Lync Server при установке локального хранилища конфигурации, если вы не предустановили SQL Server 2012 или SQL Server 2008 R2 на сервере.

    
    </div>

  - Программное обеспечение для принятия образов системы.
    
    <div>
    

    > [!TIP]  
    > Мы рекомендуем использовать копию системы после установки операционной системы и SQL Server, а также до начала восстановления, чтобы использовать это изображение в качестве точки отката в случае, если что-то пойдет не так во время восстановления.

    
    </div>

  - Установка программного обеспечения Lync Server 2013. Мастер развертывания Lync Server находится в папке установки Lync Server или на носителе во время \\ установки \\ amd64 \\Setup.exe.

Во время восстановления используются следующие инструменты:

  - Командлеты командной консоли Lync Server

  - Import-CsUserData

  - Средства для восстановления папок Windows

  - Построитель топологий

  - Служебные программы для баз данных SQL Server, например SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Подготовка к восстановлению сервера

Перед восстановлением сервера необходимо выполнить следующие действия:

1.  Установите операционную систему.

2.  Если сервер является внутренним сервером, установите SQL Server 2012 или SQL Server 2008 R2.

3.  Восстановите или повторно зарегистрируйте сертификаты. Сведения о сертификатах можно найти в статье "дополнительные требования к резервному копированию" в статье [требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Создайте образ системы перед началом восстановления, чтобы использовать его в качестве точки отката, если что-то пойдет не так во время восстановления.

<div>


> [!NOTE]  
> Мастер развертывания Lync Server и командлеты, описанные в процедурах, описанных в этой статье, и связанные темы задают все необходимые списки управления доступом (ACL).



</div>

Прежде чем начать восстановление, убедитесь, что оборудование и программное обеспечение, необходимое для восстанавливаемых компонентов, доступны. После установки операционной системы и сервера SQL Server большинство действий, описанных в следующих процедурах восстановления, могут быть запущены удаленно. Исключения указаны в процедурах.

Кроме того, вы должны иметь план резервного копирования и восстановления вашей организации, а также сведения из последней резервной копии, такие как сведения на листах в этом документе (Дополнительные сведения см. в статье [резервное копирование и восстановление для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), которые доступны до начала восстановления.

</div>

</div>

<span> </span>

</div>

</div>

</div>

