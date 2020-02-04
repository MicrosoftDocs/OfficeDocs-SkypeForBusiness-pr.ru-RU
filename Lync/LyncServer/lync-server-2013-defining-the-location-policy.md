---
title: 'Lync Server 2013: определение политики расположения'
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
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="bac41-102">Определение политики расположения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac41-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac41-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bac41-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bac41-104">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="bac41-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="bac41-105">**Службы экстренной помощи включены**</span><span class="sxs-lookup"><span data-stu-id="bac41-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="bac41-106">Если это значение равно **Да**, клиент включен для E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="bac41-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="bac41-107">Когда клиент регистрируется, он пытается получить место из службы сведений о местоположении и будет включать сведения о расположении в процессе вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="bac41-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="bac41-108">**Требуется расположение**</span><span class="sxs-lookup"><span data-stu-id="bac41-108">**Location Required**</span></span>  
    <span data-ttu-id="bac41-109">Этот параметр используется только в том случае, если для функции "  **включен для экстренных служб**" установлено значение **"Да"**.</span><span class="sxs-lookup"><span data-stu-id="bac41-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="bac41-110">Вы можете настроить **требуемый параметр расположения** , чтобы определить поведение клиента.</span><span class="sxs-lookup"><span data-stu-id="bac41-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="bac41-111">Если задать значение **Нет**, расположение не будет запрашиваться у пользователя.</span><span class="sxs-lookup"><span data-stu-id="bac41-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="bac41-112">Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="bac41-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="bac41-113">Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе.</span><span class="sxs-lookup"><span data-stu-id="bac41-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="bac41-114">В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="bac41-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bac41-p103">Текст заявления не отображается, если пользователь вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление. </span><span class="sxs-lookup"><span data-stu-id="bac41-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bac41-117">**Заявление об отказе расширенных экстренных служб**</span><span class="sxs-lookup"><span data-stu-id="bac41-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="bac41-118">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="bac41-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="bac41-119">В Lync Server 2013 вы можете использовать политику расположения для настройки различных отказов на использование разных языковых стандартов и разных групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="bac41-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bac41-120">Этот параметр политики расположения отличается от Lync Server 2010, в котором вы использовали командлет <STRONG>Set-ксенханцедемерженцисервицедисклаимер</STRONG> , чтобы задать глобальный отказ для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="bac41-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="bac41-121">Если глобальный отказ от ответственности уже существует, необходимо указать этот отказ в политике расположения.</span><span class="sxs-lookup"><span data-stu-id="bac41-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="bac41-122">Это значит, что в Lync Server 2013 используются только те отказы, которые указаны в политике "расположение".</span><span class="sxs-lookup"><span data-stu-id="bac41-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bac41-123">**Строка набора номера для экстренной помощи**</span><span class="sxs-lookup"><span data-stu-id="bac41-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="bac41-124">Эта строка набора номера (меньше, чем интерлиньяж "+", но все нормализация, выполненные абонентской панелью пользователя Lync) указывает на то, что звонок является экстренным звонком.</span><span class="sxs-lookup"><span data-stu-id="bac41-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="bac41-125">На клиенте **строка набора аварийного номера** обеспечивает включение в вызов данных о местоположении и информации для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bac41-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bac41-126">Если в вашей организации не используется префикс доступа к внешней линии, вам не нужно создавать соответствующее правило нормализации для абонентской группы, добавляющее "+" в строку 911 перед отправкой вызова на исходящую маршрутизацию на сервере пула Lync. "+" будет автоматически добавлен клиентом Lync в качестве результата политики расположения.</span><span class="sxs-lookup"><span data-stu-id="bac41-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="bac41-127">Однако если на сайте используется префикс внешнего доступа, необходимо добавить правило нормализации для соответствующей политики абонентского плана, которое удаляет префикс доступа к внешним данным и добавляет знак "+".</span><span class="sxs-lookup"><span data-stu-id="bac41-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="bac41-128">Например, если в вашем местоположении используется префикс внешнего доступа 9 и пользователь набирает номер 9&nbsp;911 для вызова экстренной помощи, клиент будет использовать политику абонентской группы для нормализации этого номера до версии + 911 перед тем, как они будут оценены маршрутами в профиле местоположения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="bac41-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bac41-129">**Маски строк в экстренных звонках**</span><span class="sxs-lookup"><span data-stu-id="bac41-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="bac41-130">Список разделенных точкой с запятой строк набора номера, который преобразуется в указанную **строку для экстренного набора**.</span><span class="sxs-lookup"><span data-stu-id="bac41-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="bac41-131">Например, вы можете добавить 112, который является номером службы экстренной помощи в большинстве стран Европы.</span><span class="sxs-lookup"><span data-stu-id="bac41-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="bac41-132">Посетители Lync из Европы могут не знать, что 911 является номером экстренной помощи в США, но может набрать номер 112 и получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="bac41-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="bac41-133">Как и в случае со строкой набора экстренных вызовов, не включайте знак "+" перед каждым числом, и если вы используете коды доступа внешней линии, убедитесь в том, что в политике абонентской группы пользователя есть правила нормализации для удаления цифр кода доступа.</span><span class="sxs-lookup"><span data-stu-id="bac41-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="bac41-134">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="bac41-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="bac41-135">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="bac41-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bac41-p109">Политике расположения можно назначить только один режим. Этот режим использования ТСОП будет переопределять другие режимы, назначенные в политике голосовой связи пользователя. Однако он будет применяться только к вызовам, указанным в строке набора аварийного номера или одной из масок строки набора аварийного номера.</span><span class="sxs-lookup"><span data-stu-id="bac41-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bac41-138">**URI уведомления**</span><span class="sxs-lookup"><span data-stu-id="bac41-138">**Notification URI**</span></span>  
    <span data-ttu-id="bac41-p110">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="bac41-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="bac41-141">**Идентификатор URI конференции**</span><span class="sxs-lookup"><span data-stu-id="bac41-141">**Conference URI**</span></span>  
    <span data-ttu-id="bac41-142">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.  </span><span class="sxs-lookup"><span data-stu-id="bac41-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="bac41-143">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="bac41-143">**Conference Mode**</span></span>  
    <span data-ttu-id="bac41-144">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи. </span><span class="sxs-lookup"><span data-stu-id="bac41-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="bac41-145">**Интервал обновления данных расположения**</span><span class="sxs-lookup"><span data-stu-id="bac41-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="bac41-146">Указывает время (в часах) между запросами клиентов на обновление расположения в службе сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="bac41-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="bac41-147">The value can be set to any value between 1 and 12.</span><span class="sxs-lookup"><span data-stu-id="bac41-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="bac41-148">The default value is 4.</span><span class="sxs-lookup"><span data-stu-id="bac41-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

