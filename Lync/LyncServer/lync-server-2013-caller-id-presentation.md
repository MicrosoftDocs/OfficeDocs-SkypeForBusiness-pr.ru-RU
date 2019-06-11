---
title: 'Lync Server 2013: Презентация идентификации вызывающего абонента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="ca26f-102">Презентация идентификации вызывающего абонента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca26f-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca26f-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ca26f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ca26f-104">При использовании Lync Server 2010 номер телефона вызываемого абонента (т. е. номер телефона) можно перевести из формата E. 164 в локальный формат набора номера, который требуется магистральным одноранговым узлом (то есть шлюзом, частным обменом филиалов или телефонной магистральной панелью SIP).</span><span class="sxs-lookup"><span data-stu-id="ca26f-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="ca26f-105">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="ca26f-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="ca26f-106">Lync Server 2013 предлагает способ перевода номера телефона вызывающего абонента (т. е. номера телефона, с которого осуществляется звонок) из формата E. 164 в локальный формат набора, необходимый для однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="ca26f-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="ca26f-107">Например, можно создать правило преобразования для замены +44 в начале строки набора на 0144.</span><span class="sxs-lookup"><span data-stu-id="ca26f-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="ca26f-108">**Настройка идентификации вызывающего абонента с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="ca26f-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="ca26f-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca26f-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ca26f-110">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ca26f-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ca26f-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca26f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca26f-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca26f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca26f-113">На левой панели навигации щелкните **Маршрутизация голосовой связи** и **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="ca26f-114">На странице **Конфигурация магистрали** дважды щелкните существующую магистраль (например, **глобальную**), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="ca26f-115">Настройка представления идентификатора звонящего</span><span class="sxs-lookup"><span data-stu-id="ca26f-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="ca26f-116">Для выбора одного или нескольких правил из списка всех правил перевода, доступных в вашем развертывании Enterprise Voice, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ca26f-117">В окне **Правила трансляции вызывающего номера** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ca26f-118">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="ca26f-119">Подробные сведения о том, как определить новое правило, приведены в разделе [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ca26f-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ca26f-120">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="ca26f-121">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ca26f-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ca26f-122">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="ca26f-123">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ca26f-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="ca26f-124">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ca26f-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ca26f-125">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="ca26f-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

