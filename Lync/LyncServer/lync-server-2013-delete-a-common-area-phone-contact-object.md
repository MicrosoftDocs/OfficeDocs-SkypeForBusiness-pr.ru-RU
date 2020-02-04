---
title: 'Lync Server 2013: удаление объекта контактного телефона для общего города'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="fdeb5-102">Удаление объекта контактного телефона из общей области в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdeb5-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdeb5-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fdeb5-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fdeb5-104">Возможно, вы захотите удалить объект контакта, связанный с телефонами с общим диапазоном.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="fdeb5-105">Например, если вы удалите телефон из вашего сотрудника, нет необходимости иметь объект контакта, связанный с этим телефоном.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="fdeb5-106">Командлет **Remove-кскоммонареафоне** позволяет удалить общие учетные записи для телефонной области.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="fdeb5-107">При запуске этого командлета телефон удаляется из списка распространенных телефонов, возвращенных функцией **Get-кскоммонареафоне**.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="fdeb5-108">Кроме того, объект контакта, связанный с этим телефоном, удаляется из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="fdeb5-109">С помощью **Remove-кскоммонареафоне** можно удалить один или несколько стандартных телефонов, которые содержат общий элемент, например отображаемое имя или код страны и города.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="fdeb5-110">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fdeb5-111">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdeb5-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="fdeb5-112">Удаление указанного телефонного телефона с общим регионом</span><span class="sxs-lookup"><span data-stu-id="fdeb5-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="fdeb5-113">Следующая команда удаляет стандартную телефонную область с адресом SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="fdeb5-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="fdeb5-114">Удаление общих телефонов с областями на основе их отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="fdeb5-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="fdeb5-115">Эта команда удаляет все общие телефоны, в которых отображаемое имя содержит строковое значение "здание 14".</span><span class="sxs-lookup"><span data-stu-id="fdeb5-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="fdeb5-116">Удаление общих телефонов с областями на основе кодов стран и городов</span><span class="sxs-lookup"><span data-stu-id="fdeb5-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="fdeb5-117">Эта команда удаляет все обычные телефоны для США (код страны 1) и код города 425:</span><span class="sxs-lookup"><span data-stu-id="fdeb5-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="fdeb5-118">Дополнительные сведения можно найти в разделе справки по командлету [Remove-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="fdeb5-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fdeb5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fdeb5-119">See Also</span></span>


[<span data-ttu-id="fdeb5-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="fdeb5-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

