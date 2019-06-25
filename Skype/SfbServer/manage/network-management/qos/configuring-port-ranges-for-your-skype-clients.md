---
title: Настройка диапазонов портов и политики качества обслуживания для клиентов
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описано, как настраивать диапазоны портов для клиентов и настраивать политики качества обслуживания в Skype для бизнеса Server для клиентов, работающих под управлением Windows 10.
ms.openlocfilehash: ce1690c295f1f5ed991780919370e5dbf5b5d6b1
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35204016"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="bd184-103">Настройка диапазонов портов и политики качества обслуживания для клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bd184-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="bd184-104">В этой статье описано, как настраивать диапазоны портов для клиентов и настраивать политики качества обслуживания в Skype для бизнеса Server для клиентов, работающих под управлением Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bd184-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="bd184-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="bd184-105">Configure port ranges</span></span>

<span data-ttu-id="bd184-106">По умолчанию клиентские приложения Skype для бизнеса могут использовать любой порт между портами 1024 и 65535 при включении в сеанс связи. Это происходит из-за того, что определенные диапазоны портов не включены автоматически для клиентов.</span><span class="sxs-lookup"><span data-stu-id="bd184-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="bd184-107">Тем не менее, чтобы использовать качество обслуживания, вам потребуется переназначить различные типы трафика (звук, видео, мультимедиа, общий доступ к приложениям и передачу файлов) на ряд уникальных диапазонов портов.</span><span class="sxs-lookup"><span data-stu-id="bd184-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="bd184-108">Это можно сделать с помощью командлета Set-КсконференЦингконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="bd184-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="bd184-109">Конечные пользователи не могут вносить эти изменения.</span><span class="sxs-lookup"><span data-stu-id="bd184-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="bd184-110">Изменение портов может выполняться только администраторами с помощью командлета Set-КсконференЦингконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="bd184-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="bd184-111">Вы можете определить, какие диапазоны портов используются в сеансах связи, выполнив следующую команду в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="bd184-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="bd184-112">Если вы не внесли никаких изменений в параметры конференц-связи после установки Skype для бизнеса Server, вы должны получить информацию, которая включает следующие значения свойств:</span><span class="sxs-lookup"><span data-stu-id="bd184-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="bd184-113">Если вы ближе просмотрит предыдущий результат, вы увидите два важных элемента.</span><span class="sxs-lookup"><span data-stu-id="bd184-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="bd184-114">Сначала свойство Клиентмедиапортранжеенаблед имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="bd184-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="bd184-115">Это важно, так как в случае, если для этого свойства задано значение false, клиенты Skype для бизнеса будут использовать любой доступный порт между портами 1024 и 65535 при использовании в сеансе связи. Это справедливо независимо от других параметров порта (например, Клиентмедиапорт или Клиентвидеопорт).</span><span class="sxs-lookup"><span data-stu-id="bd184-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="bd184-116">Если вы хотите ограничить использование заданным набором портов (и это нужно сделать, если вы планируете реализовать качество обслуживания), необходимо сначала включить диапазоны портов для клиента мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bd184-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="bd184-117">Это можно сделать с помощью следующей команды Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bd184-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd184-118">Предыдущая команда включает диапазоны порта клиента мультимедиа для глобальной коллекции параметров конфигурации конференций. Однако эти параметры также можно применять к области действия сайта и (или) области службы (только для службы сервера конференц-связи).</span><span class="sxs-lookup"><span data-stu-id="bd184-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="bd184-119">Чтобы включить диапазон портов клиента мультимедиа для определенного сайта или сервера, укажите удостоверение этого сайта или сервера при вызове Set-КсконференЦингконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="bd184-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd184-120">Кроме того, вы можете использовать эту команду для одновременного включения диапазонов портов для всех параметров настройки конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bd184-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bd184-121">Во втором случае важно заметить, что в примере вывода показано, что по умолчанию диапазоны портов мультимедиа, заданные для каждого типа сетевого трафика, идентичны:</span><span class="sxs-lookup"><span data-stu-id="bd184-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="bd184-122">Для реализации QoS каждый из этих диапазонов должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="bd184-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="bd184-123">Например, вы можете настроить диапазоны портов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bd184-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd184-124">Тип трафика клиента</span><span class="sxs-lookup"><span data-stu-id="bd184-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="bd184-125">Начало порта</span><span class="sxs-lookup"><span data-stu-id="bd184-125">Port Start</span></span></th>
<th><span data-ttu-id="bd184-126">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="bd184-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd184-127">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="bd184-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="bd184-128">50020</span><span class="sxs-lookup"><span data-stu-id="bd184-128">50020</span></span></p></td>
<td><p><span data-ttu-id="bd184-129">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd184-130">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="bd184-130">Video</span></span></p></td>
<td><p><span data-ttu-id="bd184-131">58000</span><span class="sxs-lookup"><span data-stu-id="bd184-131">58000</span></span></p></td>
<td><p><span data-ttu-id="bd184-132">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd184-133">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="bd184-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bd184-134">42000</span><span class="sxs-lookup"><span data-stu-id="bd184-134">42000</span></span></p></td>
<td><p><span data-ttu-id="bd184-135">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd184-136">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="bd184-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="bd184-137">42020</span><span class="sxs-lookup"><span data-stu-id="bd184-137">42020</span></span></p></td>
<td><p><span data-ttu-id="bd184-138">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd184-139">В приведенной выше таблице диапазоны портов клиента представляют собой подмножество диапазонов портов, настроенных для серверов.</span><span class="sxs-lookup"><span data-stu-id="bd184-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="bd184-140">Например, на серверах общий доступ к приложениям настроен на использование портов 40803 – 49151; на клиентских компьютерах общий доступ к приложениям настроен на использование портов 42000 – 42019.</span><span class="sxs-lookup"><span data-stu-id="bd184-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="bd184-141">Это тоже делается для того, чтобы упростить администрирование QoS: клиентские порты не должны представлять подмножество портов, используемых на сервере.</span><span class="sxs-lookup"><span data-stu-id="bd184-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="bd184-142">(Например, на клиентских компьютерах вы можете настроить общий доступ к приложениям, например, с помощью портов 10000 – 10019.) Тем не менее рекомендуется сделать порт клиента подмножеством диапазонов портов сервера.</span><span class="sxs-lookup"><span data-stu-id="bd184-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="bd184-143">Кроме того, вы могли заметить, что порты 8348 были настроены для совместного использования приложений на серверах, но для совместного использования приложений на клиентских компьютерах задано только 20 портов.</span><span class="sxs-lookup"><span data-stu-id="bd184-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="bd184-144">Это также рекомендовано, но не является жесткой и быстрым правилом.</span><span class="sxs-lookup"><span data-stu-id="bd184-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="bd184-145">Как правило, вы можете использовать каждый доступный порт для представления одного сеанса связи: Если в диапазоне портов есть доступные порты 100, это означает, что ваш компьютер может принимать участие в сеансах связи 100 в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="bd184-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="bd184-146">Поскольку серверы, скорее чем, будут работать в большинстве сеансов, чем клиенты, имеет смысл открыть на серверах больше портов, чем на клиентах.</span><span class="sxs-lookup"><span data-stu-id="bd184-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="bd184-147">Настройка 20 портов для совместного использования приложений на клиенте означает, что пользователь может принимать участие в 20 сеансах общего разделения приложений на указанном устройстве и одновременно.</span><span class="sxs-lookup"><span data-stu-id="bd184-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="bd184-148">Это должно быть достаточно для самых разнообразных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bd184-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="bd184-149">Для назначения предыдущих диапазонов портов глобальному семейству параметров настройки конференц-связи можно использовать следующую команду командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="bd184-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bd184-150">Кроме того, можно использовать эту команду для назначения одинаковых диапазонов портов для всех параметров настройки конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bd184-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bd184-151">Отдельные пользователи должны выйти из Skype для бизнеса, а затем снова войти в систему, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="bd184-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="bd184-152">Вы также можете включить диапазоны портов клиента мультимедиа, а затем назначить эти диапазоны портов с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="bd184-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="bd184-153">Например:</span><span class="sxs-lookup"><span data-stu-id="bd184-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="bd184-154">Настройка политик качества обслуживания для клиентов, работающих в Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd184-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="bd184-155">Помимо задания диапазонов портов для клиентов Skype для бизнеса, необходимо также создать отдельные политики качества обслуживания, которые будут применяться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd184-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="bd184-156">(Политики качества обслуживания, созданные для конференций, приложений и серверов-исправлений, не следует применять на клиентских компьютерах.) Эти сведения относятся только к компьютерам, на которых установлен клиент Skype для бизнеса и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bd184-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="bd184-157">В следующем примере используется набор диапазонов портов для создания политики голосовой и видеополитики.</span><span class="sxs-lookup"><span data-stu-id="bd184-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd184-158">Тип трафика клиента</span><span class="sxs-lookup"><span data-stu-id="bd184-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="bd184-159">Начало порта</span><span class="sxs-lookup"><span data-stu-id="bd184-159">Port Start</span></span></th>
<th><span data-ttu-id="bd184-160">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="bd184-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd184-161">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="bd184-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="bd184-162">50020</span><span class="sxs-lookup"><span data-stu-id="bd184-162">50020</span></span></p></td>
<td><p><span data-ttu-id="bd184-163">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd184-164">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="bd184-164">Video</span></span></p></td>
<td><p><span data-ttu-id="bd184-165">58000</span><span class="sxs-lookup"><span data-stu-id="bd184-165">58000</span></span></p></td>
<td><p><span data-ttu-id="bd184-166">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd184-167">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="bd184-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bd184-168">42000</span><span class="sxs-lookup"><span data-stu-id="bd184-168">42000</span></span></p></td>
<td><p><span data-ttu-id="bd184-169">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd184-170">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="bd184-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="bd184-171">42020</span><span class="sxs-lookup"><span data-stu-id="bd184-171">42020</span></span></p></td>
<td><p><span data-ttu-id="bd184-172">средняя</span><span class="sxs-lookup"><span data-stu-id="bd184-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd184-173">Чтобы создать политику звука качества обслуживания для компьютеров с Windows 10, сначала войдите на компьютер, на котором установлен компонент управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="bd184-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="bd184-174">Откройте **средство**управления групповыми политиками (нажмите кнопку **Пуск**, выберите пункт Администрирование, а затем — **Управление групповыми политиками**), а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd184-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="bd184-175">В разделе Управление групповой политикой найдите контейнер, в котором нужно создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="bd184-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="bd184-176">Например, если все клиентские компьютеры находятся в подразделении с именем "клиенты", в подразделении клиента следует создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="bd184-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="bd184-177">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **создать объект групповой политики в этом домене и свяжите его**.</span><span class="sxs-lookup"><span data-stu-id="bd184-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="bd184-178">В диалоговом окне **создание GPO** введите имя нового объекта групповой политики в поле **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bd184-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="bd184-179">Щелкните созданную политику правой кнопкой мыши и выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="bd184-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="bd184-180">В редакторе управления групповыми политиками разверните узел **Конфигурация компьютера**, разверните раздел **Параметры Windows**, щелкните правой кнопкой мыши службу **QoS на основе политики**, а затем выберите команду **создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="bd184-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="bd184-181">В диалоговом окне **QoS на основе политики** на первой странице в поле **имя** введите имя новой политики.</span><span class="sxs-lookup"><span data-stu-id="bd184-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="bd184-182">Выберите **задать значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="bd184-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="bd184-183">Оставьте параметр **задать частоту исходящих подключений** невыбранным и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd184-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="bd184-184">На следующей странице выберите **только приложения с именем исполняемого файла**, введите в качестве имени **Lync. exe** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd184-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="bd184-185">Этот параметр дает политике приоритет только для трафика, совпадающего с клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bd184-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="bd184-186">На третьей странице убедитесь, что выбраны оба **IP-адреса источника** и **конечный IP-адрес** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd184-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="bd184-187">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, на каком компьютере (IP-адрес) отправили эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="bd184-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="bd184-188">На четвертой странице в раскрывающемся списке выберите протокол **TCP и UDP** , который будет **применяться этой политикой QoS** .</span><span class="sxs-lookup"><span data-stu-id="bd184-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="bd184-189">Протокол TCP и протокол UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Skype для бизнеса Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="bd184-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="bd184-190">Под заголовком **укажите номер исходного порта**, выберите **из этого исходного порта или диапазона**.</span><span class="sxs-lookup"><span data-stu-id="bd184-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="bd184-191">В сопроводительном текстовом поле введите диапазон портов, зарезервированный для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="bd184-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="bd184-192">Например, если вы зарезервированы порты 50020 через порты 50039 для звукового трафика, введите диапазон портов в следующем формате: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="bd184-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="bd184-193">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bd184-193">Click **Finish**.</span></span>

