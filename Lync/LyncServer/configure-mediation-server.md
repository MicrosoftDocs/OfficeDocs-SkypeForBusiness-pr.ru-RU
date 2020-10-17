---
title: Настройка сервера-посредника
description: Настройка сервера-посредника.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5723d9446122b85f7bd1812f7c6f411c5c1c9dbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543005"
---
# <a name="configure-mediation-server"></a><span data-ttu-id="0cefc-103">Настройка сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0cefc-103">Configure Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cefc-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0cefc-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0cefc-105">В этой процедуре описываются действия по настройке пула Lync Server 2013 для использования сервера-посредника Lync Server 2013 вместо устаревшего сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0cefc-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="0cefc-p101">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо выполнить вход в качестве члена групп RTCUniversalServerAdmins и "Администраторы домена". Кроме того можно делегировать надлежащие права и разрешения администратора для добавления ролей сервера. Дополнительные сведения см. в разделе "Делегирование разрешений на установку" в документации по развертыванию сервера Standard Edition или сервера Enterprise Edition. Для всех остальных изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0cefc-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cefc-110">Последние сведения о поиске подходящих шлюзов PSTN, IP-УАТС и магистрали SIP, работающих с Lync Server 2013, можно найти в статье "Microsoft Unified Communications Open Communications Program" <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .</span><span class="sxs-lookup"><span data-stu-id="0cefc-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="0cefc-111">Чтобы настроить сервер-посредник с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="0cefc-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="0cefc-112">Откройте существующую топологию в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="0cefc-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="0cefc-113">На левой панели перейдите к пункту **Шлюзы ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="0cefc-114">Щелкните правой кнопкой мыши **Шлюзы ТСОП**, затем щелкните **Создать шлюз IP/ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="0cefc-115">Заполните страницу **Определение нового шлюза IP/ТСОП**, указав приведенные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="0cefc-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="0cefc-p102">Введите полное доменное имя или IP-адрес шлюза. Полное доменное имя шлюза необходимо, если шлюз использует протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="0cefc-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="0cefc-118">Примите значение по умолчанию для параметра **Порт прослушивания для шлюза IP/ТСОП** или введите новый порт прослушивания.</span><span class="sxs-lookup"><span data-stu-id="0cefc-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="0cefc-119">Определите значение параметра **Транспортный протокол SIP**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="0cefc-120">На левой панели перейдите в раздел **Интерфейсный пул Enterprise Edition** или **Сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="0cefc-121">Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="0cefc-122">В разделе **Сервер-посредник** определите значение параметра **Порты прослушивания**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="0cefc-123">Затем сопоставьте новый созданный шлюз ТСОП, выбрав его и нажав кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="0cefc-124">В **построителе топологий** выберите узел верхнего уровня **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="0cefc-125">В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cefc-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="0cefc-126">По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="0cefc-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cefc-127">Важно выполнить следующий раздел, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">изменить маршруты голосовой связи для использования нового сервера-посредника Lync server 2013</A> , чтобы убедиться, что маршруты голосовой связи указывают на правильный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="0cefc-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

