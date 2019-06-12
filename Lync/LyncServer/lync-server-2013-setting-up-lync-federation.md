---
title: 'Lync Server 2013: настройка федерации в Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="aed69-102">Настройка федерации в Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aed69-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aed69-103">_**Тема последнего изменения:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="aed69-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="aed69-104">Если вы уже развернули сервер пограничного сервера или серверы, добавьте возможности федеративных сценариев прямо вперед.</span><span class="sxs-lookup"><span data-stu-id="aed69-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="aed69-105">Если вы не настроили пограничные серверы, необходимо сначала сделать это.</span><span class="sxs-lookup"><span data-stu-id="aed69-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="aed69-106">Подробности можно найти в статье [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию и [развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="aed69-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aed69-107">Если вы хотите настроить любое сочетание КСМПП Федерации, Федерации Lync или общедоступной службы обмена мгновенными сообщениями, вы можете развернуть их параллельно или по одной из них по очереди.</span><span class="sxs-lookup"><span data-stu-id="aed69-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="aed69-108">Если вы настроили параметры с помощью построителя топологии и командной консоли Lync Server, а затем запустите мастер развертывания на пограничном сервере после настройки параметров для одного, двух или всех трех типов Федерации, вы можете сократить количество необходимых действий.</span><span class="sxs-lookup"><span data-stu-id="aed69-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="aed69-109">Настройка Федерации Lync в построителе топологии и мастере развертывания</span><span class="sxs-lookup"><span data-stu-id="aed69-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="aed69-110">На сервере переднего плана откройте окно Построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="aed69-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="aed69-111">Разверните узел Edge Pools, а затем щелкните правой кнопкой мыши граничный сервер или пул пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="aed69-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="aed69-112">Нажмите кнопку изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="aed69-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="aed69-113">В диалоговом окне Изменение свойств в разделе Общие установите флажок включить федерацию для этого пограничного пула (порт 5061).</span><span class="sxs-lookup"><span data-stu-id="aed69-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="aed69-114">Нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="aed69-114">Click OK.</span></span>

3.  <span data-ttu-id="aed69-115">Нажмите кнопку действие, выберите пункт топология, нажмите кнопку Опубликовать.</span><span class="sxs-lookup"><span data-stu-id="aed69-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="aed69-116">При появлении запроса на публикацию топологии нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="aed69-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="aed69-117">Завершив публикацию, нажмите кнопку Готово.</span><span class="sxs-lookup"><span data-stu-id="aed69-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="aed69-118">На пограничном сервере откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aed69-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="aed69-119">Щелкните Установка или обновление операционной системы Lync Server, а затем нажмите кнопку Настройка или удалите компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aed69-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="aed69-120">Нажмите кнопку выполнить еще раз.</span><span class="sxs-lookup"><span data-stu-id="aed69-120">Click Run Again.</span></span>

