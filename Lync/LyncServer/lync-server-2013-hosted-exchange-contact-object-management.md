---
title: 'Lync Server 2013: управление объектом Contact в размещенной системе Exchange'
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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="c55ae-102">Управление объектом Contact в размещенной системе Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c55ae-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c55ae-103">_**Тема последнего изменения:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="c55ae-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="c55ae-104">Вам нужно настроить объект контакта для каждого номера автосекретаря и номера абонентского доступа в вашем меж-либо из вашего локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="c55ae-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="c55ae-105">Для интеграции с размещенной UM-службой оксумутил. exe нельзя использовать для управления объектами контакта, так как это зависит от параметров службы каталогов Active Directory в UM-среде.</span><span class="sxs-lookup"><span data-stu-id="c55ae-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="c55ae-106">В случае междоменного развертывания Lync Server 2013 и размещенная UM-среде Exchange устанавливаются в разных лесах, не имеющих доверительных отношений между ними.</span><span class="sxs-lookup"><span data-stu-id="c55ae-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="c55ae-107">По соображениям безопасности Lync Server 2013 Administrators не имеет прямого доступа к параметрам Active Directory единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="c55ae-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="c55ae-108">В результате Lync Server 2013 предоставляет другую модель для управления объектами контакта в *общем адресном пространстве SIP* , доступном как для Lync Server 2013, так и для размещенной службы Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="c55ae-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="c55ae-109">Размещенный объектный рабочий процесс объекта контакта</span><span class="sxs-lookup"><span data-stu-id="c55ae-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="c55ae-110">Ниже приведены общие инструкции по работе с размещенным администратором клиента Exchange для управления контактными объектами.</span><span class="sxs-lookup"><span data-stu-id="c55ae-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="c55ae-111">Администратор Exchange запрашивает номера телефонов для доступа подписчика UM Exchange и контактных объектов автоматического ассистента.</span><span class="sxs-lookup"><span data-stu-id="c55ae-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="c55ae-112">Администратор Lync Server 2013 создает объект контакта для каждого номера телефона и назначает политику размещенной голосовой почты каждому объекту контакта.</span><span class="sxs-lookup"><span data-stu-id="c55ae-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="c55ae-113">Администратор Lync Server 2013 предоставляет номера телефонов для администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="c55ae-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="c55ae-114">Администратор Exchange назначает номера телефонов для соответствующих абонентских групп единой системы обмена сообщениями для автосекретаря и абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="c55ae-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c55ae-115">Вам не нужно настраивать параметры телефонной группы Lync Server 2013 для объектов контакта так же, как и в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="c55ae-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="c55ae-116">Настройка размещенных объектов контакта</span><span class="sxs-lookup"><span data-stu-id="c55ae-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c55ae-117">Прежде чем можно будет включить объект контакта Lync Server 2013 для размещенной единой системы обмена сообщениями Exchange, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним.</span><span class="sxs-lookup"><span data-stu-id="c55ae-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="c55ae-118">Эта политика может быть общедоступной, на уровне сайта или для отдельных пользователей, если она применяется к объекту контакта, который вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="c55ae-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="c55ae-119">Подробнее смотрите в разделе <A href="lync-server-2013-hosted-voice-mail-policies.md">политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c55ae-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c55ae-120">Для настройки размещенных объектов контактов для автоматического ассистента и доступа абонентов в рамках локального развертывания необходимо использовать следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="c55ae-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="c55ae-121">**New-ксексумконтакт** создает новый объект контакта для размещенной единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c55ae-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="c55ae-122">**Set-ксексумконтакт** изменяет существующий объект контакта для размещенной единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c55ae-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="c55ae-123">В следующем примере создается объект контакта автоматического ассистента.</span><span class="sxs-lookup"><span data-stu-id="c55ae-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="c55ae-124">В этом примере создается новый объект контакта UM Exchange с адресом SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c55ae-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="c55ae-125">Имя пула, в котором работает служба регистратора Lync Server 2013, — RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c55ae-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="c55ae-126">Организационное подразделение Active Directory, в котором будут храниться эти данные, — OU = Ексумконтактс, DC = плана litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="c55ae-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="c55ae-127">Номер телефона объекта Contact — 2065554567.</span><span class="sxs-lookup"><span data-stu-id="c55ae-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="c55ae-128">Параметр необязательного автосекретаря $True указывает на то, что этот объект является автоматическим контактным объектом-участником.</span><span class="sxs-lookup"><span data-stu-id="c55ae-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="c55ae-129">Если для параметра автосекретаря задано значение false (значение по умолчанию), указывает объект контакта доступа абонента.</span><span class="sxs-lookup"><span data-stu-id="c55ae-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="c55ae-130">Сведения о командлетах New-Ксексумконтакт и Set-Ксексумконтакт можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c55ae-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

