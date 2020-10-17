---
title: 'Lync Server 2013: определение пограничной топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceba1f397493ac0ef6961099877643f802c11d93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504566"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="2eab8-102">Определение пограничной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eab8-102">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eab8-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2eab8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2eab8-104">Для создания топологии необходимо использовать построитель топологий, а для развертывания пограничного сервера необходимо настроить по крайней мере один внутренний пул переднего плана или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2eab8-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="2eab8-105">Используйте следующую процедуру, чтобы определить пограничный сервер для отдельного пограничного сервера, а затем выполните действия из статьи [Публикация топологии в Lync server 2013](lync-server-2013-publish-your-topology.md) и [экспортируйте топологию Lync Server 2013 и скопируйте ее на внешние носители для установки пограничного](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) сервера, чтобы опубликовать топологию и сделать ее доступной для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2eab8-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eab8-p102">Внутренний пограничный интерфейс и внешний пограничный интерфейс должны использовать один тип балансировки нагрузки. Нельзя использовать балансировку нагрузки на DNS в одном пограничном интерфейсе и аппаратную балансировку нагрузки в другом пограничном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="2eab8-108">Для успешной публикации, активации или отключения топологии при добавлении или удалении роли сервера вы должны войти в систему как пользователь, входящий в группы RTCUniversalServerAdmins и "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="2eab8-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="2eab8-109">Вы также можете предоставить учетной записи пользователя права и разрешения администратора, необходимые для добавления ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="2eab8-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="2eab8-110">Для получения дополнительных сведений обратитесь к разделу [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2eab8-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="2eab8-111">Для других изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2eab8-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="2eab8-112">Если вы определили пограничную топологию, когда вы определили и опубликовали внутреннюю топологию и не хотите вносить никаких изменений в пограничной топологии, которую вы определили ранее, вам не нужно определять ее и повторно публиковать ее.</span><span class="sxs-lookup"><span data-stu-id="2eab8-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="2eab8-113">Используйте следующую процедуру только в том случае, если необходимо внести изменения в пограничной топологии.</span><span class="sxs-lookup"><span data-stu-id="2eab8-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="2eab8-114">Вы должны сделать определенную и опубликованную топологию доступной для пограничных серверов, выполнив процедуру [экспорта топологии Lync Server 2013 и скопировать ее на внешние носители для установки пограничной системы](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="2eab8-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2eab8-115">Построитель топологий невозможно запустить с пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2eab8-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="2eab8-116">Это средство следует запускать на сервере переднего плана или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2eab8-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="2eab8-117">Процесс определения топологии пограничного сервера выполняется в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="2eab8-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="2eab8-118">Далее перечислены три основных типа топологий пограничного сервера, которые вы можете планировать и настраивать:</span><span class="sxs-lookup"><span data-stu-id="2eab8-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="2eab8-119">для определения топологии отдельного пограничного сервера;</span><span class="sxs-lookup"><span data-stu-id="2eab8-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="2eab8-120">для определения топологии пула пограничных серверов с балансировкой нагрузки;</span><span class="sxs-lookup"><span data-stu-id="2eab8-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="2eab8-121">для определения топологии пула с балансировкой нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="2eab8-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="2eab8-122">Определение топологии отдельного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2eab8-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="2eab8-123">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2eab8-124">В дереве консоли разверните сайт, на котором требуется развернуть пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="2eab8-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="2eab8-125">Щелкните правой кнопкой мыши **пограничные пулы**, а затем выберите команду **создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="2eab8-126">В окне **Определение нового пограничного пула** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="2eab8-127">В окне **Определение полного доменного имени пограничного пула** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-128">В поле **Полное доменное имя пула** введите полное доменное имя (FQDN) внутреннего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2eab8-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="2eab8-129">Указанное имя должно совпадать с именем компьютера, заданным на сервере.</span><span class="sxs-lookup"><span data-stu-id="2eab8-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="2eab8-130">По умолчанию именем компьютера, не присоединенного к домена,является короткое, а не полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="2eab8-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2eab8-131">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2eab8-132">Поэтому вы должны настроить суффикс DNS в имени компьютера, который будет развернут как пограничный сервер, не присоединенный к домену.</span><span class="sxs-lookup"><span data-stu-id="2eab8-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2eab8-133">Используйте только стандартные символы (в том числе A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверов Lync Server, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="2eab8-134">Не используйте символы Юникода или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2eab8-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2eab8-135">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-системами и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="2eab8-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="2eab8-136">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера приведены <A href="lync-server-2013-configure-dns-for-edge-support.md">в статье Настройка DNS для поддержки пограничного сервера в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2eab8-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-137">Щелкните **Пул из одного компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2eab8-138">В разделе **Выбор компонентов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-139">Если вы планируете использовать одно полное доменное имя и IP-адрес для службы доступа SIP, службы веб-конференций Lync Server 2013 и пограничного сервера аудио-и видеоданных, установите флажок **использовать одно полное доменное имя и IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="2eab8-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="2eab8-140">Если вы планируете включить федерацию, установите **Включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p108">Вы можете выбрать этот параметр, но только один пограничный пул или пограничный сервер в организации может быть опубликован внешне для федерации. Весь доступ федеративных пользователей, в том числе пользователей общедоступных служб обмена мгновенными сообщениями, осуществляется через один пограничный пул или пограничный сервер. Например, если развертывание содержит пограничный пул или один пограничный сервер в Нью-Йорке, и другой пограничный сервер в Лондоне и вы включаете поддержку федерации в нью-йоркском пуле или на одном пограничном сервере, трафик для федеративных пользователей будет передаваться через нью-йоркский пул или один пограничный сервер. Это справедливо даже для взаимодействия с лондонскими пользователями, хотя внутренние пользователи из Лондона, вызывающие федеративного пользователя из Лондона, применяют лондонский пул или пограничный сервер для аудио-видео трафика.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-145">Если для развертывания планируется поддержка расширяемого протокола обмена сообщениями и контроля присутствия (XMPP), установите флажок **Включить поддержку федерации XMPP (порт 5269)**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="2eab8-146">В окне **Выбор параметров IP** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-147">**Включить IPv4 во внутреннем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внутреннему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-148">**Включить IPv6 во внутреннем интерфейсе**: Установите этот флажок, если вы хотите применить IPv6-адрес к внутреннему интерфейсу пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-149">**Включить IPv4 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="2eab8-150">**Включить IPv6 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv6-адрес к внешнему серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="2eab8-151">Вы также можете настроить пограничный сервер или пограничный пул на использование адреса преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="2eab8-152">Для этого установите флажок **Внешний IP-адрес пограничного пула преобразуется службой NAT**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="2eab8-153">В разделе **Внешние полные доменные имена** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-154">Если в окне **Выбор компонентов** вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите полное доменное имя в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p110">Если выбран данный параметр, необходимо указать различные номера портов для каждой из пограничных служб (рекомендуемые порты: 5061 для пограничной службы доступа, 444 для службы веб-конференций и 443 для пограничной службы аудио- и видеоданных). Выбор этого параметра позволяет предотвратить потенциальные проблемы с подключением и упростить настройку, поскольку вы сможете использовать один номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-157">Если в окне **Выбор компонентов** вы не выбрали использование одного полного доменного имени и IP-адреса, введите внешние полные доменные имена для **доступа к SIP**, **веб-конференций** и \*\* аудио- и видео данных\*\*, сохранив порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="2eab8-158">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-158">Click **Next**.</span></span>

