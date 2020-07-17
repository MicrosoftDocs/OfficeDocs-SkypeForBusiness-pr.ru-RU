---
title: Настройка сервера-посредника
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
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="f1887-102">Настройка сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="f1887-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1887-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f1887-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f1887-104">В этой процедуре описываются действия по настройке пула Lync Server 2013 для использования сервера-посредника Lync Server 2013 вместо устаревшего сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f1887-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="f1887-p101">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо выполнить вход в качестве члена групп RTCUniversalServerAdmins и "Администраторы домена". Кроме того можно делегировать надлежащие права и разрешения администратора для добавления ролей сервера. Дополнительные сведения см. в разделе "Делегирование разрешений на установку" в документации по развертыванию сервера Standard Edition или сервера Enterprise Edition. Для всех остальных изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f1887-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1887-109">Последние сведения о поиске подходящих шлюзов PSTN, IP-УАТС и магистрали SIP, работающих с Lync Server 2013, можно найти в статье "Microsoft Unified Communications Open Communications Program" <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .</span><span class="sxs-lookup"><span data-stu-id="f1887-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="f1887-110">Чтобы настроить сервер-посредник с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="f1887-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="f1887-111">Откройте существующую топологию в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="f1887-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="f1887-112">На левой панели перейдите к пункту **Шлюзы ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="f1887-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="f1887-113">Щелкните правой кнопкой мыши **Шлюзы ТСОП**, затем щелкните **Создать шлюз IP/ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="f1887-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="f1887-114">Заполните страницу **Определение нового шлюза IP/ТСОП**, указав приведенные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="f1887-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="f1887-p102">Введите полное доменное имя или IP-адрес шлюза. Полное доменное имя шлюза необходимо, если шлюз использует протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="f1887-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="f1887-117">Примите значение по умолчанию для параметра **Порт прослушивания для шлюза IP/ТСОП** или введите новый порт прослушивания.</span><span class="sxs-lookup"><span data-stu-id="f1887-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="f1887-118">Определите значение параметра **Транспортный протокол SIP**.</span><span class="sxs-lookup"><span data-stu-id="f1887-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="f1887-119">На левой панели перейдите в раздел **Интерфейсный пул Enterprise Edition** или **Сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="f1887-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="f1887-120">Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="f1887-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="f1887-121">В разделе **Сервер-посредник** определите значение параметра **Порты прослушивания**.</span><span class="sxs-lookup"><span data-stu-id="f1887-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="f1887-122">Затем сопоставьте новый созданный шлюз ТСОП, выбрав его и нажав кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f1887-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="f1887-123">В **построителе топологий** выберите узел верхнего уровня **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f1887-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="f1887-124">В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1887-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="f1887-125">По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="f1887-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1887-126">Важно выполнить следующий раздел, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">изменить маршруты голосовой связи для использования нового сервера-посредника Lync server 2013</A> , чтобы убедиться, что маршруты голосовой связи указывают на правильный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="f1887-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

