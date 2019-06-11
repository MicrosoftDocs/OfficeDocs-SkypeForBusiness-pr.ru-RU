---
title: 'Lync Server 2013: создание или изменение объекта контакта общего телефонного модуля'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1345477178d7991083332e809de3f764be4c3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="cce8b-102">Создание или изменение объекта контактного телефона для общего города в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cce8b-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cce8b-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cce8b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cce8b-104">Чтобы создать объекты-контакты доменных служб Active Directory для всех распространенных телефонов с областями, используйте командлет **New-кскоммонареафоне** .</span><span class="sxs-lookup"><span data-stu-id="cce8b-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="cce8b-105">Этот командлет может создавать новые объекты контактов для использования с телефонами с общим заполнением, а также связывать существующие объекты контактов с новым стандартным телефоном.</span><span class="sxs-lookup"><span data-stu-id="cce8b-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="cce8b-106">Чтобы изменить свойства объектов контакта, связанных с телефонами с общими областями, используйте командлет **Set-кскоммонареафоне** .</span><span class="sxs-lookup"><span data-stu-id="cce8b-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="cce8b-107">Необязательные параметры для **Set-кскоммонареафоне** позволяют изменять такие элементы, как отображаемое имя или универсальный код ресурса (URI) для контакта, а также включать и отключать учетную запись для использования в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cce8b-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="cce8b-108">Сведения обо всех доступных изменениях можно найти в разделе "Параметры" на странице [Set-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="cce8b-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="cce8b-109">Подробные сведения о **новых параметрах-кскоммонареафоне** можно найти в статьях [New-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="cce8b-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="cce8b-110">Эти два командлета можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cce8b-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cce8b-111">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cce8b-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="cce8b-112">Создание объекта контакта общего телефонного модуля</span><span class="sxs-lookup"><span data-stu-id="cce8b-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="cce8b-113">Чтобы создать новый объект контакта с общим объемом на телефоне, используйте командлет **New-кскоммонареафоне** .</span><span class="sxs-lookup"><span data-stu-id="cce8b-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="cce8b-114">Как минимум, при создании объекта контакта необходимо указать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cce8b-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="cce8b-115">**Линеури**: номер телефона, назначенный стандарту для телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="cce8b-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="cce8b-116">Обратите внимание, что при указании номера телефона необходимо использовать формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="cce8b-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="cce8b-117">**Регистрарпул**: полное доменное имя (FQDN) пула регистраторов, на котором будет размещен объект-контакт.</span><span class="sxs-lookup"><span data-stu-id="cce8b-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="cce8b-118">**OU**: различающееся имя контейнера Active Directory, в котором будет создан объект контакта.</span><span class="sxs-lookup"><span data-stu-id="cce8b-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="cce8b-119">Кроме того, мы рекомендуем предоставить отображаемое имя доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cce8b-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="cce8b-120">В противном случае вы должны использовать GUID для указания идентификатора телефона.</span><span class="sxs-lookup"><span data-stu-id="cce8b-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="cce8b-121">Например:</span><span class="sxs-lookup"><span data-stu-id="cce8b-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="cce8b-122">Изменение объекта контакта общего телефонного модуля</span><span class="sxs-lookup"><span data-stu-id="cce8b-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="cce8b-123">Чтобы изменить свойства существующего телефонного телефона, свяжитесь с помощью командлета **Set-кскоммонареафоне** .</span><span class="sxs-lookup"><span data-stu-id="cce8b-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="cce8b-124">Например, эта команда конфигурирует адрес SIP для общего телефона с отображаемым именем DisplayName.</span><span class="sxs-lookup"><span data-stu-id="cce8b-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="cce8b-125">Подробные сведения можно найти в разделах справки по командлетам [New-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) и командлету [Set-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="cce8b-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

