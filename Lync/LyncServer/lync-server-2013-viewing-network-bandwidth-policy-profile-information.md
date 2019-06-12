---
title: 'Lync Server 2013: Просмотр данных профиля политики пропускной способности сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Просмотр данных профиля политики пропускной способности сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности. В Microsoft Lync Server 2013 можно назначать ограничения пропускной способности только для модальностей аудио и видео. Вы можете настроить общие ограничения пропускной способности и ограничения сеанса. С помощью панели управления Lync Server вы можете создавать, изменять и удалять профили контейнеров для этих политик. Каждый профиль политики пропускной способности может быть связан с одним или несколькими сетевыми сайтами. Чтобы просмотреть профиль политики пропускной способности, выполните указанные ниже действия. Чтобы создать или изменить профиль политики пропускной способности, ознакомьтесь с разразделами [Создание и изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Просмотр профиля политики пропускной способности

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **политика пропускной способности**.

4.  На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите просмотреть.

5.  В меню **Правка** щелкните **Подробнее**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Просмотр данных профиля политики пропускной способности сети с помощью командлетов Windows PowerShell

Профили пропускной способности сети можно просматривать с помощью Windows PowerShell и командлета Get-Кснетворкбандвидсполиципрофиле. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Просмотр данных профиля политики пропускной способности сети

  - Чтобы просмотреть сведения о профиле политики пропускной способности сети, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Команда возвращает примерно следующую информацию:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворкбандвидсполиципрофиле](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Удаление профилей политики пропускной способности сети в Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Настройка управления допуском звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

