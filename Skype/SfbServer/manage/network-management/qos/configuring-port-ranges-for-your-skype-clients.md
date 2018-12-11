---
title: Настройка диапазонов портов и политики качества обслуживания для клиентов
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описывается настройка диапазонов портов для клиентов и настройка политики качества обслуживания в Скайп для Business Server для клиентов, работающих на Windows 10.
ms.openlocfilehash: 112d5a42b3bf4ac89bf7adc98b3ca56e8797482e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223229"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="1d57f-103">Настройка диапазонов портов и политики качества обслуживания для клиентов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="1d57f-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="1d57f-104">В этой статье описывается настройка диапазонов портов для клиентов и настройка политики качества обслуживания в Скайп для Business Server для клиентов, работающих на Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1d57f-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="1d57f-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="1d57f-105">Configure port ranges</span></span>

<span data-ttu-id="1d57f-106">По умолчанию, Скайп для бизнес-клиентского приложения можно использовать любой порт между порты 1024 до 65535 при участвующих в сеансах связи; Это, так как диапазоны портов автоматически не включены для клиентов.</span><span class="sxs-lookup"><span data-stu-id="1d57f-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="1d57f-107">Чтобы использовать качества обслуживания, тем не менее, необходимо будет переназначать различные типы трафика (аудио, видео, мультимедиа, общий доступ к приложениям и передачи файлов) в набор диапазонов портов уникальный.</span><span class="sxs-lookup"><span data-stu-id="1d57f-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="1d57f-108">Это можно сделать с помощью командлета Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1d57f-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="1d57f-109">Конечные пользователи не могут выполнить эти изменения сами.</span><span class="sxs-lookup"><span data-stu-id="1d57f-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="1d57f-110">Порт изменения можно выполнить только администраторами с помощью командлета Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1d57f-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="1d57f-111">Можно определить, какие диапазоны портов используются в текущий момент для сеансов связи, выполнив следующую команду в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="1d57f-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="1d57f-112">Если предполагается, что вы не вносили изменений в параметры конференц-связи с момента установки Скайп для Business Server, вы должны получить данные со следующими значениями свойств:</span><span class="sxs-lookup"><span data-stu-id="1d57f-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="1d57f-113">Если внимательно изучите выше выходные данные, вы увидите два следующих аспекта важности.</span><span class="sxs-lookup"><span data-stu-id="1d57f-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="1d57f-114">Во-первых параметры ClientMediaPortRangeEnabled свойству значение False:</span><span class="sxs-lookup"><span data-stu-id="1d57f-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="1d57f-115">Важно, так как при задано значение False, Скайп для бизнеса клиенты будут использовать любой доступный порт между порты 1024 до 65535 при участвующих в сеансах связи; Это значение true, независимо от того, любые другие параметры порта (например, ClientMediaPort или ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="1d57f-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="1d57f-116">Если требуется ограничить использование указанного набора портов (и это то, что вы собираетесь выполнить при планировании реализации качества обслуживания), необходимо сначала включить диапазонов портов мультимедиа клиента.</span><span class="sxs-lookup"><span data-stu-id="1d57f-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="1d57f-117">Который можно выполнить с помощью следующей команды Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1d57f-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="1d57f-118">Приведенная выше команда включает клиента диапазонов портов мультимедиа для глобальной коллекции параметров конфигурации конференц-связи; Тем не менее эти параметры можно также применяются на уровне сайта и/или области службы (сервер конференций только для службы).</span><span class="sxs-lookup"><span data-stu-id="1d57f-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="1d57f-119">Для включения клиентских портов, диапазонов для определенного сайта или сервера, укажите идентификатор этого сайта или сервера при вызове Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="1d57f-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="1d57f-120">Кроме того чтобы одновременно включить диапазоны порты для всех параметров конфигурации конференц-связи можно использовать эту команду:</span><span class="sxs-lookup"><span data-stu-id="1d57f-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="1d57f-121">Второй важный момент — это что примере выходных данных показано, что по умолчанию для каждого типа сетевого трафика набор диапазонов портов мультимедиа идентичны:</span><span class="sxs-lookup"><span data-stu-id="1d57f-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="1d57f-122">Для реализации QoS, каждый из этих диапазонов портов необходимо быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="1d57f-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="1d57f-123">Например можно настроить диапазоны портов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1d57f-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d57f-124">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="1d57f-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="1d57f-125">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="1d57f-125">Port Start</span></span></th>
<th><span data-ttu-id="1d57f-126">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="1d57f-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d57f-127">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="1d57f-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="1d57f-128">50020</span><span class="sxs-lookup"><span data-stu-id="1d57f-128">50020</span></span></p></td>
<td><p><span data-ttu-id="1d57f-129">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d57f-130">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="1d57f-130">Video</span></span></p></td>
<td><p><span data-ttu-id="1d57f-131">58000</span><span class="sxs-lookup"><span data-stu-id="1d57f-131">58000</span></span></p></td>
<td><p><span data-ttu-id="1d57f-132">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d57f-133">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="1d57f-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="1d57f-134">42000</span><span class="sxs-lookup"><span data-stu-id="1d57f-134">42000</span></span></p></td>
<td><p><span data-ttu-id="1d57f-135">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d57f-136">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="1d57f-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="1d57f-137">42020</span><span class="sxs-lookup"><span data-stu-id="1d57f-137">42020</span></span></p></td>
<td><p><span data-ttu-id="1d57f-138">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d57f-139">В приведенной выше таблице диапазоны портов клиента представляют набор диапазонов портов, настроенных для серверов.</span><span class="sxs-lookup"><span data-stu-id="1d57f-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="1d57f-140">Например на серверах, совместное использование приложений был настроен для использования портов 40803 до 49151; на клиентских компьютерах совместное использование приложений настроен для использования портов 42000 через 42019.</span><span class="sxs-lookup"><span data-stu-id="1d57f-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="1d57f-141">Слишком, это делается в первую очередь для упрощения администрирования QoS: порты на клиенте нет необходимости представляют поднабор портов, используемых на сервере.</span><span class="sxs-lookup"><span data-stu-id="1d57f-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="1d57f-142">(Например, на клиентских компьютерах можно настроить общий доступ к приложениям для использования, например, порты 10000 через 10019.) Тем не менее, рекомендуется сделать клиент порт для диапазона подмножество диапазонов портов на сервере.</span><span class="sxs-lookup"><span data-stu-id="1d57f-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="1d57f-143">Кроме того вы могли заметить, что 8348 портов были выделяемых для совместного использования на серверах приложений, но только 20 портов были выделяемых для совместного использования на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1d57f-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="1d57f-144">Это, слишком, рекомендуется, но не является hard-and-fast правила.</span><span class="sxs-lookup"><span data-stu-id="1d57f-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="1d57f-145">Как правило, необходимо учитывать каждый доступный порт для представления сеанс связи одним: при наличии 100 портов в диапазоне портов, это означает, что этот компьютер может участвовать в, не более 100 сеансов связи в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="1d57f-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="1d57f-146">Так как серверы вероятно будет принять участие в несколькими беседами более чем клиенты, имеет смысл откройте несколько других портов на серверах, чем на клиентах.</span><span class="sxs-lookup"><span data-stu-id="1d57f-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="1d57f-147">Параметр сторону 20 портов для совместного использования на клиенте означает, что пользователи могут принимать участие в сеансах общего доступа к 20 приложения на указанном устройстве и все в то же время.</span><span class="sxs-lookup"><span data-stu-id="1d57f-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="1d57f-148">Который должен быть достаточно для подавляющего большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d57f-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="1d57f-149">Чтобы назначить предыдущие диапазоны портов глобальной коллекции параметров конфигурации конференций, можно использовать следующие Скайп для командной консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="1d57f-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="1d57f-150">Или использовать эту команду, чтобы назначить эти же диапазоны портов для всех конференций параметров конфигурации:</span><span class="sxs-lookup"><span data-stu-id="1d57f-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="1d57f-151">Отдельные пользователи должны выйти Скайп для бизнеса и снова войдите в систему перед эти изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="1d57f-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="1d57f-152">Можно также включить диапазонов портов мультимедиа клиента и назначьте этих диапазонов портов с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="1d57f-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="1d57f-153">Например:</span><span class="sxs-lookup"><span data-stu-id="1d57f-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="1d57f-154">Настройка политики качества обслуживания для клиентов, работающих на Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d57f-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="1d57f-155">Кроме возможности задания диапазонов портов для использования с вашей Скайп пользователей, необходимо также создать отдельные политики качества обслуживания, которые будут применяться к клиентским компьютерам.</span><span class="sxs-lookup"><span data-stu-id="1d57f-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="1d57f-156">(Не следует применять политики качества обслуживания, созданные для серверов конференц-связи, приложений и посредника на клиентских компьютерах). Эта информация относится только на компьютерах под управлением Скайп для клиента Business и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1d57f-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="1d57f-157">В следующем примере этот набор диапазонов портов используется для создания политики звука и политики видео:</span><span class="sxs-lookup"><span data-stu-id="1d57f-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d57f-158">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="1d57f-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="1d57f-159">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="1d57f-159">Port Start</span></span></th>
<th><span data-ttu-id="1d57f-160">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="1d57f-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d57f-161">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="1d57f-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="1d57f-162">50020</span><span class="sxs-lookup"><span data-stu-id="1d57f-162">50020</span></span></p></td>
<td><p><span data-ttu-id="1d57f-163">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d57f-164">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="1d57f-164">Video</span></span></p></td>
<td><p><span data-ttu-id="1d57f-165">58000</span><span class="sxs-lookup"><span data-stu-id="1d57f-165">58000</span></span></p></td>
<td><p><span data-ttu-id="1d57f-166">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d57f-167">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="1d57f-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="1d57f-168">42000</span><span class="sxs-lookup"><span data-stu-id="1d57f-168">42000</span></span></p></td>
<td><p><span data-ttu-id="1d57f-169">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d57f-170">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="1d57f-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="1d57f-171">42020</span><span class="sxs-lookup"><span data-stu-id="1d57f-171">42020</span></span></p></td>
<td><p><span data-ttu-id="1d57f-172">20</span><span class="sxs-lookup"><span data-stu-id="1d57f-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1d57f-173">Для создания политики звука качества обслуживания для компьютеров Windows 10, сначала Войдите на компьютер, где была установлена консоль Управление групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="1d57f-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="1d57f-174">Откройте консоль Управление групповой политикой (нажмите кнопку **Пуск**, выберите пункт **Администрирование**и выберите **Управление групповой политикой**), а затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1d57f-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="1d57f-175">В консоли Управление групповой политикой Найдите контейнер, где должен быть создан новой политики.</span><span class="sxs-lookup"><span data-stu-id="1d57f-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="1d57f-176">Например если на клиентских компьютерах, находятся в Подразделении с именем клиенты, новой политики должны быть созданы в Подразделения клиента.</span><span class="sxs-lookup"><span data-stu-id="1d57f-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="1d57f-177">Щелкните правой кнопкой мыши соответствующий контейнер и нажмите кнопку **создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="1d57f-178">В диалоговом окне **Новый объект групповой Политики** в поле **имя** введите имя для нового объекта групповой политики и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="1d57f-179">Щелкните правой кнопкой мыши созданную политику и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="1d57f-180">В редакторе управления групповой политики разверните узлы **Конфигурация компьютера**, параметры **Windows**, щелкните правой кнопкой мыши **QoS на основе политики**и выберите команду **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="1d57f-181">В диалоговом окне **QoS на основе политики** на первой странице введите имя новой политики в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="1d57f-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="1d57f-182">Выберите **Укажите значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="1d57f-183">Оставьте в поле **Укажите исходящих частоту передачи** не выбран и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="1d57f-184">На следующей странице убедитесь в том, что выбран пункт **все приложения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="1d57f-185">Этот параметр указывает сети для поиска всех пакетов с помощью разметки DSCP 46, не только пакетов, созданный с конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="1d57f-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="1d57f-186">На странице третий убедитесь, что выбраны **все исходный IP-адрес** и **любой конечный IP-адрес** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="1d57f-187">Эти два параметра убедитесь, что пакеты будут управляться независимо от того, какой компьютер пакеты отправляемых (IP-адрес) и (IP-адрес) компьютер, который будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="1d57f-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="1d57f-188">На странице четырех выберите в раскрывающемся списке **выберите протокол, к которому применяется данная политика качества обслуживания для** **TCP и UDP-ПОРТ** .</span><span class="sxs-lookup"><span data-stu-id="1d57f-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="1d57f-189">TCP (Transmission Control Protocol) и UDP-ПОРТ (протокол) — это два сетевых протоколов, чаще всего используемые Скайп Business Server и его клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="1d57f-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="1d57f-190">В разделе **Укажите номер порта источника**выберите выберите **этот исходный порт или диапазон**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="1d57f-191">В соответствующем текстовом поле введите диапазон портов зарезервированы для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="1d57f-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="1d57f-192">Например, если зарезервированные порты 50020 через порты 50039 для трафика аудио введите диапазон портов, используя следующий формат: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="1d57f-193">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="1d57f-193">Click **Finish**.</span></span>

