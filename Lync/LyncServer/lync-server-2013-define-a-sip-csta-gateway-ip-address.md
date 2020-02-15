---
title: 'Lync Server 2013: определение IP-адреса шлюза SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="ac170-102">Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac170-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac170-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ac170-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ac170-104">Если Lync Server будет подключаться к шлюзу SIP/CSTA, развернутому для удаленного управления звонками с помощью подключения по протоколу TCP, необходимо определить IP-адрес шлюза в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ac170-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="ac170-105">Этот шаг не требуется для шлюзов, поддерживающих подключения TLS.</span><span class="sxs-lookup"><span data-stu-id="ac170-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="ac170-106">Для любого шлюза, поддерживающего TLS подключения, можно пропустить эту процедуру и продолжить развертывание удаленного управления звонками, выполнив действия, описанные в статье [Включение удаленного управления звонками для пользователей Lync в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="ac170-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="ac170-107">Задание IP-адреса шлюза SIP/CSTA с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="ac170-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="ac170-108">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ac170-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ac170-109">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ac170-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="ac170-110">Выберите загрузку существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="ac170-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="ac170-111">Разверните узел **Trusted application servers** (Доверенные серверы приложений).</span><span class="sxs-lookup"><span data-stu-id="ac170-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="ac170-112">Щелкните правой кнопкой мыши созданный пул доверенных приложений, как описано в разделе [Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), а затем щелкните **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ac170-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ac170-113">Снимите флажок **Enable replication of configuration data to this pool** (Включить репликацию данных конфигурации для этого пула).</span><span class="sxs-lookup"><span data-stu-id="ac170-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="ac170-p102">Щелкните **Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). По умолчанию используется параметр **Use all configured IP addresses** (Использовать все настроенные IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="ac170-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="ac170-116">В текстовом поле **Primary IP address** (Основной IP-адрес) введите IP-адрес шлюза SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="ac170-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="ac170-117">Чтобы обновить топологию в центральном хранилище управления, в дереве консоли выберите узел **Lync Server** и затем на панели **Действия** щелкните **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="ac170-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac170-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ac170-118">See Also</span></span>


[<span data-ttu-id="ac170-119">Настройка статического маршрута для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac170-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="ac170-120">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac170-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

