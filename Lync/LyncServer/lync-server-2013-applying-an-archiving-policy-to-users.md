---
title: 'Lync Server 2013: применение политики архивации к пользователям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Применение политики архивации к пользователям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Если пользователь включил приложение Lync Server 2013 и вы создали одну или несколько политик пользователей для архивации пользователей, размещенных на Lync Server 2013, вы можете реализовать поддержку архивации для определенных пользователей, применяя соответствующие политики к этим пользователям или группам пользователей. Например, если вы создаете политику для поддержки архивации внутренних данных, вы можете применить ее по крайней мере к одному пользователю или группе пользователей, чтобы обеспечить поддержку архивации данных пользователей Lync Server 2013.

<div>


> [!NOTE]  
> Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте. Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации. Дополнительные сведения можно найти в разделе <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайты и пулы</A> в документации по эксплуатации.



</div>

В этой статье описана процедура применения ранее созданной политики архивации пользователей к одной или нескольким учетным записям пользователей или группам пользователей.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Применение политики архивации пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить.

4.  В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.

5.  В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую вы хотите применить.
    
    <div>
    

    > [!NOTE]  
    > Для <STRONG> &lt;параметров&gt; автоматической</STRONG> настройки применяются параметры установки сервера по умолчанию. Данные параметры автоматически применяются сервером.

    
    </div>

6.  Нажмите **Исполнить**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Назначение политики архивации для пользователей с помощью командлетов Windows PowerShell

Политики архивации на пользователя можно назначить с помощью Windows PowerShell и командлетом **Grant-ксарчивингполици** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Назначение политики архивации отдельных пользователей для одного пользователя

  - Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Назначение политики архивации на пользователя для нескольких пользователей

  - Эта команда назначает политику архивации пользователей Редмондарчивингполици всем пользователям, у которых есть учетные записи, размещенные на atl-cs-001.litwareinc.com пула регистраторов. Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Назначение политики архивации на пользователя

  - Следующая команда отменяет назначение каждой политики архивации пользователей, ранее назначенной для Кен мер. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Дополнительные сведения можно найти в документации по командлету [Grant-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>См. также


[Управление архивированием внутренней и внешней связи в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Назначение политик для пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

