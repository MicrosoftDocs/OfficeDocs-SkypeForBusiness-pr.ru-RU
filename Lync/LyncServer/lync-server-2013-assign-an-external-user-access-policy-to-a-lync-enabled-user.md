---
title: 'Lync Server 2013: назначение политики доступа внешних пользователей пользователю, разрешенному для Lync'
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
ms.openlocfilehash: 523907fbf4bc4cca93be8e529b6b607b43f0ea87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Если для пользователя разрешено использование Lync Server, вы можете настроить федерацию SIP, Федерацию КСМПП, удаленный доступ к данным и обмен мгновенными сообщениями на панели управления Lync Server, применив соответствующие политики для конкретных пользователей. Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю, прежде чем пользователь сможет подключиться к серверу Lync Server из удаленного местоположения и будет работать совместно с внешними пользователями из удаленного местоположения.

<div>


> [!NOTE]  
> Для поддержки внешнего доступа пользователей необходимо включить поддержку для каждого типа внешних пользователей, которые будут поддерживаться, и настроить соответствующие политики и другие параметры для управления его использованием. Подробности можно найти в разделе <A href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки внешних пользователей в Lync server 2013</A> в документации по развертыванию или <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Управление интеграцией и внешним доступом к Lync Server 2013</A> в документации по эксплуатации.



</div>

В этой статье описана процедура применения ранее созданной политики доступа внешних пользователей к одной или нескольким учетным записям пользователей.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Применение политики внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.

4.  В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.

5.  В диалоговом окне **изменение пользователя Lync Server** в разделе " **Политика внешнего доступа**" выберите политику пользователей, которую вы хотите применить.
    
    <div>
    

    > [!NOTE]  
    > Параметры <STRONG> &lt;автоматической&gt; </STRONG> настройки применяются к параметрам сервера или глобальной политики, используемым по умолчанию.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение политик внешнего доступа для каждого пользователя с помощью командлетов Windows PowerShell

Политики внешнего доступа для каждого пользователя можно назначить с помощью Windows PowerShell и командлета Grant-Ксекстерналакцессполици. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа для отдельных пользователей одному пользователю

  - Эта команда назначает политику внешнего доступа для каждого пользователя, Редмондекстерналакцессполици пользователю Кен мер.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа для каждого пользователя нескольким пользователям

  - Эта команда назначает политику внешнего доступа "на пользователя" Усаекстерналакцессполици всем пользователям, у которых есть учетные записи в подразделении "США" в Active Directory. Дополнительные сведения о параметре OU, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Отмена назначения политики внешнего доступа для каждого пользователя

  - Эта команда отменяет назначение любой пользовательской политики внешнего доступа, ранее назначенной для Кен мер. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Дополнительные сведения можно найти в разделе справки о командлете [Grant-ксекстерналакцессполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

