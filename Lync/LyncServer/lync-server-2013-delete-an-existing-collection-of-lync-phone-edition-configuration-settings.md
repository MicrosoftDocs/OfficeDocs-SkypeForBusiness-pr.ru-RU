---
title: Удаление существующей коллекции параметров конфигурации Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Если вы больше не хотите использовать набор параметров для устройств с Lync Phone Edition, удалите его. Если вы удалите коллекцию для сайта, глобальные параметры будут применяться к телефонам на этом сайте. Вы не можете удалить глобальную коллекцию.

<div>


> [!NOTE]
> Вместо удаления коллекции может потребоваться изменить некоторые параметры. Сведения о том, как это сделать, можно найти <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">в статье Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Удаление коллекции параметров конфигурации Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Настройки устройств**.

4.  На странице " **Конфигурация устройства** " щелкните удаляемую коллекцию, а затем выберите команду **Удалить**в меню **Правка** .
    
    <div>
    

    > [!NOTE]
    > Если вы удаляете глобальную коллекцию, параметры просто возвращаются к параметрам по умолчанию. Коллекция не отключается.

    
    </div>

5.  В окне подтверждения нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell

Параметры конфигурации Lync Phone Edition можно удалить с помощью Windows PowerShell и командлета **Remove – ксукконфигуратион** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Удаление указанной коллекции параметров конфигурации Lync Phone Edition

  - Эта команда удаляет параметры конфигурации телефона UC, применяемые к сайту Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации Lync Phone Edition, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации телефона UC, применяемые к области службы:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Удаление всех параметров конфигурации Lync Phone Edition, в которых отключена Блокировка телефона

  - Эта команда удаляет любую коллекцию параметров конфигурации телефона UC, в которых отключена Блокировка телефона:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Дополнительные сведения см. в разделе [Remove – CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

