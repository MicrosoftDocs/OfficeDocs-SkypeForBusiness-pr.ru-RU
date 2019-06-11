---
title: 'Lync Server 2013: определение пограничной топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="d0f06-102">Определение пограничной топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f06-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0f06-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d0f06-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d0f06-104">Для создания топологии вы должны использовать построитель топологии, а перед развертыванием пограничного сервера нужно настроить хотя бы один внутренний пул внешних интерфейсов или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d0f06-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="d0f06-105">Используйте описанную ниже процедуру, чтобы определить топологию пограничного сервера, и выполните действия, описанные в разделе [Публикация топологии в Lync server 2013](lync-server-2013-publish-your-topology.md) и [Экспорт топологии сервера Lync Server 2013 и копирование ее на внешние носители для установки пограничного устройства](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) . чтобы опубликовать топологию и сделать ее доступной для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d0f06-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0f06-106">Балансировка нагрузки на внутреннем и внешнем пограничным интерфейсах должна относиться к одному и тому же типу.</span><span class="sxs-lookup"><span data-stu-id="d0f06-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="d0f06-107">Невозможно осуществлять балансировку нагрузки на одном пограничном интерфейсе средствами DNS, а на другом — аппаратными средствами.</span><span class="sxs-lookup"><span data-stu-id="d0f06-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="d0f06-108">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, необходимо войти в систему в качестве пользователя, который является членом группы администраторов Рткуниверсалсерверадминс и domain.</span><span class="sxs-lookup"><span data-stu-id="d0f06-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="d0f06-109">Вы также можете предоставить права администратора и разрешения, необходимые для добавления ролей сервера в учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d0f06-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="d0f06-110">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition Server или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="d0f06-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="d0f06-111">Для других изменений конфигурации требуется только членство в группе Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="d0f06-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="d0f06-112">Если вы определили топологию пограничного сервера при определении и публикации внутренней топологии, а также не требуется, чтобы топология Edge была ранее определена, вам не нужно определять ее и повторно публиковать ее.</span><span class="sxs-lookup"><span data-stu-id="d0f06-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="d0f06-113">Используйте описанную ниже процедуру только в том случае, если вам необходимо внести изменения в топологию Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="d0f06-114">Вы должны сделать определенную и опубликованную топологию доступной для пограничного сервера, выполнив действия, описанные в разделе [Экспорт топологии Lync Server 2013, и скопировать ее на внешний носитель для установки пограничного устройства](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="d0f06-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0f06-115">Построитель топологии нельзя запустить с пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d0f06-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="d0f06-116">Вы должны запустить ее на сервере переднего плана или на серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d0f06-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="d0f06-117">Процесс определения топологии пограничного сервера выполняется в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="d0f06-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="d0f06-118">Ниже перечислены три основных типа топологий пограничного сервера, которые вы планируете и настраиваете.</span><span class="sxs-lookup"><span data-stu-id="d0f06-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="d0f06-119">Определение топологии для одного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d0f06-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="d0f06-120">Определение топологии для пула пограничного сервера с балансировкой нагрузки</span><span class="sxs-lookup"><span data-stu-id="d0f06-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="d0f06-121">Определение топологии для пула Edge с балансировкой нагрузки для оборудования</span><span class="sxs-lookup"><span data-stu-id="d0f06-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="d0f06-122">Определение топологии для одного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d0f06-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="d0f06-123">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d0f06-124">В дереве консоли разверните сайт, на котором вы хотите развернуть пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="d0f06-125">Щелкните правой кнопкой мыши группу **пограничных групп**и выберите команду **создать пул пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="d0f06-126">В окне **Определение нового пула пограничного сервера**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="d0f06-127">В разделе **Определение полного доменного имени пула пограничного сервера**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-128">В поле **FQDN пула**введите полное доменное имя (FQDN) внутреннего интерфейса для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d0f06-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d0f06-129">Указанное имя должно быть идентично имени компьютера, настроенному на сервере.</span><span class="sxs-lookup"><span data-stu-id="d0f06-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="d0f06-130">По умолчанию имя компьютера, не подключенного к домену, является коротким именем, а не FQDN.</span><span class="sxs-lookup"><span data-stu-id="d0f06-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="d0f06-131">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="d0f06-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d0f06-132">Поэтому для компьютера, развертываемого в качестве пограничного сервера, не присоединенного к домену, потребуется указать DNS-суффикс.</span><span class="sxs-lookup"><span data-stu-id="d0f06-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d0f06-133">Используйте только стандартные символы (A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам.</span><span class="sxs-lookup"><span data-stu-id="d0f06-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d0f06-134">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d0f06-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0f06-135">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="d0f06-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="d0f06-136">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера можно найти <A href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка поддержки DNS для Microsoft EDGE в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0f06-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-137">Выберите **один пул компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d0f06-138">В окне **выбора функций**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-139">Если вы планируете использовать одно полное доменное имя и IP-адрес для службы доступа к SIP, Lync Server 2013 для веб-конференций и служб EDGE, установите флажок **использовать одно полное доменное имя и IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="d0f06-140">Если вы планируете включить федерацию, установите флажок **включить федерацию для этого пограничного пула (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-141">Вы можете выбрать этот параметр, но только один пул пограничного сервера или граничный сервер в вашей организации может быть опубликован извне для Федерации.</span><span class="sxs-lookup"><span data-stu-id="d0f06-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="d0f06-142">Весь доступ федеративных пользователей, в том числе пользователей общедоступной службы обмена мгновенными сообщениями, используйте один и тот же пул пограничного сервера или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-143">Например, если в развертывании есть пограничный пул или однограничный сервер, развернутый в Нью — Москва, а затем включена поддержка Федерации в пуле EDGE или однограничный сервер, трафик сигналов для федеративных пользователей будет проходить через Нью Йорк. Пограничный пул или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-144">Это справедливо даже для пользователей в Лондоне, хотя при вызове внутренним пользователем лондонского филиала федеративного пользователя в Лондоне трафик аудио- и видеосвязи будет идти через лондонский пограничный пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-145">Если вы планируете поддерживать расширяемый протокол обмена сообщениями (КСМПП) для развертывания, установите флажок **включить федерацию КСМПП (порт 5269)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="d0f06-146">В окне **выберите параметры IP-адреса**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-147">**Включить IPv4 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv4-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-148">**Включить IPv6 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-149">**Включение IPv4 во внешнем интерфейсе**: Установите этот флажок, если вы хотите применить IPv4-адрес к внешнему серверу пограничного сервера или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="d0f06-150">**Включить IPv6 во внешнем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему серверу или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="d0f06-151">Вы также можете настроить пограничный сервер или пул EDGE, чтобы использовать адрес преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="d0f06-152">Для этого установите флажок **внешний IP-адрес этого пограничного пула преобразуется посредством NAT**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="d0f06-153">Во **внешних полных доменных именах**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-154">Если в **выбранных функциях** выбрано использование одного полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы EDGE, введите внешнее полное доменное имя в **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-155">Если выбрать этот параметр, необходимо указать другой номер порта для каждой службы пограничного сервера (Рекомендуемые параметры порта: 5061 для службы Edge Access, 444 для службы Edge для веб-конференций и 443 для службы EDGE).</span><span class="sxs-lookup"><span data-stu-id="d0f06-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="d0f06-156">Выбор этого параметра поможет предотвратить возможные проблемы с подключением и упростит конфигурацию, так как вы можете использовать один и тот же номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="d0f06-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-157">Если в разделе **Выбор компонентов** , для которых не выбрано одно полное доменное имя и IP-адрес, введите внешние полные доменные имена для **доступа к SIP**, **веб-конференции** и **звукового видео**, сохранив порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="d0f06-158">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-158">Click **Next**.</span></span>

