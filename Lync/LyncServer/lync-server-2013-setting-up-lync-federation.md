---
title: 'Lync Server 2013: Настройка Федерации Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="637db-102">Настройка Федерации Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="637db-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="637db-103">_**Последнее изменение темы:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="637db-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="637db-104">Если вы уже развернули пограничные серверы, добавление возможностей для федеративных сценариев довольно просто.</span><span class="sxs-lookup"><span data-stu-id="637db-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="637db-105">Если вы не настроили пограничные серверы, это необходимо сделать.</span><span class="sxs-lookup"><span data-stu-id="637db-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="637db-106">Подробнее: [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию и [развертыванию доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="637db-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="637db-p102">Если планируется настройка какого-либо сочетания федерации XMPP, федерации Lync или подключения к общедоступным системам обмена мгновенными сообщениями, можно развернуть их одновременно или по одному. Если настроить эти параметры с помощью построителя топологии и консоли управления Lync Server, а затем запустите мастер развертывания на пограничном сервере после настройки параметров для одного, двух или всех трех типов федерации, можно сократить число необходимых действий.</span><span class="sxs-lookup"><span data-stu-id="637db-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="637db-109">Настройка федерации Lync в построителе топологий и мастере развертывания</span><span class="sxs-lookup"><span data-stu-id="637db-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="637db-p103">На интерфейсном сервере откройте построитель топологии. Разверните "Пограничные пулы", затем щелкните правой кнопкой мыши пограничный сервер или пул пограничных серверов. Выберите "Изменить свойства".</span><span class="sxs-lookup"><span data-stu-id="637db-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="637db-p104">В окне "Изменение свойств" в разделе "Общие" выберите "Включить федерацию для этого пограничного пула (порт 5061)". Нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="637db-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="637db-p105">Щелкните "Действие", выберите "Топология" и затем нажмите "Опубликовать". При появлении запроса о публикации топологии, нажмите кнопку "Далее". После завершения публикации нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="637db-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="637db-p106">На пограничном сервере откройте мастер развертывание Lync Server. Нажмите кнопку "Установить или обновить систему Lync Server", затем нажмите кнопку "Установить или удалить компоненты Lync Server". Затем снова нажмите "Выполнить".</span><span class="sxs-lookup"><span data-stu-id="637db-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="637db-p107">В диалоговом окне "Установка компонентов Lync Server" нажмите кнопку "Далее". В окне сводки будут показаны действия по мере их выполнения. После завершения развертывания нажмите кнопку "Просмотр журнала", чтобы открыть доступные файлы журналов. Нажмите кнопку "Готово", чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="637db-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="637db-p108">Вы можете выбрать этот параметр, но только один пограничный пул или пограничный сервер в организации может быть опубликован внешне для федерации. Весь доступ федеративных пользователей, в том числе пользователей общедоступных служб обмена мгновенными сообщениями, осуществляется через один пограничный пул или пограничный сервер. Например, если развертывание содержит пограничный пул или один пограничный сервер в Нью-Йорке, и другой пограничный сервер в Лондоне и вы включаете поддержку федерации в нью-йоркском пуле или на одном пограничном сервере, трафик для федеративных пользователей будет передаваться через нью-йоркский пул или один пограничный сервер. Это справедливо даже для взаимодействия с лондонскими пользователями, хотя внутренние пользователи из Лондона, вызывающие федеративного пользователя из Лондона, применяют лондонский пул или пограничный сервер для аудио-видео трафика.</span><span class="sxs-lookup"><span data-stu-id="637db-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="637db-129">Настройка федерации с партнерами</span><span class="sxs-lookup"><span data-stu-id="637db-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="637db-130">Чтобы настроить успешную Федерацию с другим сервером Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 или Office Communicator 2007, выберите тип Федерации из следующей таблицы и определите записи DNS SRV, DNS-узел (A или AAAA для IPv6) и настройте политики, которые относятся к типу Федерации:</span><span class="sxs-lookup"><span data-stu-id="637db-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="637db-131">Тип федерации</span><span class="sxs-lookup"><span data-stu-id="637db-131">Federation type</span></span></th>
    <th><span data-ttu-id="637db-132">DNS-записи</span><span class="sxs-lookup"><span data-stu-id="637db-132">DNS Records</span></span></th>
    <th><span data-ttu-id="637db-133">Определение политики</span><span class="sxs-lookup"><span data-stu-id="637db-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="637db-134">Notes</span><span class="sxs-lookup"><span data-stu-id="637db-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="637db-135">Обнаруженный домен партнера</span><span class="sxs-lookup"><span data-stu-id="637db-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="637db-136">Настройте запись SRV для формата _sipfederationtls. _tcp. &lt;имя&gt;внешнего домена, где значение порта для записи SRV равно TCP 5061, а узел, на котором размещается <strong>Эта служба</strong> , определен как SIP.</span><span class="sxs-lookup"><span data-stu-id="637db-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="637db-137">&lt;имя внешнего домена&gt; — полное доменное имя службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="637db-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="637db-138">Сведения о создании записи SRV см. <a href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка DNS для поддержки пограничного сервера в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="637db-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="637db-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="637db-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Включение и отключение обнаружения партнеров Федерации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="637db-p110">В предыдущих версиях этот тип федерации назывался <strong>открытой улучшенной федерацией</strong>. Создание SRV-записи необходимо для этого типа федерации, т. к. служит для нахождения другими партнерами этой федерации.</span><span class="sxs-lookup"><span data-stu-id="637db-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="637db-143">Разрешенный домен партнера</span><span class="sxs-lookup"><span data-stu-id="637db-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="637db-144">Настройте запись SRV для формата _sipfederationtls. _tcp. &lt;имя&gt;внешнего домена, где значение порта для записи SRV равно TCP 5061, а узел, на котором размещается <strong>Эта служба</strong> , определен как SIP.</span><span class="sxs-lookup"><span data-stu-id="637db-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="637db-145">&lt;имя внешнего домена&gt; — полное доменное имя службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="637db-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="637db-146">Сведения о создании записи SRV см. <a href="lync-server-2013-configure-dns-for-edge-support.md">в разделе Настройка DNS для поддержки пограничного сервера в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="637db-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="637db-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="637db-148">Предыдущие версии, на которые ссылается этот тип Федерации, в качестве <strong>расширенной Федерации</strong>.</span><span class="sxs-lookup"><span data-stu-id="637db-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="637db-149">Создание SRV-записи не является обязательным для этого типа федерации и служит для нахождения другими партнерами этой федерации.</span><span class="sxs-lookup"><span data-stu-id="637db-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="637db-150">Конечно, по сути это <strong>открытая улучшенная федерация</strong> или <strong>обнаруженный домен партнера</strong></span><span class="sxs-lookup"><span data-stu-id="637db-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="637db-151">Разрешенный сервер партнера</span><span class="sxs-lookup"><span data-stu-id="637db-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="637db-152">Настройте в политиках имя домена SIP и полное доменное имя пограничного сервера партнера в качестве партнера Федерации.</span><span class="sxs-lookup"><span data-stu-id="637db-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="637db-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="637db-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Настройка поддержки для разрешенных внешних доменов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="637db-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Настройка поддержки заблокированных внешних доменов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="637db-p113">Этот тип федерации является определением отношения один-к-одному, которое не поддерживает обнаружение других партнеров федерации. Каждый партнер федерации определяется явным образом. В предыдущих версиях такой тип назывался <strong>прямой федерацией</strong></span><span class="sxs-lookup"><span data-stu-id="637db-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="637db-159">Поставщик услуг размещения и общедоступный поставщик систем обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="637db-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="637db-160">Для этого типа федераций нет определенных требований к DNS</span><span class="sxs-lookup"><span data-stu-id="637db-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="637db-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="637db-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="637db-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Создание или изменение размещенных федеративных поставщиков SIP Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="637db-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="637db-164">Этот тип федерации определяет службы и поставщиков услуг размещения, которые следует настроить для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="637db-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="637db-165">Типичное использование заключается в настройке поставщиков систем обмена мгновенными сообщениями, таких как Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="637db-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="637db-166">и AOL, а также поставщики услуг хостинга, такие как Lync Online и Office 365</span><span class="sxs-lookup"><span data-stu-id="637db-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="637db-167">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="637db-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="637db-168">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="637db-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="637db-169">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="637db-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="637db-170">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="637db-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="637db-171">объявлено.</span><span class="sxs-lookup"><span data-stu-id="637db-171">has been announced.</span></span> <span data-ttu-id="637db-172">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="637db-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="637db-173">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="637db-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="637db-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="637db-174">Messenger.</span></span> <span data-ttu-id="637db-175">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="637db-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="637db-176">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="637db-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="637db-177">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="637db-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="637db-178">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="637db-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="637db-179">Определение и настройка любых требуемых SRV-записей узлов DNS (A или AAAA для IPv6)</span><span class="sxs-lookup"><span data-stu-id="637db-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="637db-180">Определите и настройте любые политики с помощью панели управления Lync Server, а также с помощью командной консоли Lync Server и соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="637db-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="637db-181">Дополнительные сведения о командлетах командной консоли Lync Server содержатся [в статье командлеты Федерации и внешнего доступа в Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="637db-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="637db-182">Система комнат Lync (LRS) не отображает кнопку присоединения для собраний, отправленных организаторов в федеративных партнерах Lync.</span><span class="sxs-lookup"><span data-stu-id="637db-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="637db-183">Для отображения ссылки присоединения к собранию в LRS необходимо включить отправку TNEF с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="637db-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="637db-184">Обратите внимание, что это не относится к LRS.</span><span class="sxs-lookup"><span data-stu-id="637db-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="637db-185">Outlook и Lync также не будут показывать ссылки присоединения в этом случае, так как свойства MAPI не переносятся, но в случае Outlook пользователь может открыть приглашение на собрание и щелкнуть URL-адрес собрания.</span><span class="sxs-lookup"><span data-stu-id="637db-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="637db-186">Если для TNEFEnabled задано значение true Exchange 2013, свойства MAPI, в том числе Онлинемитинжекстерналлинк, и кнопка присоединение будут отображаться в памятке.</span><span class="sxs-lookup"><span data-stu-id="637db-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="637db-187">См. также</span><span class="sxs-lookup"><span data-stu-id="637db-187">See Also</span></span>


[<span data-ttu-id="637db-188">Планирование SIP, Федерации XMPP и общедоступных мгновенных сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="637db-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="637db-189">Управление федерациями и внешним доступом к Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="637db-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

