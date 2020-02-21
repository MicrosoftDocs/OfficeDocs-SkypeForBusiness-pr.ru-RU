---
title: 'Lync Server 2013: Управление объектами контактов размещенного сервера Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="b8dbf-102">Управление объектом контакта размещенного сервера Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8dbf-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8dbf-103">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="b8dbf-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="b8dbf-104">Необходимо настроить контактный объект для каждого номера автосекретаря и кода доступа в распределенном развертывании.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="b8dbf-105">Для интеграции с размещенной единой системой обмена сообщениями Exchange ocsumutil.exe не может использоваться для управления контактными объектами, поскольку оно зависит от параметров единой системы обмена сообщениями Exchange в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="b8dbf-106">В распределенном развертывании Lync Server 2013 и размещенная единая служба обмена сообщениями Exchange устанавливаются в отдельных лесах без доверия между ними.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="b8dbf-107">Из соображений безопасности Lync Server 2013 администраторы не имеют прямого доступа к параметрам Active Directory единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="b8dbf-108">В результате Lync Server 2013 предоставляет другую модель для управления контактными объектами в *общем адресном пространстве SIP* , доступном как в Lync Server 2013, так и в размещенной службе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="b8dbf-109">Рабочий процесс размещенных контактных объектов</span><span class="sxs-lookup"><span data-stu-id="b8dbf-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="b8dbf-110">Далее приводятся общие действия для совместной работы с администратором клиента размещенного Exchange по управлению контактными объектами.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="b8dbf-111">Администратор Exchange запрашивает телефонные номера для доступа абонентов единой системы обмена сообщениями Exchange и контактные объекты автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="b8dbf-112">Администратор Lync Server 2013 создает объект Contact для каждого номера телефона и назначает политику размещенной голосовой почты каждому объекту контакта.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="b8dbf-113">Администратор Lync Server 2013 предоставляет номера телефонов администратору Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="b8dbf-114">Администратор Exchange назначает эти телефонные номера соответствующим абонентским группам единой системы обмена сообщениями Exchange для автосекретарей и абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8dbf-115">Нет необходимости настраивать параметры абонентской группы Lync Server 2013 для объектов Contact, как и в случае с локальными развертываниями.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="b8dbf-116">Настройка размещенных контактных объектов</span><span class="sxs-lookup"><span data-stu-id="b8dbf-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8dbf-117">Перед тем как можно будет включить поддержку объектов контактов для размещенной единой системы обмена сообщениями Exchange Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="b8dbf-118">Эта политика может быть задана на глобальном уровне, на уровне сайта или на уровне пользователя, если она применяется к контактному объекту, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="b8dbf-119">Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b8dbf-120">Для настройки размещенных контактных объектов автосекретаря и абонентского доступа в распределенном развертывании необходимо использовать следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="b8dbf-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="b8dbf-121">**New-CsExUmContact**, который создает новый контактный объект для размещенной единой системы обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="b8dbf-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="b8dbf-122">**Set-CsExUmContact**, который изменяет существующий контактный объект для размещенной единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="b8dbf-123">В следующем примере создается контактный объект автосекретаря:</span><span class="sxs-lookup"><span data-stu-id="b8dbf-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="b8dbf-124">В этом примере создается новый контактный объект единой системы обмена сообщениями Exchange с SIP-адресом sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="b8dbf-125">Имя пула, в котором работает служба регистратора Lync Server 2013, — RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="b8dbf-126">Сведения будут сохраняться в подразделении Active Directory OU=ExUmContacts,DC=litwareinc,DC=com.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="b8dbf-127">Телефонный номер контактного объекта — 2065554567.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="b8dbf-128">Дополнительный параметр -AutoAttendant $True указывает, что этот объект является контактным объектом автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="b8dbf-129">Значение False параметра -AutoAttendant (установленное по умолчанию) указывает контактный объект абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="b8dbf-130">Сведения о командлетах New – CsExUmContact и Set CsExUmContact можно найти в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8dbf-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

