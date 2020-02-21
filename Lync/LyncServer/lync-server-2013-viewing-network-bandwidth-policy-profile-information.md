---
title: 'Lync Server 2013: Просмотр сведений о профиле политики пропускной способности сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ecfb3e43a817a190e3bee1199164b1eaf0c51e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Просмотр сведений о профиле политики пропускной способности сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей. В Microsoft Lync Server 2013 ограничения пропускной способности могут быть назначены только для модальности аудио и видео. Вы можете задать общие ограничения и ограничения сеанса. Вы можете использовать панель управления Lync Server для создания, изменения или удаления профиля контейнера для этих политик. Каждый профиль политики полосы пропускания можно связать с одним или несколькими сетевыми узлами. Используйте следующие процедуры для просмотра профиля политики полосы пропускания . Чтобы создать или изменить профиль политики пропускной способности, ознакомьтесь со статьей [Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Просмотр профиля политики пропускной способности

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Политика полосы пропускания **.

4.  На странице **политика пропускной способности** щелкните профиль политики пропускной способности, который требуется просмотреть.

5.  В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о профиле политики пропускной способности сети с помощью командлетов Windows PowerShell

Профили пропускной способности сети можно просматривать с помощью Windows PowerShell и командлета Get – CsNetworkBandwidthPolicyProfile. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Просмотр сведений о профиле политики пропускной способности сети

  - Чтобы просмотреть сведения обо всех профилях политики пропускной способности сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Дополнительные сведения см. в разделе справки о командлете [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Удаление профилей политики пропускной способности сети в Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Настройка контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

