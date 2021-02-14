---
title: Настройка диапазонов портов и политики качества обслуживания для клиентов
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
description: В этой статье описывается настройка диапазонов портов для клиентов и настройка политик качества обслуживания в Skype для бизнеса Server для клиентов под управлением Windows 10.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814209"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="74a3f-103">Настройка диапазонов портов и политики качества обслуживания для клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="74a3f-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="74a3f-104">В этой статье описывается настройка диапазонов портов для клиентов и настройка политик качества обслуживания в Skype для бизнеса Server для клиентов под управлением Windows 10.</span><span class="sxs-lookup"><span data-stu-id="74a3f-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="74a3f-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="74a3f-105">Configure port ranges</span></span>

<span data-ttu-id="74a3f-106">По умолчанию клиентские приложения Skype для бизнеса могут использовать любой порт между портами 1024 и 65535 при использовании сеанса связи; Это происходит потому, что определенные диапазоны портов не включены автоматически для клиентов.</span><span class="sxs-lookup"><span data-stu-id="74a3f-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="74a3f-107">Однако для использования качества обслуживания необходимо перенаказать различные типы трафика (звук, видео, мультимедиа, общий доступ к приложениям и передачу файлов) на ряд уникальных диапазонов портов.</span><span class="sxs-lookup"><span data-stu-id="74a3f-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="74a3f-108">Это можно сделать с помощью Set-CsConferencingConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="74a3f-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="74a3f-109">Конечные пользователи не могут вносить эти изменения самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="74a3f-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="74a3f-110">Изменения портов могут внести только администраторы с помощью Set-CsConferencingConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="74a3f-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="74a3f-111">Вы можете определить, какие диапазоны портов в настоящее время используются для сеансов связи, вы можете использовать следующую команду в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="74a3f-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="74a3f-112">Предположим, что с момента установки Skype для бизнеса Server вы не внесе никаких изменений в параметры conferencing, вы должны получить сведения, включающие следующие значения свойств:</span><span class="sxs-lookup"><span data-stu-id="74a3f-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="74a3f-113">Если внимательно посмотреть на предыдущие данные, можно увидеть две важных вещи.</span><span class="sxs-lookup"><span data-stu-id="74a3f-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="74a3f-114">Во-первых, для свойства ClientMediaPortRangeEnabled задано значение False:</span><span class="sxs-lookup"><span data-stu-id="74a3f-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="74a3f-115">Это важно, так как, если для этого свойства установлено значение False, клиенты Skype для бизнеса будут использовать любой доступный порт между портами 1024 и 65535 при использовании сеанса связи; Это справедливо независимо от других параметров порта (например, ClientMediaPort или ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="74a3f-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="74a3f-116">Если вы хотите ограничить использование указанным набором портов (и это необходимо сделать, если вы планируете реализовать качество обслуживания), необходимо сначала включить диапазоны портов мультимедиа клиента.</span><span class="sxs-lookup"><span data-stu-id="74a3f-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="74a3f-117">Это можно сделать с помощью следующей Windows PowerShell команды:</span><span class="sxs-lookup"><span data-stu-id="74a3f-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="74a3f-p105">Приведенная выше команда активирует диапазоны портов мультимедиа клиентов для глобальной коллекции параметров конфигурации конференций. Однако данные настройки также могут применяться к области сайта или службы (только для службы сервера конференций). Чтобы включить диапазоны портов мультимедиа клиентов для определенного сайта или сервера, укажите идентификатор этого сайта или сервера при вызове команды Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="74a3f-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="74a3f-120">Или же вы можете использовать следующую команду, чтобы одновременно включить диапазоны порты для всех параметров конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="74a3f-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="74a3f-121">Второй важный момент — в примере выходных данных показано, что по умолчанию набор диапазонов портов мультимедиа для каждого типа сетевого трафика идентичны:</span><span class="sxs-lookup"><span data-stu-id="74a3f-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="74a3f-p106">Чтобы реализовать QoS, каждый из этих диапазонов портов должен быть уникальным. Например, вы можете настроить следующие диапазоны портов:</span><span class="sxs-lookup"><span data-stu-id="74a3f-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a3f-124">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="74a3f-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="74a3f-125">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="74a3f-125">Port Start</span></span></th>
<th><span data-ttu-id="74a3f-126">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="74a3f-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a3f-127">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="74a3f-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="74a3f-128">50020</span><span class="sxs-lookup"><span data-stu-id="74a3f-128">50020</span></span></p></td>
<td><p><span data-ttu-id="74a3f-129">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a3f-130">Видео</span><span class="sxs-lookup"><span data-stu-id="74a3f-130">Video</span></span></p></td>
<td><p><span data-ttu-id="74a3f-131">58000</span><span class="sxs-lookup"><span data-stu-id="74a3f-131">58000</span></span></p></td>
<td><p><span data-ttu-id="74a3f-132">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a3f-133">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="74a3f-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="74a3f-134">42000</span><span class="sxs-lookup"><span data-stu-id="74a3f-134">42000</span></span></p></td>
<td><p><span data-ttu-id="74a3f-135">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a3f-136">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="74a3f-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="74a3f-137">42020</span><span class="sxs-lookup"><span data-stu-id="74a3f-137">42020</span></span></p></td>
<td><p><span data-ttu-id="74a3f-138">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74a3f-139">В приведенной выше таблице диапазоны портов клиента представляют подмножество диапазонов портов, настроенных для ваших серверов.</span><span class="sxs-lookup"><span data-stu-id="74a3f-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="74a3f-140">Например, на серверах для совместного использования приложений были настроены порты с 40803 по 49151.</span><span class="sxs-lookup"><span data-stu-id="74a3f-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="74a3f-141">Это также сделано главным образом для упростить администрирование QoS: клиентские порты не должны представлять подмножество портов, используемых на сервере.</span><span class="sxs-lookup"><span data-stu-id="74a3f-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="74a3f-142">(Например, на клиентских компьютерах можно настроить общий доступ к приложениям для использования, например, портов от 10000 до 10019.) Однако рекомендуется сделать диапазоны портов клиента подмножество диапазонов портов сервера.</span><span class="sxs-lookup"><span data-stu-id="74a3f-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="74a3f-143">Кроме того, вы могли заметить, что 8348 портов было выделено для совместного использования приложений на серверах, но всего 20 портов было выделено для совместного использования приложений на клиентах.</span><span class="sxs-lookup"><span data-stu-id="74a3f-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="74a3f-144">Это также рекомендуется, но не является жестко и быстрое правило.</span><span class="sxs-lookup"><span data-stu-id="74a3f-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="74a3f-145">Как правило, каждый доступный порт может представлять один сеанс связи: если в диапазоне портов доступно 100 портов, это означает, что компьютер может участвовать не более чем в 100 сеансах связи в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="74a3f-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="74a3f-146">Поскольку серверы, вероятно, будут участвовать в большем числе сеансов, чем клиенты, имеет смысл открыть намного больше портов на серверах, чем на клиентах.</span><span class="sxs-lookup"><span data-stu-id="74a3f-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="74a3f-147">Выделение 20 портов для совместного использования приложений на клиентах означает, что пользователь одновременно может участвовать в 20 сеансах совместного применения приложений на указанном устройстве.</span><span class="sxs-lookup"><span data-stu-id="74a3f-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="74a3f-148">Если должно быть достаточно для подавляющего большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="74a3f-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="74a3f-149">Чтобы назначить предыдущие диапазоны портов глобальной коллекции параметров конфигурации, можно использовать следующую команду командной оболочки Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="74a3f-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="74a3f-150">Или с помощью этой команды можно назначить эти же диапазоны портов всем параметрам конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="74a3f-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="74a3f-151">Отдельные пользователи должны выйти из Skype для бизнеса, а затем снова войти в систему, чтобы эти изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="74a3f-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="74a3f-152">Вы также можете включить диапазоны портов мультимедиа клиентов, а затем назначить эти диапазоны портов с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="74a3f-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="74a3f-153">Например:</span><span class="sxs-lookup"><span data-stu-id="74a3f-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="74a3f-154">Настройка политик качества обслуживания для клиентов, работающих в Windows 10</span><span class="sxs-lookup"><span data-stu-id="74a3f-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="74a3f-155">Помимо указания диапазонов портов для использования клиентами Skype для бизнеса, необходимо также создать отдельные политики качества обслуживания, которые будут применяться к клиентских компьютерам.</span><span class="sxs-lookup"><span data-stu-id="74a3f-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="74a3f-156">(Политики качества обслуживания, созданные для серверов-служб, приложений и серверов-посредников, не должны применяться к клиентских компьютерам.) Эти сведения применимы только к компьютерам с клиентом Skype для бизнеса и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="74a3f-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="74a3f-157">В следующем примере этот набор диапазонов портов используется для создания политики звука и политики видео:</span><span class="sxs-lookup"><span data-stu-id="74a3f-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a3f-158">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="74a3f-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="74a3f-159">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="74a3f-159">Port Start</span></span></th>
<th><span data-ttu-id="74a3f-160">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="74a3f-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a3f-161">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="74a3f-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="74a3f-162">50020</span><span class="sxs-lookup"><span data-stu-id="74a3f-162">50020</span></span></p></td>
<td><p><span data-ttu-id="74a3f-163">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a3f-164">Видео</span><span class="sxs-lookup"><span data-stu-id="74a3f-164">Video</span></span></p></td>
<td><p><span data-ttu-id="74a3f-165">58000</span><span class="sxs-lookup"><span data-stu-id="74a3f-165">58000</span></span></p></td>
<td><p><span data-ttu-id="74a3f-166">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a3f-167">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="74a3f-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="74a3f-168">42000</span><span class="sxs-lookup"><span data-stu-id="74a3f-168">42000</span></span></p></td>
<td><p><span data-ttu-id="74a3f-169">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a3f-170">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="74a3f-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="74a3f-171">42020</span><span class="sxs-lookup"><span data-stu-id="74a3f-171">42020</span></span></p></td>
<td><p><span data-ttu-id="74a3f-172">20</span><span class="sxs-lookup"><span data-stu-id="74a3f-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="74a3f-173">Чтобы создать политику качества обслуживания для компьютеров с Windows 10, сначала войдите на компьютер, на котором установлено управление групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="74a3f-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="74a3f-174">Откройте управление групповыми политиками (нажмите кнопку **"Начните",** выберите пункт "Администрирование" и выберите пункт **"Управление** групповой политикой"), а затем выполните следующую процедуру: </span><span class="sxs-lookup"><span data-stu-id="74a3f-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="74a3f-175">В консоли управления групповыми политиками найдите контейнер, в котором следует создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="74a3f-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="74a3f-176">Например, если все клиентские компьютеры находятся в под названием "Клиенты", новую политику следует создать в клиенте.</span><span class="sxs-lookup"><span data-stu-id="74a3f-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="74a3f-177">Щелкните правой кнопкой мыши соответствующий контейнер и выберите "Создать **GPO в этом** домене" и связать его здесь.</span><span class="sxs-lookup"><span data-stu-id="74a3f-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="74a3f-178">В **диалоговом** окне "Новый объект групповой политики"  введите имя нового объекта групповой политики в поле "Имя" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="74a3f-179">Щелкните правой кнопкой мыши созданную политику и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="74a3f-180">В редакторе управления групповыми политиками разйдите "Конфигурация **компьютера",**"Параметры **Windows",** щелкните правой кнопкой мыши **"QoS на** основе политики" и выберите **"Создать новую политику".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="74a3f-181">В **диалоговом окне "QoS** на основе политики" на открываемой странице введите имя новой политики в поле **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="74a3f-182">Выберите поле **Укажите значение DSCP** и установите значение **46**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="74a3f-183">Оставьте поле **Укажите частоту передачи** пустым и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="74a3f-184">На следующей странице выберите только приложения с этим исполняемым именем, **Lync.exe** в качестве имени, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="74a3f-185">Этот параметр предписывает политике только устанавливать приоритеты для совпадающих трафика из клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="74a3f-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="74a3f-186">На третьей странице убедитесь, что выбраны  как любой исходный **IP-адрес,** так и любой адрес назначения, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="74a3f-187">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, с какого компьютера (IP-адреса) отправляются эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="74a3f-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="74a3f-188">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="74a3f-189">TCP (Transmission Control Protocol) и UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Skype для бизнеса Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="74a3f-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="74a3f-p117">В разделе **Укажите номер исходного порта** выберите **От этого исходного порта или диапазона**. В сопутствующем текстовом поле введите диапазон портов, зарезервированный для передачи звука. Например, если вы зарезервировали для звукового трафика порты от 50020 до 50039, укажите этот диапазон портов в следующем формате: **50020:50039**. Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="74a3f-p118">После создания политики QoS для звука следует создать вторую политику для видео. Для этого выполните ту же основную процедуру, которой вы следовали при создании политики для аудио, внеся следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="74a3f-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="74a3f-196">Используйте другое (и уникальное) имя политики.</span><span class="sxs-lookup"><span data-stu-id="74a3f-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="74a3f-p119">Для значения DSCP вместо 46 укажите **34**. (Как было отмечено ранее, вы не обязаны использовать значение DSCP 34; просто назначьте для видео значение DSCP, отличное от значения для аудио.)</span><span class="sxs-lookup"><span data-stu-id="74a3f-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="74a3f-199">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="74a3f-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="74a3f-200">Например, если для видео зарезервированы порты от 58000 до 58019, установите диапазон портов: **58000:58019.**</span><span class="sxs-lookup"><span data-stu-id="74a3f-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="74a3f-201">Если вы решили создать политику для управления трафиком общего доступа к приложениям, сделайте эти подстановки:</span><span class="sxs-lookup"><span data-stu-id="74a3f-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="74a3f-202">Используйте другое (и уникальное) имя политики (например, Общий доступ к приложениям Skype для бизнеса **Server).**</span><span class="sxs-lookup"><span data-stu-id="74a3f-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="74a3f-p121">Для значения DSCP вместо 46 укажите **24**. (Опять же, это значение не должно быть равно 24, оно просто должно отличаться от значений DSCP, используемых для аудио и видео.)</span><span class="sxs-lookup"><span data-stu-id="74a3f-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="74a3f-205">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="74a3f-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="74a3f-206">Например, если для общего доступа к приложениям зарезервированы порты с 42000 по 42019, установите диапазон портов: **42000:42019.**</span><span class="sxs-lookup"><span data-stu-id="74a3f-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="74a3f-207">Для политики передачи файлов</span><span class="sxs-lookup"><span data-stu-id="74a3f-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="74a3f-208">Используйте другое (и уникальное) имя политики (например, Передача файлов Skype для бизнеса **Server).**</span><span class="sxs-lookup"><span data-stu-id="74a3f-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="74a3f-209">Установите значение DSCP, равное **14**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="74a3f-210">(Опять же, это значение не должно быть равно именно 14, оно просто должно быть уникальным кодом DSCP.)</span><span class="sxs-lookup"><span data-stu-id="74a3f-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="74a3f-211">Используйте ранее настроенный диапазон портов для приложения.</span><span class="sxs-lookup"><span data-stu-id="74a3f-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="74a3f-212">Например, если вы зарезервировали порты с 42020 по 42039 для общего доступа к приложениям, установите этот диапазон портов: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="74a3f-p125">Новые политики не будут действовать, пока не обновится групповая политика на клиентских компьютерах. Хотя групповая политика периодически обновляется сама по себе, можно принудительно вызвать немедленное обновление, выполнив на каждом компьютере, на котором требуется обновление групповой политики, следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74a3f-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="74a3f-p126">Эту команду можно выполнить из любого окна командной строки, запущенного с учетными данными администратора. Чтобы запустить командное окно с учетными данными администратора, нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="74a3f-217">Помните, что эти политики должны быть направлены на ваши клиентские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="74a3f-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="74a3f-218">Они не должны применяться к серверам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="74a3f-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="74a3f-219">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="74a3f-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="74a3f-220">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="74a3f-221">В **диалоговом** окне "Выполнить" введите **regedit** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="74a3f-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="74a3f-222">В редакторе реестра развертка **HKEY \_ LOCAL \_ MACHINE,** развернуть **SYSTEM,** **развернуть CurrentControlSet,** развернуть службы, а затем развернуть **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="74a3f-223">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="74a3f-224">После создания нового ключа реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать ключ.</span><span class="sxs-lookup"><span data-stu-id="74a3f-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="74a3f-225">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="74a3f-226">После создания нового значения реестра введите "Не использовать **NLA"** и нажмите ввод, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="74a3f-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="74a3f-227">Дважды щелкните элемент **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="74a3f-228">В **диалоговом окне** "Изменение  строки" введите **1** в поле данных "Значение" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="74a3f-229">Закройте редактор реестра и перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="74a3f-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="74a3f-230">Настройка качества обслуживания на компьютерах с несколькими сетевыми адаптерами</span><span class="sxs-lookup"><span data-stu-id="74a3f-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="74a3f-231">Если у вас есть компьютер с несколькими сетевыми адаптерами, иногда могут возникнуть проблемы, в которых значения DSCP показаны как 0x00 а не заданные значения.</span><span class="sxs-lookup"><span data-stu-id="74a3f-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="74a3f-232">Обычно это происходит на компьютерах, где одному или нескольким сетевым адаптерам не удается получить доступ к вашему домену Active Directory (например, если эти адаптеры используются в частной сети).</span><span class="sxs-lookup"><span data-stu-id="74a3f-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="74a3f-233">В таких случаях значения DSCP помечаются для адаптеров, которые могут осуществить доступ к домену, и не помечаются для адаптеров, которым такой доступ получить не удается.</span><span class="sxs-lookup"><span data-stu-id="74a3f-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="74a3f-234">Если вы хотите пометить значения DSCP для всех сетевых адаптеров на компьютере, включая адаптеры, которые не имеют доступа к вашему домену, необходимо добавить и настроить значение в реестре.</span><span class="sxs-lookup"><span data-stu-id="74a3f-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="74a3f-235">Это можно сделать посредством следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="74a3f-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="74a3f-236">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="74a3f-237">В **диалоговом** окне "Выполнить" введите **regedit** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="74a3f-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="74a3f-238">В редакторе реестра развертка **HKEY \_ LOCAL \_ MACHINE,** развернуть **SYSTEM,** **развернуть CurrentControlSet,** развернуть службы, а затем развернуть **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="74a3f-239">Если вы не видите раздел реестра **QoS**, щелкните элемент **Tcpip** правой кнопкой мыши, выберите пункт **Создать** и пункт **Раздел**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="74a3f-240">После создания нового ключа введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать ключ.</span><span class="sxs-lookup"><span data-stu-id="74a3f-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="74a3f-241">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="74a3f-242">После создания нового значения реестра введите "Не использовать **NLA"** и нажмите ввод, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="74a3f-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="74a3f-243">Дважды щелкните элемент **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="74a3f-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="74a3f-244">В **диалоговом окне** "Изменение  строки" введите **1** в поле данных "Значение" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="74a3f-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="74a3f-245">После создания и настройки нового значения реестра необходимо перезагрудить компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="74a3f-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="74a3f-246">См. также</span><span class="sxs-lookup"><span data-stu-id="74a3f-246">See also</span></span>

[<span data-ttu-id="74a3f-247">Создание объекта групповой политики в Windows 10</span><span class="sxs-lookup"><span data-stu-id="74a3f-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