10. <span data-ttu-id="2eab8-p111">В окне **Определение внутреннего IP-адреса** введите IP-адрес пограничного сервера в поле **Внутренний IPv4-адрес** и **Внутренний IPv6-адрес**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="2eab8-161">В окне **Определение внешнего IP-адреса** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-162">Если вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv4-адрес пограничного сервера в поле **Доступ к SIP**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="2eab8-163">Если вы решили использовать IPv6-адреса, введите внешний IPv6-адрес пограничного сервера в поле **Доступ к SIP**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="2eab8-164">Если вы не выбирали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv4-адрес пограничного сервера в поле **Доступ к SIP**, **Веб-конференции** и **Аудио- и видеоконференции**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="2eab8-165">Если вы выбрали использование IPv6-адресов и не выбирали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv6-адрес пограничного сервера в поле **Доступ к SIP**, **Веб-конференции** и **Аудио- и видеоконференции**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-166">Если не было выбрано включение и назначение адресов IPv6, это диалоговое окно не будет открываться.</span><span class="sxs-lookup"><span data-stu-id="2eab8-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="2eab8-p112">Если используется NAT, появится диалоговое окно. В поле **Общедоступный IPv4-адрес для пограничной службы обработки аудио- и видеоданных** введите IPv4-адрес для трансляции с помощью NAT, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-169">Это должен быть внешний IP-адрес пограничной службы аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="2eab8-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="2eab8-p113">Если используется NAT и IPv6-адреса, появится диалоговое окно. В поле **Общедоступный IPv6-адрес для пограничной службы обработки аудио- и видеоданных** введите IPv6-адрес для трансляции с помощью NAT, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-172">Это должен быть внешний IP-адрес службы пограничного сервера аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="2eab8-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="2eab8-p114">В окне **Определение следующего прыжка** в списке **Следующий пул прыжков** выберите имя внутреннего пула, которым может быть пул переднего плана или пул Standard Edition. Или же, если в развертывании используется Директор, выберите его. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="2eab8-176">В окне **Связь пулов переднего плана** выберите один или несколько внутренних пулов, к которым могут относиться пулы переднего плана и серверы Standard Edition, для связи с этим пограничным сервером, выбрав имена внутренних пулов, которые будут использовать этот пограничный сервер для взаимодействия с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="2eab8-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-p115">Только один пограничный пул или один пограничный сервер с балансировкой нагрузки можно связать с каждым внутренним пулом для трафика аудио- и видеоданных. Если у вас уже есть внутренний пул, связанные с пограничным пулом или пограничным сервером, отображается предупреждение о том, что внутренний пул уже связан с пограничным пулом или сервером. При выборе пула, который уже связан с другим пограничным сервером, связь будет изменена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="2eab8-180">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-180">Click **Finish**.</span></span>

