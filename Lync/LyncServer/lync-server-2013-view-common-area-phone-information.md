---
title: 'Lync Server 2013: Просмотр сведений о телефонах общей области'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b3fbf748569e12e0801f727ecfc0ad6372f4af2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="1b3ba-102">Просмотр сведений о телефонах общей области в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b3ba-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b3ba-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1b3ba-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1b3ba-104">Вы можете просмотреть сведения о телефонах, настроенных для использования в Организации, с помощью командлета **Get – CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="1b3ba-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="1b3ba-105">При использовании без параметров этот командлет возвращает сведения обо всех телефонах, используемых в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="1b3ba-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="1b3ba-106">Необязательные параметры предоставляют различные способы фильтрации информации.</span><span class="sxs-lookup"><span data-stu-id="1b3ba-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="1b3ba-107">Например, вы можете вернуть все телефонные телефоны с контактами в указанном подразделении или всех объектах Contacts, расположенных в указанном здании.</span><span class="sxs-lookup"><span data-stu-id="1b3ba-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="1b3ba-108">Дополнительные сведения о параметрах **Get – CsCommonAreaPhone** можно найти в статье [Get – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="1b3ba-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="1b3ba-109">Выполните командлет **Get – CsCommonAreaPhone** либо в командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b3ba-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="1b3ba-110">Просмотр сведений обо всех телефонах на общем участке</span><span class="sxs-lookup"><span data-stu-id="1b3ba-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="1b3ba-111">Чтобы просмотреть сведения обо всех телефонах вашей сети, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="1b3ba-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="1b3ba-112">Вы получите сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="1b3ba-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="1b3ba-113">Дополнительные сведения см. в разделе справки по командлету [Get – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="1b3ba-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

