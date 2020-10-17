---
title: 'Lync Server 2013: Настройка параметров парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72d3f60747f9b3456a6999358b0cf318b5e6d91d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521166"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="61730-102">Настройка параметров парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61730-102">Configure Call Park settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61730-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="61730-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="61730-104">Если вы не хотите использовать параметры парковки вызовов по умолчанию, их можно настроить.</span><span class="sxs-lookup"><span data-stu-id="61730-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="61730-105">При установке приложения парковки вызовов глобальные параметры настраиваются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61730-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="61730-106">Вы можете изменять глобальные параметры, а также задавать параметры для конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="61730-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="61730-107">Используйте командлет **New-CsCpsConfiguration** для создания новых параметров, связанных с сайтом.</span><span class="sxs-lookup"><span data-stu-id="61730-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="61730-108">Используйте командлет **Set – CsCpsConfiguration** для изменения существующих параметров.</span><span class="sxs-lookup"><span data-stu-id="61730-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61730-109">Мы рекомендуем вам настроить хотя бы параметр <STRONG>OnTimeoutURI</STRONG> для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61730-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="61730-110">Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:</span><span class="sxs-lookup"><span data-stu-id="61730-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61730-111">Данный параметр:</span><span class="sxs-lookup"><span data-stu-id="61730-111">This option:</span></span></th>
<th><span data-ttu-id="61730-112">Указывает следующее:</span><span class="sxs-lookup"><span data-stu-id="61730-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61730-113"><strong>каллпиккуптимеаутсрешолд</strong></span><span class="sxs-lookup"><span data-stu-id="61730-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="61730-114">Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.</span><span class="sxs-lookup"><span data-stu-id="61730-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="61730-p102">Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="61730-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-118"><strong>енаблемусиконхолд</strong></span><span class="sxs-lookup"><span data-stu-id="61730-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="61730-119">Воспроизводится ли музыка для звонящего при парковке вызова.</span><span class="sxs-lookup"><span data-stu-id="61730-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="61730-p103">Доступны значения True и False. Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="61730-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-122"><strong>макскаллпиккупаттемптс</strong></span><span class="sxs-lookup"><span data-stu-id="61730-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="61730-p104">Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для <strong>OnTimeoutURI</strong>. Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="61730-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="61730-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="61730-126">SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения <strong>MaxCallPickupAttempts</strong>.</span><span class="sxs-lookup"><span data-stu-id="61730-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="61730-p105">Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.</span><span class="sxs-lookup"><span data-stu-id="61730-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="61730-130">Настройка параметров парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="61730-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="61730-131">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="61730-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="61730-132">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="61730-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="61730-133">Выполняем</span><span class="sxs-lookup"><span data-stu-id="61730-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="61730-134">Используйте командлет <STRONG>Get-CsSite</STRONG> для идентификации сайта.</span><span class="sxs-lookup"><span data-stu-id="61730-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="61730-135">Дополнительные сведения см. в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61730-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="61730-136">Например:</span><span class="sxs-lookup"><span data-stu-id="61730-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61730-137">См. также</span><span class="sxs-lookup"><span data-stu-id="61730-137">See Also</span></span>


[<span data-ttu-id="61730-138">Настройка музыки парковки вызовов на удержании в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61730-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="61730-139">New — CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="61730-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="61730-140">Set — CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="61730-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="61730-141">Get — CsSite</span><span class="sxs-lookup"><span data-stu-id="61730-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

