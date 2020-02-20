---
title: 'Lync Server 2013: удаление объекта контактного телефона общего пользования'
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
ms.openlocfilehash: c77d9c220502abbd4275af337142927786be9be3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="d07cd-102">Удаление объекта контактного телефона общего пользования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d07cd-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d07cd-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d07cd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d07cd-104">Возможно, вы захотите удалить объект Contact, связанный с телефоном на общем участке.</span><span class="sxs-lookup"><span data-stu-id="d07cd-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="d07cd-105">Например, если удалить телефон из неактивного сотрудника, нет необходимости иметь объект Contact, связанный с этим телефоном.</span><span class="sxs-lookup"><span data-stu-id="d07cd-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="d07cd-106">Командлет **Remove – CsCommonAreaPhone** позволяет удалять общие учетные записи телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d07cd-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="d07cd-107">При выполнении этого командлета в списке общедоступных телефонов, возвращенных командлетом **Get-CsCommonAreaPhone**, удаляется телефон.</span><span class="sxs-lookup"><span data-stu-id="d07cd-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="d07cd-108">Кроме того, объект Contact, связанный с этим телефоном, удаляется из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d07cd-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="d07cd-109">Используйте **Remove – CsCommonAreaPhone** , чтобы удалить один общий телефон или все общие телефоны, имеющие общий элемент, такие как отображаемое имя или код страны и города.</span><span class="sxs-lookup"><span data-stu-id="d07cd-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="d07cd-110">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07cd-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d07cd-111">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="d07cd-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="d07cd-112">Удаление указанного телефона на общем участке</span><span class="sxs-lookup"><span data-stu-id="d07cd-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="d07cd-113">Следующая команда удаляет телефон общей области с адресом SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d07cd-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="d07cd-114">Удаление общих телефонов на основе отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="d07cd-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="d07cd-115">Эта команда удаляет все общие телефоны, для которых отображаемое имя содержит строковое значение "Построение 14":</span><span class="sxs-lookup"><span data-stu-id="d07cd-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="d07cd-116">Удаление телефонной области на основе кодов их стран и областей</span><span class="sxs-lookup"><span data-stu-id="d07cd-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="d07cd-117">Эта команда удаляет все общие телефоны для США (код страны 1) и код города 425:</span><span class="sxs-lookup"><span data-stu-id="d07cd-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="d07cd-118">Дополнительные сведения см. в разделе справки для командлета [Remove – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="d07cd-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d07cd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d07cd-119">See Also</span></span>


[<span data-ttu-id="d07cd-120">Get — CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="d07cd-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