10. <span data-ttu-id="d0f06-159">В разделе **определение внутреннего IP-адреса**введите IP-адрес пограничного сервера по **внутреннему адресу IPv4** и внутреннему IPv6- **адресу** , как в соответствии с вашими требованиями.</span><span class="sxs-lookup"><span data-stu-id="d0f06-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="d0f06-160">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-160">Click **Next**.</span></span>

11. <span data-ttu-id="d0f06-161">В разделе **Определение внешнего IP-адреса**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-162">Если вы решили использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций и службы EDGE, введите внешний IPv4-адрес пограничного сервера в поле **SIP Access**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="d0f06-163">Если вы решили использовать IPv6-адреса, введите внешний IPv6-адрес пограничного сервера в поле **SIP Access**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="d0f06-164">Если вы не выбрали использование единого полного доменного имени и IP-адреса для доступа по протоколу SIP, службы веб-конференций и службы EDGE, введите внешние IPv4-адреса пограничного сервера в " **доступ к SIP**", " **конференции через Интернет**" и в конференц-связи **с/v**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d0f06-165">Если вы решили использовать IPv6-адреса и не выбрали использование единого полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы EDGE, введите внешние адреса IPv6 пограничного сервера в **доступ SIP**, **веб-конференции**и **a/ V Конференция**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-166">Если вы не решили включить и назначить адресацию IPv6, диалоговое окно не появится.</span><span class="sxs-lookup"><span data-stu-id="d0f06-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="d0f06-167">Если вы решили использовать NAT, появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d0f06-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="d0f06-168">В **общедоступном IPv4-адресе для службы Edge/V**введите общедоступный IPv4-адрес, который нужно перевести NAT, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-169">Это должен быть внешний IP-адрес службы Edge/V.</span><span class="sxs-lookup"><span data-stu-id="d0f06-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="d0f06-170">Если вы решили использовать адреса NAT и IPv6, появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d0f06-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="d0f06-171">В **общедоступном IPv6-адресе для службы Edge/V**введите общедоступный IPv6-адрес, который нужно перевести с помощью NAT, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-172">Это должен быть внешний IP-адрес службы Edge/V.</span><span class="sxs-lookup"><span data-stu-id="d0f06-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="d0f06-173">В разделе **определение следующего прыжка**в **пуле очередного прыжка**выберите имя внутреннего пула, который может быть либо интерфейсным пулом, либо стандартным пулом выпуска.</span><span class="sxs-lookup"><span data-stu-id="d0f06-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="d0f06-174">Если в развертывании есть режиссер, выберите режиссер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="d0f06-175">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="d0f06-176">В разделе **сопоставление интерфейсных пулов**добавьте один или несколько внутренних пулов, которые могут включать в себя пулы интерфейсных служб и серверы стандартных выпусков, которые должны быть связаны с этим пограничным сервером, выбирая имена внутренних пулов, которые должны использовать этот сервер пограничного сервера. связь с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="d0f06-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-177">С каждым внутренним пулом может быть связан только один граничный пул с балансировкой нагрузки или один граничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="d0f06-178">Если у вас уже есть внутренний пул, связанный с пограничным пулом или пограничным сервером, появится предупреждение о том, что внутренний пул уже связан с граничным пулом или пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="d0f06-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="d0f06-179">Выбор пула, уже связанного с другим пограничным сервером, приводит к изменению связи.</span><span class="sxs-lookup"><span data-stu-id="d0f06-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="d0f06-180">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-180">Click **Finish**.</span></span>

