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
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Подготовка к восстановлению Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Прежде чем приступить к восстановлению серверов и баз данных после сбоя, необходимо определить указанные ниже действия.

  - Что необходимо восстановить.

  - Оборудование, программное обеспечение, данные и инструменты, необходимые для восстановления.

<div>

## <a name="determining-what-to-restore"></a>Определение содержимого для восстановления

В этой статье описано, как восстановить сбои сервера Lync Server, происходящие на уровне сервера, пула или центра управления. Если центральное хранилище Management завершается сбоем, развертывание Lync Server продолжает работать, но вы не можете вносить какие – либо изменения в конфигурацию. В случае сбоя сервера или сервера Standard Edition пул пользователей перестает работать. Если какой – либо другой сервер завершается сбоем, значение этого параметра зависит от роли сервера, на котором запущен сервер, и от того, содержит ли сервер одну или несколько баз данных.

### <a name="what-to-restore"></a>Что нужно восстановить

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Если это не удалось</th>
<th>Ознакомьтесь с разделом:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Восстановление сервера Standard Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>управления</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Восстановление сервера, на котором размещается центральное хранилище для управления в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Серверная версия Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление сервера выпуска Enterprise Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Зеркальный сервер основного выпуска Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013-PRIMARY</a></p></td>
</tr>
<tr class="odd">
<td><p>Дополнительный сервер зеркального отображения для выпуска Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013 — зеркало</a></p></td>
</tr>
<tr class="even">
<td><p>Любой сервер Enterprise Edition, на котором работает серверная роль, например сервер переднего плана, пограничный сервер, режиссер, сервер-посредник или сохраняемый сервер чата.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление сервера участника Enterprise Edition в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Пул всего сервера Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Восстановление пула сервера Lync Server в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Корпоративное хранилище файлов в выпуске</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Восстановление хранилища файлов в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Автономная база данных мониторинга или архивная база данных</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Восстановление данных мониторинга или архивации в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Отдельная база данных сохраняемого чата</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Восстановление данных из сохраняемого чата в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Сбор сведений о оборудовании, программном обеспечении и инструментах

При восстановлении сервера необходимо начать с нового или чистого компьютера. Кроме того, на компьютере должно быть доступно следующее оборудование и программное обеспечение:

  - Пустой или новый сервер с таким же полным доменным именем (FQDN), как и у сервера, на котором произошел сбой.
    
    <div>
    

    > [!IMPORTANT]  
    > При установке операционной системы убедитесь в том, что вы не удаляете учетную запись компьютера в доменных службах Active Directory и убедитесь в том, что разрешения группы для учетной записи сохранены.

    
    </div>

  - Установка программного обеспечения для операционной системы. Для установки операционной системы используйте процедуры развертывания сервера и конфигурации, установленные вашей организацией. При восстановлении службы вам должны быть доступны указанные ниже процедуры и требования к конфигурации.

  - Установка программного обеспечения SQL Server 2012 или SQL Server 2008 R2. Чтобы установить сервер базы данных, используйте соответствующую версию SQL Server, а также процедуры и конфигурации сервера базы данных, установленные вашей организацией. При восстановлении службы вам должны быть доступны указанные ниже процедуры и требования к конфигурации.
    
    <div>
    

    > [!NOTE]  
    > Мастер развертывания Lync Server автоматически устанавливает SQL Server 2012 Express на сервер Standard Edition и на любой другой сервер Lync Server при установке локального хранилища конфигураций, если только вы не предустановили SQL Server 2012 или SQL Server 2008 R2 для сервер.

    
    </div>

  - Программное обеспечение для принятия изображений системы.
    
    <div>
    

    > [!TIP]  
    > Мы рекомендуем использовать копию системы после установки операционной системы и сервера SQL Server, а также перед началом восстановления для использования этого образа в качестве точки отката в случае, если что-то пошло не так во время восстановления.

    
    </div>

  - Установка программного обеспечения Lync Server 2013. Мастер развертывания Lync Server находится в папке установки Lync Server или мультимедиа в \\файле Setup. exe\\программы\\установки amd64.

Во время восстановления вы используете следующие инструменты:

  - Командлеты оболочки Lync Server Management Shell

  - Import-CsUserData

  - Средства для восстановления папок Windows

  - топологий

  - Служебные программы для работы с базами данных SQL Server, например SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Подготовка к восстановлению сервера

Прежде чем восстанавливать сервер, необходимо выполнить следующие действия:

1.  Установите операционную систему.

2.  Если сервер является конечным сервером, установите SQL Server 2012 или SQL Server 2008 R2.

3.  Восстановите и порегистрируйте сертификаты. Подробнее о сертификатах можно узнать в статье "дополнительные требования к резервному копированию" в статье [требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Сделайте снимок системы перед началом восстановления, чтобы использовать его в качестве точки отката, если что-то пойдет не так во время восстановления.

<div>


> [!NOTE]  
> Мастер развертывания Lync Server и командлеты, описанные в описанных в этой статье процедурах, и связанные разделы, задают все необходимые списки управления доступом (ACL).



</div>

Перед началом восстановления убедитесь в том, что оборудование и программное обеспечение, необходимое для восстановления необходимых компонентов, доступны. После установки операционной системы и сервера SQL Server можно выполнить удаленное выполнение практических действий, описанных в описанных ниже процедурах восстановления. Исключения указаны в процедурах.

Кроме того, вы должны иметь план резервного копирования и восстановления своей организации, а также данные из последней резервной копии, такие как данные на листах в этом документе (Дополнительные сведения можно найти в разделе [листы резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), которые доступны перед началом восстановления.

</div>

</div>

<span> </span>

</div>

</div>

</div>

