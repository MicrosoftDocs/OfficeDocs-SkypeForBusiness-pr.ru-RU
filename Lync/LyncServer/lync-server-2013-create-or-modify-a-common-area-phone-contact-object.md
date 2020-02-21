---
title: 'Lync Server 2013: создание или изменение объекта контактного телефона общего пользования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d2eb58df1e5c83f23fdb1d31ba73b408d107a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="002ca-102">Создание или изменение объекта контактного телефона общего пользования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="002ca-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="002ca-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="002ca-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="002ca-104">Чтобы создать объекты контактов доменных служб Active Directory для всех телефонов общедоступных телефонов, используйте командлет **New – CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="002ca-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="002ca-105">Этот командлет может создавать новые объекты контактов для использования с телефонными телефонами, а также связывать существующие объекты контактов с новым общим телефоном.</span><span class="sxs-lookup"><span data-stu-id="002ca-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="002ca-106">Чтобы изменить свойства контактных объектов, связанных с телефонами на общих участках, используйте командлет **Set – CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="002ca-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="002ca-107">Необязательные параметры для **Set-CsCommonAreaPhone** позволяют изменять такие элементы, как отображаемое имя контакта Active Directory или универсальный код ресурса (URI), связанный с телефоном, а также включать и отключать учетную запись для использования с сервером Lync Server.</span><span class="sxs-lookup"><span data-stu-id="002ca-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="002ca-108">Подробные сведения обо всех доступных изменениях можно найти в разделе Parameters (параметры [) на странице Set — CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="002ca-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="002ca-109">Дополнительные сведения о параметрах **New – CsCommonAreaPhone** можно найти в статье [New — CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="002ca-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="002ca-110">Эти два командлета можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="002ca-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="002ca-111">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="002ca-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="002ca-112">Создание объекта контактного телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="002ca-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="002ca-113">Чтобы создать новый объект контактного телефона для общей области, используйте командлет **New – CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="002ca-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="002ca-114">Как минимум, при создании объекта Contact необходимо указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="002ca-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="002ca-115">**LineUri**: номер телефона, назначенный телефону общей области.</span><span class="sxs-lookup"><span data-stu-id="002ca-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="002ca-116">Обратите внимание, что при указании номера телефона необходимо использовать формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="002ca-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="002ca-117">**RegistrarPool**: полное доменное имя (FQDN) пула регистратора, в котором будет размещаться объект Contact.</span><span class="sxs-lookup"><span data-stu-id="002ca-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="002ca-118">**OU**: различающееся имя контейнера Active Directory, в котором будет создан объект Contact.</span><span class="sxs-lookup"><span data-stu-id="002ca-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="002ca-119">Мы также рекомендуем указать отображаемое имя доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="002ca-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="002ca-120">В противном случае для указания удостоверения телефона необходимо использовать GUID.</span><span class="sxs-lookup"><span data-stu-id="002ca-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="002ca-121">Например:</span><span class="sxs-lookup"><span data-stu-id="002ca-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="002ca-122">Изменение объекта контактного телефона для общей области</span><span class="sxs-lookup"><span data-stu-id="002ca-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="002ca-123">Чтобы изменить свойства существующего телефона, обратитесь к объекту Contact с помощью командлета **Set – CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="002ca-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="002ca-124">Например, эта команда настраивает SIP адрес для телефона общего пользования с отображаемым именем DisplayName:</span><span class="sxs-lookup"><span data-stu-id="002ca-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="002ca-125">Дополнительные сведения можно найти в разделах справки для командлета [New – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) и командлета [Set – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="002ca-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

