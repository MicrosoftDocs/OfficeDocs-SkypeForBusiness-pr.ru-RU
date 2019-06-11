---
title: 'Lync Server 2013: создание объектов Contact для размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="adb1b-102">Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adb1b-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adb1b-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="adb1b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="adb1b-104">Ниже описана процедура создания объектов контактов для автоматического ассистента (AA) и доступа к абонентам (SA) для единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="adb1b-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="adb1b-105">Дополнительные сведения можно найти [в разделе Управление объектами контактных данных Exchange в среде Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="adb1b-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="adb1b-106">Дополнительные сведения о настройке объектов контакта можно найти в документации по оболочке управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="adb1b-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="adb1b-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="adb1b-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="adb1b-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="adb1b-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="adb1b-109">Прежде чем можно будет включить объект контакта Lync Server 2013 для размещенной единой системы обмена сообщениями Exchange, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним.</span><span class="sxs-lookup"><span data-stu-id="adb1b-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="adb1b-110">Подробнее смотрите в разделе <A href="lync-server-2013-hosted-voice-mail-policies.md">политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="adb1b-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="adb1b-111">Создание объектов контактов AA или SA для размещенной единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="adb1b-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="adb1b-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="adb1b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="adb1b-113">Запустите командлет New-Ксексумконтакт, чтобы создать любые объекты контактов, необходимые для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="adb1b-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="adb1b-114">Например, чтобы создать объект AA и контакт SA, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="adb1b-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="adb1b-115">В этих примерах устанавливаются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="adb1b-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="adb1b-116">**Сипаддресс** указывает адрес SIP объекта Contact.</span><span class="sxs-lookup"><span data-stu-id="adb1b-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="adb1b-117">Это должен быть адрес, который еще не использовался для настройки объекта пользователя или контакта в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="adb1b-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="adb1b-118">Это значение должно быть в формате SIP:\<*SIP Address*\>, как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="adb1b-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="adb1b-119">**Регистрарпул** указывает полное доменное имя (FQDN) пула, на котором запущена служба регистратора.</span><span class="sxs-lookup"><span data-stu-id="adb1b-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="adb1b-120">Объекты контактов Exchange UM нельзя переместить в пулы, которые являются частью развертывания Lync Server 2013 до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="adb1b-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="adb1b-121">**OU** . определяет подразделение Active Directory, в котором будет находиться этот объект контакта.</span><span class="sxs-lookup"><span data-stu-id="adb1b-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="adb1b-122">**Дисплайнумбер** указывает телефонный номер объекта контакта.</span><span class="sxs-lookup"><span data-stu-id="adb1b-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="adb1b-123">Номер телефона для каждого объекта контакта должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="adb1b-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="adb1b-124">**Автосекретарь** указывает, является ли объект контакта автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="adb1b-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="adb1b-125">Автосекретарь предлагает набор голосовых запросов, которые позволяют вызывающим абонентам перемещаться по телефонной системе и обращаться к ним, к которым нужно обратиться.</span><span class="sxs-lookup"><span data-stu-id="adb1b-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="adb1b-126">Значение **false** (по умолчанию) для этого параметра указывает на объект контакта доступа абонента.</span><span class="sxs-lookup"><span data-stu-id="adb1b-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

