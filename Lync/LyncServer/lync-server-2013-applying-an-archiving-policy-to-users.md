---
title: 'Lync Server 2013: применение политики архивации к пользователям'
description: 'Lync Server 2013: применение политики архивации к пользователям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544975"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Применение политики архивации к пользователям в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Если для пользователя включена поддержка Lync Server 2013 и вы создали одну или несколько политик пользователей для архивации для пользователей, размещенных на Lync Server 2013, вы можете реализовать поддержку архивации для определенных пользователей, применив соответствующие политики к этим пользователям или группам пользователей. Например, если вы создаете политику для поддержки архивации внутренних коммуникаций, вы можете применить ее по крайней мере к одному пользователю или группе пользователей, чтобы обеспечить поддержку архивации связи Lync Server 2013 для пользователей.

<div>


> [!NOTE]  
> Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включено ли архивирование для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации. Дополнительные сведения: <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</A> в документации по операциям.



</div>

Используйте процедуру в этом разделе, чтобы применить ранее созданную политику архивации пользователя к одной или нескольким учетным записям пользователей или группам пользователей.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Применение пользовательской политики архивации к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  В разделе **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую нужно применить.
    
    <div>
    

    > [!NOTE]  
    > Параметры <STRONG> &lt; автоматического &gt; </STRONG> применения применяют параметры установки сервера по умолчанию. Данный параметр автоматически применяется сервером.

    
    </div>

6.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Назначение политики архивации Per-User с помощью командлетов Windows PowerShell

Политики архивации на уровне пользователей можно назначить с помощью Windows PowerShell и командлета **Grant – CsArchivingPolicy** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Назначение политики архивации на уровне пользователя одному пользователю

  - Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Назначение политики архивации на уровне пользователей нескольким пользователям

  - Эта команда назначает политику архивации на уровне пользователя RedmondArchivingPolicy всем пользователям, чьи учетные записи размещены в пуле регистраторов atl-cs-001.litwareinc.com. Для получения дополнительных сведений о параметре Filter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Назначение политики архивации на уровне пользователя

  - Следующей командой отменяется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей отменена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Дополнительные сведения см. в документации по командлету [Grant – CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>См. также


[Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Назначение политик для отдельных пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

