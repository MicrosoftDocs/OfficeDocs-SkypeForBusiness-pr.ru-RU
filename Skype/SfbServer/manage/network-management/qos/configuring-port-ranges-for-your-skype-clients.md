---
title: Настройка диапазонов портов и политика качества обслуживания для клиентов
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье описывается настройка диапазонов портов для клиентов и настройка политик качества обслуживания в Skype для бизнеса Server для клиентов, работающих на Windows 10.
ms.openlocfilehash: 9cd5fe3fa84c4acd9365e02c0e5801b63d5497d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122433"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="42a99-103">Настройка диапазонов портов и политика качества обслуживания для клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="42a99-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="42a99-104">В этой статье описывается настройка диапазонов портов для клиентов и настройка политик качества обслуживания в Skype для бизнеса Server для клиентов, работающих на Windows 10.</span><span class="sxs-lookup"><span data-stu-id="42a99-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="42a99-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="42a99-105">Configure port ranges</span></span>

<span data-ttu-id="42a99-106">По умолчанию клиентские приложения Skype для бизнеса могут использовать любой порт между портами 1024 и 65535 при вовлечении в сеанс связи; это происходит из-за того, что определенные диапазоны портов автоматически не включены для клиентов.</span><span class="sxs-lookup"><span data-stu-id="42a99-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="42a99-107">Однако для использования качества службы необходимо перенаделить различные типы трафика (аудио, видео, мультимедиа, общий доступ к приложениям и передача файлов) в ряд уникальных диапазонов портов.</span><span class="sxs-lookup"><span data-stu-id="42a99-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="42a99-108">Это можно сделать с помощью Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="42a99-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="42a99-109">Конечные пользователи не могут самостоятельно вносить эти изменения.</span><span class="sxs-lookup"><span data-stu-id="42a99-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="42a99-110">Изменения порта могут вноситься только администраторами с помощью Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="42a99-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="42a99-111">Вы можете определить, какие диапазоны портов в настоящее время используются для сеансов связи, запуская следующую команду из командной команды Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="42a99-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="42a99-112">Предполагая, что с момента установки Skype для бизнеса Server вы не внесли никаких изменений в параметры конференций, необходимо получить сведения, включающие следующие значения свойств:</span><span class="sxs-lookup"><span data-stu-id="42a99-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="42a99-113">Если внимательно посмотреть на предыдущие данные, можно увидеть две важных вещи.</span><span class="sxs-lookup"><span data-stu-id="42a99-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="42a99-114">Во-первых, для свойства ClientMediaPortRangeEnabled задано значение False:</span><span class="sxs-lookup"><span data-stu-id="42a99-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="42a99-115">Это важно, так как, когда это свойство заданной для False, клиенты Skype для бизнеса будут использовать любой доступный порт между портами 1024 и 65535 при вовлечении в сеанс связи; это верно независимо от других параметров порта (например, ClientMediaPort или ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="42a99-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="42a99-116">Если вы хотите ограничить использование определенного набора портов (и это то, что вы хотите сделать, если вы планируете реализовать качество службы), то сначала необходимо включить диапазоны клиентских медиа-портов.</span><span class="sxs-lookup"><span data-stu-id="42a99-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="42a99-117">Это можно сделать с помощью следующей Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42a99-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="42a99-p105">Приведенная выше команда активирует диапазоны портов мультимедиа клиентов для глобальной коллекции параметров конфигурации конференций. Однако данные настройки также могут применяться к области сайта или службы (только для службы сервера конференций). Чтобы включить диапазоны портов мультимедиа клиентов для определенного сайта или сервера, укажите идентификатор этого сайта или сервера при вызове команды Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="42a99-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="42a99-120">Или же вы можете использовать следующую команду, чтобы одновременно включить диапазоны порты для всех параметров конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="42a99-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="42a99-121">Второй важный момент — в примере выходных данных показано, что по умолчанию набор диапазонов портов мультимедиа для каждого типа сетевого трафика идентичны:</span><span class="sxs-lookup"><span data-stu-id="42a99-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="42a99-p106">Чтобы реализовать QoS, каждый из этих диапазонов портов должен быть уникальным. Например, вы можете настроить следующие диапазоны портов:</span><span class="sxs-lookup"><span data-stu-id="42a99-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42a99-124">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="42a99-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="42a99-125">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="42a99-125">Port Start</span></span></th>
<th><span data-ttu-id="42a99-126">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="42a99-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42a99-127">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="42a99-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="42a99-128">50020</span><span class="sxs-lookup"><span data-stu-id="42a99-128">50020</span></span></p></td>
<td><p><span data-ttu-id="42a99-129">20</span><span class="sxs-lookup"><span data-stu-id="42a99-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42a99-130">Видео</span><span class="sxs-lookup"><span data-stu-id="42a99-130">Video</span></span></p></td>
<td><p><span data-ttu-id="42a99-131">58000</span><span class="sxs-lookup"><span data-stu-id="42a99-131">58000</span></span></p></td>
<td><p><span data-ttu-id="42a99-132">20</span><span class="sxs-lookup"><span data-stu-id="42a99-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42a99-133">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="42a99-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="42a99-134">42000</span><span class="sxs-lookup"><span data-stu-id="42a99-134">42000</span></span></p></td>
<td><p><span data-ttu-id="42a99-135">20</span><span class="sxs-lookup"><span data-stu-id="42a99-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42a99-136">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="42a99-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="42a99-137">42020</span><span class="sxs-lookup"><span data-stu-id="42a99-137">42020</span></span></p></td>
<td><p><span data-ttu-id="42a99-138">20</span><span class="sxs-lookup"><span data-stu-id="42a99-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42a99-139">В приведенной выше таблице диапазоны портов клиента представляют подмножество диапазонов портов, настроенных для ваших серверов.</span><span class="sxs-lookup"><span data-stu-id="42a99-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="42a99-140">Например, на серверах для совместного использования приложений были настроены порты с 40803 по 49151.</span><span class="sxs-lookup"><span data-stu-id="42a99-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="42a99-141">Это также делается в первую очередь для упростить администрирование QoS: клиентские порты не должны представлять подмножество портов, используемых на сервере.</span><span class="sxs-lookup"><span data-stu-id="42a99-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="42a99-142">(Например, на клиентских компьютерах можно настроить общий доступ к приложениям для использования, скажем, портов от 10000 до 10019.) Однако рекомендуется сделать клиентский порт диапазоном подмножество диапазонов портов сервера.</span><span class="sxs-lookup"><span data-stu-id="42a99-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="42a99-143">Кроме того, вы могли заметить, что 8348 портов было выделено для совместного использования приложений на серверах, но всего 20 портов было выделено для совместного использования приложений на клиентах.</span><span class="sxs-lookup"><span data-stu-id="42a99-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="42a99-144">Это также рекомендуется, но не является правилом жесткой и быстрой.</span><span class="sxs-lookup"><span data-stu-id="42a99-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="42a99-145">Как правило, каждый доступный порт может представлять один сеанс связи: если в диапазоне портов доступно 100 портов, это означает, что компьютер, о которых идет речь, может участвовать в не более чем 100 сеансах связи в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="42a99-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="42a99-146">Поскольку серверы, вероятно, будут участвовать в большем числе сеансов, чем клиенты, имеет смысл открыть намного больше портов на серверах, чем на клиентах.</span><span class="sxs-lookup"><span data-stu-id="42a99-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="42a99-147">Выделение 20 портов для совместного использования приложений на клиентах означает, что пользователь одновременно может участвовать в 20 сеансах совместного применения приложений на указанном устройстве.</span><span class="sxs-lookup"><span data-stu-id="42a99-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="42a99-148">Если должно быть достаточно для подавляющего большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="42a99-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="42a99-149">Чтобы назначить предыдущие диапазоны портов глобальной коллекции параметров конфигурации конференций, можно использовать следующую команду командной командой Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="42a99-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="42a99-150">Или с помощью этой команды можно назначить эти же диапазоны портов всем параметрам конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="42a99-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="42a99-151">Отдельные пользователи должны выйти из Skype для бизнеса, а затем войти обратно, прежде чем эти изменения действительно в силу.</span><span class="sxs-lookup"><span data-stu-id="42a99-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="42a99-152">Вы также можете включить диапазоны портов мультимедиа клиентов, а затем назначить эти диапазоны портов с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="42a99-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="42a99-153">Например:</span><span class="sxs-lookup"><span data-stu-id="42a99-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="42a99-154">Настройка политик качества обслуживания для клиентов, работающих в Windows 10</span><span class="sxs-lookup"><span data-stu-id="42a99-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="42a99-155">Помимо указания диапазонов портов для использования клиентами Skype для бизнеса необходимо также создать отдельные политики качества обслуживания, которые будут применяться к клиентным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="42a99-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="42a99-156">(Политики качества служб, созданные для серверов conferencing, Application и Mediation, не должны применяться к клиентских компьютерам.) Эта информация распространяется только на компьютеры с клиентом Skype для бизнеса и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="42a99-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="42a99-157">В следующем примере этот набор диапазонов портов используется для создания политики звука и политики видео:</span><span class="sxs-lookup"><span data-stu-id="42a99-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42a99-158">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="42a99-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="42a99-159">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="42a99-159">Port Start</span></span></th>
<th><span data-ttu-id="42a99-160">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="42a99-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42a99-161">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="42a99-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="42a99-162">50020</span><span class="sxs-lookup"><span data-stu-id="42a99-162">50020</span></span></p></td>
<td><p><span data-ttu-id="42a99-163">20</span><span class="sxs-lookup"><span data-stu-id="42a99-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42a99-164">Видео</span><span class="sxs-lookup"><span data-stu-id="42a99-164">Video</span></span></p></td>
<td><p><span data-ttu-id="42a99-165">58000</span><span class="sxs-lookup"><span data-stu-id="42a99-165">58000</span></span></p></td>
<td><p><span data-ttu-id="42a99-166">20</span><span class="sxs-lookup"><span data-stu-id="42a99-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42a99-167">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="42a99-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="42a99-168">42000</span><span class="sxs-lookup"><span data-stu-id="42a99-168">42000</span></span></p></td>
<td><p><span data-ttu-id="42a99-169">20</span><span class="sxs-lookup"><span data-stu-id="42a99-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42a99-170">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="42a99-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="42a99-171">42020</span><span class="sxs-lookup"><span data-stu-id="42a99-171">42020</span></span></p></td>
<td><p><span data-ttu-id="42a99-172">20</span><span class="sxs-lookup"><span data-stu-id="42a99-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="42a99-173">Чтобы создать политику качества звука службы для компьютеров Windows 10, сначала войдите на компьютер, на котором установлено управление групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="42a99-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="42a99-174">Откройте управление групповой политикой (нажмите **кнопку Начните,** указать на **административные** средства, а затем нажмите кнопку **Управление** групповой политикой), а затем выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="42a99-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="42a99-175">В консоли управления групповыми политиками найдите контейнер, в котором следует создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="42a99-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="42a99-176">Например, если все клиентские компьютеры находятся в OU с именем Customers, новая политика должна быть создана в клиентской OU.</span><span class="sxs-lookup"><span data-stu-id="42a99-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="42a99-177">Щелкните правой кнопкой мыши соответствующий контейнер, а затем **нажмите кнопку Создать GPO в** этом домене, и ссылка его здесь .</span><span class="sxs-lookup"><span data-stu-id="42a99-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="42a99-178">В **диалоговом** окне New GPO введите имя нового объекта групповой политики в поле **Имя** и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="42a99-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="42a99-179">Щелкните правой кнопкой мыши вновь созданную политику и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="42a99-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="42a99-180">В редакторе управления групповой политикой разойдитесь по конфигурации **компьютера,** расширйте **параметры Windows,** щелкните правой кнопкой мыши **QoS** на основе политики, а затем нажмите **кнопку Создать новую политику.**</span><span class="sxs-lookup"><span data-stu-id="42a99-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="42a99-181">В **диалоговом окне QoS** на основе политики на странице открытия введите имя новой политики в поле **Имя.**</span><span class="sxs-lookup"><span data-stu-id="42a99-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="42a99-182">Выберите поле **Укажите значение DSCP** и установите значение **46**.</span><span class="sxs-lookup"><span data-stu-id="42a99-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="42a99-183">Оставьте поле **Укажите частоту передачи** пустым и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42a99-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="42a99-184">На следующей странице выберите только приложения с этим исполняемым именем, **введите** Lync.exeимя, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42a99-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="42a99-185">Этот параметр предписывает политике только приоритизировать соответствие трафику клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="42a99-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="42a99-186">На третьей странице убедитесь, что выбраны  любой исходный **IP-адрес** и любой IP-адрес назначения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="42a99-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="42a99-187">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, с какого компьютера (IP-адреса) отправляются эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="42a99-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="42a99-188">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="42a99-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="42a99-189">TCP (Протокол управления передачей) и UDP (User Datagram Protocol) — это два сетевых протокола, наиболее часто используемых Skype для бизнеса Server и его клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="42a99-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="42a99-p117">В разделе **Укажите номер исходного порта** выберите **От этого исходного порта или диапазона**. В сопутствующем текстовом поле введите диапазон портов, зарезервированный для передачи звука. Например, если вы зарезервировали для звукового трафика порты от 50020 до 50039, укажите этот диапазон портов в следующем формате: **50020:50039**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="42a99-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="42a99-p118">После создания политики QoS для звука следует создать вторую политику для видео. Для этого выполните ту же основную процедуру, которой вы следовали при создании политики для аудио, внеся следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="42a99-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="42a99-196">Используйте другое (и уникальное) имя политики.</span><span class="sxs-lookup"><span data-stu-id="42a99-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="42a99-p119">Для значения DSCP вместо 46 укажите **34**. (Как было отмечено ранее, вы не обязаны использовать значение DSCP 34; просто назначьте для видео значение DSCP, отличное от значения для аудио.)</span><span class="sxs-lookup"><span data-stu-id="42a99-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="42a99-199">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="42a99-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="42a99-200">Например, если для видео зарезервированы порты от 58000 до 58019, установите диапазон порта: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="42a99-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="42a99-201">Если вы решили создать политику управления трафиком общего доступа к приложениям, сделайте эти замены:</span><span class="sxs-lookup"><span data-stu-id="42a99-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="42a99-202">Используйте другое (и уникальное) имя политики (например, **Skype for Business Server Application Sharing).**</span><span class="sxs-lookup"><span data-stu-id="42a99-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="42a99-p121">Для значения DSCP вместо 46 укажите **24**. (Опять же, это значение не должно быть равно 24, оно просто должно отличаться от значений DSCP, используемых для аудио и видео.)</span><span class="sxs-lookup"><span data-stu-id="42a99-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="42a99-205">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="42a99-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="42a99-206">Например, если вы зарезервировали порты с 42000 по 42019 для общего доступа к приложениям, установите диапазон портов таким образом: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="42a99-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="42a99-207">Для политики передачи файлов</span><span class="sxs-lookup"><span data-stu-id="42a99-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="42a99-208">Используйте другое (и уникальное) имя политики (например, **Передача файлов Skype для бизнеса Server).**</span><span class="sxs-lookup"><span data-stu-id="42a99-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="42a99-209">Установите значение DSCP, равное **14**.</span><span class="sxs-lookup"><span data-stu-id="42a99-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="42a99-210">(Опять же, это значение не должно быть равно именно 14, оно просто должно быть уникальным кодом DSCP.)</span><span class="sxs-lookup"><span data-stu-id="42a99-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="42a99-211">Используйте ранее настроенный диапазон портов для приложения.</span><span class="sxs-lookup"><span data-stu-id="42a99-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="42a99-212">Например, если вы зарезервировали порты 42020 до 42039 для общего доступа к приложениям, установите диапазон портов таким образом: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="42a99-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="42a99-p125">Новые политики не будут действовать, пока не обновится групповая политика на клиентских компьютерах. Хотя групповая политика периодически обновляется сама по себе, можно принудительно вызвать немедленное обновление, выполнив на каждом компьютере, на котором требуется обновление групповой политики, следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42a99-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="42a99-p126">Эту команду можно выполнить из любого окна командной строки, запущенного с учетными данными администратора. Чтобы запустить командное окно с учетными данными администратора, нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="42a99-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="42a99-217">Помните, что эти политики должны быть направлены на ваши клиентские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="42a99-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="42a99-218">Они не должны применяться к серверам под управлением Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42a99-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="42a99-219">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="42a99-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="42a99-220">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="42a99-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="42a99-221">В **диалоговом** окне Run введите **regedit** и нажмите кнопку ENTER.</span><span class="sxs-lookup"><span data-stu-id="42a99-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="42a99-222">В редакторе реестра раздвяйте локализатор **HKEY, \_ \_** расширйте **SYSTEM,** расширйте **CurrentControlSet,** расширяйте службы, а затем **расширяйте Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="42a99-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="42a99-223">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**.</span><span class="sxs-lookup"><span data-stu-id="42a99-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="42a99-224">После создания нового ключа реестра введите **QoS** и нажмите кнопку ENTER, чтобы переименовать ключ.</span><span class="sxs-lookup"><span data-stu-id="42a99-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="42a99-225">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="42a99-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="42a99-226">После создания нового значения реестра введите Не **используйте NLA,** а затем нажмите кнопку ENTER, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="42a99-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="42a99-227">Дважды щелкните элемент **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="42a99-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="42a99-228">В **диалоговом окне Изменить строку** введите **1** в поле **данных Значение,** а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="42a99-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="42a99-229">Закройте редактор реестра и перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="42a99-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="42a99-230">Настройка качества обслуживания на компьютерах с помощью нескольких сетевых адаптеров</span><span class="sxs-lookup"><span data-stu-id="42a99-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="42a99-231">Если у вас есть компьютер с несколькими сетевыми адаптерами, иногда можно запускать проблемы, в которых значения DSCP показаны как 0x00, а не настроено.</span><span class="sxs-lookup"><span data-stu-id="42a99-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="42a99-232">Обычно это происходит на компьютерах, где одному или нескольким сетевым адаптерам не удается получить доступ к вашему домену Active Directory (например, если эти адаптеры используются в частной сети).</span><span class="sxs-lookup"><span data-stu-id="42a99-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="42a99-233">В таких случаях значения DSCP помечаются для адаптеров, которые могут осуществить доступ к домену, и не помечаются для адаптеров, которым такой доступ получить не удается.</span><span class="sxs-lookup"><span data-stu-id="42a99-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="42a99-234">Если вы хотите отметить значения DSCP для всех сетевых адаптеров на компьютере, включая адаптеры, которые не имеют доступа к вашему домену, необходимо добавить и настроить значение в реестр.</span><span class="sxs-lookup"><span data-stu-id="42a99-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="42a99-235">Это можно сделать посредством следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="42a99-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="42a99-236">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="42a99-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="42a99-237">В **диалоговом** окне Run введите **regedit** и нажмите кнопку ENTER.</span><span class="sxs-lookup"><span data-stu-id="42a99-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="42a99-238">В редакторе реестра раздвяйте локализатор **HKEY, \_ \_** расширйте **SYSTEM,** расширйте **CurrentControlSet,** расширяйте службы, а затем **расширяйте Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="42a99-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="42a99-239">Если вы не видите раздел реестра **QoS**, щелкните элемент **Tcpip** правой кнопкой мыши, выберите пункт **Создать** и пункт **Раздел**.</span><span class="sxs-lookup"><span data-stu-id="42a99-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="42a99-240">После создания нового ключа введите **QoS** и нажмите кнопку ENTER, чтобы переименовать ключ.</span><span class="sxs-lookup"><span data-stu-id="42a99-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="42a99-241">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="42a99-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="42a99-242">После создания нового значения реестра введите Не **используйте NLA,** а затем нажмите кнопку ENTER, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="42a99-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="42a99-243">Дважды щелкните элемент **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="42a99-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="42a99-244">В **диалоговом окне Изменить строку** введите **1** в поле **данных Значение,** а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="42a99-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="42a99-245">После создания и настройки нового значения реестра необходимо будет перезагрудить компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="42a99-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="42a99-246">См. также</span><span class="sxs-lookup"><span data-stu-id="42a99-246">See also</span></span>

[<span data-ttu-id="42a99-247">Создание объекта групповой политики в Windows 10</span><span class="sxs-lookup"><span data-stu-id="42a99-247">Create a Group Policy Object in Windows 10</span></span>](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)