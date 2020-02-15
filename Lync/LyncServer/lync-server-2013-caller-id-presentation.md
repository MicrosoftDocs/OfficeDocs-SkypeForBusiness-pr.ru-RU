---
title: 'Lync Server 2013: Презентация идентификации звонящего'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6962035f5de6b1b3885db3ff31b23058a71bdc4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="2bc96-102">Презентация идентификации звонящего в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bc96-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bc96-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2bc96-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2bc96-104">При использовании Lync Server 2010 телефонный номер вызываемого абонента (то есть номер телефона) можно перевести из формата E. 164 в местный формат набора номера, который требуется магистральным одноранговым узлом (то есть, связанным шлюзом, УАТС или магистральной магистралью SIP).</span><span class="sxs-lookup"><span data-stu-id="2bc96-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="2bc96-105">Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="2bc96-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="2bc96-106">Lync Server 2013 представляет параметр для перевода номера телефона абонентского абонента (то есть номера телефона, с которого вызывается абонент) из формата E. 164 в местный формат набора номера, необходимый одноранговому одноранговому узлу.</span><span class="sxs-lookup"><span data-stu-id="2bc96-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="2bc96-107">Например, можно написать правило преобразования для удаления +44 из начала строки набора и замены на 0144.</span><span class="sxs-lookup"><span data-stu-id="2bc96-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="2bc96-108">**Настройка идентификатора звонящего с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="2bc96-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2bc96-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2bc96-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2bc96-110">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2bc96-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2bc96-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bc96-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2bc96-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2bc96-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2bc96-113">В левой панели навигации последовательно выберите пункты **Маршрутизация голосовой связи** и **Конфигурация магистрали**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="2bc96-114">На странице **Конфигурация магистрали** дважды щелкните существующую магистраль (например, **глобальную**), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="2bc96-115">Настройка представления идентификатора звонящего</span><span class="sxs-lookup"><span data-stu-id="2bc96-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="2bc96-116">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="2bc96-117">В окне **Правила трансляции вызывающего номера** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2bc96-118">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="2bc96-119">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2bc96-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="2bc96-120">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="2bc96-121">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2bc96-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="2bc96-122">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="2bc96-123">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2bc96-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="2bc96-124">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2bc96-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2bc96-125">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="2bc96-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