<span data-ttu-id="1d57f-194">После создания политики качества обслуживания для аудио следует затем создайте второй политики для видео.</span><span class="sxs-lookup"><span data-stu-id="1d57f-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="1d57f-195">Создание политики для видео, выполните ту же основную процедуру, были выполнены при создании политики звука, что следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="1d57f-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="1d57f-196">Используйте разные (и уникальное) имя политики.</span><span class="sxs-lookup"><span data-stu-id="1d57f-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="1d57f-197">Установите значение DSCP **34** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="1d57f-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="1d57f-198">(Как указывалось ранее, нет необходимости использовать значение DSCP 34, просто необходимо назначить разные значения DSCP от того, используемых для совершения).</span><span class="sxs-lookup"><span data-stu-id="1d57f-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="1d57f-199">Используйте диапазон портов ранее настроенные для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="1d57f-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="1d57f-200">Например, если зарезервированные порты 58000 через 58019 для видео, необходимо задать диапазон портов на этот: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="1d57f-201">Если вы решите создать политику для управления трафика совместного использования приложений, внесите следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="1d57f-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="1d57f-202">Используйте другое (и уникальное) политики имя (например, **Скайп для Business Server общий доступ к приложениям**).</span><span class="sxs-lookup"><span data-stu-id="1d57f-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="1d57f-203">Задайте значение DSCP **24** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="1d57f-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="1d57f-204">(Еще раз, это значение не должен быть 24; он просто должно отличаться от значения DSCP, используемые для аудио и видео).</span><span class="sxs-lookup"><span data-stu-id="1d57f-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="1d57f-205">Используйте диапазон портов ранее настроенные для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="1d57f-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="1d57f-206">Например, если зарезервированные порты 42000 через 42019 для общего доступа к приложениям, необходимо задать диапазон портов на этот: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="1d57f-207">Для политики передачи файлов:</span><span class="sxs-lookup"><span data-stu-id="1d57f-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="1d57f-208">Используйте другое (и уникальное) политики имя (например, **Скайп для передачи файлов Business Server**).</span><span class="sxs-lookup"><span data-stu-id="1d57f-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="1d57f-209">Установите значение DSCP **14**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="1d57f-210">(Еще раз, это значение не должен быть 14; он просто должен быть уникальный код DSCP).</span><span class="sxs-lookup"><span data-stu-id="1d57f-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="1d57f-211">Используйте диапазон портов ранее настроенные для приложения.</span><span class="sxs-lookup"><span data-stu-id="1d57f-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="1d57f-212">Например, если зарезервированные порты 42020 через 42039 для общего доступа к приложениям, необходимо задать диапазон портов на этот: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="1d57f-213">Новые политики, созданные вами, не вступят в силу только после обновления групповой политики на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1d57f-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="1d57f-214">Хотя групповая политика периодически обновляется сама, вы можете обновить ее принудительно, запустив на каждом нужном компьютере следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1d57f-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="1d57f-215">Команду можно выполнить в любом командном окне, запущенном от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1d57f-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="1d57f-216">Чтобы открыть такое окно с правами администратора, в меню **Пуск** правой кнопкой мыши щелкните **Командная строка** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="1d57f-217">Имейте в виду, что эти политики нацелить нужно достигло предельного на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1d57f-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="1d57f-218">Они не применимы к серверам с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d57f-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="1d57f-219">Чтобы обеспечить, что сетевых пакетов соответствующим значением DSCP, следует также создать новый раздел реестра на каждом компьютере, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="1d57f-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="1d57f-220">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="1d57f-221">В диалоговом окне **выполнить** введите **regedit**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1d57f-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="1d57f-222">В редакторе реестра разверните **HKEY\_ЛОКАЛЬНОГО\_МАШИНЫ**, разверните узлы **системы**, разверните **CurrentControlSet**, разверните узел **службы**и затем **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="1d57f-223">Щелкните правой кнопкой мыши **Tcpip**, выберите команду **Создать**и затем щелкните **раздел**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="1d57f-224">После создания нового раздела реестра введите **качества обслуживания**и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="1d57f-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="1d57f-225">Щелкните правой кнопкой мыши **QoS**, выберите команду **Создать**и затем **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="1d57f-226">После создания нового значения реестра введите **не используйте NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="1d57f-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="1d57f-227">Дважды щелкните **не использовать NLA**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="1d57f-228">В диалоговом окне **Изменение строкового параметра** в поле **значение** введите **1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="1d57f-229">Закройте редактор реестра и eboot компьютер.</span><span class="sxs-lookup"><span data-stu-id="1d57f-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="1d57f-230">Настройка качества обслуживания на компьютерах с несколькими сетевыми адаптерами</span><span class="sxs-lookup"><span data-stu-id="1d57f-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="1d57f-231">Если у вас есть компьютер с несколькими сетевыми адаптерами, могут иногда выполняются в проблемы, где отображаются значения DSCP следующим 0x00 вместо значения, настроенные.</span><span class="sxs-lookup"><span data-stu-id="1d57f-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="1d57f-232">Обычно это происходит на компьютерах, где один или несколько сетевых адаптеров, не могут получить доступ к вашего домена Active Directory (например, если эти адаптеры используются для частной сети).</span><span class="sxs-lookup"><span data-stu-id="1d57f-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="1d57f-233">В тех случаях, как будет помечен значения DSCP для сетевых адаптеров, которые могут получить доступ к домену, но не будет помечен для сетевых адаптеров, которые не могут получить доступ к домену.</span><span class="sxs-lookup"><span data-stu-id="1d57f-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="1d57f-234">Если вы хотите значения DSCP тегов для всех сетевых адаптеров на компьютер, включая адаптеры, у которых нет доступа к домену, необходимо добавить и настроить значение в реестр.</span><span class="sxs-lookup"><span data-stu-id="1d57f-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="1d57f-235">Который может выполняться, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="1d57f-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="1d57f-236">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="1d57f-237">В диалоговом окне **выполнить** введите **regedit**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1d57f-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="1d57f-238">В редакторе реестра разверните **HKEY\_ЛОКАЛЬНОГО\_МАШИНЫ**, разверните узлы **системы**, разверните **CurrentControlSet**, разверните узел **службы**и затем **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="1d57f-239">Если раздел реестра меткой **QoS** , затем щелкните правой кнопкой мыши **Tcpip**не отображаются, выберите команду **Создать**и щелкните **раздел**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="1d57f-240">После создания нового ключа введите **качества обслуживания**и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="1d57f-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="1d57f-241">Щелкните правой кнопкой мыши **QoS**, выберите команду **Создать**и затем **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="1d57f-242">После создания нового значения реестра введите **не используйте NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="1d57f-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="1d57f-243">Дважды щелкните **не использовать NLA**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="1d57f-244">В диалоговом окне **Изменение строкового параметра** в поле **значение** введите **1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d57f-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="1d57f-245">После создания и настройки нового значения реестра, необходимо перезагрузить компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="1d57f-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d57f-246">См. также</span><span class="sxs-lookup"><span data-stu-id="1d57f-246">See also</span></span>

[<span data-ttu-id="1d57f-247">Создание объекта групповой политики в Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d57f-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)