---
title: 'Lync Server 2013: создание объектов Contact для размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="79bf3-102">Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79bf3-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79bf3-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="79bf3-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="79bf3-104">В этом разделе описывается создание контактных объектов автосекретаря или абонентского доступа для размещенной единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="79bf3-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="79bf3-105">Дополнительные сведения: [Управление контактными объектами размещенного Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="79bf3-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="79bf3-106">Для получения дополнительных сведений о настройке объектов Contact обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="79bf3-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="79bf3-107">New — CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="79bf3-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="79bf3-108">Set — CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="79bf3-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="79bf3-109">Перед тем как можно будет включить поддержку объектов контактов для размещенной единой системы обмена сообщениями Exchange Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним.</span><span class="sxs-lookup"><span data-stu-id="79bf3-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="79bf3-110">Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="79bf3-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="79bf3-111">Создание контактных объектов автосекретаря или абонентского доступа для размещенной единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="79bf3-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="79bf3-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="79bf3-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="79bf3-p102">Чтобы создать любой контактный объект, необходимо выполнить командлет New-CsExUmContact. Например, для создания контактного объекта автосекретаря и абонентского доступа выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="79bf3-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="79bf3-115">В этих примерах используются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="79bf3-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="79bf3-116">**SipAddress** указывает SIP-адрес контактного объекта.</span><span class="sxs-lookup"><span data-stu-id="79bf3-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="79bf3-117">В качестве значения необходимо использовать адрес, который еще не использовался для настройки пользователя или контактного объекта в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79bf3-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="79bf3-118">Это значение должно быть в формате SIP:\<*SIP Address*\>, как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="79bf3-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="79bf3-119">**RegistrarPool** указывает полное доменное имя пула, в котором выполняется служба регистратора.</span><span class="sxs-lookup"><span data-stu-id="79bf3-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="79bf3-120">Объекты контактов Exchange единой системы обмена сообщениями невозможно переместить в пулы, которые входят в состав развертываний Lync Server 2013 до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79bf3-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="79bf3-121">**OU** задает подразделение Active Directory, в котором будет находиться данный контактный объект.</span><span class="sxs-lookup"><span data-stu-id="79bf3-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="79bf3-p104">**DisplayNumber** указывает номер телефона контактного объекта. Номер телефона для каждого контактного объекта должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="79bf3-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="79bf3-p105">**AutoAttendant** указывает, является ли данный контактный объект автосекретарем. Автосекретарь предоставляет набор голосовых приглашений, которые позволяют звонящим перемещаться по телефонной системе, чтобы найти требуемого абонента. Значение **False** (по умолчанию) для этого параметра указывает контактный объект абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="79bf3-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

