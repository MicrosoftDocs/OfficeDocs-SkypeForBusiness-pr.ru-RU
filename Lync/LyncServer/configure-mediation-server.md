---
title: Настройка сервера-посредника
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="aa7af-102">Настройка сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="aa7af-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="aa7af-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="aa7af-103"></span></span>

<span data-ttu-id="aa7af-104">_**Последнее изменение раздела:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="aa7af-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="aa7af-105">В этой процедуре приведены действия для настройки пула Lync Server 2013 для использования сервера посредника Lync Server 2013 вместо прежних версий Office Communications Server 2007 R2 сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="aa7af-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="aa7af-106">Для успешной публикации, включения или отключения топологии при добавлении или удалении роль сервера, вы должны войти в систему как пользователь, являющийся членом группы RTCUniversalServerAdmins и "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="aa7af-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="aa7af-107">Можно также делегировать соответствующие права и разрешения администратора для добавления роли сервера.</span><span class="sxs-lookup"><span data-stu-id="aa7af-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="aa7af-108">Дополнительные сведения см Делегирование разрешений на установку на сервере Standard Edition или Enterprise Edition server документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="aa7af-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="aa7af-109">Другие изменения конфигурации необходим только входить в группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aa7af-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa7af-110">Для получения последних сведений о поиске квалифицированного шлюзы ТСОП, IP-УАТС и служб распределения каналов SIP, которые работают с Lync Server 2013 видеть «Microsoft Unified Communications программы открытого взаимодействия» <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span><span class="sxs-lookup"><span data-stu-id="aa7af-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="aa7af-111">Настройка с помощью построителя топологии Mediation Server</span><span class="sxs-lookup"><span data-stu-id="aa7af-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="aa7af-112">Откройте существующую топологию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="aa7af-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="aa7af-113">В левой области перейдите к **пункту шлюзы ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="aa7af-114">Щелкните правой кнопкой мыши **шлюзы ТСОП**и выберите команду **Создать шлюз IP/ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="aa7af-115">Заполните страницу **Определение нового шлюза IP/ТСОП** со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="aa7af-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="aa7af-116">Введите полное доменное имя или IP-адрес шлюза.</span><span class="sxs-lookup"><span data-stu-id="aa7af-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="aa7af-117">Полное доменное имя шлюза является обязательным, если шлюз использует протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="aa7af-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="aa7af-118">Примите значение по умолчанию, **порт прослушивания для шлюза IP/ТСОП** или введите новый порт прослушивания, если она была изменена.</span><span class="sxs-lookup"><span data-stu-id="aa7af-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="aa7af-119">Задайте **транспортный протокол Sip**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="aa7af-120">В левой области перейдите к **пулу переднего плана Enterprise Edition** или **Сервера Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="aa7af-121">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="aa7af-122">В разделе **Сервер-посредник**задайте **порты прослушивания**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="aa7af-123">Затем сопоставьте новый созданный шлюз ТСОП, выбрав его и нажав кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="aa7af-124">В **Построителе топологий**выберите узел верхнего уровня **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="aa7af-125">В меню **Действие** выберите команду **Опубликовать топологию** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aa7af-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="aa7af-126">После завершения работы **мастера публикации** , нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="aa7af-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa7af-127">Важно выполнить следующий раздел <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Изменение маршрутов голосовых вызовов для использования нового сервера посредника для Lync Server 2013</A> , чтобы убедиться, что маршруты голосовой связи указывали на нужный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="aa7af-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="aa7af-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="aa7af-128"></span></span></div>