<span data-ttu-id="bd184-194">После создания политики качества обслуживания для звука вы должны создать вторую политику для видео.</span><span class="sxs-lookup"><span data-stu-id="bd184-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="bd184-195">Чтобы создать политику для видео, выполните те же действия, что и при создании политики звука, заменив указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="bd184-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="bd184-196">Используйте другое (и уникальное) имя политики.</span><span class="sxs-lookup"><span data-stu-id="bd184-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="bd184-197">Задайте для параметра DSCP значение **34** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="bd184-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="bd184-198">(Как отмечалось ранее, вам не нужно использовать значение DSCP 34; вы просто должны назначить другое значение DSCP, отличное от используемого для звука.)</span><span class="sxs-lookup"><span data-stu-id="bd184-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="bd184-199">Используйте ранее настроенный диапазон портов для видеоканала.</span><span class="sxs-lookup"><span data-stu-id="bd184-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="bd184-200">Например, если вы зарезервированы порты 58000 – 58019 для видео, задайте диапазон портов следующим образом: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="bd184-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="bd184-201">Если вы решили создать политику для управления трафиком общего использования приложений, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="bd184-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="bd184-202">Используйте другое (и уникальное) имя политики (например, **общий доступ к приложениям в Skype для бизнеса Server**).</span><span class="sxs-lookup"><span data-stu-id="bd184-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="bd184-203">Задайте для параметра DSCP значение **24** , а не 46.</span><span class="sxs-lookup"><span data-stu-id="bd184-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="bd184-204">(Опять же, это значение не обязательно должно быть 24; оно будет отличаться от значений DSCP, используемых для аудио-и видеофайлов.)</span><span class="sxs-lookup"><span data-stu-id="bd184-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="bd184-205">Используйте ранее настроенный диапазон портов для видеоканала.</span><span class="sxs-lookup"><span data-stu-id="bd184-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="bd184-206">Например, если у вас есть резервированные порты 42000 – 42019 для совместного использования приложений, задайте диапазон портов следующим образом: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="bd184-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="bd184-207">Для политики передачи файлов выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd184-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="bd184-208">Используйте другое (и уникальное) имя политики (например, серверная **Передача файлов в Skype для бизнеса**).</span><span class="sxs-lookup"><span data-stu-id="bd184-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="bd184-209">Задайте для параметра DSCP значение **14**.</span><span class="sxs-lookup"><span data-stu-id="bd184-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="bd184-210">(Опять же, это значение не обязательно должно быть 14; оно просто должен быть уникальным кодом DSCP.)</span><span class="sxs-lookup"><span data-stu-id="bd184-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="bd184-211">Используйте ранее настроенный диапазон портов для приложения.</span><span class="sxs-lookup"><span data-stu-id="bd184-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="bd184-212">Например, если у вас есть резервированные порты 42020 – 42039 для совместного использования приложений, задайте диапазон портов следующим образом: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="bd184-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="bd184-213">Новые политики, созданные вами, вступят в силу только после обновления групповой политики на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd184-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="bd184-214">Хотя групповая политика периодически обновляется сама, вы можете обновить ее принудительно, запустив на каждом нужном компьютере следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bd184-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="bd184-215">Команду можно выполнить в любом командном окне, запущенном от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="bd184-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="bd184-216">Чтобы открыть такое окно с правами администратора, в меню **Пуск** правой кнопкой мыши щелкните **Командная строка** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="bd184-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="bd184-217">Имейте в виду, что эти политики должны быть нацелены на клиентские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="bd184-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="bd184-218">Они не должны применяться к серверам, на которых установлен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd184-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="bd184-219">Чтобы убедиться в том, что сетевые пакеты помечены с использованием соответствующего значения DSCP, необходимо также создать новый параметр реестра на каждом компьютере, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd184-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="bd184-220">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bd184-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="bd184-221">В диалоговом окне **выполнить** введите regedit и нажмите клавишу ВВОД. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd184-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="bd184-222">В редакторе реестра разверните раздел **\_hKey локальный\_компьютер**, разверните раздел **система**, разверните **куррентконтролсет**, затем — **службы**, а затем — значок **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="bd184-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="bd184-223">Щелкните правой кнопкой мыши **tcpip**, наведите указатель на пункт **создать**и выберите **клавишу**.</span><span class="sxs-lookup"><span data-stu-id="bd184-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="bd184-224">После создания нового раздела реестра введите **QoS**и нажмите КЛАВИШу ввод, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="bd184-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="bd184-225">Щелкните правой кнопкой мыши **QoS**, наведите указатель на пункт **создать**и выберите **строковое значение**.</span><span class="sxs-lookup"><span data-stu-id="bd184-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="bd184-226">После создания нового значения реестра введите команду не **использовать NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="bd184-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="bd184-227">Дважды щелкните **не использовать NLA**.</span><span class="sxs-lookup"><span data-stu-id="bd184-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="bd184-228">В диалоговом окне **изменение строки** введите **1** в поле **значение** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bd184-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="bd184-229">Закройте редактор реестра и ебут компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd184-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="bd184-230">Настройка качества обслуживания на компьютерах с несколькими сетевыми адаптерами</span><span class="sxs-lookup"><span data-stu-id="bd184-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="bd184-231">Если у вас есть компьютер с несколькими сетевыми адаптерами, может возникнуть ситуация, когда значения DSCP отображаются как 0x00, а не настроенное значение.</span><span class="sxs-lookup"><span data-stu-id="bd184-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="bd184-232">Обычно это происходит на компьютерах, на которых один или несколько сетевых адаптеров не могут получить доступ к домену Active Directory (например, если эти адаптеры используются для частной сети).</span><span class="sxs-lookup"><span data-stu-id="bd184-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="bd184-233">В таких случаях значения DSCP будут помечены для адаптеров, которые могут получить доступ к домену, но не будут помечены для адаптеров, которые не могут получить доступ к домену.</span><span class="sxs-lookup"><span data-stu-id="bd184-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="bd184-234">Если вы хотите пометить значения DSCP для всех сетевых адаптеров на компьютере, в том числе для тех, у которых нет доступа к вашему домену, вам потребуется добавить в реестр значение и настроить его.</span><span class="sxs-lookup"><span data-stu-id="bd184-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="bd184-235">Это можно сделать, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bd184-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="bd184-236">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bd184-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="bd184-237">В диалоговом окне **выполнить** введите regedit и нажмите клавишу ВВОД. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd184-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="bd184-238">В редакторе реестра разверните раздел **\_hKey локальный\_компьютер**, разверните раздел **система**, разверните **куррентконтролсет**, затем — **службы**, а затем — значок **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="bd184-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="bd184-239">Если вы не видите раздел реестра с меткой **QoS** , щелкните правой кнопкой мыши **tcpip**и выберите пункт **создать**, а затем — **раздел**.</span><span class="sxs-lookup"><span data-stu-id="bd184-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="bd184-240">После создания нового ключа введите **QoS**и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="bd184-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="bd184-241">Щелкните правой кнопкой мыши **QoS**, наведите указатель на пункт **создать**и выберите **строковое значение**.</span><span class="sxs-lookup"><span data-stu-id="bd184-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="bd184-242">После создания нового значения реестра введите команду не **использовать NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="bd184-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="bd184-243">Дважды щелкните **не использовать NLA**.</span><span class="sxs-lookup"><span data-stu-id="bd184-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="bd184-244">В диалоговом окне **изменение строки** введите **1** в поле **значение** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bd184-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="bd184-245">После создания и настройки нового значения реестра вам потребуется перезагрузить компьютер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="bd184-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd184-246">См. также</span><span class="sxs-lookup"><span data-stu-id="bd184-246">See also</span></span>

[<span data-ttu-id="bd184-247">Создание объекта групповой политики в Windows 10</span><span class="sxs-lookup"><span data-stu-id="bd184-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
