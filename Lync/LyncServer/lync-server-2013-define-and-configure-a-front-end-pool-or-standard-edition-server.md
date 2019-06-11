---
title: Определение и настройка пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="ba7d5-102">Определение и настройка пула переднего плана или сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba7d5-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba7d5-103">_**Тема последнего изменения:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="ba7d5-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="ba7d5-104">Для этой процедуры не требуется членство в группе локального администратора или привилегированного домена.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="ba7d5-105">Войдите в систему как обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="ba7d5-106">Если вы разворачиваете сервер предприятия, необходимо запустить минимальное число серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="ba7d5-107">В приведенной ниже таблице перечислены эти требования.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba7d5-108">Общее количество серверов переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="ba7d5-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="ba7d5-109">Число работающих серверов, требуемое для правильного функционирования пула</span><span class="sxs-lookup"><span data-stu-id="ba7d5-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7d5-110">1-2</span><span class="sxs-lookup"><span data-stu-id="ba7d5-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-111">1</span><span class="sxs-lookup"><span data-stu-id="ba7d5-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7d5-112">3-4</span><span class="sxs-lookup"><span data-stu-id="ba7d5-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-113">2</span><span class="sxs-lookup"><span data-stu-id="ba7d5-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7d5-114">5-6</span><span class="sxs-lookup"><span data-stu-id="ba7d5-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-115">3</span><span class="sxs-lookup"><span data-stu-id="ba7d5-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7d5-116">7-8</span><span class="sxs-lookup"><span data-stu-id="ba7d5-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-117">4</span><span class="sxs-lookup"><span data-stu-id="ba7d5-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba7d5-118">9-10</span><span class="sxs-lookup"><span data-stu-id="ba7d5-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-119">5</span><span class="sxs-lookup"><span data-stu-id="ba7d5-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7d5-120">11-12</span><span class="sxs-lookup"><span data-stu-id="ba7d5-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="ba7d5-121">6</span><span class="sxs-lookup"><span data-stu-id="ba7d5-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="ba7d5-122">Для Lync Server 2013 каждый раз, когда вы добавляете или удаляете сервер переднего плана из пула, необходимо перезапустить службы.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="ba7d5-123">Удаление и добавление серверов должно выполняться как отдельные операции.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="ba7d5-124">Например, если вы собираетесь добавить два сервера переднего плана и удалить два сервера переднего плана, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="ba7d5-125">Удалите два сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="ba7d5-126">Опубликуйте и повторно активируйте топологию.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="ba7d5-127">Перезапуск служб</span><span class="sxs-lookup"><span data-stu-id="ba7d5-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="ba7d5-128">Добавьте два сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="ba7d5-129">Опубликуйте и повторно активируйте топологию.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="ba7d5-130">Перезапустите службы.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="ba7d5-131">Определив топологию, выполните описанные ниже действия, чтобы определить пул переднего плана для сайта.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="ba7d5-132">Подробнее об определении топологии можно узнать в разделе [Определение и Настройка топологии в построителе топологии для Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ba7d5-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="ba7d5-133">Определение пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="ba7d5-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="ba7d5-134">В мастере определение пула переднего плана на странице **Определение новой группы** переднего плана нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="ba7d5-135">На странице **Определение полного доменного имени пула переднего плана** введите полное доменное имя (FQDN) для создаваемого пула, щелкните **пул переднего плана Enterprise Edition**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="ba7d5-136">На странице **Определение компьютеров в пуле** введите полное доменное имя компьютера для первого сервера переднего плана в пуле и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="ba7d5-137">Повторите эти действия для всех дополнительных компьютеров (не более двенадцати), которые вы хотите добавить в группу, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="ba7d5-138">На странице " **Выбор компонентов** " установите флажки для нужных функций в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="ba7d5-139">Например, если вы разворачиваете только возможности обмена мгновенными сообщениями и сведениями о присутствии, установите флажок **Конференц** -связь, чтобы разрешить многофакторную передачу мгновенных сообщений, но не выбирайте **конференции с телефонным подключением (КТСОП)**, **корпоративной голосовой**связью или \*\* \*\*Флажки для управления допуском звонков, которые представляют собой голосовую, видеосвязь и функцию совместной конференции.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="ba7d5-140">**Конференции**   этот выбор включает широкий набор функциональных возможностей, в том числе:</span><span class="sxs-lookup"><span data-stu-id="ba7d5-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="ba7d5-141">Обмен мгновенными сообщениями с более чем двумя сторонами в сеансе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="ba7d5-142">Конференции, включая совместную работу с документами, общий доступ к приложениям и демонстрацию рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="ba7d5-143">Конференц-связь с телефонным подключением, которая позволяет пользователям использовать голосовые и видеоконференции в реальном времени (A/V) без внешних служб, таких как служба Live Meeting или сторонний звуковой мост.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="ba7d5-144">**Конференц-связь с телефонным подключением (PSTN)**   позволяет пользователям присоединиться к звуковой части конференции Lync Server 2013 с помощью телефонной сети общего пользования (PSTN), не требуя поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="ba7d5-145">\*\*\*\* Корпоративная голосовая связь – это решение для передачи голоса по протоколу IP (VoIP) в Lync Server 2013, позволяющее пользователям совершать и принимать телефонные звонки.   </span><span class="sxs-lookup"><span data-stu-id="ba7d5-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="ba7d5-146">Если вы планируете использовать Lync Server 2013 для голосовой связи, голосовой почты и других функций, использующих аппаратное устройство или клиентское программное обеспечение, вы можете развернуть эту функцию.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="ba7d5-147">**Управление допуском звонков (CAC)**   CAC определяет, в зависимости от доступной пропускной способности сети, возможность устанавливать сеансы связи в реальном времени, такие как голосовые и видеозвонки.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="ba7d5-148">Если вы развернули только сообщение и сведения о присутствии, CAC не требуется, так как ни одна из этих двух функций не использует CAC.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="ba7d5-149">\*\*\*\* Архивация архивации позволяет архивировать содержимое мгновенных сообщений, Конференц-связь (собрания) и т. д., отправленные с помощью Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="ba7d5-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="ba7d5-150">**Мониторинг**   сервера мониторинга позволяет собирать числовые данные, описывающие качество мультимедиа в сети и конечных точках, сведения об использовании, связанные с вызовами VoIP, мгновенными сообщениями, беседами, собраниями, общим доступом к приложениям и файлами передача сведений об ошибках и устранение неполадок звонка для неудачных звонков.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ba7d5-151">Если вы хотите включить CAC в развертывании, необходимо включить CAC только в одном пуле для одного центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="ba7d5-152">Если вы развертываете голосовые функции или конференц-связь/V, рекомендуется использовать CAC.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="ba7d5-153">В следующей таблице показаны доступные функции (сверху) и функции, предложенные пользователям (слева).</span><span class="sxs-lookup"><span data-stu-id="ba7d5-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="ba7d5-154">В таблице выберите нужные параметры, чтобы включить эти функции для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="ba7d5-155">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="ba7d5-155">Conferencing</span></span></th>
    <th><span data-ttu-id="ba7d5-156">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="ba7d5-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="ba7d5-157">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="ba7d5-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="ba7d5-158">Контроль допуска звонков</span><span class="sxs-lookup"><span data-stu-id="ba7d5-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ba7d5-159">Мгновенные сообщения и присутствие</span><span class="sxs-lookup"><span data-stu-id="ba7d5-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-160">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ba7d5-161">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="ba7d5-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-162">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-162">X</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-163">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ba7d5-164">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="ba7d5-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-165">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-165">X</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-166">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="ba7d5-167">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ba7d5-168">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="ba7d5-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="ba7d5-169">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-169">X</span></span></p></td>
    <td><p><span data-ttu-id="ba7d5-170">X</span><span class="sxs-lookup"><span data-stu-id="ba7d5-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="ba7d5-171">На странице **Выбор размещенных ролей сервера** можно выделять сервер-посредник на сервере переднего плана или развернуть его как изолированный сервер.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="ba7d5-172">Вы можете разгруппировать сервер исправлений на интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="ba7d5-173">Убедитесь, что вы собираетесь выделять сервер, на котором установлен этот флажок, в пуле уровня Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="ba7d5-174">Данная роль сервера будет развернута на серверах пула.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="ba7d5-175">Если вы планируете развернуть сервер-посредник как отдельный сервер, снимите соответствующий флажок.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="ba7d5-176">Сервер обновлений будет развертываться на отдельном этапе развертывания после полного развертывания клиентского сервера.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ba7d5-177">По возможности мы рекомендуем использовать по своему соотношении сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="ba7d5-178">Подробные сведения о поддержке размещенных или изолированных серверов-исправлений можно найти в разделе <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">компоненты и топологии для сервера-посредника в Lync server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="ba7d5-179">**Роли сервера свяжите с этой страницей в пуле** позволяют определять роли сервера и связывать их с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="ba7d5-180">Доступны следующие роли:</span><span class="sxs-lookup"><span data-stu-id="ba7d5-180">The following role is available:</span></span>
    
    <span data-ttu-id="ba7d5-181">**Включение**   пограничного пула определяет и связывает один граничный сервер или пул пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="ba7d5-182">Пограничный сервер обеспечивает взаимодействие и совместную работу пользователей в организации и людей за пределами организации, в том числе федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="ba7d5-183">Существует два возможных сценария, которые можно использовать для развертывания и связывания ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="ba7d5-184">В первом сценарии вы определяете новую топологию для новой установки.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="ba7d5-185">Вы можете подходить к установке одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="ba7d5-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="ba7d5-186">Оставьте флажок снятым и продолжите Определение топологии.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="ba7d5-187">После публикации, настройки и тестирования ролей сервера переднего плана и внутреннего сервера можно запустить построитель топологий еще раз, чтобы добавить роли сервера в топологию.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="ba7d5-188">С помощью этой стратегии вы сможете протестировать пул переднего плана и сервер SQL Server, не изменяя дополнительные возможности для работы с дополнительными ролями.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="ba7d5-189">После завершения первоначального тестирования можно повторно запустить построитель топологий, чтобы выбрать роли, которые необходимо развернуть.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="ba7d5-190">Выберите роли, которые необходимо установить, а затем настройте оборудование для размещения выбранных ролей.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="ba7d5-191">Для сценария 2 у вас есть существующее развертывание, и ваша инфраструктура готова к новым ролям или вам нужно связать существующие роли с новым сервером переднего плана:</span><span class="sxs-lookup"><span data-stu-id="ba7d5-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="ba7d5-192">В этом случае вы будете выбирать роли, которые вы планируете развертывать или связывать с новым сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="ba7d5-193">В любом случае вы продолжаете определять роли, настраиваете все необходимое оборудование и продолжаете установку.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="ba7d5-194">На странице **Определение хранилища SQL** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ba7d5-195">Чтобы использовать существующее хранилище SQL Server, которое уже было определено в топологии, выберите экземпляр из **хранилища SQL**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="ba7d5-196">Чтобы определить новый экземпляр SQL Server для хранения сведений о пуле, нажмите кнопку **создать** , а затем укажите **полное доменное имя SQL Server**в диалоговом окне **Определение нового хранилища SQL** .</span><span class="sxs-lookup"><span data-stu-id="ba7d5-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="ba7d5-197">Чтобы указать имя экземпляра SQL Server, выберите **Именованный экземпляр**, а затем укажите имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="ba7d5-198">Чтобы использовать экземпляр по умолчанию, щелкните **Экземпляр по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="ba7d5-199">Для использования зеркального отображения SQL выберите **включить зеркальное отображение SQL** и выберите существующий экземпляр или создайте новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="ba7d5-200">На странице **Определение общего файлового файла** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ba7d5-201">Чтобы использовать общий файловый ресурс, который уже определен в топологии, выберите параметр **Использовать ранее определенный файловый ресурс**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="ba7d5-202">Чтобы определить новый ресурс, выберите параметр **Определить новый файловый ресурс**, в поле **Полное доменное имя файлового сервера** введите полное доменное имя существующего файлового сервер, на котором будет размещаться файловый ресурс, а затем введите имя ресурса в поле **Файловый ресурс**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ba7d5-203">Не удается найти общую файловую систему для Lync Server 2013 на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="ba7d5-204">Обратите внимание, что в этом примере файловый общий доступ размещен на сервере SQL Server с интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="ba7d5-205">Это может быть не оптимальным расположением для требований Организации, а файловый сервер лучше подходит.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="ba7d5-206">Хранилище файлов можно определить без создания самого хранилища.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="ba7d5-207">Хранилище файлов потребуется создать в выбранном месте перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="ba7d5-208">На странице " **укажите URL-адрес сайта** " выполните одно или оба указанных ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ba7d5-209">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="ba7d5-210">Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="ba7d5-211">Если у вас больше одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="ba7d5-212">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="ba7d5-213">При настройке балансировки нагрузки DNS установите флажок **переопределить полное доменное имя пула** , введите внутренний базовый URL-адрес, который должен отличаться от полного доменного имени пула (например, внутренний URL-\<адрес\>). \*\* Внутренний базовый URL-адрес\*\*.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="ba7d5-214">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="ba7d5-215"><STRONG>Используйте только стандартные символы</STRONG> (A–Z, a–z, 0–9 и дефис) при написании URL-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="ba7d5-216">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="ba7d5-217">Нестандартные символы в URL-адресе или полном доменном имени часто не поддерживаются внешними DNS-серверами и общими центрами сертификации (например, когда URL-адрес или полное доменное имя необходимо назначить имени или альтернативному имени субъекта в сертификате).</span><span class="sxs-lookup"><span data-stu-id="ba7d5-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="ba7d5-218">При необходимости введите внешний базовый URL-адрес во **внешнем базовом URL-адресе**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="ba7d5-219">Вы должны ввести внешний базовый URL-адрес, чтобы отличать его от вашего внутреннего доменного имени.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="ba7d5-220">Например, внутренний домен — contoso.net, но имя внешнего домена — contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="ba7d5-221">Вы можете определить URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="ba7d5-222">Это также важно при использовании обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="ba7d5-223">Доменное имя внешнего базового URL-адреса должно совпадать с полным доменным именем обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="ba7d5-224">Для обмена мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP к пулу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ba7d5-225">Для использования балансировки нагрузки DNS необходимо создать соответствующие записи DNS.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="ba7d5-226">Подробности можно найти <A href="lync-server-2013-configure-dns-for-load-balancing.md">в разделе Настройка DNS для балансировки нагрузки в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="ba7d5-227">Если вы выбрали **Конференц** -связь на странице "Выбор **компонентов** ", на странице " **Выбор сервера Office Web Apps** " выберите пункт " **связать пул с сервером Office Web Apps** " и нажмите кнопку " **создать** " (или выберите существующие веб-приложения Office Сервер из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="ba7d5-228">В диалоговом окне **Определение нового сервера Office Web Apps** введите полное доменное имя (FQDN) сервера Office Web Apps в поле **Полное доменное имя сервера Office Web Apps**; при этом URL-адрес для обнаружения сервера Office Web Apps автоматически вводится в поле **URL-адрес обнаружения сервера Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="ba7d5-229">Если сервер Office Web Apps установлен в локальной сети и в той же сетевой зоне, что и Lync Server 2013, этот вариант не должен быть установлен на **внешний сервер Office Web Apps (например, демилитаризованная зона или Интернет)** .</span><span class="sxs-lookup"><span data-stu-id="ba7d5-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="ba7d5-230">Если сервер Office Web Apps развернут за пределами внутреннего брандмауэра, выберите режим **Сервер Office Web Apps развернут во внешней сети (периметр/Интернет)**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ba7d5-231">Подробности можно найти <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">в разделе Настройка интеграции с Office Web Apps Server и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="ba7d5-232">На странице **Определение архивирования в хранилище SQL** выберите существующий экземпляр или SQL Server или создайте новый экземпляр для хранения данных, связанных с архивацией данных.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="ba7d5-233">На странице **Определение хранилища SQL Store** выберите существующий экземпляр или SQL Server или создайте новый экземпляр для хранения данных, связанных с данными мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="ba7d5-234">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-234">Click **Next**.</span></span> <span data-ttu-id="ba7d5-235">Если вы определили другие серверы ролей в **ролях сервера свяжите с этой** страницей пула, будет открыта отдельная страница мастера настройки ролей для настройки ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="ba7d5-236">Дополнительные сведения можно найти в перечисленных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="ba7d5-237">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba7d5-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="ba7d5-238">Если вы не выбрали дополнительные роли сервера для настройки и развертывания или закончите настройку дополнительных серверов ролей, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ba7d5-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

