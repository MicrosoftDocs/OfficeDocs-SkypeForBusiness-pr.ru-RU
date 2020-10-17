---
title: 'Lync Server 2013: Настройка политики качества обслуживания для серверов конференц-связи, приложений и серверов-посредников'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca1e1e243fe6957fdc5233b248c358d82817516
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508876"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="4ffaf-102">Настройка политики качества обслуживания в Lync Server 2013 для серверов конференц-связи, приложений и серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4ffaf-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ffaf-103">_**Последнее изменение темы:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="4ffaf-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="4ffaf-p101">Настройка диапазонов портов облегчает использование качества обслуживания, обеспечивая проход всего трафика определенного типа (например, всего звукового трафика) через один и тот же набор портов. Системе становится проще идентифицировать и пометить конкретный пакет: если порт 49152 зарезервирован для звукового трафика, то любой пакет, проходящий через порт 49152, может быть помечен кодом DSCP, указывающим, что это звуковой пакет. В свою очередь, это позволяет маршрутизаторам идентифицировать этот пакет как звуковой и предоставить ему более высокий приоритет, чем непомеченным пакетам (например, пакетам, использующимся для копирования файла с одного сервера на другой).</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="4ffaf-107">Однако простое ограничение ряда портов конкретным типом трафика не приведет к тому, что пакеты, проходящие через эти порты, будут помечаться соответствующим кодом DSCP.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="4ffaf-108">Помимо определения диапазонов портов необходимо также создать политики качества обслуживания, задающие код DSCP, который должен быть связан с каждым диапазоном портов.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="4ffaf-109">Для Microsoft Lync Server 2013, который обычно означает создание двух политик: один для аудио, а другой для видео.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="4ffaf-110">Политики качества обслуживания проще всего создаются и управляются с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="4ffaf-111">(Эти же политики можно также создавать с помощью локальных политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="4ffaf-112">Тем не менее, необходимо повторить одну и ту же процедуру на каждом компьютере. Первоначальный набор политик QoS (один для аудио-и видеоконференций) должен применяться только к компьютерам Lync Server, работающим на серверах конференций, серверах приложений и/или серверах-посредников.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="4ffaf-113">Если все эти компьютеры размещаются в одном подразделении Active Directory, то можно просто назначить этому подразделению новый объект групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="4ffaf-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="4ffaf-114">Можно также предпринять другие действия для назначения новой политики к указанным компьютерам; например, можно поместить соответствующие компьютеры в группу безопасности, а затем с помощью фильтров безопасности групповой политики применить этот объект групповой политики именно к этой группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="4ffaf-115">Чтобы создать политику качества обслуживания для управления звуком, войдите в компьютер, на котором установлено управление групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="4ffaf-116">Откройте управление групповыми политиками (нажмите кнопку **Пуск**, выберите **Администрирование** и щелкните **Управление групповыми политиками**), а затем выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="4ffaf-p105">В консоли управления групповой политики найдите контейнер, в котором необходимо создать политику. Например, если все компьютеры Lync Server находятся в подразделении с именем Lync Server, то новую политику следует создать в подразделении Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="4ffaf-119">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **Создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="4ffaf-120">В диалоговом окне **Создание объекта групповой** политики введите имя нового объекта групповой политики в поле **имя** (например, **Lync Server QoS**), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="4ffaf-121">Щелкните правой кнопкой мыши только что созданную политику и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="4ffaf-122">В редакторе "Управление групповыми политиками" последовательно разверните узлы **Конфигурация компьютера**, **Политики** и **Параметры Windows**, щелкните правой кнопкой мыши пункт **QoS на основе политики** и выберите команду **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="4ffaf-123">В диалоговом окне **QoS на основе политики** на открывающей странице введите имя новой политики (например, **Lync Server QoS**) в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="4ffaf-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="4ffaf-124">Выберите поле **Укажите значение DSCP** и установите значение **46**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="4ffaf-125">Оставьте поле **Укажите частоту передачи** пустым и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="4ffaf-p107">На следующей странице убедитесь, что флажок **Все приложения** установлен, и нажмите кнопку **Далее**. Это просто гарантирует, что все приложения будут сопоставлять пакеты из заданного диапазона портов с указанным кодом DSCP.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="4ffaf-p108">На третьей странице убедитесь, что флажки **Любой исходный IP-адрес и Любой конечный IP-адрес** установлены, а затем нажмите кнопку **Далее**. Эти два параметра гарантируют, что пакеты будут управляться независимо от того, с какого компьютера (IP-адреса) отправляются эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="4ffaf-130">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="4ffaf-131">Протокол TCP (TCP-протокол управления передачей) и протокол UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Lync Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="4ffaf-p110">В разделе **Укажите номер исходного порта** выберите **From this source port or range (От этого исходного порта или диапазона**. В сопутствующем текстовом поле введите диапазон портов, зарезервированный для передачи звука. Например, если вы зарезервировали для звукового трафика порты от 49152 до 57500, укажите этот диапазон портов в следующем формате: **49152:57500**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ffaf-p111">Значение DSCP 46 в некоторой степени условное: хотя DSCP 46 часто используется для пометки звуковых пакетов, вы не обязаны использовать DSCP 46 для аудиосвязи. Если качество обслуживания уже реализовано, и для звука используется другой код DSCP (например, DSCP 40), то следует настроить политику качества обслуживания так, чтобы в ней использовался тот же код (т.е. 40 для звука). Если же качество обслуживания только реализуется, то рекомендуется использовать для звука DSCP 46, просто потому что это значение обычно используется для пометки звуковых пакетов.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="4ffaf-p112">После создания политики QoS для звукового трафика следует создать вторую политику для видеотрафика (дополнительно можно создать третью политику для трафика управления общим доступом к приложениям). Чтобы создать политику для видео, выполните ту же процедуру, которая использовалась для создания политики звука, сделав следующие замены.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="4ffaf-141">Используйте другое (и уникальное) имя политики (например, **Lync Server Video**).</span><span class="sxs-lookup"><span data-stu-id="4ffaf-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="4ffaf-p113">Для значения DSCP вместо 46 укажите **34**. (Следует отметить, что вы не обязаны использовать значение DSCP 34. Единственное требование состоит в том, что для видео и звука должны использоваться разные значения DSCP.)</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="4ffaf-p114">Используйте ранее настроенный диапазон портов для трафика видео. Например, если для видео зарезервированы порты от 57501 до 65535, то установите следующий диапазон портов: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="4ffaf-147">Если вы решите создать политику для трафика управления общим доступом к приложениям, то необходимо создать третью политику, сделав следующие замены.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="4ffaf-148">Используйте другое (и уникальное) имя политики (например, **Lync Server Application Sharing**).</span><span class="sxs-lookup"><span data-stu-id="4ffaf-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="4ffaf-p115">Для значения DSCP вместо 46 укажите **24**. (Еще раз, вы не обязаны использовать значение DSCP 24. Единственное требование состоит в том, что для общего доступа к приложениям должно использоваться значение DSCP, отличное от используемого для звука или видео.)</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="4ffaf-p116">Используйте ранее настроенный диапазон портов для трафика видео. Например, если для общего доступа к приложениям зарезервированы порты от 40803 до 49151, то установите следующий диапазон портов: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="4ffaf-154">Созданные вами новые политики вступят в силу только после обновления групповой политики на компьютерах Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="4ffaf-155">Хотя групповая политика периодически обновляется сама по себе, можно принудительно вызвать немедленное обновление, выполнив на каждом компьютере, на котором требуется обновление групповой политики, следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ffaf-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="4ffaf-156">Эту команду можно выполнить в командной консоли Lync Server или в любом командном окне, работающем под учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="4ffaf-157">Чтобы запустить командное окно с учетными данными администратора, нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="4ffaf-158">Чтобы проверить, применены ли новые политики QoS, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="4ffaf-159">На компьютере с Lync Server нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="4ffaf-160">В диалоговом окне **Запуск команды** введите **regedit** и нажмите клавишу ENTER.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="4ffaf-161">В редакторе реестра разверните узел **компьютер**, разверните \*\* \_ локальный \_ компьютер\*\*, а затем последовательно разверните узлы **программное обеспечение**, **политики**, **Microsoft**, разверните узел **Windows**и выберите **QoS**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="4ffaf-162">В узле **QoS** должны быть разделы реестра для каждой только что созданной политики QoS.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="4ffaf-163">Например, если вы создали две новые политики (одно с именем Lync Server Audio QoS и другое с именем Lync Server Video QoS), то должны быть созданы записи в реестре для Lync Server Audio QoS и Lync Server Video QoS.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="4ffaf-164">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="4ffaf-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="4ffaf-165">Нажмите кнопку **Пуск** и щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="4ffaf-166">В диалоговом окне **Выполнить** введите **regedit**, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="4ffaf-167">В редакторе реестра разверните узел **hKey \_ Local \_ Machine**, **система**, разверните **CurrentControlSet**, разверните узел **службы**, а затем разверните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="4ffaf-p120">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**. После создания нового раздела реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="4ffaf-p121">Щелкните элемент **QoS** правой кнопкой мыши, выберите пункт **Создать** и пункт **Строковое значение**. После создания нового значения реестра введите **Do not use NLA** и нажмите клавишу ВВОД, чтобы переименовать его.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="4ffaf-p122">Дважды щелкните элемент **Do no use NLA**. В диалоговом окне **Изменение строки** введите значение **1** в поле **Данные параметра** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-p122">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="4ffaf-174">Закройте редактор реестра, затем перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="4ffaf-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

