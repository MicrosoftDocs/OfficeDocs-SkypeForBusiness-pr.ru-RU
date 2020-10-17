---
title: 'Lync Server 2013: Update-CsAddressBook для управления адресной книгой'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdbef7a3826a734262a77aa39fb2ce32e547463
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527706"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook для управления адресной книгой в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Update-CsAddressBook — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Командлет Update-CsAddressBook заменяет собой команду **abserver.exe –syncNow** из Office Communications Server. Задача этого командлета — запустить синхронизацию немедленно, не ожидая запланированного времени. Первый пример команды обновляет все адресные книги в организации. Второй пример обновляет только адресную книгу, сопоставленную с заданным сервером.

<div>


> [!NOTE]  
> В Lync Server 2013 служба репликации пользователей Lync Server выберет изменения из Active Directory и обновляет базу данных пользователей Lync Server в соответствии с заданным интервалом. Служба Replicator пользователей Lync Server также будет быстро распространять изменения базы данных RTCab, не требуя от администратора выполнять командлет Update – CSAddressBook. Администраторы должны будут запустить Update -CSAddressBook только в случае, когда включена загрузка файла адресной книги.



</div>

Например:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>См. также


[Update — CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

