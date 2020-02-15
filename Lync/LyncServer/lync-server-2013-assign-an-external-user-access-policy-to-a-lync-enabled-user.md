---
title: 'Lync Server 2013: назначение политики доступа внешних пользователей пользователю с включенной поддержкой Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b578028b7e5d68d902557fddeb9dd5e2a61a9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Если для пользователя включена поддержка Lync Server, вы можете настроить федерацию SIP, Федерацию XMPP, удаленный доступ пользователей и подключение к общедоступным обменам мгновенными сообщениями на панели управления Lync Server, применив соответствующие политики к определенным пользователям. Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю до того, как пользователь сможет подключиться к Lync Server из удаленного расположения и совместно работать с внутренними пользователями из удаленного расположения.

<div>


> [!NOTE]  
> Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии. Дополнительные сведения: <A href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки доступа внешних пользователей в Lync server 2013</A> в документации по развертыванию или <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">управлении Федерации и внешним доступом к Lync Server 2013</A> в документации по операциям.



</div>

Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Применение политики доступа внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.

5.  В окне **Изменение пользователя Lync Server** в разделе **Политика внешнего доступа** выберите политику доступа внешних пользователей, которую нужно применить.
    
    <div>
    

    > [!NOTE]  
    > Параметры <STRONG> &lt;автоматического&gt; </STRONG> применения применяют параметры сервера по умолчанию или глобальные параметры политики.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение политик внешнего доступа для отдельных пользователей с помощью командлетов Windows PowerShell

Политики внешнего доступа на уровне пользователей можно назначить с помощью Windows PowerShell и командлета Grant – CsExternalAccessPolicy. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа на уровне пользователя одному пользователю

  - Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа на уровне пользователей нескольким пользователям

  - Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory. Для получения дополнительных сведений о параметре OU, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Отмена назначения политики внешнего доступа на уровне пользователя

  - Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

