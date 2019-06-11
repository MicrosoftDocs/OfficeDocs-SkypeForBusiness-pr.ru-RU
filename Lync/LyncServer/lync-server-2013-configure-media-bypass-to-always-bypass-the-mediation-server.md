---
title: 'Lync Server 2013: Настройка обхода мультимедийных файлов для постоянного обобхода сервера обновлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="60a44-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="60a44-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60a44-103">_**Тема последнего изменения:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="60a44-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60a44-104">В этой статье предполагается, что вы уже настроили мультимедиа для всех магистральных подключений к однорангового канала (коммутируемая телефонная сеть (PSTN), IP-УАТС или контроллер границ сеанса (SBC) в поставщике услуг телефонной связи через Интернет (ИТСП)) для определенного сайт или служба, для которых требуется, чтобы мультимедиа обходило сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="60a44-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="60a44-105">Вы не можете настроить мультимедиа так, чтобы он всегда обходился на сервере, а также включать управление допуском звонков.</span><span class="sxs-lookup"><span data-stu-id="60a44-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="60a44-106">Эти параметры несовместимы и, следовательно, являются взаимоисключающими параметрами в пользовательском интерфейсе панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60a44-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="60a44-107">Кроме включения функции обхода мультимедиа для отдельных магистральных подключений, связанных с одноранговым сервером, необходимо также настроить общие параметры для обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="60a44-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="60a44-108">Если вы используете действия, описанные в этом разделе, чтобы настроить общие параметры для обхода мультимедиа, предполагается, что у вас есть хорошее соединение между конечными точками Lync и любым одноранговым узлом, для которого вы настроили обходные носители на магистральном подключении.</span><span class="sxs-lookup"><span data-stu-id="60a44-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="60a44-109">Если у вас нет хорошей связи между конечными точками Lync Server и всеми одноранговыми узлами на сервере-посреднике, для которого соответствующие магистральные подключения включены для обхода мультимедиа, необходимо настроить глобальные параметры обхода мультимедиа, чтобы использовать сведения о сайте и регионе при используется обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="60a44-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="60a44-110">Это позволяет более подробно управлять тем, когда мультимедиа обходит сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="60a44-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="60a44-111">Для этого выполните действия, описанные в разделе [Настройка обхода мультимедиа в глобальных параметрах Lync server 2013, чтобы использовать сведения о сайте и регионе](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) и [связать подсеть с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .</span><span class="sxs-lookup"><span data-stu-id="60a44-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="60a44-112">Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60a44-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="60a44-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60a44-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60a44-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60a44-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="60a44-115">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="60a44-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="60a44-116">Дважды щелкните конфигурацию **Глобальная** в данном списке.</span><span class="sxs-lookup"><span data-stu-id="60a44-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="60a44-117">На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="60a44-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="60a44-118">Щелкните **Всегда обходить**.</span><span class="sxs-lookup"><span data-stu-id="60a44-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="60a44-119">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="60a44-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60a44-120">См. также</span><span class="sxs-lookup"><span data-stu-id="60a44-120">See Also</span></span>


[<span data-ttu-id="60a44-121">Настройка обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60a44-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="60a44-122">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60a44-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="60a44-123">Сервер-посредник и обход сервера посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60a44-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="60a44-124">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60a44-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

