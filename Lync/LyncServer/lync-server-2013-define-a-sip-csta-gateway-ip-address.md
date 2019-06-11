---
title: 'Lync Server 2013: определение IP-адреса для шлюза SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="0c759-102">Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c759-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c759-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0c759-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0c759-104">Если Lync Server подключается к шлюзу SIP/КСТА, который вы развернули для удаленного управления звонками с помощью протокола TCP, необходимо задать IP-адрес шлюза в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="0c759-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="0c759-105">Это действие не требуется для шлюзов, поддерживающих соединения TLS.</span><span class="sxs-lookup"><span data-stu-id="0c759-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="0c759-106">Для всех шлюзов, поддерживающих TLS подключения, вы можете пропустить эту процедуру и продолжить развертывание удаленного управления звонком, выполнив действия, описанные в статье [Включение пользователей Lync для удаленного управления звонками в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="0c759-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="0c759-107">Определение IP-адреса шлюза SIP/КСТА с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="0c759-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="0c759-108">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0c759-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0c759-109">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0c759-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="0c759-110">Выберите параметр для скачивания существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="0c759-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="0c759-111">Разверните узел **серверы доверенных приложений** .</span><span class="sxs-lookup"><span data-stu-id="0c759-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="0c759-112">Щелкните правой кнопкой мыши созданную группу доверенных приложений, как описано в разделе [Настройка надежной записи приложения для удаленного управления звонком в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c759-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="0c759-113">Снимите флажок **Разрешить репликацию данных конфигурации в этот пул** .</span><span class="sxs-lookup"><span data-stu-id="0c759-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="0c759-114">Нажмите кнопку **ограничить использование службы до выбранных IP-адресов**.</span><span class="sxs-lookup"><span data-stu-id="0c759-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="0c759-115">Параметр по умолчанию **использует все настроенные IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="0c759-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="0c759-116">В текстовом поле **основной IP-адрес** введите IP-адрес шлюза SIP/кста.</span><span class="sxs-lookup"><span data-stu-id="0c759-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="0c759-117">Чтобы обновить топологию в хранилище Центрального управления, в дереве консоли щелкните **Lync Server**, а затем в области **действий** нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="0c759-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c759-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c759-118">See Also</span></span>


[<span data-ttu-id="0c759-119">Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c759-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="0c759-120">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c759-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

