---
title: 'Lync Server 2013: Update-Ксаддрессбук для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22923d0227c75ee6f2055d4a2ac350a6df6b37bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-Ксаддрессбук для управления адресными книгами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Update-Ксаддрессбук локально: Рткуниверсалусерадминс, Рткуниверсалсерверадминс. Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Командлет Update-Ксаддрессбук заменяет команду **абсервер. exe – синкнов** в Office Communications Server. Цель командлета состоит в том, чтобы начать синхронизацию немедленно, вместо того чтобы ждать запланированного времени. Первый пример команды обновляет все адресные книги в Организации. Вторая обновляет только адресную книгу, связанную с определенным сервером.

<div>


> [!NOTE]  
> В Lync Server 2013 служба репликатора пользователей Lync Server выберет изменения из Active Directory и обновит базу данных пользователей Lync Server на основе заданного интервала. Служба репликации пользователей Lync Server также будет автоматически распространять изменения базы данных Рткаб, не требуя администратора запускать Update-Ксаддрессбук. Администраторам потребуется выполнить Update-Ксаддрессбук только в том случае, если разрешена загрузка файла адресной книги.



</div>

Например:

   ```
    Update-CsAddressBook
   ```

   ```
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>См. также


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