5.  <span data-ttu-id="aed69-121">В разделе Настройка серверных компонентов Lync нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="aed69-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="aed69-122">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="aed69-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="aed69-123">После завершения развертывания щелкните Просмотреть журнал, чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="aed69-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="aed69-124">Нажмите кнопку Готово, чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="aed69-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aed69-125">Вы можете выбрать этот параметр, но только один пул пограничного сервера или граничный сервер в вашей организации может быть опубликован извне для Федерации.</span><span class="sxs-lookup"><span data-stu-id="aed69-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="aed69-126">Весь доступ федеративных пользователей, в том числе пользователей общедоступной службы обмена мгновенными сообщениями, используйте один и тот же пул пограничного сервера или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="aed69-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="aed69-127">Например, если в развертывании есть пограничный пул или однограничный сервер, развернутый в Нью — Москва, а затем включена поддержка Федерации в пуле EDGE или однограничный сервер, трафик сигналов для федеративных пользователей будет проходить через Нью Йорк. Пограничный пул или однограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="aed69-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="aed69-128">Это справедливо даже для пользователей в Лондоне, хотя при вызове внутренним пользователем лондонского филиала федеративного пользователя в Лондоне трафик аудио- и видеосвязи будет идти через лондонский пограничный пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="aed69-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="aed69-129">Настройка Федерации для партнеров</span><span class="sxs-lookup"><span data-stu-id="aed69-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="aed69-130">Чтобы настроить успешную Федерацию с помощью другого сервера Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 или Office Communicator 2007, выберите тип Федерации из приведенной ниже таблицы и определите записи DNS SRV, DNS Host (A или AAAA для IPv6) и настройте политики, применимые к типу Федерации:</span><span class="sxs-lookup"><span data-stu-id="aed69-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="aed69-131">Тип Федерации</span><span class="sxs-lookup"><span data-stu-id="aed69-131">Federation type</span></span></th>
    <th><span data-ttu-id="aed69-132">DNS-записи</span><span class="sxs-lookup"><span data-stu-id="aed69-132">DNS Records</span></span></th>
    <th><span data-ttu-id="aed69-133">Определение политики</span><span class="sxs-lookup"><span data-stu-id="aed69-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="aed69-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="aed69-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="aed69-135">Обнаружен домен партнера</span><span class="sxs-lookup"><span data-stu-id="aed69-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="aed69-136">Настройте запись SRV для формата _сипфедератионтлс. _tcp. &lt;имя&gt;внешнего домена, где значение порта для записи SRV — TCP 5061, а узел, предлагающий <strong>эту службу</strong> , определен как SIP.</span><span class="sxs-lookup"><span data-stu-id="aed69-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="aed69-137">&lt;внешнее имя&gt; домена — FQDN службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="aed69-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="aed69-138">Дополнительные сведения о создании записи SRV см. <a href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка DNS для поддержки EDGE в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aed69-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="aed69-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="aed69-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Включение или отключение обнаружения федеративных партнеров в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="aed69-141">Предыдущие версии, которые ссылались на этот тип Федерации, <strong>закрывают улучшенную Федерацию</strong>.</span><span class="sxs-lookup"><span data-stu-id="aed69-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="aed69-142">Создание SRV-записи требуется для этого типа Федерации и предназначено для того, чтобы другие участники могли найти вашу федерацию.</span><span class="sxs-lookup"><span data-stu-id="aed69-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="aed69-143">Разрешенный домен партнера</span><span class="sxs-lookup"><span data-stu-id="aed69-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="aed69-144">Настройте запись SRV для формата _сипфедератионтлс. _tcp. &lt;имя&gt;внешнего домена, где значение порта для записи SRV — TCP 5061, а узел, предлагающий <strong>эту службу</strong> , определен как SIP.</span><span class="sxs-lookup"><span data-stu-id="aed69-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="aed69-145">&lt;внешнее имя&gt; домена — FQDN службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="aed69-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="aed69-146">Дополнительные сведения о создании записи SRV см. <a href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка DNS для поддержки EDGE в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="aed69-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="aed69-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="aed69-148">Предыдущие версии, на которые ссылается этот тип Федерации, и <strong>улучшенная федерация</strong>.</span><span class="sxs-lookup"><span data-stu-id="aed69-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="aed69-149">Создание SRV-записи является необязательным для этого типа Федерации и предназначено для того, чтобы другие участники могли найти вашу федерацию.</span><span class="sxs-lookup"><span data-stu-id="aed69-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="aed69-150">Разумеется, это будет <strong>открытая Расширенная Федерация</strong>или <strong>найденный домен партнера</strong></span><span class="sxs-lookup"><span data-stu-id="aed69-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="aed69-151">Разрешенный сервер-партнер</span><span class="sxs-lookup"><span data-stu-id="aed69-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="aed69-152">Настройте доменные имена SIP и FQDN пограничного сервера для партнера в разделе "политики" в качестве партнера Федерации.</span><span class="sxs-lookup"><span data-stu-id="aed69-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="aed69-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="aed69-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Настройка поддержки для разрешенных внешних доменов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="aed69-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Настройка поддержки заблокированных внешних доменов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="aed69-156">Этот тип Федерации является определением отношения "один к одному" и не допускает обнаружения других партнеров Федерации.</span><span class="sxs-lookup"><span data-stu-id="aed69-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="aed69-157">Каждый партнер Федерации настраивается явным образом.</span><span class="sxs-lookup"><span data-stu-id="aed69-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="aed69-158">В предыдущих версиях это была известна как <strong>Прямая Федерация</strong></span><span class="sxs-lookup"><span data-stu-id="aed69-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="aed69-159">Поставщик услуг размещения и общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="aed69-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="aed69-160">Для этого типа Федерации не определены конкретные требования к DNS</span><span class="sxs-lookup"><span data-stu-id="aed69-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="aed69-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="aed69-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="aed69-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Создание или изменение размещенных федеративных поставщиков SIP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aed69-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="aed69-164">Этот тип Федерации определяет службы и поставщиков услуг размещения, которые нужно настроить для пользователей.</span><span class="sxs-lookup"><span data-stu-id="aed69-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="aed69-165">Типичные применения включают конфигурацию для общедоступных служб обмена мгновенными сообщениями, таких как Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aed69-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="aed69-166">и AOL, а также поставщиков услуг размещения, таких как Lync Online и Office 365</span><span class="sxs-lookup"><span data-stu-id="aed69-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="aed69-167">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="aed69-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="aed69-168">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aed69-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="aed69-169">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="aed69-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="aed69-170">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="aed69-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="aed69-171">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="aed69-171">has been announced.</span></span> <span data-ttu-id="aed69-172">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aed69-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="aed69-173">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="aed69-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="aed69-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="aed69-174">Messenger.</span></span> <span data-ttu-id="aed69-175">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="aed69-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="aed69-176">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="aed69-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="aed69-177">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="aed69-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="aed69-178">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="aed69-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="aed69-179">Определение и настройка всех необходимых DNS-узлов (а также AAAA для IPv6) и DNS SRV-записей</span><span class="sxs-lookup"><span data-stu-id="aed69-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="aed69-180">Определите и настройте политики с помощью панели управления Lync Server или с помощью командной консоли Lync Server Management Shell и соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="aed69-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="aed69-181">Подробные сведения о командлетах командной консоли Lync Server можно найти [в разделе инструкции Федерации и внешнего доступа в Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="aed69-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aed69-182">Система комнат Lync (ЛРС) не отображает кнопку "присоединиться" для собраний, отправленных с помощью организаторов в федеративных партнерах Lync.</span><span class="sxs-lookup"><span data-stu-id="aed69-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="aed69-183">Для отображения ссылки присоединения к собранию в ЛРС необходимо включить формат TNEF с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="aed69-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="aed69-184">Обратите внимание, что это не ЛРС отдельно.</span><span class="sxs-lookup"><span data-stu-id="aed69-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="aed69-185">Outlook и Lync также не будут показывать ссылки присоединения в этом случае, так как свойства MAPI не переносятся, но в случае с Outlook пользователь может открыть приглашение на собрание и щелкнуть его URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="aed69-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="aed69-186">Если для Тнефенаблед установлено значение true Exchange 2013, свойства MAPI, в том числе Онлинемитинжекстерналлинк, и кнопка присоединиться, будут отображаться в памятке.</span><span class="sxs-lookup"><span data-stu-id="aed69-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aed69-187">См. также</span><span class="sxs-lookup"><span data-stu-id="aed69-187">See Also</span></span>


[<span data-ttu-id="aed69-188">Планирование SIP, Федерации КСМПП и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aed69-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="aed69-189">Управление федерацией и внешним доступом к Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aed69-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