17. <span data-ttu-id="2eab8-181">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="2eab8-182">Определение топологии пула пограничных серверов с балансировкой нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="2eab8-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="2eab8-183">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2eab8-184">В дереве консоли разверните сайт, на котором требуется развернуть пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="2eab8-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="2eab8-185">Щелкните правой кнопкой мыши **Пограничные пулы**, а затем выберите команду **Создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="2eab8-186">В окне **Определение нового пограничного пула** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="2eab8-187">В окне **Определение полного доменного имени пограничного пула** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-188">В поле **Полное доменное имя пула** введите полное доменное имя (FQDN) внутреннего подключения пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="2eab8-189">Указанное имя пула должно быть именем внутреннего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="2eab8-190">Оно должно быть задано как полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="2eab8-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="2eab8-191">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2eab8-192">Используйте только стандартные символы (в том числе A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверов Lync Server, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="2eab8-193">Не используйте символы Юникода или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2eab8-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2eab8-194">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-системами и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="2eab8-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-195">Щелкните **Пул из нескольких компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2eab8-196">В разделе **Выбор компонентов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-197">Если вы планируете использовать одно полное доменное имя и IP-адрес для службы доступа SIP, Lync Server 2013 и пограничные службы аудио-и видеоданных, установите флажок **использовать одно полное доменное имя и IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="2eab8-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="2eab8-p117">Если вы планируете включить федерацию, установите **Включить федерацию для этого пограничного пула (порт 5061)**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p118">Вы можете выбрать этот параметр, но только один пограничный пул или пограничный сервер в организации может быть опубликован внешне для федерации. Весь доступ федеративных пользователей, в том числе пользователей общедоступных служб обмена мгновенными сообщениями, осуществляется через один пограничный пул или пограничный сервер. Например, если развертывание содержит пограничный пул или один пограничный сервер в Нью-Йорке, и другой пограничный сервер в Лондоне и вы включаете поддержку федерации в нью-йоркском пуле или на одном пограничном сервере, трафик для федеративных пользователей будет передаваться через нью-йоркский пул или один пограничный сервер. Это справедливо даже для взаимодействия с лондонскими пользователями, хотя внутренние пользователи из Лондона, вызывающие федеративного пользователя из Лондона, применяют лондонский пул или пограничный сервер для аудио-видео трафика.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-204">Если для развертывания планируется поддержка расширяемого протокола обмена сообщениями и контроля присутствия (XMPP), установите флажок **Включить поддержку федерации XMPP (порт 5269)**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="2eab8-205">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-205">Click **Next**.</span></span>

8.  <span data-ttu-id="2eab8-206">В окне **Выбор параметров IP** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-207">**Включить IPv4 во внутреннем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внутреннему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-208">**Включить IPv6 во внутреннем интерфейсе**: Установите этот флажок, если вы хотите применить IPv6-адрес к внутреннему интерфейсу пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-209">**Включить IPv4 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="2eab8-210">**Включить IPv6 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv6-адрес к внешнему серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="2eab8-211">Вы также можете настроить пограничный сервер или пограничный пул на использование адреса преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="2eab8-212">Для этого установите флажок **Внешний IP-адрес пограничного пула преобразуется службой NAT**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="2eab8-213">В разделе **Внешние полные доменные имена** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-214">Если в окне **Выбор компонентов** вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите полное доменное имя в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p120">Если выбран данный параметр, необходимо указать различные номера портов для каждой из пограничных служб (рекомендуемые порты: 5061 для пограничной службы доступа, 444 для службы веб-конференций и 443 для пограничной службы аудио- и видеоданных). Выбор этого параметра позволяет предотвратить потенциальные проблемы с подключением и упростить настройку, поскольку вы сможете использовать один номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-p121">Если в окне **Выбор компонентов** использование одного полного доменного имени IP-адреса, введите полное доменное имя, выбранное для общедоступной стороны пограничного пула, в поле **Доступ к SIP**. В поле **Веб-конференции** введите полное доменное имя, выбранное для общедоступной стороны пограничного пула. В поле **Аудио и видео** введите полное доменное имя, выбранное для общедоступной стороны пограничного пула. Используйте порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="2eab8-221">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-221">Click **Next**.</span></span>

11. <span data-ttu-id="2eab8-222">В окне **Определение компьютеров в этом пуле** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="2eab8-223">В окне **Определение внешнего IP-адреса** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-224">В поле **Внутренний IPv4-адрес** введите IPv4-адрес и **Внутренний IPv6-адрес** первого пограничного сервера, который необходимо создать в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="2eab8-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="2eab8-225">В поле **Внутреннее полное доменное имя** введите полное доменное имя первого пограничного сервера, который необходимо создать в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="2eab8-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-226">Указанное имя должно совпадать с именем компьютера, заданным на сервере.</span><span class="sxs-lookup"><span data-stu-id="2eab8-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="2eab8-227">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="2eab8-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2eab8-228">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2eab8-229">Поэтому вы должны настроить суффикс DNS в имени компьютера, который будет развернут как пограничный сервер, не присоединенный к домену.</span><span class="sxs-lookup"><span data-stu-id="2eab8-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2eab8-230">Используйте только стандартные символы (в том числе A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверов Lync Server, пограничных серверов, пулов и массивов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="2eab8-231">Не используйте символы Юникода или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2eab8-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2eab8-232">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-системами и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="2eab8-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="2eab8-233">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера приведены <A href="lync-server-2013-configure-dns-for-edge-support.md">в статье Настройка DNS для поддержки пограничного сервера в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2eab8-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="2eab8-234">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-234">Click **Next**.</span></span>

14. <span data-ttu-id="2eab8-235">В окне **Определение внешних IP-адресов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-236">Если вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IP-адрес пограничного сервера в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="2eab8-p123">Если вы не выбирали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула, в поле **Доступ к SIP**. В поле **Веб-конференции** введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула. В поле **Аудио- и видеоконференции** введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="2eab8-240">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-240">Click **Next**.</span></span>

16. <span data-ttu-id="2eab8-241">Если выбрано включение адресов IPv6, выполните в диалоговом окне **Определение внешних IP-адресов** следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-242">Если вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv6-адрес пограничного сервера в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="2eab8-p124">Если не было выбрано использование полного имени домена и IP-адреса для SIP-доступа, веб-службы конференц-связи и службы аудио- и видеоконференц-связи, введите для **SIP-доступа** IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула. В окне **Веб-конференц-связь** введите IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула. В окне **Аудио- и видеоконференц-связь** введите IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-246">Если не было выбрано включение и назначение адресов IPv6, это диалоговое окно не будет открываться.</span><span class="sxs-lookup"><span data-stu-id="2eab8-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="2eab8-247">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-248">Вы увидите первый пограничный сервер, созданный в пуле в диалоговом окне <STRONG>Определение компьютеров в этом пуле</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2eab8-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="2eab8-249">В окне **Определение компьютеров в этом пуле** нажмите кнопку **Добавить**, а затем повторите шаги 11-14 для второго пограничного сервера, который нужно добавить в пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="2eab8-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="2eab8-250">После повторения шагов 11-14 нажмите кнопку **Далее** в окне **Определение компьютеров в этом пуле**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-251">На этом этапе вы можете увидеть оба пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="2eab8-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="2eab8-p125">Если используется NAT, появится диалоговое окно. В поле **Общедоступный IP-адрес** введите IPv4- и IPv6-адреса для трансляции с помощью NAT, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-254">Это должен быть внешний IP-адрес пограничной службы аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="2eab8-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="2eab8-p126">В окне **Определение следующего прыжка** в списке **Следующий пул прыжков** выберите имя внутреннего пула, которым может быть пул переднего плана или пул Standard Edition. Или же, если в развертывании используется Директор, выберите имя Директора. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="2eab8-258">В окне **Связь пулов переднего плана** выберите один или несколько внутренних пулов, к которым могут относиться пулы переднего плана и серверы Standard Edition, для связи с этим пограничным сервером, выбрав имена внутренних пулов, которые будут использовать этот пограничный сервер для взаимодействия с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="2eab8-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-p127">Только один пограничный пул или один пограничный сервер с балансировкой нагрузки можно связать с каждым внутренним пулом для трафика аудио- и видеоданных. Если у вас уже есть внутренний пул, связанные с пограничным пулом или пограничным сервером, отображается предупреждение о том, что внутренний пул уже связан с пограничным пулом или сервером. При выборе пула, который уже связан с другим пограничным сервером, связь будет изменена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="2eab8-262">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-262">Click **Finish**.</span></span>

24. <span data-ttu-id="2eab8-263">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="2eab8-264">Определение топологии для пула пограничных серверов с балансировкой нагрузки оборудования</span><span class="sxs-lookup"><span data-stu-id="2eab8-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="2eab8-265">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2eab8-266">В дереве консоли разверните сайт, на котором требуется развернуть пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="2eab8-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="2eab8-267">Щелкните правой кнопкой мыши **пограничные пулы**, а затем выберите **создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="2eab8-268">В окне **Определение нового пограничного пула** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="2eab8-269">В окне **Определение полного доменного имени пограничного пула** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-270">В поле **Полное доменное имя пула** введите полное доменное имя (FQDN), выбранное для внутреннего сайта пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="2eab8-271">Указанное имя пула должно быть именем внутреннего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="2eab8-272">Оно должно быть задано как полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="2eab8-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="2eab8-273">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2eab8-274">Используйте только стандартные символы (в том числе A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверов Lync Server, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="2eab8-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="2eab8-275">Не используйте символы Юникода или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2eab8-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2eab8-276">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-системами и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="2eab8-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="2eab8-277">Выберите пункт **несколько пулов компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="2eab8-278">В разделе **Выбор компонентов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="2eab8-279">Если вы планируете использовать одно полное доменное имя и IP-адрес для службы доступа SIP, службы веб-конференций Lync Server и пограничной службы аудио-и видеоданных, установите флажок **использовать одно полное доменное имя & IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="2eab8-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="2eab8-280">Если вы планируете включить федерацию, установите **Включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p129">Вы можете выбрать этот параметр, но только один пограничный пул или пограничный сервер в организации может быть опубликован внешне для федерации. Весь доступ федеративных пользователей, в том числе пользователей общедоступных служб обмена мгновенными сообщениями, осуществляется через один пограничный пул или пограничный сервер. Например, если развертывание содержит пограничный пул или один пограничный сервер в Нью-Йорке, и другой пограничный сервер в Лондоне и вы включаете поддержку федерации в нью-йоркском пуле или на одном пограничном сервере, трафик для федеративных пользователей будет передаваться через нью-йоркский пул или один пограничный сервер. Это справедливо даже для взаимодействия с лондонскими пользователями, хотя внутренние пользователи из Лондона, вызывающие федеративного пользователя из Лондона, применяют лондонский пул или пограничный сервер для аудио-видео трафика.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-285">Если для развертывания планируется поддержка расширяемого протокола обмена сообщениями и контроля присутствия (XMPP), установите флажок **Включить поддержку федерации XMPP (порт 5269)**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="2eab8-286">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-286">Click **Next**.</span></span>

8.  <span data-ttu-id="2eab8-287">В окне **Выбор параметров IP** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-288">**Включить IPv4 во внутреннем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внутреннему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-289">**Включить IPv6 во внутреннем интерфейсе**: Установите этот флажок, если вы хотите применить IPv6-адрес к внутреннему интерфейсу пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="2eab8-290">**Включить IPv4 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="2eab8-291">**Включить IPv6 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv6-адрес к внешнему серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2eab8-p130"><STRONG>Не</STRONG> устанавливайте флажок <STRONG>Внешний IP-адрес пограничного пула преобразуется службой NAT</STRONG>. Трансляция сетевых адресов (NAT) не поддерживается при балансировки нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="2eab8-294">В разделе **Внешние полные доменные имена** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-295">Если в окне **Выбор компонентов** вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите полное доменное имя в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-p131">Если выбран данный параметр, необходимо указать различные номера портов для каждой из пограничных служб (рекомендуемые порты: 5061 для пограничной службы доступа, 444 для службы веб-конференций и 443 для пограничной службы аудио- и видеоданных). Выбор этого параметра позволяет предотвратить потенциальные проблемы с подключением и упростить настройку, поскольку вы сможете использовать один номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="2eab8-p132">Если в окне **Выбор компонентов** использование одного полного доменного имени IP-адреса, введите полное доменное имя, выбранное для общедоступной стороны пограничного пула, в поле **Доступ к SIP**. В поле **Веб-конференции** введите полное доменное имя, выбранное для общедоступной стороны пограничного пула. В поле **Аудио и видео** введите полное доменное имя, выбранное для общедоступной стороны пограничного пула. Используйте порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2eab8-302">Это будут общедоступные полные доменные имена виртуальных IP-адресов (VIP) для пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="2eab8-303">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-303">Click **Next**.</span></span>

11. <span data-ttu-id="2eab8-304">В окне **Определение компьютеров в этом пуле** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="2eab8-305">В окне **Определение внешних IP-адресов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2eab8-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-306">Если вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv4-адрес пограничного сервера в поле **Доступ к SIP**. Внешний IP-адрес пограничного сервера в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="2eab8-p133">Если вы не выбирали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула, в поле **Доступ к SIP**. В поле **Веб-конференции** введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула. В поле **Аудио- и видеоконференции** введите IP-адрес, выбранный для общедоступной стороны сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="2eab8-310">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-310">Click **Next**.</span></span>

14. <span data-ttu-id="2eab8-311">Если выбрано включение адресов IPv6, выполните в диалоговом окне **Определение внешних IP-адресов** следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2eab8-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="2eab8-312">Если вы выбрали использование одного полного доменного имени IP-адреса для доступа к SIP, службе веб-конференций и пограничной службе аудио- и видеоданных, введите внешний IPv6-адрес пограничного сервера в поле **Доступ к SIP**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="2eab8-p134">Если не было выбрано использование полного имени домена и IP-адреса для SIP-доступа, веб-службы конференц-связи и службы аудио- и видеоконференц-связи, введите для **SIP-доступа** IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула. В окне **Веб-конференц-связь** введите IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула. В окне **Аудио- и видеоконференц-связь** введите IPv6-адрес, выбранный для открытой клиентской стороны данного сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-316">Если не было выбрано включение и назначение адресов IPv6, это диалоговое окно не будет открываться.</span><span class="sxs-lookup"><span data-stu-id="2eab8-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="2eab8-317">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-318">Вы увидите первый пограничный сервер, созданный в пуле в диалоговом окне <STRONG>Определение компьютеров в этом пуле</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2eab8-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="2eab8-319">В окне **Определение компьютеров в этом пуле** нажмите кнопку **Добавить**, а затем повторите шаги 11-14 для второго пограничного сервера, который нужно добавить в пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="2eab8-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="2eab8-320">После повторения шагов 11-14 нажмите кнопку **Далее** в окне **Определение компьютеров в этом пуле**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-321">На этом этапе вы можете увидеть оба пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="2eab8-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="2eab8-p135">В окне **Определение следующего прыжка** в списке **Следующий пул прыжков** выберите имя внутреннего пула, которым может быть пул переднего плана или пул Standard Edition. Или же, если в развертывании используется Директор, выберите имя Директора. Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="2eab8-325">В окне **Связь пулов переднего плана** выберите один или несколько внутренних пулов, к которым могут относиться пулы переднего плана и серверы Standard Edition, для связи с этим пограничным сервером, выбрав имена внутренних пулов, которые будут использовать этот пограничный сервер для взаимодействия с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="2eab8-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2eab8-p136">Только один пограничный пул или один пограничный сервер с балансировкой нагрузки можно связать с каждым внутренним пулом для трафика аудио- и видеоданных. Если у вас уже есть внутренний пул, связанные с пограничным пулом или пограничным сервером, отображается предупреждение о том, что внутренний пул уже связан с пограничным пулом или сервером. При выборе пула, который уже связан с другим пограничным сервером, связь будет изменена.</span><span class="sxs-lookup"><span data-stu-id="2eab8-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="2eab8-329">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2eab8-329">Click **Finish**.</span></span>

21. <span data-ttu-id="2eab8-330">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="2eab8-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

