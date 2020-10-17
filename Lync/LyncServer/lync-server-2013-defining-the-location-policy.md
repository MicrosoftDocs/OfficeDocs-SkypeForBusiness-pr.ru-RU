---
title: 'Lync Server 2013: определение политики расположения'
description: 'Lync Server 2013: определение политики расположения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567545"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="f9667-103">Определение политики расположения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9667-103">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9667-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f9667-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f9667-105">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="f9667-105">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="f9667-106">**Emergency Services Enabled** (Аварийные службы включены)</span><span class="sxs-lookup"><span data-stu-id="f9667-106">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="f9667-107">Если для этого параметра задано значение **Да**, для клиента включена поддержка E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f9667-107">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="f9667-108">Когда клиент регистрируется, он пытается получить расположение из службы сведений о местоположении и будет включать сведения о расположении в процессе экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="f9667-108">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="f9667-109">**Location Required** (Требуется указать расположение)</span><span class="sxs-lookup"><span data-stu-id="f9667-109">**Location Required**</span></span>  
    <span data-ttu-id="f9667-110">Этот параметр используется только в том случае, если для режима **появление включенных служб**   задано значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="f9667-110">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="f9667-p102">Можно настроить параметр **Требуется указать расположение**, чтобы определить поведение клиентов. Если задать значение **Нет**, расположение не будет запрашиваться у пользователя. Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос. Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе. В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="f9667-p102">You can configure the **Location Required** setting to define the client behavior. Setting the value to **No** means that the user will not be prompted for a location. Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt. Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9667-p103">Текст заявления не отображается, если пользовать вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление.</span><span class="sxs-lookup"><span data-stu-id="f9667-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="f9667-118">**Enhanced Emergency Service Disclaimer** (Расширенное заявление об отказе аварийных служб)</span><span class="sxs-lookup"><span data-stu-id="f9667-118">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="f9667-119">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="f9667-119">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="f9667-120">В Lync Server 2013 вы можете использовать политику расположения, чтобы задать разные заявления об отказе для разных языковых стандартов или разных наборов пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9667-120">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9667-121">Этот параметр политики расположений отличается от Lync Server 2010, где вы использовали командлет <STRONG>Set – ксенханцедемерженцисервицедисклаимер</STRONG> для установки глобального заявления об отказе для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="f9667-121">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="f9667-122">Если глобальный отказ уже существует, необходимо указать этот отказ в политике расположения.</span><span class="sxs-lookup"><span data-stu-id="f9667-122">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="f9667-123">То есть Lync Server 2013 использует в политике расположения только отказы, указанные в политике расположения.</span><span class="sxs-lookup"><span data-stu-id="f9667-123">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="f9667-124">**Emergency Dial String** (Строка набора аварийного номера)</span><span class="sxs-lookup"><span data-stu-id="f9667-124">**Emergency Dial String**</span></span>  
    <span data-ttu-id="f9667-p106">Эта строка набора номера (за исключением начального символа “+”, включая любые правила нормализации, примененные абонентской группой пользователя Lync) указывает, что вызов является звонком в аварийную службу. Параметр **Строка набора аварийного номера** указывает клиенту на необходимость включения в вызов данных о расположении и обратном вызове.</span><span class="sxs-lookup"><span data-stu-id="f9667-p106">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call. The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9667-127">Если в Организации не используется префикс доступа к внешней линии, не требуется создавать соответствующее правило нормализации абонентской группы, которое добавляет символ "+" в строку 911 перед отправкой вызова на маршрутизацию исходящей почты на сервере пула Lync; "+" будет автоматически добавлен клиентом Lync в качестве результата политики расположения.</span><span class="sxs-lookup"><span data-stu-id="f9667-127">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="f9667-128">Тем не менее, если сайт использует префикс внешнего доступа, необходимо добавить правило нормализации к соответствующей политике абонентской группы, которая удаляет префикс внешнего доступа и добавляет "+".</span><span class="sxs-lookup"><span data-stu-id="f9667-128">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="f9667-129">Например, если в вашем расположении используется префикс внешнего доступа 9, а пользователь набирает номер 9 &nbsp; 911 для совершения звонка, клиент будет использовать политику абонентской группы для нормализации до + 911 до того, как набираемые номера будут оцениваться маршрутами в профиле расположения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f9667-129">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="f9667-130">**Emergency Dial String Masks** (Маски строки набора аварийного номера)</span><span class="sxs-lookup"><span data-stu-id="f9667-130">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="f9667-p108">Список строк набора номера, разделенных запятыми, преобразуемый в указанную **строку набора аварийного номера**. Например, может потребоваться добавить номер 112 (номер аварийных служб в большинстве стран Европы). Пользователи Lync, прибывшие из Европы, могут не знать номера аварийных служб в США (911). Эта настройка позволит им набирать номер 112 с тем же результатом. Как и при настройке параметра "Строка набора аварийного номера" не добавляйте символ “+” в начало номеров и при использовании кодов доступа к внешней линии убедитесь, что в политике абонентской группы пользователя есть правила нормализации, которые будут отсекать цифры кода доступа.</span><span class="sxs-lookup"><span data-stu-id="f9667-p108">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**. For example, you may want to add 112, which is the emergency service number for most of Europe. A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result. As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="f9667-135">**Режим работы с ТСОП**</span><span class="sxs-lookup"><span data-stu-id="f9667-135">**PSTN Usage**</span></span>  
    <span data-ttu-id="f9667-136">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="f9667-136">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9667-p109">Политике расположения можно назначить только один режим. Этот режим использования ТСОП будет переопределять другие режимы, назначенные в политике голосовой связи пользователя. Однако он будет применяться только к вызовам, указанным в строке набора аварийного номера или одной из масок строки набора аварийного номера.</span><span class="sxs-lookup"><span data-stu-id="f9667-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="f9667-139">**Notification URI** (URI уведомления)</span><span class="sxs-lookup"><span data-stu-id="f9667-139">**Notification URI**</span></span>  
    <span data-ttu-id="f9667-p110">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="f9667-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="f9667-142">**Conference URI** (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="f9667-142">**Conference URI**</span></span>  
    <span data-ttu-id="f9667-143">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.</span><span class="sxs-lookup"><span data-stu-id="f9667-143">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="f9667-144">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="f9667-144">**Conference Mode**</span></span>  
    <span data-ttu-id="f9667-145">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи.</span><span class="sxs-lookup"><span data-stu-id="f9667-145">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="f9667-146">**Location Refresh Interval** (Интервал обновления данных расположения)</span><span class="sxs-lookup"><span data-stu-id="f9667-146">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="f9667-147">Указывает время (в часах) между запросами клиентов на обновление расположения из службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="f9667-147">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="f9667-148">Значение можно задать в диапазоне от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="f9667-148">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="f9667-149">Значение по умолчанию: 4 часа.</span><span class="sxs-lookup"><span data-stu-id="f9667-149">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

