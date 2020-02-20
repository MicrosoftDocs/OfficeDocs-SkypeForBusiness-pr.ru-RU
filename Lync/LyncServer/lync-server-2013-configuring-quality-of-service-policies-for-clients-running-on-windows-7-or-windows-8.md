---
title: 'Lync Server 2013: Настройка политик качества обслуживания для клиентов, работающих под управлением Windows 7 или Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdb331a8d0e6a369f67726c755d76ab1d3bec58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="72010-102">Настройка политик качества обслуживания в Lync Server 2013 для клиентов под управлением Windows 7 или Windows 8</span><span class="sxs-lookup"><span data-stu-id="72010-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72010-103">_**Последнее изменение темы:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="72010-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="72010-104">Кроме указания диапазонов портов для использования клиентами Lync, необходимо также создать отдельные политики качества обслуживания, которые будут применяться к клиентским компьютерам.</span><span class="sxs-lookup"><span data-stu-id="72010-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="72010-105">(Политики качества обслуживания, созданные для конференц-связи, приложений и серверов-посредников, не должны применяться к клиентским компьютерам.) Эти сведения относятся только к компьютерам, на которых установлен клиент Lync 2013 и Windows 7 или Windows 8.</span><span class="sxs-lookup"><span data-stu-id="72010-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="72010-106">В следующем примере этот набор диапазонов портов используется для создания политики звука и политики видео:</span><span class="sxs-lookup"><span data-stu-id="72010-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72010-107">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="72010-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="72010-108">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="72010-108">Port Start</span></span></th>
<th><span data-ttu-id="72010-109">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="72010-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72010-110">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="72010-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="72010-111">50020</span><span class="sxs-lookup"><span data-stu-id="72010-111">50020</span></span></p></td>
<td><p><span data-ttu-id="72010-112">двадцать</span><span class="sxs-lookup"><span data-stu-id="72010-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72010-113">Видео</span><span class="sxs-lookup"><span data-stu-id="72010-113">Video</span></span></p></td>
<td><p><span data-ttu-id="72010-114">58000</span><span class="sxs-lookup"><span data-stu-id="72010-114">58000</span></span></p></td>
<td><p><span data-ttu-id="72010-115">двадцать</span><span class="sxs-lookup"><span data-stu-id="72010-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72010-116">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="72010-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="72010-117">42000</span><span class="sxs-lookup"><span data-stu-id="72010-117">42000</span></span></p></td>
<td><p><span data-ttu-id="72010-118">двадцать</span><span class="sxs-lookup"><span data-stu-id="72010-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72010-119">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="72010-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="72010-120">42020</span><span class="sxs-lookup"><span data-stu-id="72010-120">42020</span></span></p></td>
<td><p><span data-ttu-id="72010-121">двадцать</span><span class="sxs-lookup"><span data-stu-id="72010-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="72010-122">Чтобы создать политику звука качества обслуживания для компьютеров с Windows 7 или Windows 8, сначала войдите на компьютер, на котором установлена консоль управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="72010-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="72010-123">Откройте управление групповыми политиками (нажмите кнопку **Пуск**, выберите **Администрирование** и щелкните **Управление групповыми политиками**), а затем выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="72010-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="72010-p103">В консоли управления групповыми политиками найдите контейнер, в котором следует создать новую политику. Например, если все ваши клиентские компьютеры расположены в подразделении с именем Lync Server, то новую политику следует создавать в этом подразделении.</span><span class="sxs-lookup"><span data-stu-id="72010-p103">In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="72010-126">Щелкните соответствующий контейнер правой кнопкой мыши и выберите пункт **Создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="72010-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="72010-127">В диалоговом окне **Создание нового объекта групповой политики** в поле **Имя** введите имя для этого нового объекта групповой политики (например, **Звук Lync**) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72010-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="72010-128">Щелкните правой кнопкой мыши только что созданную политику и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="72010-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="72010-129">В редакторе "Управление групповыми политиками" последовательно разверните узлы **Конфигурация компьютера**, **Политики** и **Параметры Windows**, щелкните правой кнопкой мыши пункт **QoS на основе политики** и выберите команду **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="72010-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="72010-p104">В диалоговом окне **QoS на основе политики** на открывшейся странице введите имя для новой политики (например, **Звук Lync**) в поле **Имя**. Выберите поле **Укажите значение DSCP** и установите значение **46**. Оставьте поле **Укажите частоту передачи** пустым и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="72010-p104">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="72010-133">На следующей странице выберите **только приложения с именем исполняемого файла** и введите имя **Lync. exe**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="72010-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="72010-134">Этот параметр предписывает политике определять только приоритетный трафик, совпадающий с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="72010-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="72010-p106">На третьей странице убедитесь, что выбраны оба параметра **Любой исходный IP-адрес** и **Любой конечный IP-адрес**, и нажмите кнопку **Далее**. Эти два параметра используются, чтобы гарантировать, что пакеты будут управляться независимо от того, какой компьютер (IP-адрес) отправил их и какой компьютер (IP-адрес) получит эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="72010-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="72010-137">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="72010-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="72010-138">Протокол TCP (TCP-протокол управления передачей) и протокол UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Lync Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="72010-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="72010-p108">В разделе **Укажите номер исходного порта** выберите **От этого исходного порта или диапазона**. В сопутствующем текстовом поле введите диапазон портов, зарезервированный для передачи звука. Например, если вы зарезервировали для звукового трафика порты от 50020 до 50039, укажите этот диапазон портов в следующем формате: **50020:50039**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="72010-p108">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="72010-p109">После создания политики QoS для звука следует создать вторую политику для видео. Для этого выполните ту же основную процедуру, которой вы следовали при создании политики для аудио, внеся следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="72010-p109">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="72010-145">Используйте другое (и уникальное) имя политики (например, **Видео Lync**).</span><span class="sxs-lookup"><span data-stu-id="72010-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="72010-p110">Для значения DSCP вместо 46 укажите **34**. (Как было отмечено ранее, вы не обязаны использовать значение DSCP 34; просто назначьте для видео значение DSCP, отличное от значения для аудио.)</span><span class="sxs-lookup"><span data-stu-id="72010-p110">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="72010-p111">Используйте ранее настроенный диапазон портов для трафика видео. Например, если для видео зарезервированы порты от 58000 до 58019, то установите следующий диапазон портов: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="72010-p111">Use the previously-configured port range for video traffic. For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="72010-150">Если вы решили создать политику для управления трафиком совместного использования приложений, внесите следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="72010-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="72010-151">Используйте другое (и уникальное) имя политики (например, **Совместное использование приложений Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="72010-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="72010-p112">Для значения DSCP вместо 46 укажите **24**. (Опять же, это значение не должно быть равно 24, оно просто должно отличаться от значений DSCP, используемых для аудио и видео.)</span><span class="sxs-lookup"><span data-stu-id="72010-p112">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="72010-p113">Используйте ранее настроенный диапазон портов для трафика видео. Например, если для общего доступа к приложениям зарезервированы порты от 42000 до 42019, то установите следующий диапазон портов: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="72010-p113">Use the previously-configured port range for video traffic. For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="72010-156">Для политики передачи файлов</span><span class="sxs-lookup"><span data-stu-id="72010-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="72010-157">Используйте другое (и уникальное) имя политики (например, **Передача файлов Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="72010-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="72010-p114">Установите значение DSCP, равное **14**. (Опять же, это значение не должно быть равно именно 14, оно просто должно быть уникальным кодом DSCP.)</span><span class="sxs-lookup"><span data-stu-id="72010-p114">Set the DSCP value to **14**. (Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="72010-160">Используйте ранее настроенный диапазон портов для приложения.</span><span class="sxs-lookup"><span data-stu-id="72010-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="72010-161">Например, если для общего доступа к приложениям зарезервированы порты от 42020 до 42039, то установите следующий диапазон портов: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="72010-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="72010-p116">Новые политики не будут действовать, пока не обновится групповая политика на клиентских компьютерах. Хотя групповая политика периодически обновляется сама по себе, можно принудительно вызвать немедленное обновление, выполнив на каждом компьютере, на котором требуется обновление групповой политики, следующую команду:</span><span class="sxs-lookup"><span data-stu-id="72010-p116">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="72010-p117">Эту команду можно выполнить из любого окна командной строки, запущенного с учетными данными администратора. Чтобы запустить командное окно с учетными данными администратора, нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="72010-p117">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="72010-166">Помните, что эти политики должны быть направлены на ваши клиентские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="72010-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="72010-167">Они не должны применяться к серверам, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72010-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="72010-168">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="72010-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="72010-169">Нажмите кнопку **Пуск** и щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="72010-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="72010-170">В диалоговом окне **Выполнить** введите **regedit**, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="72010-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="72010-171">В редакторе реестра разверните узел **hKey\_Local\_Machine**, **система**, разверните **CurrentControlSet**, разверните узел **службы**, а затем разверните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="72010-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="72010-p119">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**. После создания нового раздела реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="72010-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="72010-p120">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**. После создания нового параметра реестра введите **Do not use NLA** и нажмите клавишу ВВОД для переименования значения.</span><span class="sxs-lookup"><span data-stu-id="72010-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="72010-p121">Дважды щелкните элемент **Do no use NLA**. В диалоговом окне **Изменение строки** введите значение **1** в поле **Данные параметра** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72010-p121">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="72010-178">Закройте редактор реестра и перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="72010-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="72010-179">Настройка качества обслуживания на компьютерах с несколькими сетевыми адаптерами</span><span class="sxs-lookup"><span data-stu-id="72010-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="72010-p122">Если вы используете компьютер с несколькими сетевыми адаптерами, то можете столкнуться с проблемами, когда значения DSCP отображаются как 0x00 вместо заданного значения. Обычно это происходит на компьютерах, где одному или нескольким сетевым адаптерам не удается получить доступ к вашему домену Active Directory (например, если эти адаптеры используются в частной сети). В таких случаях значения DSCP помечаются для адаптеров, которые могут осуществить доступ к домену, и не помечаются для адаптеров, которым такой доступ получить не удается.</span><span class="sxs-lookup"><span data-stu-id="72010-p122">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value. This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network). In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="72010-p123">Если вы хотите пометить значения DSCP для всех сетевых адаптеров на компьютере, включая те, которые не имеют доступа к домену, потребуется добавить и настроить значение в реестре. Для этого можно выполнить следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="72010-p123">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry. That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="72010-185">Нажмите кнопку **Пуск** и выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="72010-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="72010-186">В диалоговом окне **Выполнить** введите **regedit**, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="72010-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="72010-187">В редакторе реестра разверните узел **hKey\_Local\_Machine**, **система**, разверните **CurrentControlSet**, разверните узел **службы**, а затем разверните **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="72010-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="72010-p124">Если вы не видите раздел реестра **QoS**, щелкните элемент **Tcpip** правой кнопкой мыши, выберите пункт **Создать** и пункт **Раздел**. После создания нового раздела реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать его.</span><span class="sxs-lookup"><span data-stu-id="72010-p124">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**. After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="72010-p125">Щелкните элемент **QoS** правой кнопкой мыши, выберите пункт **Создать** и пункт **Строковое значение**. После создания нового значения реестра введите **Do not use NLA** и нажмите клавишу ВВОД, чтобы переименовать его.</span><span class="sxs-lookup"><span data-stu-id="72010-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="72010-p126">Дважды щелкните элемент **Do no use NLA**. В диалоговом окне **Изменение строки** введите значение **1** в поле **Данные параметра** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72010-p126">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="72010-194">После создания и настройки нового значения реестра потребуется перезагрузить компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="72010-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

