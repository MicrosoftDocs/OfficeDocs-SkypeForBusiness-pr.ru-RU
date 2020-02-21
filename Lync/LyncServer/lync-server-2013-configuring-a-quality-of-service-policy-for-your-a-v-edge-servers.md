---
title: Настройка политики качества обслуживания для пограничных серверов аудио-и видеоданных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30fece45c4b13bd9cd2c9243dd21cdac1d779733
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="99fe2-102">Настройка политики качества обслуживания для пограничных серверов аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99fe2-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99fe2-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="99fe2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="99fe2-p101">Помимо создания политик QoS для серверов конференций, приложений и серверов-посредников, также необходимо создать политики для аудио и видео для внутренней стороны пограничных серверов аудио- и видеоданных. Тем не менее, политики, используемые на пограничных серверах, отличаются от политик, используемых на серверах конференций, приложений и серверах-посредниках. Для серверов конференций, приложений и посредников вы указывали исходный диапазон портов. Для пограничных серверов необходимо указать конечный диапазон портов. Из-за этого нельзя просто применить политики QoS серверов конференций, приложений и серверах-посредников к пограничным серверам: эти политики просто не будут работать. Вместо этого нужно создать новые политики и применить их только к пограничным серверам.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="99fe2-p102">В приведенной ниже процедуре описан процесс создания объектов групповой политики Active Directory, которые могут использоваться для управления качеством обслуживания на пограничных серверах. Конечно, возможно, что ваши пограничные серверы являются автономными серверами без учетных записей Active Directory. В этом случае можно использовать локальную групповую политику вместо групповой политики Active Directory: единственное различие состоит в том, что необходимо создать эти локальные политики с помощью редактора локальной групповой политики, и нужно отдельно создавать один и тот же набор политик на каждом пограничном сервере. Чтобы запустить редактор локальной групповой политики на пограничном сервере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99fe2-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="99fe2-113">В меню **Пуске** щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="99fe2-114">В диалоговом окне **Выполнить** введите **gpedit.msc** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="99fe2-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="99fe2-p103">Если вы создаете политику на основе Active Directory, войдите на компьютер, где установлен компонент управления групповой политикой. Откройте управление групповыми политиками (нажмите кнопку **Пуске**, выберите **Администрирование**, а затем щелкните **Управление групповой политикой**) и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99fe2-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="99fe2-p104">В консоли управления групповой политики найдите контейнер, в котором необходимо создать политику. Например, если все компьютеры Lync Server находятся в подразделении с именем Lync Server, то новую политику следует создать в подразделении Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="99fe2-119">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **Создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="99fe2-120">В диалоговом окне **Создание нового объекта групповой политики** в поле **Имя** введите имя для этого нового объекта групповой политики (например, **Lync Server Audio**) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="99fe2-121">Щелкните правой кнопкой мыши созданную политику и выберите команду **Правка**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="99fe2-122">С этого момента процесс одинаков независимо от того, создаете ли вы политику Active Directory или локальную политику:</span><span class="sxs-lookup"><span data-stu-id="99fe2-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="99fe2-123">В редакторе управления групповой политикой или редакторе локальной групповой политики последовательно разверните узлы **Конфигурация компьютера**, **Политики**, **Параметры Windows**, щелкните правой кнопкой мыши **QoS на основе политики**, а затем щелкните **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="99fe2-p105">На первой странице в диалоговом окне **QoS на основе политики** введите имя новой политики (например, **Аудио Lync Server**) в поле **Имя**. Выберите **Указать значение DSCP** и введите значение **46**. Не устанавливайте флажок **Укажите частоту передачи** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="99fe2-p106">На следующей странице убедитесь, что выбран параметр **Все приложения** и нажмите кнопку **Далее**. Этот параметр дает указание сети искать все пакеты со значением DSCP 46, а не только пакеты, созданные определенным приложением.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="99fe2-p107">На третьей странице убедитесь, что выбраны оба параметра **Любой исходный IP-адрес** и **Любой конечный IP-адрес**, и нажмите кнопку **Далее**. Эти два параметра используются, чтобы гарантировать, что пакеты будут управляться независимо от того, какой компьютер (IP-адрес) отправил их и какой компьютер (IP-адрес) получит эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="99fe2-131">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="99fe2-132">Протокол TCP (TCP-протокол управления передачей) и протокол UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Lync Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="99fe2-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="99fe2-p109">Под заголовком **Укажите номер порта назначения** выберите **От этого порта или диапазона назначения**. В соответствующем текстовом поле введите диапазон портов, зарезервированный для передачи аудиоданных. Например, если вы зарезервировали порты 49152-57500 для аудиотрафика, введите этот диапазон в следующем формате: **49152:57500**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="99fe2-p110">После создания политики QoS для аудиотрафика следует создать вторую политику для видеотрафика. Для этого выполните ту же основную процедуру, которой вы следовали при создании политики для аудио, внеся следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="99fe2-139">Используйте другое (уникальное) имя политики (например, **Видео Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="99fe2-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="99fe2-p111">Установите значение DSCP равным **34** вместо 46. (Обратите внимание, что нет необходимости в использовании значения DSCP, равного 34. Единственно требование состоит в том, что для видео необходимо использовать значение DSCP, отличное от значения DSCP для аудио.)</span><span class="sxs-lookup"><span data-stu-id="99fe2-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="99fe2-p112">Используйте ранее настроенный диапазон портов для видеотрафика. Например, если вы зарезервировали порты 57501-65535 для видео, то установите следующий диапазон портов: **57501:65535**. Опять же, этот диапазон нужно настроить как диапазона портов назначения.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="99fe2-146">Если вы решите создать политику для управления трафиком совместного использования приложений, необходимо создать третью политику, внеся следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="99fe2-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="99fe2-147">Используйте другое (и уникальное) имя политики (например, **Lync Server Application Sharing**).</span><span class="sxs-lookup"><span data-stu-id="99fe2-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="99fe2-p113">Для значения DSCP вместо 46 укажите **24**. (Еще раз, вы не обязаны использовать значение DSCP 24. Единственное требование состоит в том, что для общего доступа к приложениям должно использоваться значение DSCP, отличное от используемого для звука или видео.)</span><span class="sxs-lookup"><span data-stu-id="99fe2-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="99fe2-p114">Используйте ранее настроенный диапазон портов для видеотрафика. Например, если вы зарезервировали порты 40803-49151 для совместного использования приложений, то установите следующий диапазон портов: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="99fe2-p115">Созданные политики не вступят в силу до обновления групповой политики на пограничных серверах. Хотя групповая политика периодически обновляется самостоятельно, вы можете обновить ее принудительно, выполнив следующую команду на каждом компьютере, на котором требуется обновить групповую политику:</span><span class="sxs-lookup"><span data-stu-id="99fe2-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="99fe2-155">Эту команду можно выполнить на сервере Lync Server или в любом командном окне, работающем под учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="99fe2-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="99fe2-156">Для запуска окна командной строки с учетными данными администратора нажмите кнопку **Пуск**, щелкните правой кнопкой **Командная строка**, а затем выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="99fe2-157">Учтите, что вам может потребоваться перезапустить пограничный сервер после выполнения Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="99fe2-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="99fe2-158">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="99fe2-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="99fe2-159">Нажмите кнопку **Пуск** и щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="99fe2-160">В диалоговом окне **Выполнить** введите **regedit**, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="99fe2-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="99fe2-161">В редакторе реестра разверните узел **hKey\_Local\_Machine**, **система**, разверните **CurrentControlSet**, разверните узел **службы**, а затем разверните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="99fe2-p117">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**. После создания нового раздела реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="99fe2-p118">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**. После создания нового параметра реестра введите **Do not use NLA** и нажмите клавишу ВВОД для переименования значения.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="99fe2-p119">Дважды щелкните **Do no use NLA**. В диалоговом окне **Изменение строкового параметра** введите **1** в поле **Значение**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99fe2-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="99fe2-168">Закройте редактор реестра, затем перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="99fe2-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