17. <span data-ttu-id="d0f06-181">Опубликуйте свою топологию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="d0f06-182">Определение топологии для пула пограничного сервера балансировки нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="d0f06-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="d0f06-183">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d0f06-184">В дереве консоли разверните сайт, на котором вы хотите развернуть пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="d0f06-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="d0f06-185">Щелкните правой кнопкой мыши группу **пограничных групп**и выберите команду **создать пул пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="d0f06-186">В окне **Определение нового пула пограничного сервера**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="d0f06-187">В разделе **Определение полного доменного имени пула пограничного сервера**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-188">В поле **FQDN пула**введите полное доменное имя (FQDN) для внутреннего подключения пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d0f06-189">Имя, указанное для пула, должно быть внутренним именем пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="d0f06-190">Оно должно быть определено как полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="d0f06-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="d0f06-191">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="d0f06-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d0f06-192">Используйте только стандартные символы (A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам.</span><span class="sxs-lookup"><span data-stu-id="d0f06-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d0f06-193">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d0f06-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0f06-194">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="d0f06-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-195">Выберите пункт **несколько групп компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d0f06-196">В окне **выбора функций**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-197">Если вы планируете использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций Lync Server 2013 и служб Edge/V, установите флажок **использовать одно полное доменное имя и IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="d0f06-198">Если вы планируете включить федерацию, установите флажок **включить федерацию для этого пула пограничного сервера (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="d0f06-199">Нажмите кнопку **Next (далее** ).</span><span class="sxs-lookup"><span data-stu-id="d0f06-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-200">Вы можете выбрать этот параметр, но только один пул пограничного сервера или граничный сервер в вашей организации может быть опубликован извне для Федерации.</span><span class="sxs-lookup"><span data-stu-id="d0f06-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="d0f06-201">Весь доступ федеративных пользователей, в том числе пользователей общедоступной службы обмена мгновенными сообщениями, используйте один и тот же пул пограничного сервера или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-202">Например, если в развертывании используется пограничный пул или сервер, развернутый в Нью-Йорке, а также пул или сервер, развернутый в Лондоне, и была включена поддержка федерации в пограничном пуле или сервере Нью-Йорка, сигнальный трафик для федеративных пользователей будет проходить через пограничный пул или сервер в Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="d0f06-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-203">Это справедливо даже для пользователей в Лондоне, хотя при вызове внутренним пользователем лондонского филиала федеративного пользователя в Лондоне трафик аудио- и видеосвязи будет идти через лондонский пограничный пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-204">Если вы планируете поддерживать расширяемый протокол обмена сообщениями (КСМПП) для развертывания, установите флажок **включить федерацию КСМПП (порт 5269)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="d0f06-205">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-205">Click **Next**.</span></span>

8.  <span data-ttu-id="d0f06-206">В окне **выберите параметры IP-адреса**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-207">**Включить IPv4 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv4-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-208">**Включить IPv6 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-209">**Включение IPv4 во внешнем интерфейсе**: Установите этот флажок, если вы хотите применить IPv4-адрес к внешнему серверу пограничного сервера или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="d0f06-210">**Включить IPv6 во внешнем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему серверу или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="d0f06-211">Вы также можете настроить пограничный сервер или пул EDGE, чтобы использовать адрес преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="d0f06-212">Для этого установите флажок **внешний IP-адрес этого пограничного пула преобразуется посредством NAT**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="d0f06-213">Во **внешних полных доменных именах**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-214">Если в **выбранных функциях** выбрано использование одного полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы EDGE, введите внешнее полное доменное имя в **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-215">Если выбрать этот параметр, необходимо указать другой номер порта для каждой службы пограничного сервера (Рекомендуемые параметры порта: 5061 для службы Edge Access, 444 для службы Edge для веб-конференций и 443 для службы EDGE).</span><span class="sxs-lookup"><span data-stu-id="d0f06-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="d0f06-216">Выбрав этот параметр, вы можете предотвратить возможные проблемы с подключением и упростить настройку, так как вы можете использовать один и тот же номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="d0f06-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-217">Если в разделе **Выбор компонентов** , которые не использовали один и тот же доменный адрес, введите полное доменное имя, которое вы выбрали для общедоступной стороны пула EDGE, для **доступа**по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="d0f06-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="d0f06-218">В разделе **веб-конференции**введите полное доменное имя, которое вы выбрали для общедоступной стороны пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="d0f06-219">В поле **аудио/видео**введите полное доменное имя, которое вы выбрали для общедоступной стороны пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="d0f06-220">Используйте порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-220">Use the default ports.</span></span>

10. <span data-ttu-id="d0f06-221">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-221">Click **Next**.</span></span>

11. <span data-ttu-id="d0f06-222">В разделе **Определение компьютеров в этом пуле**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="d0f06-223">Для **внутренних полных доменных имен и IP-адресов**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-224">В поле **внутренний адрес IPv4**введите адрес IPv4 и **Внутренний IPv6-** адрес в соответствии с требованиями для первого пограничного сервера, который вы хотите создать в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="d0f06-225">В поле **внутренний доменное имя**введите полное доменное имя (FQDN) первого пограничного сервера, который вы хотите создать в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-226">Указываемое вами имя должно в точности совпадать с настроенным на сервере именем компьютера.</span><span class="sxs-lookup"><span data-stu-id="d0f06-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="d0f06-227">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="d0f06-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="d0f06-228">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="d0f06-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d0f06-229">Поэтому для компьютера, развертываемого в качестве пограничного сервера, не присоединенного к домену, потребуется указать DNS-суффикс.</span><span class="sxs-lookup"><span data-stu-id="d0f06-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d0f06-230">Для назначения полных доменных имен серверам Lync, пограничным серверам, пулам и массивам используйте только стандартные символы (включая A-Z, a-z, 0 – 9 и дефисы).</span><span class="sxs-lookup"><span data-stu-id="d0f06-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="d0f06-231">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d0f06-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0f06-232">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="d0f06-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="d0f06-233">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера можно найти <A href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка поддержки DNS для Microsoft EDGE в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0f06-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="d0f06-234">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-234">Click **Next**.</span></span>

14. <span data-ttu-id="d0f06-235">В разделе **Определение внешних IP-адресов**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-236">Если вы решили использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций и службы EDGE, введите внешний IP-адрес пограничного сервера в **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="d0f06-237">Если вы не выбрали использование единого полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы конференции/V, введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула, для **доступа к SIP**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="d0f06-238">В разделе **веб-конференции**введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="d0f06-239">В **конференц-связи с**телефонным подключением введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="d0f06-240">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-240">Click **Next**.</span></span>

16. <span data-ttu-id="d0f06-241">Если вы решили включить IPv6-адреса, в разделе **Определение внешних IP-адресов**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-242">Если вы решили использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций и службы EDGE, введите внешний IPv6-адрес пограничного сервера в поле **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="d0f06-243">Если вы не выбрали использование единого полного доменного имени и IP-адреса для доступа по протоколу SIP, службы веб-конференций и службы конференции/V, введите адрес IPv6, выбранный для общедоступной стороны этого сервера пограничного пула, для **доступа к SIP**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="d0f06-244">В разделе **веб-конференции**введите адрес IPv6, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="d0f06-245">В **конференц-связи с**телефонным подключением введите IPv6-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-246">Если вы не решили включить и назначить адресацию IPv6, диалоговое окно не появится.</span><span class="sxs-lookup"><span data-stu-id="d0f06-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="d0f06-247">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-248">В диалоговом окне <STRONG>Определение компьютеров в пуле</STRONG> вы увидите первый пограничный сервер, созданный в пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="d0f06-249">В разделе **Определение компьютеров в этом пуле**нажмите кнопку **Добавить**, а затем повторите шаги 11 – 14 для второго пограничного сервера, который вы хотите добавить в пул Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="d0f06-250">После повторения шагов 11 – 14 нажмите **Далее** в разделе **Определение компьютеров в этом пуле**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-251">На этом этапе вы видите оба пограничных сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="d0f06-252">Если вы решили использовать NAT, появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d0f06-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="d0f06-253">В **общедоступном IP-адресе**введите адреса IPv4 и IPv6 (при необходимости), которые нужно перевести с помощью NAT, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-254">Это должен быть внешний IP-адрес A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="d0f06-255">В разделе **определение следующего прыжка**в списке **пул следующего прыжка** выберите имя внутреннего пула, которое может быть либо пулом переднего плана, либо стандартным пулом выпусков.</span><span class="sxs-lookup"><span data-stu-id="d0f06-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="d0f06-256">Если в развертывании есть режиссер, выберите его имя.</span><span class="sxs-lookup"><span data-stu-id="d0f06-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="d0f06-257">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="d0f06-258">В разделе **сопоставление интерфейсных пулов**добавьте один или несколько внутренних пулов, которые могут содержать пулы интерфейсов и серверы стандартных выпусков, которые будут связаны с этим пограничным сервером, выбирая имена внутренних пулов, которые должны использовать этот пограничный сервер. связь с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="d0f06-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-259">С каждым внутренним пулом может быть связан только один граничный пул с балансировкой нагрузки или один граничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="d0f06-260">Если у вас уже есть внутренний пул, связанный с пограничным пулом или пограничным сервером, появится предупреждение о том, что внутренний пул уже связан с граничным пулом или пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="d0f06-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="d0f06-261">Выбор пула, уже связанного с другим пограничным сервером, приводит к изменению связи.</span><span class="sxs-lookup"><span data-stu-id="d0f06-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="d0f06-262">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-262">Click **Finish**.</span></span>

24. <span data-ttu-id="d0f06-263">Опубликуйте свою топологию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="d0f06-264">Определение топологии для пула пограничного сервера с балансировкой нагрузки для оборудования</span><span class="sxs-lookup"><span data-stu-id="d0f06-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="d0f06-265">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d0f06-266">В дереве консоли разверните сайт, на котором вы хотите развернуть пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="d0f06-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="d0f06-267">Щелкните правой кнопкой мыши группу **пограничных групп**и выберите пункт **создать пул Edge**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="d0f06-268">В окне **Определение нового пула пограничного сервера**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="d0f06-269">В разделе **Определение полного доменного имени пула пограничного сервера**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-270">В поле **FQDN**введите полное доменное имя (FQDN), выбранное для внутренней стороны пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d0f06-271">Имя, указанное для пула, должно быть внутренним именем пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="d0f06-272">Оно должно быть определено как полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="d0f06-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="d0f06-273">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="d0f06-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d0f06-274">Используйте только стандартные символы (A–Z, a–z, 0–9 и дефис) при назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам.</span><span class="sxs-lookup"><span data-stu-id="d0f06-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d0f06-275">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d0f06-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0f06-276">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS и общедоступными центрами сертификации (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="d0f06-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="d0f06-277">Выберите пункт **несколько групп компьютеров**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="d0f06-278">В разделе **Выбор функций** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="d0f06-279">Если вы планируете использовать одно полное доменное имя и IP-адрес для службы доступа к SIP, службы веб-конференций Lync Server и службы EDGE, установите флажок **использовать одно полное доменное имя & IP-адрес** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="d0f06-280">Если вы планируете включить федерацию, установите флажок **включить федерацию для этого пула пограничного сервера (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-281">Вы можете выбрать этот параметр, но только один граничный пул или граничный сервер в вашей организации могут быть опубликованы извне для Федерации.</span><span class="sxs-lookup"><span data-stu-id="d0f06-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="d0f06-282">Весь доступ федеративных пользователей, в том числе пользователей общедоступной службы обмена мгновенными сообщениями, используйте один и тот же пул пограничного сервера или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-283">Например, если в развертывании используется пограничный пул или сервер, развернутый в Нью-Йорке, а также пул или сервер, развернутый в Лондоне, и была включена поддержка федерации в пограничном пуле или сервере Нью-Йорка, сигнальный трафик для федеративных пользователей будет проходить через пограничный пул или сервер в Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="d0f06-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="d0f06-284">Это справедливо даже для пользователей в Лондоне, хотя при вызове внутренним пользователем лондонского филиала федеративного пользователя в Лондоне трафик аудио- и видеосвязи будет идти через лондонский пограничный пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-285">Если вы планируете поддерживать расширяемый протокол обмена сообщениями (КСМПП) для развертывания, установите флажок **включить федерацию КСМПП (порт 5269)** .</span><span class="sxs-lookup"><span data-stu-id="d0f06-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="d0f06-286">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-286">Click **Next**.</span></span>

8.  <span data-ttu-id="d0f06-287">В окне **выберите параметры IP-адреса**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-288">**Включить IPv4 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv4-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-289">**Включить IPv6 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="d0f06-290">**Включение IPv4 во внешнем интерфейсе**: Установите этот флажок, если вы хотите применить IPv4-адрес к внешнему серверу пограничного сервера или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="d0f06-291">**Включить IPv6 во внешнем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему серверу или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d0f06-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0f06-292"><STRONG></STRONG> Не устанавливайте флажок <STRONG>внешний IP-адрес пограничного пула преобразуется с помощью NAT</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d0f06-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="d0f06-293">Преобразование сетевых адресов (NAT) не поддерживается при использовании аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d0f06-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="d0f06-294">Во **внешних полных доменных именах**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-295">Если в **выбранных функциях** выбрано использование одного полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы EDGE, введите внешнее полное доменное имя в **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-296">Если вы выберете этот параметр, необходимо указать другой номер порта для каждой службы пограничного сервера (Рекомендуемые параметры порта: 5061 для службы Edge Access, 444 для службы Edge для веб-конференций и 443 для службы Edge/V).</span><span class="sxs-lookup"><span data-stu-id="d0f06-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="d0f06-297">Выбрав этот параметр, вы можете предотвратить возможные проблемы с подключением и упростить настройку, так как вы можете использовать один и тот же номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="d0f06-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0f06-298">Если в разделе **Выбор компонентов** , которые не использовали один и тот же доменный адрес, введите полное доменное имя, которое вы выбрали для общедоступной стороны пула EDGE, для **доступа**по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="d0f06-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="d0f06-299">В разделе **веб-конференции**введите полное доменное имя, которое вы выбрали для общедоступной стороны пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="d0f06-300">В поле **аудио/видео**введите полное доменное имя, которое вы выбрали для общедоступной стороны пула Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="d0f06-301">Используйте порты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0f06-302">Это будут общедоступные доменные имена виртуальных IP-адресов для пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="d0f06-303">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-303">Click **Next**.</span></span>

11. <span data-ttu-id="d0f06-304">В разделе **Определение компьютеров в этом пуле**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="d0f06-305">В разделе **Определение внешних IP-адресов**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-306">Если вы решили использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций и службы EDGE, введите внешний адрес IPv4 пограничного сервера в поле **SIP Access**. внешний IP-адрес пограничного сервера в **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="d0f06-307">Если вы не выбрали использование единого полного доменного имени и IP-адреса для доступа к SIP, службы веб-конференций и службы конференции/V, введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула, для **доступа к SIP**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="d0f06-308">В разделе **веб-конференции**введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="d0f06-309">В **конференц-связи с**телефонным подключением введите IP-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="d0f06-310">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-310">Click **Next**.</span></span>

14. <span data-ttu-id="d0f06-311">Если вы решили включить IPv6-адреса, в разделе **Определение внешних IP-адресов**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d0f06-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="d0f06-312">Если вы решили использовать одно полное доменное имя и IP-адрес для доступа к SIP, службы веб-конференций и службы EDGE, введите внешний IPv6-адрес пограничного сервера в поле **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="d0f06-313">Если вы не выбрали использование единого полного доменного имени и IP-адреса для доступа по протоколу SIP, службы веб-конференций и службы конференции/V, введите адрес IPv6, выбранный для общедоступной стороны этого сервера пограничного пула, для **доступа к SIP**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="d0f06-314">В разделе **веб-конференции**введите адрес IPv6, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="d0f06-315">В **конференц-связи с**телефонным подключением введите IPv6-адрес, который вы выбрали для общедоступной стороны этого сервера пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d0f06-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-316">Если вы не решили включить и назначить адресацию IPv6, диалоговое окно не появится.</span><span class="sxs-lookup"><span data-stu-id="d0f06-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="d0f06-317">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-318">В диалоговом окне <STRONG>Определение компьютеров в пуле</STRONG> вы увидите первый пограничный сервер, созданный в пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="d0f06-319">В разделе **Определение компьютеров в этом пуле**нажмите кнопку **Добавить**, а затем повторите шаги 11 – 14 для второго пограничного сервера, который вы хотите добавить в пул Edge.</span><span class="sxs-lookup"><span data-stu-id="d0f06-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="d0f06-320">После повторения шагов 11 – 14 нажмите **Далее** в разделе **Определение компьютеров в этом пуле**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-321">На этом этапе вы видите оба пограничных сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="d0f06-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="d0f06-322">В разделе **определение следующего прыжка**в списке **пул следующего прыжка** выберите имя внутреннего пула, которое может быть либо пулом переднего плана, либо стандартным пулом выпусков.</span><span class="sxs-lookup"><span data-stu-id="d0f06-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="d0f06-323">Если в развертывании есть режиссер, выберите его имя.</span><span class="sxs-lookup"><span data-stu-id="d0f06-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="d0f06-324">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="d0f06-325">В разделе **сопоставление интерфейсных пулов**добавьте один или несколько внутренних пулов, которые могут содержать пулы интерфейсов и серверы стандартных выпусков, которые будут связаны с этим пограничным сервером, выбирая имена внутренних пулов, которые должны использовать этот пограничный сервер. связь с поддерживаемыми внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="d0f06-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f06-326">С каждым внутренним пулом может быть связан только один граничный пул с балансировкой нагрузки или один граничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d0f06-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="d0f06-327">Если у вас уже есть внутренний пул, связанный с пограничным пулом или пограничным сервером, появится предупреждение о том, что внутренний пул уже связан с граничным пулом или пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="d0f06-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="d0f06-328">Выбор пула, уже связанного с другим пограничным сервером, приводит к изменению связи.</span><span class="sxs-lookup"><span data-stu-id="d0f06-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="d0f06-329">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0f06-329">Click **Finish**.</span></span>

21. <span data-ttu-id="d0f06-330">Опубликуйте свою топологию.</span><span class="sxs-lookup"><span data-stu-id="d0f06-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

